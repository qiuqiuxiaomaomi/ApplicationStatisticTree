# ApplicationStatisticTree
应用统计分析

数据采集

![](https://i.imgur.com/mE7u30q.png)

<pre>
数据采集的核心问题
       第一步骤：
           数据采集是最核心的问题。数据采集是否丰富，采集的数据是否准确，采集是否及时，都
       直接影响整个数据平台的应用的效果。
         
       数据采集遵循的两个基本原则
           1：优先在后端收集数据
           2：属性尽可能采集全面

       虽然之前已经详细描述过前端埋点的一些问题。
          例如：
              需要等待网络情况良好才能发送数据，
              需要积攒一定的量才能发送数据，
              需要在本地暂存而本地暂存空间有一系列在数据传输性和数据可靠性上的一些问题
       但是前段埋点毕竟有一些后端采集数据所无法替代的地方：
          例如：
              分析前段界面设计是否合理
              分析一些在于后端没有交互的前端行为
          还是必须采用前端埋点方案的。前端埋点作为一个比较成熟并且被广泛采用的数据接入手段。
</pre>

可视化埋点技术

![](https://i.imgur.com/Y4KJepu.png)

![](https://i.imgur.com/Arhxd7W.png)

<pre>
前端埋点技术介绍
    目前常见的分类
        1:在某个空间操作发生时通过预先写好的代码来发数据的代码埋点
          国内主要的有百度统计，友盟，TalkingData
          技术原理：
                 在APP或者界面初始化的时候，初始化第三方数据分析服务商的SDK，然后在某个
              事件发生时调用SDK里面相应的数据发送接口进行发送数据。例如，我们想统计APP里
              某个按钮的点击次数，则在APP的某个按钮被点击时，可以再这个按钮对应的
              OnClick()函数里调用SDK的数据发送接口来发送数据。

              缺点：
                  每次添加埋点信息，都需要更新APP

        2：通过可视化界面配置空间操作与事件发生关系的可视化埋点
           从前端埋点到可视化埋点是一个非常顺理成章的演进。既然埋点代价大，每个埋点都需要
           写代码，那么久参考Visual Studio等一系列IDE的做法，用可视化交互手段来代替写
           代码即可；既然每次埋点都需要等待APP的更新，那么久参考很多手游的做法，把核心
           代码和配置，资源分开，在APP启动的时候通过网络更新配置和资源即可。

        3：先收集所有数据再在后端筛选需要分析的对象的“无埋点”
</pre>