[![LICENSE](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

English | [简体中文](./README.zh-CN.md)


<p align="center"><img src="https://o2qq673j2.qnssl.com/tower-loading.gif"/></p>
<h1 align="center">塔楼建造游戏</h1>
<p align="center"><strong>使用纯html+css+javascript编写的塔楼建造游戏<br><em>持续更新 ing～</em></strong></p>

<div align="center">
    <a href="https://www.weilanx.com/"><img src="https://img.shields.io/badge/个人博客-蔚蓝-orange.svg?style=plasticr"></a>
    <a href="https://github.com/Azure12355/tower_game"><img src="https://img.shields.io/badge/github-项目地址-yellow.svg?style=plasticr"></a>
    <a href="https://github.com/Azure12355/tower_game"><img src="https://img.shields.io/badge/码云-项目地址-orange.svg?style=plasticr"></a>
    <a href="https://azure12355.github.io/tower_game/"><img src="https://img.shields.io/badge/online-点我即玩-blueviolet.svg?style=plasticr"></a>
    
</div>

## 效果展示
<p align="center"><img src="https://user-images.githubusercontent.com/17680888/47480922-93a20c00-d864-11e8-8f7c-6d1d60184730.gif"/></p>
<h2 align="center"><a href="https://azure12355.github.io/tower_game/">塔楼建造在线版（点我即玩）</a></h2>
<h4 align="center">移动设备可扫描下方二维码：</h4>
<p align="center">
  <img src="https://user-images.githubusercontent.com/17680888/47480646-abc55b80-d863-11e8-9337-4ea768ebe55d.png" />
</p>

## Game Rule 游戏规则

以下为默认游戏规则，也可参照下节自定义游戏参数

- 每局游戏生命值为3，掉落一块楼层生命值减1，掉落3块后游戏结束，单局游戏无时间限制

- 成功盖楼加25分，完美盖楼加50分，连续完美盖楼额外加25分，楼层掉落扣除生命值1，单局游戏共有3次掉落机会

栗子：第一块完美盖楼加50分，第二块连续完美盖楼加75分，第三块连续完美盖楼加100分，依此类推……

<p align="center">
  <img src="https://o2qq673j2.qnssl.com/Fv7ewqHHXeAnUAlF7AI9ndQulEOC" />
</p>

## Customise 自定义

```
git clone https://github.com/iamkun/tower_game.git
cd tower_game
npm install
npm start
```
打开 `http://localhost:8082`

- 图片、音频资源可以直接替换 `assets` 目录下对应的资源文件
- 游戏规则可以修改 `index.html` 文件 `L480` 的 `option` 对象

## Option 自定义选项

可以使用以下 `option` 表格里的参数，完成游戏自定义，**所有参数都是非必填项**

| Option | Type | Description |
|---------|--------|-------------|
| width          | number | 游戏主画面宽度 |
| height         | number | 游戏主画面高度 |
| canvasId       | string | Canvas 的 DOM ID |
| soundOn        | boolean | 是否开启声音 |
| successScore   | number | 成功盖楼分数 |
| perfectScore   | number | 完美盖楼额外奖励分数 |
| <a href="#hookspeed">hookSpeed</a> | function | 钩子平移速度 |
| <a href="#hookangle">hookAngle</a> | function | 钩子摆动角度 |
| <a href="#landblockspeed">landBlockSpeed</a> | function | 下方楼房横向速度 |
| <a href="#setgamescore">setGameScore</a> | function | 当前游戏分数hook |
| <a href="#setgamesuccess">setGameSuccess</a> | function | 当前游戏成功次数hook |
| <a href="#setgamefailed">setGameFailed</a> | function | 当前游戏失败次数hook |

#### hookSpeed
钩子平移速度
函数接收两个参数，当前成功楼层和当前分数，返回速度数值
```
function(currentFloor, currentScore) {
  return number
}
```

#### hookAngle
钩子摆动角度
函数接收两个参数，当前成功楼层和当前分数，返回角度数值
```
function(currentFloor, currentScore) {
  return number
}
```

#### landBlockSpeed
下方楼房平移速度
函数接收两个参数，当前成功楼层和当前分数，返回速度数值
```
function(currentFloor, currentScore) {
  return number
}
```

#### setGameScore
当前游戏分数hook
函数接收一个参数，当前游戏分数
```
function(score) {
  // your logic
}
```

#### setGameSuccess
当前游戏成功次数hook
函数接收一个参数，当前游戏成功次数
```
function(successCount) {
  // your logic
}
```

#### setGameFailed
当前游戏失败次数hook
函数接收一个参数，当前游戏失败次数
```
function(failedCount) {
  // your logic
}
```

## License

MIT license.
