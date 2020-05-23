# uni-app-urltobase64
uni-app url转base64

## 源码
```javascript
urlTobase64(url) {
  const imgData = uni.getFileSystemManager().readFileSync(url, 'base64');
  const base64 = 'data:image/jpeg;base64,' + imgData;
  return base64;
}
```

## 调用
```javascript
this.urlTobase64(res.tempFilePaths[0]);
// wxfile://tmp_64f1ab8a1e796874f93d50fea64e2d4852e6b99722f666d0.jpg
```
## 兼容性
只在微信小程序测试可用，其他端未知。


谢谢！

https://github.com/Liuxianlu/uni-app-urltobase64
