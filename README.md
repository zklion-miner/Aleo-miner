
## 1、準備挖礦設備

操作系統：推薦使用ubuntu 20.04 server版、暫不兼容桌面版ubuntu系統

系統下載地址：https://releases.ubuntu.com/focal/ubuntu-20.04.6-live-server-amd64.iso

GPU：推薦擁有6GB以上顯存，NVIDIA顯卡，驅動版本515或更高。

驅動下載：[NVIDIA官方驅動下載](https://www.nvidia.com/Download/index.aspx?lang=en-us)



## 2、註冊zklion礦池帳戶
礦池地址：https://pool.zklion.com

zklion ALEO挖礦方式為用戶名挖礦，需註冊礦池帳戶後根據引導創建挖礦用戶。

訪問zklion官網，根據指引完成註冊即可獲取用戶名，登錄帳戶後，點擊用戶頭像賬戶設置創建挖礦用戶，用於配置挖礦參數。

開始挖礦後，挖礦收益會自動累計在各自帳戶中



## 3、下載挖礦程序

[下載地址](https://github.com/zklion-miner/Aleo-miner/releases)
```shell
zklion-pool-prover 	//Ubuntu系統礦池挖礦程序

zklion-solo-prover 	//Ubuntu系統solo挖礦程序

zklionminer 		//HiveOS系統礦池挖礦程序
```



## 4、程序參數解釋

```shell
#礦池挖礦程序
./zklion-pool-prover --help
ZKLION-pool-prover 0.1.0 (7b503b8 2023-11-08)

USAGE:
    zklion-pool-prover [OPTIONS] --pool <POOL> --account <ACCOUNT> --worker-name <WORKER_NAME>

OPTIONS:
        --account <ACCOUNT>            //礦池中生成的挖礦用戶名
    -h, --help                         //打印幫助信息
        --pool <POOL>                  //礦池連接地址、wss://aleo.zklion.com:3777
        --rest <REST>                  //本地監聽端口、默認0.0.0.0:9988
    -v, --version                      //程序版本
        --worker-name <WORKER_NAME>    //輸入你的礦機名稱

```

```shell
#solo挖礦程序
./zklion-solo-prover --help
ZKLION-solo-prover 0.1.0 (7b503b8 2023-11-08)

USAGE:
    zklion-solo-prover [OPTIONS] --proxy <PROXY> --address <ADDRESS>

OPTIONS:
        --address <ADDRESS>            //你的aleo錢包地址
    -h, --help                         //打印幫助信息
        --proxy <PROXY>                //礦池連接地址、wss://aleo.zklion.com:3666
        --rest <REST>                  //本地監聽端口、默認0.0.0.0:9988
    -v, --version                      //程序版本
        --worker-name <WORKER_NAME>    //輸入你的礦機名稱
```

## 5、示例 

```shell
#下載後首先添加可執行權限
chmod +x zklion-pool-prover
#礦池程序啟動示例
./zklion-pool-prover --account test01 --pool wss://aleo.zklion.com:3777 --worker-name 192-168-100-101

#solo程序啟動示例
./zklion-solo-prover --address aleo1308gq2pfn0y3hgm722wysx4ks8szxsxaxsdnjnabdy --proxy wss://aleo.zklion.com:3666 --worker-name x99-01
```

## 6、後臺運行挖礦程序
```shell
nohup ./zklion-pool-prover --account test01 --pool wss://aleo.zklion.com:3777 --worker-name 192-168-100-101 &> /root/zklion-pool-prover.log &
```

檢查zklion-pool-prover.log日誌、顯示如下信息，則說明程序運行正常
<img width="847" alt="image" src="https://github.com/chihua2023/ZKLion/assets/137146992/cfaa57cc-f719-4d50-b214-9177db560bb0">

