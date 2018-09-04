# debugging-a-smart-contract
truffle公式サイトのdebugging-a-smart-contractやってみた

## デバック方法
1. `truffle console`
1. `truffle(develop)> migrate`
1. `truffle(develop)> SimpleStorage.deployed().then(function(instance){return instance.get.call();}).then(function(value){return value.toNumber()});`  
toNumber()をつけないと，BigNumberが表示されるので注意
solidityでは，uintで定義された変数は0が設定される.

1. `truffle(develop)> SimpleStorage.deployed().then(function(instance){return instance.set(4);});`

1. `truffle(develop)> SimpleStorage.deployed().then(function(instance){return instance.get.call();}).then(function(value){return value.toNumber()});`
1. `4`


