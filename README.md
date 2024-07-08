使用thriftAPI或者是P4runtimeAPI来编写控制器控制器BMV2交换机流表下发的前提是控制器能ping通BMV2交换机。
在此基础上，使用P4-learning及其配套环境能极大程度简化控制器的编写。
目前来看，就实验室的环境而言，使用thriftAPI开发控制器更为简单直接。thrift控制器样本如文件thrift_controller.py所示



TIPS：如何使用你自己的电脑远程连接到机房的BMV2实体交换机
众所周知，一般而言，实验室机房内的这几台BMV2实体交换机所在的网络环境是与外界隔绝的，which means，你无法使用在自己笔记本上来ping通这几台实体交换机。
但是我们可以有别的解决方案，我们可以借助ssh远程连接的端口映射。毕竟从本质上而言，控制器与BMV2交换机建立连接本质上就是建立TCP连接。所以我们可以使用以下示例步骤：
现在，打开你的虚拟机，开启一个terminal，在当中输入这个命令：ssh -L 9090:localhost:9090 -p 6182 sinet@219.242.112.215
意味着你访问自己虚拟机上的9090端口就是访问远程服务器的9090端口。6182是远程ssh服务器提供ssh服务的TCP端口，后面的信息是远程服务器上的用户名和BMV2交换机的公网IP地址。
现在，你就可以使用控制器往这里面进行流表的增删改查操作了。
