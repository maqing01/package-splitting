## lerna 工程包托管
[参考文章https://www.jianshu.com/p/63ec67445b0f] (https://www.jianshu.com/p/63ec67445b0f)

### 实际作用：
* 包托管 -- 子包依赖管理、批量发布

### 我这么用：
* 对未发布包相互依赖进行管理，创建符号链接，使得未发布包可像发布包一样使用
* 批量发布自定义包
* `注意`：未发布包依赖关系由`package.json`文件中`dependencies`和`devDependencies`项指定 

### 常用命令：  
* lerna init --independent
  * 在根目录下创建`packages`目录，开发者将未发布包放在这个目录下
  * 在根目录下生成`learn.json`文件，作为基本配置文件，可修改

* lerna bootstrap
  * 引导packages下的包安装各自的依赖
  * 创建未发布包的符号链接

* lerna publish
  * 更新子包版本号
  * 发布子包

### 特别提醒：
* 执行`lerna bootstrap
`后，packages里的未发布包仍然不能像正常包一样引用
* 需要创建符号链接，将packages目录下的未发布包关联到node_modules目录
  