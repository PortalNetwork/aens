# Docker Guideline

## Aelf CLI
1. Clone our repository and stay on the dev branch

```
git clone https://github.com/AElfProject/AElf.git aelf
```

2. Go into the aelf directory

```
cd aelf
```

3. Build AElf with docker

```
cd script
sh aelf-cli.sh <PORT>
```

After success build, it will the aelf console
```
Yungde-MacBook-Pro-2:scripts phyrex$ sh aelf-cli.sh 6900
Check port parameter ...
  >> Use input port value: 6900
Sync time info ...
30 Aug 16:00:53 ntpdate[56672]: adjust time server 80.127.119.186 offset 0.006779 sec
Pull latest aelf/node image ...
dev-v0.1.1: Pulling from aelf/node
Digest: sha256:5bf659965c9be600ced0566ea068269273addf2305c9d50a7617563893430080
Status: Image is up to date for aelf/node:dev-v0.1.1
Delete container if exist ...
  >> Stop container ...
aelf-node-cli
  >> Delete existed container ...
aelf-node-cli
Start cli container ...
------------------------------------------------
Welcome to AElf!
------------------------------------------------
Use "get_commands" to print available commands
Usage: command_name <param1> <param2> ...
To Quit: Type 'Quit'


aelf>
```

4. Create new account. The account will be a private key public key pair stored in `<root>/keys/` folder.

```
aelf> account new
password:
Account address: 0x046a115ab06a88e5bdfb86ac2a29891b0d32
aelf> account list
account #0 : 0x046a115ab06a88e5bdfb86ac2a29891b0d32
aelf> account unlock 0x046a115ab06a88e5bdfb86ac2a29891b0d32 notimeout
password:
account successfully unlocked!
```

## Aelf node

```
sudo docker run -it -v /Users/phyrex/Documents/aelf:/app/aelf aelf/node:latest dotnet AElf.Launcher/AElf.Launcher.csproj -t keyvalue -m true --nodeaccount 0x046a115ab06a88e5bdfb86ac2a29891b0d32 --port 6800 --rpc.port 6900 -g true

sudo docker run -it -p 6800:6800 -v /Users/phyrex/Documents/aelf:/app/aelf -v /Users/phyrex/Documents/aelf/ChainInfo.json:/app/ChainInfo.json --name aelf-node-launcher aelf/node:dev-v0.1.1 dotnet AElf.Launcher.dll -t keyvalue --rpc.port 6900
"aelf-node.sh"
```

## FAQ

### Error on mount '/home/aelf'

Problem:
```
Yungde-MacBook-Pro-2:scripts phyrex$ sh aelf-cli.sh
Check port parameter ...
  >> Use default port value: 6900
Sync time info ...
Password:
30 Aug 15:57:29 ntpdate[55995]: adjust time server 80.127.119.186 offset 0.010058 sec
Pull latest aelf/node image ...
dev-v0.1.1: Pulling from aelf/node
Digest: sha256:5bf659965c9be600ced0566ea068269273addf2305c9d50a7617563893430080
Status: Image is up to date for aelf/node:dev-v0.1.1
Delete container if exist ...
  >> Stop container ...
aelf-node-cli
  >> Delete existed container ...
aelf-node-cli
Start cli container ...
docker: Error response from daemon: error while creating mount source path '/home/aelf': mkdir /home/aelf: operation not supported.
```

Solution:  
Change the `/home/aelf` under `aelf-cli.sh` to `/Users/<root>/aelf`
