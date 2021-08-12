---
cssclass: crm
---

## 实现汇总所有的pdf的dataview代码:
```dataviewjs


var a = this.app.vault.getFiles();
var b = [];
var c = [];
var d = [];
for(var i = 0; i < a.length; i++)
{
	b.push(a[i].path);
}
var patt = /[^/]*.pdf/i;
for (i = 0; i < a.length; i++){
	if(patt.exec(b[i])){
		console.log(b[i])
		b[i] = patt.exec(b[i])
		var c = this.app.va
		b[i] = "[[" + b[i] + "]]"
		d.push(b[i])
	}
	
}
dv.list(d)


```


## 实现dataview 展示图片的效果


```dataviewjs

// Absolute path for use in displaying local images
const absolutepath ="app://local/" + encodeURIComponent(app.vault.adapter.basePath) + "/"
const pages = dv
    // Get from folder people
    .pages('"people"')
    // Excluding this file
    .where((file) => file.file.name !== "Index")
    .map((k) => {
        const { file } = k
		
        // Get the `TFile`
        const currentFile = app.vault.getAbstractFileByPath(file.path)
        // And a the metadata
        const metadata = app.metadataCache.getFileCache(currentFile)
        // Default "image"
        let img = "<span>No Profile<span>"
        if (metadata.embeds) {
            // Assume first embed to the profile photo
            const profile = metadata.embeds[0].link
            if (profile) {
                const info = app.vault.getAbstractFileByPath(`attachments/${profile}`)
                img = `<img async defer src="${absolutepath + encodeURIComponent(info.path)}" />`

            }
        }
        // Get the most recent backlink
        const inlinks = file.inlinks.map((link) => app.vault.getAbstractFileByPath(link.path))
        .sort((a,b) => a.stat.ctime - b.stat.ctime)[0]
        if (inlinks) {
            return [file.link, k.Relation, k.Located, `[[${inlinks.basename}]]`, img]
			
        } else {
            return [file.link, k.Relation, k.Located, null, img]
        }
    })
console.log(["Person", "Relation", "Location", "Last Interaction", "Profile"],pages)
dv.table(["Person", "Relation", "Location", "Last Interaction", "Profile"], pages)


```

要实现卡片的方式,只需要加一个CSS片段就可以了.
- [ ] 要是自己会写css就好了呀

## dataview table--->markdowntable 
主要的目的是方便导出
day:: 2018-1-2
theme:: fiction
readings:: 42
week:: 16th

```dataviewjs

const pages = dv.pages("").where(f => f.theme && f.readings);

const uniqueWeeks = new Set();
pages.forEach(p => uniqueWeeks.add(p.week));

let pWeeks = {};
uniqueWeeks.forEach(week => {
    pages.forEach(page => {
        if (page.week === week) {
            if (!pWeeks[week]) pWeeks[week] = [];
            pWeeks[week] = [...pWeeks[week], page];
        }
    })
})

let markdownTable = "";

uniqueWeeks.forEach(week => {
    dv.header(3, week);
    const tableTopRow = ["Day", "Theme", "Readings"];
    const tableRows = pWeeks[week].map(p => [p.day, p.theme, p.readings]);
    dv.table(tableTopRow, tableRows);
    
    // Add week header
    markdownTable += `### ${week}\n`;
    // Add row top
    markdownTable += `| ${tableTopRow.map(cell => cell + " |").join("")}\n`;
    markdownTable += "|" + " --- |".repeat(tableTopRow.length) + "\n";
    // Add body
    tableRows.map(p => {
        markdownTable += `| ${p.map(cell => {
            let cellContent;
            
            if (typeof cell !== 'string' && cell[Symbol.iterator]) {
                cellContent = cell.map(c => c.display ?? c).map(v => `- ${v}`).join("<br>");
            } else {
                cellContent = cell.display ?? cell;
            }
            
            return (cellContent + " |")
        
        }).join("")}\n`;
    });
});

const copyToClipboard = str => {
  const el = document.createElement('textarea');
  el.value = str;
  document.body.appendChild(el);
  el.select();
  document.execCommand('copy');
  document.body.removeChild(el);
};

const copyButtonMaker = () => {
    const btn = this.container.createEl('button', {"text": "Copy"});
    
    btn.addEventListener('click', async (evt) => {
        evt.preventDefault();
        copyToClipboard(markdownTable);
    });
    
    return btn;
}

dv.paragraph(copyButtonMaker());

```


### 16th
| Day |Theme |Readings |
| --- | --- | --- |
| 2018-1-2 |fiction |42 |
