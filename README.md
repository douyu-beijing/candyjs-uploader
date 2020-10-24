## candyjs 文件上传组件

此组件基于 formidable 开发，旨在为 candyjs 提供文件上传功能

## 使用

#### 安装

```
npm install @candyjs/uploader
```

#### 直接使用

```
const Uploader = require('@candyjs/uploader');

module.exports = class UploadController {
    async run(req, res) {
        const up = new Uploader({
            // 必须参数
            basePath: './public/upload',

            // 可选参数
            allowTypes: 'image/jpg, image/jpeg, image/png',
            maxSize: 1048576,  // 1024 * 1024 = 1Mb
        });

        let data = await up.upload(req, 'editorfile');
        res.end(JSON.stringify(data));
    }
}
```

#### 指定文件名

```
const Uploader = require('@candyjs/uploader');

module.exports = class UploadController {
    async run(req, res) {
        const up = new Uploader({
            // 必须参数
            basePath: './public/upload',

            useRandomName: false,
            givenName: '1'  // 使用指定的文件名
        });

        let data = await up.upload(req, 'editorfile');
        res.end(JSON.stringify(data));
    }
}
```

## CHANGELOG

+ 2020-10-24

    * 0.1.0 节日快乐 提交插件

