# Plinko

Luck Draw with Galton board (Plinko) 类似伽尔顿版的抽奖

Code from <https://codepen.io/borntofrappe/pen/QWWwOWO>

## What is the rule

Avatars will drop on the right. The first one to the leftmost side in the given time `T = 30s` wins.

## How to compose URL

| Name  | Description           |
| ----- | --------------------- |
| prize | Index of the prize    |
| api   | API point of the data |

For example:

```
http://localhost:8000/?prize=0&api=data.json
```

Or just visit https://pkuphysu.github.io/?prize=0&api=data.json

## How to prepare data

| Key        | Description                     |
| ---------- | ------------------------------- |
| name       | User name                       |
| investment | Investment points of each prize |
| avatar     | Image (data) URL of user avatar |

For example, have a look at`data.json`

## 较详细的中文介绍

这个抽奖系统的原型是伽尔顿板，国外也有称呼为 plinko 的。相信大家对伽尔顿板都很熟悉了。我们充分利用了下落后呈近似正态分布的特点，并对其加以改造，指定如下规则：

1. 使用正方形微信头像，从中间偏右侧一定范围内下落
2. 头像每轮下落约 200 个，根据投点数会有不同的概率
3. 头像与头像、点、板之间都会发生非完全弹性碰撞
4. 在给定时间内，最先到达最左侧（相对于本轮所有头像而言）者为幸运者
5. 在抽奖过程中，屏幕上方会显示当前领先者。当尘埃落定时显示的领先者即为系统判定的中奖者

当然，这一抽奖系统本质上还是计算机的随机数，也不必钻牛角尖。如果想了解代码详情，可在 GitHub 上进入 pkuphysu 组织查看。

![image](https://user-images.githubusercontent.com/36528777/102891675-8fe88f00-4499-11eb-8831-0aed86f2f70c.jpg)