使用thriftAPI或者是P4runtimeAPI来编写控制器控制器BMV2交换机流表下发的前提是控制器能ping通BMV2交换机。
在此基础上，使用P4-learning及其配套环境能极大程度简化控制器的编写。
目前来看，就实验室的环境而言，使用thriftAPI开发控制器更为简单直接。thrift控制器样本如文件thrift_controller.py所示
