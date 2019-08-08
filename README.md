# eth dapp开发

## metamask钱包

我用的是chrome,在扩展程序里查找下metamask进行安装


## remix 环境
打开https://remix.ethereum.org  它是网页编辑工具

## hello world 小例子

### 1 可以参照下 https://blog.csdn.net/qq_27317475/article/details/80894593

```javascript

pragma solidity ^0.4.24;
contract HelloWorld{
    function say() public pure returns(string){
        return "Hello Wrold";
    }
}

```

### 2 在用remix 的Deploy过程中，需要metamask进行确认
    我搭建的是私链，而且设置了chainId,会报 error: Invalid sender的错误，解决可以看下 https://blog.csdn.net/zhujie_666/article/details/88818160 如何查chainId它没说，可以查看下创建私链的genesis.json 文件,我的chainId是123。

### 3 测试智能合约　
    
    attach到私链，或者自己写下 js 测试程序，我是attach到私链的
    geth attach http://127.0.0.1:8545

```javascript

    var abi=[{"constant": true,"inputs": [],"name": "say","outputs": [{"name": "","type": "string"}],"payable": false,"stateMutability": "pure","type": "function"}]

    var contractAddress = "0x740DFC102F2497E0fbe26E67Dfc21004201C2b53"

    var contract = eth.contract(abi).at(contractAddress);

    contract.say()
    //"Hello Wrold"
```
