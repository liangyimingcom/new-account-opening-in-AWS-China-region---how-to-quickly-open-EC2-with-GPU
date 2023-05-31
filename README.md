# AWS中国区新开账号 - 如何快速开启带GPU的EC2



## 背景：

由于AWS的账号为无门槛限制的自助开通方式，为了防止欺诈行为，AWS对账号有一套积分用于fraud risk assessment。 一些新开通的账号和一些疑似有fraud risk的账号，评估分数可能会低，进而会限制其EC2的开启数量和类型限制（新账号通常无法直接开启带GPU的G和P系列EC2）。对于apigateway和serverless，也存在限制，如lambda的max concurrency和max memory。



### 解决方案： 

1）提Service Quotas

2）联络AWS BD 告知 case id 可以加速过程；

3）随着时间推移，正常账号的使用，会逐渐解除各类限制；



#### 解除GPU EC2限制的操作步骤：

一、登录AWS账号后，输入“quotas”关键字如下图：

![image-20230531171917708](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/image-20230531171917708.png)



二、点击“Amazon Elastic Compute Cloud (Amazon EC2)“菜单

![image-20230531172004313](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/image-20230531172004313.png)



三、进入后你会发现上百条类型，这个时候需要使用搜索来找到目标EC2.



举例：对于日常开机的带显卡的 g4dn.xlarge EC2来说，输入的关键字是“on-demand G”，如下图：

![image-20230531172257497](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/image-20230531172257497.png)



举例：对于日常开机的带显卡的 M6/C6/R6 类型 EC2来说，输入的关键字是“on-demand Standard”，如下图：

![image-20230531172537396](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/image-20230531172537396.png)



四、进入后，点击《Request quota increase》，输入你想要申请的，此类型的EC2最大允许的开机数量，如下图。

![image-20230531172754065](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/image-20230531172754065.png)



五、你可以看到你的申请处于了pending状态。

![image-20230531172911523](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/image-20230531172911523.png)



六、刚才Request的行为，其实创建了一个新的support case，下图的操作能够看到case的进程。 你可以在case里面补充你申请EC2的用途和原因，从而加速审批的进程。

![image-20230531173233886](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/image-20230531173233886.png)



七、如果你认识AWS的客户经理（BD），可以直接把全部提升的case id 转给 客户经理（BD），他可以用最短的时间内协调AWS后台给你解除限制 - 以便开通资源。

