

对于开源，我有好多好多问号？



章一

第一段 题引

最近 中国厂商 Oynx 拒发源码，被指违反 GPL 许可在国内外社交网络上被讨论的沸沸扬扬，缘由是Onyx 的电子书设备基于 Linux 内核修改发布的，而 Linux 内核基于 GPL v2 许可证发布，由于该许可证具备“传染性”，要求在进行二次分发时使用相同的许可证。根据 Reddit上的对话截图，有人向 Onyx 指出了其[违规问题](https://www.reddit.com/r/Onyx_Boox/comments/hk7d5v/onyx_is_violating_the_linux_kernels_license/)，而 Onyx 官方回应“技术团队表示目前不能把源码开放”，并希望他人谅解

图

Onyx事件在网络上引起广泛的讨论，有人表明绝不会购买Onyx产品，也有部分批评者认为Onyx事件暴露了中国厂商不尊重开源协议，质疑中国法律无法有效保障开源协议，“对于大多数中国公司而言，GPL 之类的许可证只是垃圾桶中的一张纸……保护自己的唯一方法就是不要与他们共享代码”

图

第二段 中国开源环境现状

中国是世界的一部分，开源亦是。中国已经逐渐成为开源世界的重要玩家。根据全球最大代码托管平台 GitHub 在 2019 年发布的[年度报告](https://www.infoq.cn/article/bWhDOufOZrL7r3ZuBopy)中显示

2019年中国、印度和德国的开源使用速度加快。中国的开发者`forked`和`cloned`的项目比去年多48%。

图

截至2018年，中国成为 GitHub 贡献排名第二的国家，排名仅次于美国

图

在开源贡献度上阿里、百度、PingCap、腾讯，除了头部的大厂，也有越来越多的中小企业积极拥抱开源，将自己的产品贡献给顶级的开源基金会，例如Apache基金会，Kylin、 DolphinScheduler（待补充）

图

第三段 许可证现状

随着开源环境越来越好，开发者和厂商对开源也越来越重视，国内的开发者正积极拥抱开源，但是对开源的许可证的还是不够重视（反转，从开源引导到 不重视许可证）

前两天，Apache孵化器项目DolphinScheduler的mentor在审查代码时，发现有段外部开发者贡献的代码实际上是源于Oracle JDK，但贡献者对该段代码进行重命名，并且删除了原有的协议声明，替换为Apache License 协议。这段代码不过数百行，占整个工程代码几乎可以忽略不计，若不是mentor 在发版前发现了这个问题并及时进行了回滚，分发出去的影响却是非常大的



从这个事件也反映很部分开发者对开源软件版权意识是非常淡薄的，也许是因为大部分开源许可证都是冗长的英文，以及类法律的行文风格，笔者自己从业十年，用过无数开源软件，也在github开源自己的软件，但是对许可证这个事情一无所知



前段时间，MATLAB 所属公司 MathWorks 称因接到美国政府的进出口管制名单，无法继续为哈工大提供正版授权。依美国出口管制条例(简称EAR），美国人、美国公司将软件出口至美国境外，或在美国境内提供给外国人作为出口的预备行为，必须申请取得许可。但符合「公开可及(Publicly available)」定义的软件，不在 EAR 管制范围，亦即不需要申请许可。也就是说开源软件，只要不涉非公开可及的加解密技术，不会被 EAR管制，这也就导致了当商业软件被管制后，开源软件的价值和理念被重新讨论，同时也推动中国厂商和开发者更加重视和尊重版权



借着这个契机，很多公司（笔者所在的公司）对其商业项目也进行了梳理review，非开源的组件和使用了GPL协议的组件被列为风险事项，立刻立项进行替换，笔者也对常用的开源许可证进行学习和梳理，现将自己收集和梳理的资料整理成文发布



章二

段一 基础： 版权、著作权概念

先了解下法律上的 著作权/版权

中华人民共和国著作权法

美国版权法



协议是否具备法律效应。。。

暂时在法律上没有特别明确的法律地位。

开源许可证既不是一种法律明文规定的权利，也不是一般意义的合同。但它仍然具备一定的法律效力。

此前研究过一些CC协议的司法判例，某些情况下会被法院所采纳与支持。毕竟CC协议和开源许可证，在法律世界里的根基是著作权。其他人如果不遵守约定，作者还是可以拿起著作权来保护自身权益。



美国案例和中国案例



段二

什么是开源，开源的宗旨（开源组织的开源理念，osi fsf的宗旨），你为什么开源



开源的7大理念https://mp.weixin.qq.com/s/15kCZNCG1psxyWv0WfOHAw



所以，我们看到，操作系统Linux、Android；编辑器Vim、Emacs、Atom、Brackets、VS code，版本管理系统SVN、Git；数据库MySQL、MongoDB、Redis、Postgres；大数据平台Hadoop、Elasticsearch、Hbase、Spark；Web服务器Apache、Nginx、Node.js、Tomcat；DevOps工具Jenkins、Maven、Ansible、Chef；虚拟化软件KVM、Xen、Docker、Kubernetes，如雨后春笋般应运而生，这些列出的和没有列出的开源软件，形成了一个完整的软件生态环境，黑客们已经生活在一个很幸福的时代，他几乎是想要什么就有什么，而几乎在所有的IT企业和大型非IT企业里，你都能看到这些开源软件的身影



段三

开源协议的组成

为了更好的实现产品开源的初衷，被赋予了哪些权利，但是对使用者有哪些约束限制，最后都会带上免责声明，规避一些不必要的风险

名词解释





段四 

开源许可证那么多，我的产品该选择哪种？

如何选择开源许可证，或者在使用开源项目时候需要注意的风险要素

对比图





对比图解释



章三

常见问答





引用：

- onyx事件https://www.reddit.com/r/Onyx_Boox/comments/hk7d5v/onyx_is_violating_the_linux_kernels_license/
- 2019中国开源报告https://github.com/kaiyuanshe/2019-China-Open-Source-Report/blob/master/insight.md
- matlap事件https://www.oschina.net/news/116379/matlab-ban-and-edu-schools
- 专家解读：开源软件项目是否会被限制出口?https://mp.weixin.qq.com/s/_wmBHskWi5CCTjDWu6fMAg
- 中华人民共和国著作权法 https://www.wipo.int/edocs/lexdocs/laws/zh/cn/cn031zh.pdf
- 世界版权公约[https://zh.wikipedia.org/wiki/%E4%B8%96%E7%95%8C%E7%89%88%E6%9D%83%E5%85%AC%E7%BA%A6](https://zh.wikipedia.org/wiki/世界版权公约)
- 伯尔尼公约[https://zh.wikipedia.org/wiki/%E4%BC%AF%E5%B0%94%E5%B0%BC%E4%BF%9D%E6%8A%A4%E6%96%87%E5%AD%A6%E5%92%8C%E8%89%BA%E6%9C%AF%E4%BD%9C%E5%93%81%E5%85%AC%E7%BA%A6](https://zh.wikipedia.org/wiki/伯尔尼保护文学和艺术作品公约)
- GPL FAQ  https://www.gnu.org/licenses/gpl-faq.html

