
## 1、准备挖矿设备

操作系统：Ubuntu 18.04、Ubuntu 20.04

GPU：推荐拥有6GB以上显存，NVIDIA显卡，驱动版本515或更高。

驱动下载：[NVIDIA官方驱动下载](https://www.nvidia.cn/Download/index.aspx?lang=cn)



## 2、注册zklion矿池账户
矿池地址：https://pool.zklion.com

zklion ALEO挖矿方式为用户名挖矿，需注册矿池帐户后根据引导创建挖矿用户。

访问zklion官网，根据指引完成注册即可获取用户名，登录帐户后，点击用户头像账户设置创建挖矿用户，用于配置挖矿参数。

开始挖矿后，挖矿收益会自动累计在各自帐户中



## 3、下载挖矿程序

[下载地址](https://github.com/chihua2023/ZKLion)
```shell
zklion-pool-prover 	//Ubuntu系统矿池挖矿程序

zklion-solo-prover 	//Ubuntu系统solo挖矿程序

zklionminer 		//HiveOS系统矿池挖矿程序
```



## 4、程序参数解释

```shell
#矿池挖矿程序
./zklion-pool-prover --help
ZKLION-pool-prover 0.1.0 (7b503b8 2023-11-08)

USAGE:
    zklion-pool-prover [OPTIONS] --pool <POOL> --account <ACCOUNT> --worker-name <WORKER_NAME>

OPTIONS:
        --account <ACCOUNT>            //矿池中生成的挖矿用户名
    -h, --help                         //打印帮助信息
        --pool <POOL>                  //矿池连接地址、wss://aleo.zklion.com:3777
        --rest <REST>                  //本地监听端口、默认0.0.0.0:9988
    -v, --version                      //程序版本
        --worker-name <WORKER_NAME>    //输入你的矿机名称

```

```shell
#solo挖矿程序
./zklion-solo-prover --help
ZKLION-solo-prover 0.1.0 (7b503b8 2023-11-08)

USAGE:
    zklion-solo-prover [OPTIONS] --proxy <PROXY> --address <ADDRESS>

OPTIONS:
        --address <ADDRESS>            //你的aleo钱包地址
    -h, --help                         //打印帮助信息
        --proxy <PROXY>                //矿池连接地址、wss://aleo.zklion.com:3666
        --rest <REST>                  //本地监听端口、默认0.0.0.0:9988
    -v, --version                      //程序版本
        --worker-name <WORKER_NAME>    //输入你的矿机名称
```

## 5、示例 

```shell
#下载后首先添加可执行权限
chmod +x zklion-pool-prover
#矿池程序启动示例
./zklion-pool-prover --account test01 --pool wss://aleo.zklion.com:3777 --worker-name 192-168-100-101

#solo程序启动示例
./zklion-solo-prover --address aleo1308gq2pfn0y3hgm722wysx4ks8szxsxaxsdnjnabdy --proxy wss://aleo.zklion.com:3666 --worker-name x99-01
```

## 6、后台运行挖矿程序
```shell
nohup ./zklion-pool-prover --account test01 --pool wss://aleo.zklion.com:3777 --worker-name 192-168-100-101 &> /root/zklion-pool-prover.log &
```

检查zklion-pool-prover.log日志、显示如下信息，则说明程序运行正常
<img width="847" alt="image" src="https://github.com/chihua2023/ZKLion/assets/137146992/cfaa57cc-f719-4d50-b214-9177db560bb0">

