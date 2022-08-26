# m3u8-player
调试通过vue的vue-video-player播放m3u8视频，使用vue 2.6.x版本（兼容现有项目）。

## 安装
```
npm install
```
## 运行
```
npm run serve

然后在Chrome浏览器中访问该项目的本地调试服务页面: http://localhost:8080/ 或者http://localhost:8081/等
```

## 问题
播放器在刚初始化的时候就提示错误（控制台）：

video.cjs.js?ac2e:440 VIDEOJS: ERROR: (CODE:4 MEDIA_ERR_SRC_NOT_SUPPORTED) No compatible source was found for this media.

## 背景
项目中的vue-video-player 使用的还是比较低一点的版本 4.0.6， 而新版本已经是6.0.0。我曾经升级到过 5.x.x版本，也还是报错。