
# Docsify笔记

首先需要安装node软件，然后`node -v`，`npm -v`进行检查，
执行语句`npm i docsify-cli -g`，安装docsify。

在本地文件夹中执行语句：`docsify init ./docs`，生成初始化文件。然后执行`docsify serve docs`语句，会给出如下结果，按Ctrl+C关闭命令行。

```
Serving C:\Users\ll\Documents\GitHub\Skalate.github.io\docs now.
Listening at http://localhost:3000
```

浏览器打开网址`http://localhost:3000`即可查看。

`index.html` as the entry file

`README.md` as the home page

`.nojekyll` prevents GitHub Pages from ignoring files that begin with an underscore



``` html
<!-- index.html -->

<!DOCTYPE html>
<html>
<head>
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <meta charset="UTF-8">
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/themes/vue.css" />
</head>
<body>
  <div id="app"></div>
  <script>
    window.$docsify = {
      //...
    }
  </script>
  <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
</body>
</html>
```