# SERO挖矿教程

本文主要说明如何从二进制包安装SERO并且用之挖矿的过程。要获得更多的信息可以访问我们的[产品技术WIKI](https://wiki.sero.cash)。



# 奖励计划 (2020年2月29日后实际最大总量为6.5亿)

SERO一共发行10亿数量的SERO币 ，除了其中10%作为早期捐赠的报酬之外，80%由矿工挖掘出来作为社区节点贡献的奖励，10%作为团队份额与社区贡献奖励同比释放。也就是说，有8亿的SERO币作为SERO矿工挖矿的奖励。挖矿奖励遵循下面的规则：

* ### 奖励计划在101年内发放完毕，每四年奖励减半，第一次减半在2020年5月前后。

   > **由于初期SERO社区网络还比较弱小，因此我们采取这样的策略：**
   >
   > * 为了确保难度小的时候具备公平性，我们根据挖掘难度从大到小设立5个阶段。
   >  * 在前4个阶段，每块的奖励会小于目标值，但会随着难度增加而增加。
   >  * 达到第5个阶段后，按照满额发放奖励。
   >
   > 具体的规则可以参考 [SIP1：奖励改进计划](?file=News/Important/sip1-mine-reward-plan)

* ### 从BetaNet-Release版本开始以POW共识挖矿，届时其上的SERO代币会映1:1射到MainNet，而在MainNet上节点维护奖励的发放将遵循SE-Random共识。

   > **BetaNet的版本**
   >    * RC版本：BetaNet的发布候选版本，距离正式的BetaNet还需要做几个版本的调整，创建的账本会在此RC版本测试结束后被清除掉。
   >
   >    * Release版本：BetaNet的正式版，会在2019年1月7日24时被部署，后续版本更新的时候不会清除账本。
   >
   >      `原定2018年12月31日，由于圣诞和元旦的影响，我们决定延后一周`

* ### 为了确保网络初期的安全，在BetaNet期间挖矿需要向SERO团队申请许可证。
  > **申请流程**
  > * 先运行[全节点服务(gero)](http://sero.cash)或者[客户端钱包(wallet)](http://sero.cash)
  > * 导入或者创建挖矿用户，并获取该用户的公钥地址。
  > * 加入SERO在微信/Discord/Telegram/Gitter上的miner社区
  >     * **gitter：** <https://gitter.im/sero-cash/miner?utm_source=share-link&utm_medium=link&utm_campaign=share-link>。
  >     * **微信：** SERO9413
  >     * **Discord：**  <https://discord.gg/n5HVxE>
  >     * **Telegram：** <https://t.me/SeroOfficial>
  >   `这一步可以首先进行，这样你在使用SERO过程中遇到问题，可以在社区中提出。`
  > * 发邮件给 [license@sero.vip](mailto:license@sero.vip) ，说明你的情况，并附上你的公钥地址。
  > * SERO团队会在48小时内生成公钥地址对应的许可证，并回复你的邮件。
  >   <br>

 >**BetaNet-Releaes版本发布后，会对每个申请做严格的审核。**

# 挖矿步骤

## 1. 安装SERO

> **有两种选择可以让你在自己的机器上安装好SERO**
>
> * 一种是安装`全节点服务程序(gero)`，并通过其提供的`命令行控制台`操作`gero`。
> * 另一种是直接安装`客户端钱包(wallet)`，通过GUI界面进行操作。
>
> **`注意：本文只说明如何从SERO发布的"二进制程序包"安装gero服务`**
>
> **如果想要从`源码`安装`gero`，可以参考**
>
> * [《SERO轻松入门 * 从源码开始——基于CentOS7》](https://wiki.sero.cash/zh/index.html?file=Start/from-the-sourcecode-base-on-centos7)
>
> **如果想要安装`Wallet`，可以参考**
>
> * [《SERO教程 * 客户端钱包使用手册》](https://wiki.sero.cash/zh/index.html?file=Tutorial/manual-of-wallet)



* ### **通过github下载`gero`最新版本的二进制包。**

    读者可以访问链接[https://github.com/sero-cash/go-sero/releases](https://github.com/sero-cash/go-sero/releases)下载最新的二进制包。

    ![image.png](http://sero-media.s3-website-ap-southeast-1.amazonaws.com/images/201904/277023-b731e437b567c179.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/600)

    > **在Assets栏目，可以看到不同系统环境对应的二进制包**
    > * `gero-[VERSION]-darwin-amd64.tar.gz` 对应64位的`MacOS`系统
    > * `gero-[VERSION]-linux-amd64-v3.tar.gz` 对应64位`linux3`内核系统
    > * `gero-[VERSION]-linux-amd64-v4.tar.gz` 对应64位`linux4`内核系统
    > * `gero-v0.3.1-beta.rc.5-windows-amd64.zip` 对应64位`WIN7/WIN8/WIN10`系统

    > **在BetaNet-RC5发布时**
    > * 最新的`Ubuntu & CentOS7`发行版默认是`Linux3`内核
    > * 最新的`Fedora`发行版默认是`Linux4`内核

    > **`注意：本文是基于CentOS系统，其他系统在二进制包的使用方面是类似的。`**

    下面下载CentOS7对应的二进制包：

    ```sh
    $ pwd
    /root
    ```
    
    `注意：请到github release获取最新的下载链接。` [https://github.com/sero-cash/go-sero/releases](https://github.com/sero-cash/go-sero/releases)

    ```sh
    $ wget https://github.com/sero-cash/go-sero/releases/download/v0.3.1-beta.rc.5/gero-v0.3.1-beta.rc.5-linux-amd64-v3.tar.gz
    ```

    ```sh
    $ ls
    gero-v0.3.1-beta.rc.5-linux-amd64-v3.tar.gz
    ```

    ```sh
    $ tar -xvf gero-v0.3.1-beta.rc.5-linux-amd64-v3.tar.gz
    $ ls
    geropkg gero-v0.3.1-beta.rc.5-linux-amd64-v3.tar.gz
    ```

    `geropkg`就是解压出来含有二进制程序的目录，我们看看里面有什么：

    ```sh
    $ ls geropkg
    attach.sh  bin  clean.sh  czero  startup.sh  stop.sh
    ```

    > **各个文件说明：**
    >
    > * `czero`里面是SERO的零知识证明库
    > * `bin`里面有SERO的主程序gero
    > * `startup.sh`是服务启动脚本
    > * `stop.sh`是停止服务脚本
    > * `attach.sh`是控制台启动脚本
    > * `clean.sh`是清除账本数据脚本
    >     * **注意：**执行后，不会清除keystore目录，但是会重新同步账本数据。


* ### **确定`datadir`**

    > * SERO第一个重要目录是`datadir`，它里面放置同步的账本数据
    > * 另外一个重要的目录是`keystore`，它里面放置加密后的`账户文件`以及挖矿用的`license文件`，就像下面这样：
    >
    >   ![image.png](http://sero-media.s3-website-ap-southeast-1.amazonaws.com/images/201904/277023-d8801c3d87c486e5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    为了在今后升级`geropkg`的时候不会影响已经同步的数据，我们将数据目录独立出来，比如：

    ```sh
    $ mkdir .sero-data
    $ ls -a
    . .. .sero-data geropkg gero-v0.3.1-beta.rc.5-linux-amd64-v3.tar.gz
    ```


* ### **启动`gero`**

    执行`startup.sh`来启动`gero`

    > **`startup.sh`的启动参数**
    > ```sh
    > ./startup.sh [--datadir DATA_DIR] [--keystore KEYSTORE_DIR]
    > ```
    > 其中`DATA_DIR`用来指定`datadir`位置，`KEYSTORE_DIR`用来指定`keystore`目录的位置。
    >
    > **这个脚本遵循下面的规则**
    >
    > * 如果不指定`keystore`，`gero`会将它默认创建在`datadir`下。
    > * 如果不指定`datadir`，`gero`会默认将它创建在当前目录下。

    **我们进入`geropkg`目录，并确保它下面有log文件目录**

    ```sh
    $ cd geropkg
    $ mkdir log
    $ ls
    attach.sh  bin  clean.sh  czero  log  startup.sh  stop.sh
    ```
    **然后执行`startup.sh`脚本**

    ```sh
    $ startup.sh --datadir "../.sero-data"
    /root/geropkg/czero/lib/
    /root/geropkg/bin/gero --datadir=../[datadir] --port 60602
    ```

    **我们可以查看`log`确定是`gero`是否运行正常**

    ```sh
    $ tail -f log/gero.log
    ```

    **你会看到类似于下面的文本**

    ![image.png](http://sero-media.s3-website-ap-southeast-1.amazonaws.com/images/201904/277023-8397a48ee35318a9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/600)

    只要看到`IPC endpoint opened`这句话，就说明启动成功了。

## 2. 创建账户

* ### **启动控制台**
    通过执行`attach.sh`来启动控制台
    > **`attach.sh`的启动参数**
    > ```sh
    > ./attach.sh [DATA_DIR]
    > ```
    > 其中`DATA_DIR`用来指定启动gero时`datadir`的位置。如果不指定，gero会在默认的位置寻找`datadir`。

    ```sh
    $./attach.sh "../sero-data"
    ```

    如果看到类似下面的控制台界面，控制台启动就成功了。

    ![image.png](http://sero-media.s3-website-ap-southeast-1.amazonaws.com/images/201904/277023-9511643359456b35.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/600)


* ### **创建账户**
    现在我们可以开始输入命令创建账户：

    **`注意：gero控制台支持按[TAB建]补全命令`**

    ```javascript
    > personal.newAccount("123456")
    "4GYNYzECNovCniXiYi1VV58vk97U1vWF7KfSRJCTFVv95kbdVhWYX4kjkcYBpw2zzfDZfaeEqB8YhANGDGFkG3SP"
    ```
    `newAccount` 函数输入值你设定的密码，请记好该密码，丢失后将失去账户的控制权，且无法寻回。返回值是被创建账户的公钥地址`PK`。

    > `PK` 可以安全的交给另一方作为转账接收地址

    如果要查看本节点创建的账户，可以调用下面的指令获取所有账户的公钥：

    ```javascript
    > sero.accounts
    ["4GYNYzECNovCniXiYi1VV58vk97U1vWF7KfSRJCTFVv95kbdVhWYX4kjkcYBpw2zzfDZfaeEqB8YhANGDGFkG3SP"]
    ```

    为了安全，账户创建之后，5分钟不使用会被锁定，如果出现账户被锁定的提示，需要输入密码解锁账户。

    ```javascript
    > sero.sendTransaction(...)
    Error: authentication needed: password or unlock
    
    > personal.unlockAccount(sero.accounts[0],"123456")
    true
    ```

    > 注意：挖矿所得的奖励默认会进入当前节点第一个创建的账户中，也就是 `sero.accounts[0]` 代表的账户中。

    退出控制台的命令是：

    ```javascript
    > exit
    ```

<br/>

## 3. MainNet-V1.0.1 版之后已经不再需要挖矿许可证了。



## 4. 开始挖矿

现在就可以开始愉快的挖矿了，让我们再次进入控制台，然后开启挖矿：

```javascript
> miner.start()
```

停止挖矿的指令：

```javascript
> miner.stop()
```

查看是否正在挖矿的指令：
```javascript
> sero.mining
true
```
> 返回`true`代表正在挖矿

查看当前区块高度：

```javascript
> sero.blockNumber
32165
```

查看你是否挖到SERO：

```javascript
> sero.getBalance(sero.accounts[0])
{
  tkn: {
    SERO: 2.03085359120665e+22
  }
}
```

上面的单位是`Ta` (1 SERO = $10^{18}$ Ta)，转为`SERO`单位可以调用：

```javascript
> web3.fromTa(2.03085359120665e+22)
"20308.5359120665"
```

<br/>

## 5. 最后

基本的从二进制包安装开始的挖矿过程就到这儿了，如果想要详细的了解`SERO`的原理或者详细的操作教程,可以访问我们的[官网](https://sero.cash)下载白皮书，或者访问我们的[产品技术WIKI](https://wiki.sero.cacsh)。
