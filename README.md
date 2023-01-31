# mkdocs
快速、简单、华丽的静态网站生成器
用Markdown编写，并使用一个YAML文件来进行配置
```bash
#安装 mkdocs
pip install mkdocs #安装 MkDocs 基于Python3
mkdocs help #mkdocs [help|new|build|serve|gh-deploy] {options}

#直接在项目中 创建 mkdocs 文档 -- (推荐)
mkdocs new .
vi mkdocs.yml #把 site_name 改成自己项目的名称
#或者 先建 mkdocs 文档， 再移到项目中
mkdocs new <mysite> #新建站点项目
mv ./mysite/* <project_path> 

#在本地运行站点
mkdocs serve 
访问 localhost:8000

#将 site/ 加入 .gitignore 忽略文件中  -- 防止 site/ 影响 master 分支
echo "site/" >> .gitignore

部署方式一： -- (推荐)
mkdocs gh-deploy --clean #编译打包、提交、部署
#1. 自动创建 gh-pages 分支
#2. 自动将当前目录中的 site/目录(没有会自动创建) 推送到远程的 gh-pages 分支。
#3. 自动 开启 GitHub Pages (分支发布 且 分支来源为 gh-pages) -- 无需手动设置     

----------------

部署方式二： 将项目打包，再由个人将打包文件上传至服务器对应的目录下进行部署；
#站点生成
mkdocs build #生成静态文件 该命令创建了一个 site 新目录，源码被分别输出为 site/ 中的 index.html 和 about/index.html. 主题中的其他文件也被复制到了 site 目录中.
mkdocs build --clean #一段时间后, 可能有文件被从源码中移除了, 但是相关的文档仍残留在 site 目录中. 在构建命令中添加 --clean 参数即可移除这些文档.
```