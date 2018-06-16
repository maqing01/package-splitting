## node 符号链接

* 作用：将某个目录|文件关联到另一个目录下，形成修改连动
* 场景：为项目中目录添加配套`package.json`，关联到`node_modules`目录下
* 效果：可以像使用npm包一样使用该目录，并且对该目录的修改会同步到node_modules目录

> 建立符号链接  

```js
	#!/usr/bin/env node

	const fs = require("fs");
	const rootPath = process.cwd();
	try {
	    fs.symlinkSync(`${rootPath}/services`, `${rootPath}/node_modules/services`, "dir");
	} catch (err) {
	    console.log(err.toString());
	}
```

> 解除符号链接
 
```js
	#!/usr/bin/env node 

	const fs = require("fs");
	const rootPath = process.cwd();
	try {
	    fs.unlinkSync(`${ rootPath }/node_modules/services`)
	} catch (err) {
	    console.log(err.toString());
	}
```