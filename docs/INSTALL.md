## Install Guideline

1. Clone our repository and stay on the dev branch

```
git clone https://github.com/AElfProject/AElf.git aelf
```

2. Go into the aelf directory

```
cd aelf
```

3. Build AElf solution

```
dotnet build --configuration Release
```

If this successfully completes, you should see `0 Error(s)`. You will see some warnings but that’s normal and you can safely ignore them.
  
You will see the image after successful build.  
![https://i.imgur.com/prBN16D.jpg](https://i.imgur.com/prBN16D.jpg)

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
