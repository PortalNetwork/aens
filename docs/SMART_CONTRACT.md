## Deploy Smart Contract

1. Load smart contract ABI
```
load_contract_abi
``` 

2. Unlock account
```
account unlock <address> notimeout
```
![](https://user-images.githubusercontent.com/11625554/45281335-1d428800-b50a-11e8-80c8-e35cb0c73075.png)

3. To get nonce of account 
```
get_increment <address>
```
![](https://user-images.githubusercontent.com/11625554/45281372-377c6600-b50a-11e8-8d61-a68042548f1e.png)

4. Deploy smart contract and get result
```
deploy_contract <contract_name> <account_nonce> <address>
``` 
![](https://user-images.githubusercontent.com/11625554/45281465-7ca09800-b50a-11e8-869f-37b9e1781a28.png)

5. Get transaction result
```
get_tx_result <tx_id>
```
![](https://user-images.githubusercontent.com/11625554/45281502-99d56680-b50a-11e8-9b62-a8409744b68b.png)

6. Load contract ABI
```
load_contract_abi <contract_address>
```
![](https://user-images.githubusercontent.com/11625554/45281526-ae196380-b50a-11e8-862c-894199d31a90.png)

7. Invoke smart contract's method
```
broadcast_tx '{"from":"0x0475491dae162dae5547e5ce09226470e6be","to":"0x3b793892110f80845b2f2e66ca4c02e6117b","method":"Greet","incr":"18446744073709551615","params":[]}'
```
![](https://user-images.githubusercontent.com/11625554/45281611-e9b42d80-b50a-11e8-9b43-caa4341a94d8.png)
