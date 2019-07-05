---
title: 让vs code支持region和endregion
linkname: vscode-support-region-and-endregion
date: 2019-07-05
updated: 2019-07-05
categories:
- 编程工具
tags:
- vscode
- setting
---

在 `Microsoft VS Code\resources\app\extensions/XXX/language-configuration.json` 文件的最后一个 `}` 前加入如下内容：

```
,
	"folding": {
		"offSide": true,
		"markers": {
			"start": "^\\s*//\\s*#?region",
			"end": "^\\s*//\\s*#?endregion"
		}
	}
```

文件路径中的 `XXX` 为你要使用的语言，例如go、php等。

本示例语言使用 `//` 作为注释标识。
开始部分使用 `//region` 或 `//#region` ，结束部分使用 `//endregion` 或 `//#endregion` 。

如使用语言不使用 `//` 作为注释标识，则将 `start` 和 `end` 中的 `//` 替换为对应的注释标识。

<!-- more -->