https://zhuanlan.zhihu.com/p/61634111


## 关于参考文献管理的工作流的思考
### 目前工作流
使用这个软件主要是为了完成论文的参考文献的管理。
目前的工作流： 2021-6-29的最优工作流了。

- 在DBLP这个数据库里面，查找自己的文献，导入RIS文件，获得相应的各个field的值。
		这里的Field不会很全面，无论从哪个数据库里面导入，总有缺失的值。信息的多少取决于数据库能提供多少。编辑这些数据的过程中，需要你对文献有一个理解，这是很烦的一点。
		如果有模板，可以对照着模板填Field的值，还好。
- 手动搜索Field的值，填入到EndNote里面
- 使用EndNote的Word插件，进行参考文献的插入。
- 在EndNote preference 里面修改参考文献的格式，
	（在这一步骤，你需要知道你的目标刊物的格式要求，如果有模板，再好不过，没有就只能手动调整了。）
- 最后在Word里面修改参考文献的格式，定住。

### latex
latex确实**好像**可以提高编辑的效率，引用很方便。但是并不通用的，转换成Word有很多的不方便的东西。没有必要学这个latex了。

![[Pasted image 20210629153405.png]]

RIS文件各个词条的含义
https://blog.csdn.net/itnerd/article/details/109952776

英文参考文献的格式主要有4种：APA格式、MLA格式、CMS格式、哈佛文献格式（Harvard System）
ICONIP 这个会议使用的确实是 Springer LNCS格式，EndNote官网可以下载到。



###  Zotero我感觉可以把endnote淘汰掉了.
<font color = 'red'> 在切换的时候妥善的处理好新旧数据的交接问题。。</font>


参考文献endnote to zetero的转换
http://www.360doc.com/content/20/0707/16/69393506_922801517.shtml

- 就样式而言，Zotero可以直接下载GB7714和LNCS 而EndNote不可以
- 就分类系统而言，Zotero可以使用标签，键入搜索关键词直接出搜索结果
- 文献的导入，支持剪切板导入，支持自动识别文件格式。
- 浏览器的集成非常的好用。endnote需要下载，自己用脚本导入软件，太呆了。

Zotero修改文献格式的方法。
jianshu.com/p/f6d8679f0f