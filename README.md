# fis3-deploy-ftp

将代码通过ftp的方式上传， 由[fis-deploy-ftp][id]修改而来，以支持fis3
[id]:https://www.npmjs.com/package/fis-deploy-ftp "https://www.npmjs.com/package/fis-deploy-ftp"

配置

```
fis.media('upload').match('*', {
    deploy: fis.plugin('ftp', {
        //console: true,
        remoteDir : '/temp/',
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