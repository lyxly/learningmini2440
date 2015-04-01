### Subversion简明命令手册 ###

**创建仓库（Repository）**

svnadmin create /path/to/repository

svnadmin是有用的subversion系统管理命令，使用svnadmin help查看在线帮助信息。

**添加新的项目（import new project）**

subversion的手册推荐的项目目录结构，
project/
+ branches/
+ tags/
+ trunk/
+ dir1/
+ file1
+ file2
+ dir2/

svn import project [file:///repository_name/project](file:///repository_name/project) -m "Comment"

svn import project http://host/svn_dir/repository_name/project -m "Comment"

**检出项目（checkout）**

svn checkout [file:///repository_name/project/trunk](file:///repository_name/project/trunk) project

svn checkout http://host/svn_dir/repository_name/project/trunk project

**列出仓库中的项目（list）**

svn list --verbose [file:///repository_name/project](file:///repository_name/project)

svn list --verbose http://host/svn_dir/repository_name/project

**状态查询（status）**

svn status
给出新文件，已经改变的文件和被删除的文件列表;

**添加文件或目录（add）**

svn add

**删除文件或目录（delete）**

svn delete

svn delete http://host/svn_dir/repository/project_dir 这条命令刚好可以用来删除错误的import的某些项目！！

**提交（commit）**

svn commit http://host/svn_dir/repository/project_dir

**更新（update）**

svn update
更新仓库中的文件到本地。

**标签和特殊版本项目**

使用copy命令
svn copy http://host/repos/project/trunk http://host/repos/project/tags/1.0.0

**用于创建某个特定版本的快照（snapshot）**

svn list http://host/repos/project/tags/1.0.0