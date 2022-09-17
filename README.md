<a href="https://lab.magiconch.com/sakana/?v=takina" target="_blank">
  <img src="html/takina.png" height="160px">
</a><a href="https://lab.magiconch.com/sakana/?v=chisato" target="_blank">
  <img src="html/chisato.png" height="160px">
</a>

# 🍑「好耶!」希桃模拟器 （修改自石蒜模拟器）

[![NPM](https://img.shields.io/npm/v/sakana)](https://www.npmjs.com/package/sakana)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

地址 https://lab.magiconch.com/sakana/

## 功能
 - 按住立牌拖拽、松手后立牌会向反方向弹跳
 - 点击底座切换角色
 - 手机开启陀螺仪权限、摇一摇可甩动立牌 [#12 待解决](https://github.com/itorr/sakana/pull/12)
 - 自走模式，以随机间隔、施加一个大小随机的力 [#7](https://github.com/itorr/sakana/pull/7) [@milkybird98](https://github.com/milkybird98)
 - 音效，在适当区间松手时的语音效果 [#9](https://github.com/itorr/sakana/pull/9) [@zthxxx](https://github.com/zthxxx)
 - 多语言支持 [#26](https://github.com/itorr/sakana/pull/26) [@dsrkafuu](https://github.com/dsrkafuu)

### 选项与方法 
```javascript
// 设定静音
Sakana.setMute(true);

// 获取静音状态
const { isMute } = Sakana.Voices;

// 启动
const sakana = Sakana.init({
  // 选项: 默认值
  el:         '.sakana-box',     // 启动元素 node 或 选择器
  character:  'takina',          // 启动角色 'chisato','takina' 
  inertia:    0.01,              // 惯性
  decay:      0.99,              // 衰减
  r:          60,                // 启动角度
  y:          10,                // 启动高度
  scale:      1,                 // 缩放倍数
  translateY: 0,                 // 位移高度
  canSwitchCharacter: false,     // 允许换角色
  onSwitchCharacter(character){  // 切换角色回调
    console.log(`${character} dayo~`);
  },
});

// 设定归零角度
sakana.setOriginRotate(10);

// 获取角色运行状态
const v = sakana.getValue();

// 确保运行
sakana.confirmRunning();

// 切换角色
sakana.switchCharacter();

// 暂停动作
sakana.pause();

// 恢复动作
sakana.play();

// 切换特定角色
sakana.setCharacter('chisato');
```


### 放在窗口右下
```css
html .sakana-box{
  position: fixed;
  right: 0;
  bottom: 0;
  transform-origin: 100% 100%; /* 从右下开始变换 */
}
```

## 本地调试
`.less` 需要编译成 `.css` 样式文件 [#6](https://github.com/itorr/sakana/pull/6)

## 编译
 - `npm i`
 - `npm run build`


## License

[MIT](https://opensource.org/licenses/MIT)

Copyright (c) 2022, itorr
