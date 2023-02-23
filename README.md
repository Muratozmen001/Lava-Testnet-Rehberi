<h1 align="center">Lava-Testnet-Rehberi

### Lava Node testini kuruyoruz. Sağ üstten yıldızlayıp forklamayı unutmayalım. Sorularınız olursa: <a href="https://t.me/CoinHuntersTR/34102" target="_blank" rel="Coin Hunters TR" >Coin Hunters TR</a>

![lava-network-testnet-rehberi](https://user-images.githubusercontent.com/111747226/220886500-561d6199-3c6d-4af3-8a45-b003ac7768ba.png)

## Sistem gereksinimleri:
NODE TİPİ | CPU     | RAM      | SSD     |
| ------------- | ------------- | ------------- | -------- |
| Full | 4          | 8         | 100  |


## 1) Güncellemeleri Yapıyoruz.

```
sudo apt update && sudo apt upgrade -y
```
```
sudo apt install -y unzip logrotate git jq sed wget curl coreutils systemd
```
```
temp_folder=$(mktemp -d) && cd $temp_folder
```
## 2) Go Kurulumu Yapıyoruz

```
go_package_url="https://go.dev/dl/go1.18.linux-amd64.tar.gz"
```
```
go_package_file_name=${go_package_url##*\/}
```
> Go indiriyoruz.
```
wget -q $go_package_url
```
```
sudo tar -C /usr/local -xzf $go_package_file_name
```
```
echo "export PATH=\$PATH:/usr/local/go/bin" >>~/.profile
```
```source ~/.profile
```

## 3) Node Kurulumuna Geçiyoruz.

```
git clone https://github.com/lavanet/lava-config.git
```
```
cd lava-config/testnet-1
```
```
source setup_config/setup_config.sh
```

## 3) Node yapılandırmalarına devam ediyoruz.
  
```
echo "Lava config file path: $lava_config_folder"
```
```
mkdir -p $lavad_home_folder
```
```
mkdir -p $lava_config_folder
``` 
```
cp default_lavad_config_files/* $lava_config_folder
``` 

## 4) Genesis dosyasını indiriyoruz.
  
```
cp genesis_json/genesis.json $lava_config_folder/genesis.json
```
