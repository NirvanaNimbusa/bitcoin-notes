# bitcoin-notes 比特币源码简单分析

比特币最大的问题是挖矿,算力的集中,与其去中心化的理想背道而驰.

这是对现实的折中,也使其有了被主流接受的可能.

如果去中心化最终成为主流,比特币将因此被淘汰.

<a target="_blank" href="http://shang.qq.com/wpa/qunwpa?idkey=0fef5aa161c5074030c3f2e99c6d564a4c68d469f187c08530d270e15714e7c2"><img border="0" src="https://pub.idqqimg.com/wpa/images/group.png" alt="zaobi.org官方群" title="zaobi.org官方群">130313918</a>

主要是对源码的注解,也有一些总结性的东西.***仅供参考,欢迎反馈***

源码的注解重点是头文件(头文件明白了,cpp文件基本也没问题).

目前计划只包含核心的文件,不含qt界面的代码.

本项目主要针对**山寨币开发者**，各路大牛请绕道

### 文件目录

<table>
  <tr>
    <th width=33%, bgcolor=gray >文件名</th>
    <th width=10%, bgcolor=gray>状态</th>
  </tr>
  <tr>
    <td> addrman.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> alert.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> allocators.h </td>
    <td bgcolor=OrangeRed > × </td>
  </tr>
  <tr>
    <td> base58.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> bignum.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> bitcoinrpc.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> bloom.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> checkpoints.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> checkqueue.h </td>
    <td bgcolor=yellow> ... </td>
  </tr>
  <tr>
    <td> clientversion.h </td>
    <td bgcolor=yellow> ... </td>
  </tr>
    <tr>
    <td> compat.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> crypter.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> db.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> hash.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> init.h </td>
    <td bgcolor=yellow> ... </td>
  </tr>
    <tr>
      <td> key.h </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
    <tr>
      <td> keystore.h </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
    <tr>
      <td> leveldb.h </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
    <tr>
      <td> limitedmap.h </td>
      <td bgcolor=SpringGreen> √ </td>
    </tr>
  <tr>
    <td> main.h </td>
    <td bgcolor=OrangeRed> × </td>
  </tr>
  <tr>
    <td> mruset.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> netbase.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> net.h </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> protocol.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> script.h </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>  
  <tr>
      <td> ui_interface.h </td>
      <td bgcolor=OrangeRed > X </td>
    </tr>
  <tr>
    <td> serialize.h </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> sync.h </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> threadsafety.h </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> txdb.h </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> uint256.h </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> util.h </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
  <tr>
    <td> version.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> walletdb.h </td>
    <td bgcolor=SpringGreen> √ </td>
  </tr>
  <tr>
    <td> wallet.h </td>
    <td bgcolor=OrangeRed > X </td>
  </tr>
</table>

### 前置知识

* C++
* 密码学相关知识


### 欢迎Issue、PR

### 版本

源码的版本是0.8;

最新的比特币源码结构和0.8版本有所差异,但是核心内容是不变的.

0.8版本和大部分的山寨币的源码结构也是一样的。


### 目标
使阅读比特币源码,了解比特币原理与实现 **更方便,更快捷**.
