# 链评(RankingChain)简介



## 简介

RankingChain（RC）是一套基于以太坊开发的可信评分系统，用户可以在ChianRating中发起、参与电影等项目评分。



## 项目特色

影视分值评定中引入价值因子（票房预测），使大众在评定影视作品时基于算法规则能够有效的实现更加客观公正的进行。相较于目前市面上主流的过于主观号好恶评分算法，它不但能让大众在有奖励机制的刺激下大大改善影评整体的恶意评分、抱团刷分的现象，还能更加客观公正的体现一个影视作品的优劣。

算法中引入票房预测，本质上就是加入了一个除了主观评定分以外，另一个影视价值评定分作为算法价值因子。价值因子在获得大众最终影视评分过程中能够对不合理的评分（比如恶意抬高、恶意差评等）进行适当的弱化，并能大大降低这种不合理现象的出现。整个算法分为两部分，影视评分获得算法及奖励机制算法。

影视评分算法的核心作用是获得获得大众给出的客观合理的影视作品评分。

奖励机制算法的作用是对在影视评分中成员表现的优劣进行评定，后续如果进行奖励时可以作为依据。



## 流程

![main_menu](https://github.com/rebase-network/2021Q2-hackathon/blob/master/img/voting.png) 

https://github.com/rebase-network/2021Q2-hackathon



### 链评发起

一部电影在上映前7天可以发起链评。

发起者需选择电影库中的电影ID并提供RC币手续费和奖励金，在发起期内当新的链评发起者提供的奖励金大于当前奖励金时更换发起责任人。

![create](https://github.com/rebase-network/2021Q2-hackathon/blob/master/img/create.png)  



### 链评评分

一部电影的链评发起成功后进入评分期，在上映前2天可以参与评分。

参与者需提供手续费和抵押金，并给出电影的评分和预测票房；在评分期内会定期（1h）刷新实时奖金池和参与人数，并在评分期结束时进行链评有效性判定。

![voting](https://github.com/rebase-network/2021Q2-hackathon/blob/master/img/voting.png) 



若参与人数大于有效值，则视为链评有效，进行评分公示。

若参与人数小于有效值，则视为项目无效，退回发起者的奖励金和参与者的抵押金，该电影的链评作废。



奖金池 = 发起者抵押金 + 参与者抵押金 + 挖矿增发奖金

评分期仅公示除挖矿增发奖金外的奖金池，挖矿增发奖金在结算后公示。

 



### 评分结算

确认电影的链评有效后进入结算期，时间为上映第3天至电影下映。

电影下映后，系统根据真实票房数进行评分结算。

![bonus](https://github.com/rebase-network/2021Q2-hackathon/blob/master/img/bonus.png) 

挖矿增发奖金 = 票房数 * 挖矿系数

奖金池 = 发起者抵押金 + 参与者抵押金 + 挖矿增发奖金

发起者奖励 = 奖金池 * ~~发起系数(待定)~~

参与者奖励 = 奖金池 - 发起者奖励

函数式为：

其中 A为放大因子；

​         Z为主观评分；

​         F为影评；

​         P为预测票房对应的评分；

​         T为实际票房对应的评分；

​         f(x)为误差处理函数。






























