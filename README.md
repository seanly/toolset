# toolset

一个工具镜像集合，通过镜像工具的方式归档工具，方便日常使用。

使用案例：https://github.com/seanly/opsbox

|工具|说明|
| --- | --- |
|image-syncer| 阿里出的一个镜像同步工具，可以用于同步公网进行到私有仓库。|
|docker|归档docker工具，在镜像中也提供一个docker安装包，从镜像中拷贝出来，上传到服务器上，执行脚本完成安装|
|k9s|一款终端界面的kubernetes dashboard|
|kubectl| kubernetes cli|
|kustomize| 一个 kubernetes yaml 编排工具|
|dapper|基于docker包装用于代码构建的工具，本镜像打包了一些patch功能，主要适配了dockerkit的参数|
|envsubst|一款环境变量替换工具，很实用|

