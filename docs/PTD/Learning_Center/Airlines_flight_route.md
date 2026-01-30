# 班机航路的查询和使用

Query and use of flight routes by airlines



## 前言

在中国大陆区域，所有日常班机的飞行航路都需由CAAC审核并批准后，在其中央数据库中储存，并向各航空公司发放的`FLIGHT_AIRLINE.csv`中保存的。为尽可能的模拟真实，我们推荐和希望所有的飞行员使用班机航路进行飞行，如果这条航路在现实中不存在，这时才推荐使用非班机航路的航路查询方案。



## 免责协议

**一、信息来源与性质**
本教程所涉及的全部技术方案、数据、图表及参考资料等，均来源于网络公开渠道及可合法获取的公共信息。特别包括援引自中国民用航空局于2025年6月23日出具的《政府公开申请答复书》，该文件明确指出《中国民航国内航空资料汇编》不属于民航工作国家秘密范围。

**二、非专业建议与时效性**
本教程内容仅为技术探讨、研究与学习参考之用，不构成任何领域的专业建议（包括但不限于飞行操作、工程设计与法律合规）。信息具有时效性，可能随政策、法规及技术标准的更新而发生变化，我们不对内容的即时性与完整性提供任何担保。

**三、用户责任与使用风险**
使用者有责任自行判断本教程内容的准确性、适用性与合法性。您应依据官方最新发布的规定与标准进行核实。因依赖、使用或参考本教程内容而直接或间接引发的任何风险、损失或法律责任，均由使用者自行承担，与本教程的创作者、发布者及相关贡献者无关。

**四、知识产权**
本教程尊重原始资料来源的知识产权，仅限个人学习与研究使用。您不得将本教程内容用于任何可能侵犯第三方合法权益或违反法律法规的用途。




## 使用教程

1. 进入由中航材导航技术（北京）有限公司出品的Aeronautical Information System：[https://aips.siniswift.com](https://aips.siniswift.com)

2. 点击右侧导航栏的"Route Planning"

    ![image-20251116160729089](./assets/image-20251116160729089.png)

3. 在"DEP AP"、"ARR AP"，填写出发机场、到达机场，其余项不用动，最后点击"Route Planning"

    ![image-20251116161041741](./assets/image-20251116161041741.png)

4. 这里以"ZSSS-ZPPP"为例，一组出发和到达机场间可能有多组航路，接下来就要进行合适的选择

    ![image-20251116161534528](./assets/image-20251116161534528.png)



## 选择合适的航路

在此继续以ZSSS-ZPPP为例：

| Route code | Distance(NM) | Estimated flight time(H) | Route                                                        |
| ---------- | ------------ | ------------------------ | ------------------------------------------------------------ |
| ZSSS-ZPPP  | 1075.8       | 2.69                     | ZSSS NXD W131 AKDIM A470 SAGNU W132 OREXA H165 P490 A581 XISLI ZPPP |
| ZSSS-ZPPP  | 1086.84      | 2.72                     | ZSSS OLGAP X261 P322 X262 P207 W132 OREXA H165 P490 A581 XISLI ZPPP |
| ZSSS-ZPPP  | 1122.58      | 2.81                     | ZSSS POMOK G330 PIMOL V14 NOBEM W73 MADUK W51 LEGIV W164 ADGOL W50 XSH W80 IDGAG A581 QNX W136 XISLI ZPPP |
| ZSSS-ZPPP  | 1125.58      | 2.81                     | ZSSS POMOK G330 UNTAN G345 OLRIS R343 MADUK W51 LEGIV W164 ADGOL W50 XSH W80 IDGAG A581 QNX W136 XISLI ZPPP |

我们都知道一条航路(Route)由：航路点(Way Point)、航路(Airway)两部分组成。

而，部分航路(Airway)可能涉及nAIP内容，在我们的导航数据中不存在。因此，我们应尽量选择公开的航路/将非公开内容删除。

### 公开航路

- A、B、G、R，表示国际（地区）航路航线
- L、M、N、P，表示国际（地区）区域导航航路
- W，表示不涉及周边国家或地区的对外开放航路航线（含 进离场航线）
- Y，表示不涉及周边国家或地区的对外开放区域导航航路V表示对外开放临时航线

### 非公开航路

- P，表示P字点
- H，表示国内航路航线
- Z，表示国内区域导航航路
- J，表示国内进离场航线
- X，表示国内临时航线
- V、X，系列航路需经过ATC许可

- FANS，表示自定义脱离航线

按照上文的原则，我们应该在飞行ZSSS-ZPPP时选择以下2条：

| Route code | Distance(NM) | Estimated flight time(H) | Route                                                        |
| ---------- | ------------ | ------------------------ | ------------------------------------------------------------ |
| ZSSS-ZPPP  | 1122.58      | 2.81                     | ZSSS POMOK G330 PIMOL V14 NOBEM W73 MADUK W51 LEGIV W164 ADGOL W50 XSH W80 IDGAG A581 QNX W136 XISLI ZPPP |
| ZSSS-ZPPP  | 1125.58      | 2.81                     | ZSSS POMOK G330 UNTAN G345 OLRIS R343 MADUK W51 LEGIV W164 ADGOL W50 XSH W80 IDGAG A581 QNX W136 XISLI ZPPP |


在服务器提交航路时，请勿直接将查询的航路复制，应将机场ICAO从航路中处删除后再提交  ，例如：
```
[ERROR] ZSSS POMOK G330 PIMOL V14 NOBEM W73 MADUK W51 LEGIV W164 ADGOL W50 XSH W80 IDGAG A581 QNX W136 XISLI ZPPP
-----------> POMOK G330 PIMOL V14 NOBEM W73 MADUK W51 LEGIV W164 ADGOL W50 XSH W80 IDGAG A581 QNX W136 XISLI <---
```



## ★ 为什么航路中通常第一个点和最后一个点不是进离场点？

这是为了防止终端区没法及时给出进离场程序，从而导致不可控的风险。

其次，许多小飞机的航路中只能输入高级航路点，而进场点是一个低级航路点。因此，将航路第一最后一个点延伸。

而程序中通常包含这个点或选择程序后，飞机有能力进行去重工作。

飞行员提交的计划应是包含此的。但，我们的EuroScope雷达会将其自动去除。因此，提不提交也无关紧要的。



## 参考资料

[1] [《2025年6月23日出具的<政府公开申请答复书>》](https://a1.qpic.cn/psc?/V51TNOwh2BiwO34S5eD71iOOMH0tZxQ4/TmEUgtj9EK6.7V8ajmQrEJBzNstDVuJgRVCI8tr3M9Xr6GJLX5c6oitRW68*APu89Vuh80ddPpj5GHYCcBNvM0aJghpcYsTn.CPbrn8JRr4!/b&ek=1&kp=1&pt=0&bo=*ASmBvwEpgYWECA!&tl=1&vuin=1436001938&tm=1763276400&dis_t=1763279469&dis_k=729ba61d6f02f62b57719913893aac17&sce=60-2-2&rf=viewer_311)

[2] [飞行员培训.飞行员想知道：航路属性分类及图例图解](https://mp.weixin.qq.com/s/ixdbr7HJYLgUms8d7VBEdQ)
