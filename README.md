# fis3-deploy-ftp

将代码通过ftp的方式上传， 由[fis-deploy-ftp](https://www.npmjs.com/package/fis-deploy-ftp) 修改而来，以支持fis3

### 特性
支持上传文件列表缓存，首次完整上传后，再次上传将对比文件哈希值，未改动文件自动跳过，节省发布时间。

开启方式：`cache:true`

###配置

```
fis.media('upload').match('*', {
    deploy: fis.plugin('ftp', {
        //console: true,
        cache : true,           // 是否开启上传列表缓存，开启后支持跳过未修改文件，默认：true
        remoteDir : '/temp/',   // 远程文件目录，注意！！！设置错误将导致文件被覆盖
        connect : {
            host : '127.0.0.1',
            port : '21',
            user : 'name',
            password : '****'
        }
    })
});
```

发布

```
fis release upload
```