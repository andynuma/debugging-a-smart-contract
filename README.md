
## 基本のデバック方法（コマンド雑記）
1. `truffle console`
1. `truffle(develop)> migrate`
1. `truffle(develop)> SimpleStorage.deployed().then(function(instance){return instance.get.call();}).then(function(value){return value.toNumber()});`  
toNumber()をつけないと，BigNumberが表示されるので注意
solidityでは，uintで定義された変数は0が設定される.

1. `truffle(develop)> SimpleStorage.deployed().then(function(instance){return instance.set(4);});`

1. `truffle(develop)> SimpleStorage.deployed().then(function(instance){return instance.get.call();}).then(function(value){return value.toNumber()});`
1. `4`

## トランザクションデバック
端末を２つ使用,
片方の端末で`truffle develop --log`   
もう片方で`関数呼び出し`，これでlogを取っている方にトランザクションハッシュがでる.  
トランザクションID= txの値

![2018-09-05 16 33 52](https://user-images.githubusercontent.com/29624403/45077931-8a7ca480-b129-11e8-9260-40747136f8de.png)


`truffle(develop)>debug トランザクションID`，トランザクションのデバックのモードに入る.  
使い方  
- Enterかnで次のステップに進む
- qで終了

