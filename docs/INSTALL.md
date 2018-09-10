## Install Guideline

# Setup AElf private testnet and interact with smart contract

1. Install [.Net Core](https://www.microsoft.com/net/download) 

2. Install protobuf via homebrew, [Link](https://github.com/AElfProject/AElf/issues/425)
```
$ brew install protobuf
$ brew link --overwrite protobuf
```

3. Download AElf project 
```
$ git clone https://github.com/AElfProject/AElf.git aelf
```

4. Configuration setting
```
$ mkdir /Users/<user>/.local/share/aelf/contracts
$ touch /Users/<user>/.local/share/aelf/config/miners.json
```
    
5. Edit the `miners.json`
```
{
    "producers":{
    "1": {
        "address": "<address1>"
    },
    "2": {
        "address": "<address2>"
    },
    "3": {
        "address": "<address3>"
    }
    }
}
```

6. Run the dotnet to build aelf
```
$ cd aelf
$ dotnet build --configuration Release
```

![](https://user-images.githubusercontent.com/11625554/45280997-05b6cf80-b509-11e8-86a8-6519d29a9b58.png)
  
It will run success when shows `0 Error(s)`

7. Run the `dll` file 
```
dotnet AElf.CLI/bin/Release/netcoreapp2.1/AElf.CLI.dll
```
![](https://user-images.githubusercontent.com/11625554/45281080-4c0c2e80-b509-11e8-9de7-6ca98d7e8196.png)

8. Aelf commands  
- Execute `account new` to create new account
- `account list` to print all accounts
    
![](https://user-images.githubusercontent.com/11625554/45281136-7b22a000-b509-11e8-9556-285682aa333e.png)

9. Copy your smart contract(the dll file) under 
`/Users/<user>/.local/share/aelf/contracts`

10. Launch private testnet 
```
$ dotnet run --no-build --project AElf.Launcher/AElf.Launcher.csproj --chain.new true --mine.enable true --dpos.generator true --node.peers 127.0.0.1 --node.port 6800 --node.account <address> --db.type inmemory -c Release --rpc.host 127.0.0.1 --rpc.port 1234
```
![](https://user-images.githubusercontent.com/11625554/45281224-c177ff00-b509-11e8-9485-603d21cb19a9.png)

11. Run `connect_chain`, and it will connect to the private testnet
![](https://user-images.githubusercontent.com/11625554/45281265-e40a1800-b509-11e8-824e-c0c3beaeeaa7.png)

## FAQ

### Protobuf error

#### Problem:
![https://i.imgur.com/c91k1cB.jpg](https://i.imgur.com/c91k1cB.jpg)

#### Solution:
On Mac OS, using brew install protocol buffer and overwrite the link of current one.
```
brew install protobuf
brew link --overwrite protobuf
```
