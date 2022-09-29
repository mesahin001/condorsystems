Condor System ( \@condorSystems ) 3. Görevi icin sunlari yapmamiz
gerekiyor:

To complete this task you have to:

➡️ Visit: https://speedrunethereum.com/

➡️ Complete: 🚩 Challenge 0: 🎟 Simple NFT Example
(https://speedrunethereum.com/challenge/simple-nft-example)

➡️ Every task has its own Telegram support channel.

➡️ Once you successfully submit your build, send the link to the build
here.

Bu görev icin windows 10 yada 11 altinda calisan Ubuntu sistemini
kullanacagiz.

Gerekli paketler: git, npm, yarn, node

Ilk önce varsa nodejs i kaldiriyoruz, bize lazim olan nodejs version 16

```bash
root@vmd97563:\~# sudo apt remove nodejs
```

Nodejs 16 kurmak icin su adimlari izliyoruz:

```bash
curl -s https://deb.nodesource.com/setup_16.x \| sudo bash
```

bu sekilde bir ekran cikacak:
![image](https://user-images.githubusercontent.com/62426828/193068129-614fe613-5bca-43c5-a7d4-8a7d4f638a81.png)

bu komutla kurulum yapiyoruz:

```bash
sudo apt install nodejs -y
```

kurduktan sonra versiyon kontrolü

```bash
node -v
v16.17.1
```

Daha sonra gerekli paketleri kuruyoruz:

```bash
sudo apt-get install git

sudo npm i -g yarn
```

Install:

```bash
cd 
```
yazip entere basiyoruz

Surdaki repositoriyi klonluyoruz:

```bash
git clone https://github.com/scaffold-eth/scaffold-eth-challenges.git challenge-0-simple-nft
```

![image](https://user-images.githubusercontent.com/62426828/193068307-42b096aa-f428-4921-8586-d38057b68587.png)

Daha sonra 2 tane daha putty penceresi aciyoruz, ekranin üstünde farenin
sag tusuna tiklayip ayni baglanti icinde yeni pencereler aciyoruz,
toplam 3 tane olacak:

![image](https://user-images.githubusercontent.com/62426828/193068369-0b3c306c-d813-45af-adf3-b562e7c450fa.png)

Ilk pencerede su komutlari calistiriyoruz:

```bash
cd challenge-0-simple-nft

git checkout challenge-0-simple-nft

yarn install

yarn chain
```

ekran bu sekilde kalacak sorun yok:\
![image](https://user-images.githubusercontent.com/62426828/193068494-b5fad8a0-0032-448d-9c3d-7355fac21ea3.png)

Ikinci pencerede su komutlari calistiriyoruz:

```bash
cd challenge-0-simple-nft

yarn start
```

bu sekilde bir ekranda kalacak:\
![image](https://user-images.githubusercontent.com/62426828/193068554-1244020b-6bbf-4ce8-8f24-3942addcc2e4.png)

Son olarak ücüncü pencerede bu komutlari calistiriyoruz:

```bash
cd challenge-0-simple-nft

yarn deploy
```

Bir internet browserden eger acilmadiysa bu sayfayi aciyoruz:\
\
<http://localhost:3000/>

Bu sekilde bir ekran gelecek:

![image](https://user-images.githubusercontent.com/62426828/193068610-6c0a2751-b06b-452b-8b20-54241d82f555.png)

Ilk adimlari basardiysak devam ediyoruz.

**Checkpoint 1 Gas & Cüzdan ayarlama:**

Bu adimda kullanmak icin bize biraz token lazim onu da sayfadaki faucet
tusuna basarak aliyoruz:

![image](https://user-images.githubusercontent.com/62426828/193068682-f9a47383-0a1d-431c-8dce-290ec17b57d4.png)

Daha önceden connect tusuna basip mm cüzdan bagladiysaniz baglantiyi
kesin öncelikle.

Burdaki kullanilan adresler gecici ve sistemi yeniden baslattiginizda
kaybolacaklar o yüzden disardan bu adreslere degeri olan tokenlerden
yollamayin.

Ikinci olarak faucet tek seferlik kullanildigi icin, eger tokenler
yeterli gelmezse diye browserden yeni bir gizli sekme acip ayni adresi
(<http://localhost:3000/>) giriyoruz. Orda da görüldügü gibi yeni cüzdan
adresi ve faucet var. Burdan alacagimiz tokenleri ilk actigimiz cüzdan
adresine yolluyoruz.

Bunun icin ilk önce ana sayfadaki cüzdan adresini kopyaliyoruz ( mesela
0xc7cE nin yanindaki kopyala ikonuna tiklayip hafizaya aliyoruz.) Daha
sonrada gizli sekmedeki cüzdan ikonuna tiklayip aciyoruz.

![image](https://user-images.githubusercontent.com/62426828/193068736-72657d61-153e-46e2-ba49-b20af3faef09.png)

Bu sekilde gerekli yerleri doldurup tokenleri yolluyoruz. Bu islemi
birkac kez yapabilirsiniz. Gizli sekme her yeni acildiginda farkli bir
adres ve faucet verecek. Ana cüzdana bakinca tokenlerin geldigini
göreceksiniz.

**Checkpoint 2 Mintleme:**

Burda sayfadaki "Mint NFT" yazan yere tiklayarak birkac tane nft
mintliyoruz.

![image](https://user-images.githubusercontent.com/62426828/193068788-92ea029c-5aaf-4cd1-a745-4088f4555977.png)

Yeni bir gizli sekme acip ordan bir tane nft aliyoruz ve bunu ana
cüzdana yolluyoruz.

![image](https://user-images.githubusercontent.com/62426828/193068874-451b761d-5ef3-40da-90fd-0cca6ab6ca92.png)

**Checkpoint 3 Deploy:**

Bu asamada kodlarda bazi degisikler yapacagiz ve cüzdanimizla bu web
sayfasina baglanacagiz.

```bash
nano packages/hardhat/hardhat.config.js
```
diyerek bu dosyayi aciyoruz.


![image](https://user-images.githubusercontent.com/62426828/193068964-a1a8eda0-550d-42e1-a4c1-527360af2578.png)

Burdaki ```bash defaultNetwork = "localhost" ``` olan kismi "goerli" olarak
degistiriyoruz.

![image](https://user-images.githubusercontent.com/62426828/193069068-ac97d342-c416-4ca5-a6f4-5190ebc3a5de.png)

Bu sekilde gözükmesi lazim.

Daha sonra Ctrl+O ve Ctrl+X tusuna basarak kaydedip cikiyoruz.

Su komutla yeni bir adres olusturuyoruz:

```bash
yarn generate
```

![image](https://user-images.githubusercontent.com/62426828/193069155-60a8e324-a12d-4045-b806-af5390ea160b.png)

Bu adresi bir yere kaydedin, metamsktan buraya token yollayacagiz.

```bash
yarn account
```

yazarak bu cüzdan hakkinda bilgileri ve hesap durumunu görüntülüyoruz.

![image](https://user-images.githubusercontent.com/62426828/193069232-da3c4192-2d80-4f74-88ea-2726368bcff2.png)

Goerli tesnet faucetten biraz token alip bu adrese yolluyoruz.

![image](https://user-images.githubusercontent.com/62426828/193069301-8c45d0d6-8ec0-4800-89ad-5dc4ea863d98.png)

Daha sonra tekrardan ```bash yarn account ``` komutu ile cüzdanda gelip gelmedigini
görebiliriz.

![image](https://user-images.githubusercontent.com/62426828/193069351-385f3533-bfbb-4c72-ab03-6d7d6545db70.png)

Token geldikten sonra 3. Acik olan putty penceresinden su komutu
calistiriyoruz.

```bash
yarn deploy
```

Bu ekranda bazi tx islemleri görmemiz lazim:

![image](https://user-images.githubusercontent.com/62426828/193069390-ec9d8bc2-6706-4634-9e85-0180dfc19482.png)

**Checkpoint 4 Gönderim:**

Bu asamada web sayfamizi hazirlayip internette bir yere yükleyecegiz.
Ilk önce Sayfanin standart agini degistiriyoruz:

```bash
nano packages/react-app/src/App.jsx
```

Burda asagi dogru inip bu satiri buluyoruz: "const targetNetwork =
NETWORKS.localhost; // \<\-\-\-\-\-\-- select your target frontend
network (localhos\>" Asagi Yukari 56. satirda olacak.

![image](https://user-images.githubusercontent.com/62426828/193069460-36028887-1870-4cb6-8533-a49639390ca3.png)

goerli olarak degistirip, kaydedip cikiyoruz.

![image](https://user-images.githubusercontent.com/62426828/193069514-944c7c19-c35b-4e85-bf71-f95e085eddba.png)

```bash 
yarn deploy 
``` 
yapiyoruz ve daha sonra <http://localhost:3000/> sayfasini
yeniden yüklüyoruz. Bu asamada goerli görmemiz lazim:

![image](https://user-images.githubusercontent.com/62426828/193069576-d56e033f-70da-43a7-8969-30ba29f52380.png)

Connect tusuna basip Mmask ile baglaniyoruz ve MM yi goerli tesnet agina
aliyoruz.

Orda bakiyeyi görebilmemiz lazim.

![image](https://user-images.githubusercontent.com/62426828/193069621-c26b38c4-9ece-4b82-92be-95d0e37a5668.png)

Sayfadan Mint NFT yapiyoruz ve cüzdan onayi vererek bir tane nft
aliyoruz.

![image](https://user-images.githubusercontent.com/62426828/193069669-e84abc68-11e1-493c-af90-57ba7f9380a7.png)

Burda aldigimiz nft artik bizim goerli cuzdana gelmis oldu. Daha
öncekiler gecici cüzdandaydi ve silinecekler bu nft kalacaktir.

```bash
yarn build
```

komutu ile sayfayi hazirliyoruz. Islem bittikten sonra

```bash
yarn surge
```

komutu ile sayfamizi internete yüklüyoruz.

![image](https://user-images.githubusercontent.com/62426828/193069718-2c98d997-a684-4805-bf1e-9da2d010ba19.png)

Burda size domain icin bir öneri sunuyor, isterseniz degistirip
istediginiz bir isim verebilirsiniz. Surge üyeliginiz yoksa hemen bir
tane olusturup daha sonra gelen emaile onay vermeniz lazim. Daha sonrasi
otomatik isliyor.

Hata vermeden yüklediyse

```bash
yarn test
```

ile sistemi test ediyoruz

![image](https://user-images.githubusercontent.com/62426828/193069809-045cfaa5-100e-48e4-8d8f-66b2283a2b24.png)

Ayrica domain kisminda verilen adresi web tarayicida acip bakiyoruz.

![image](https://user-images.githubusercontent.com/62426828/193069842-55ee8e0e-774f-46b1-9107-a604ac2aafca.png)

**Checkpoint 5 Kontrat dogrulama:**

```bash
nano packages/hardhat/package.json
  ```
dosyasini acip kendimizin etherscan keyini koyuyoruz.

![image](https://user-images.githubusercontent.com/62426828/193069887-42f23b78-4d8f-4aa3-8bf6-2c656995b1ff.png)

Key almak icin <https://etherscan.io/myapikey> bu sayfaya gidip login
oluyoruz ve ordan adresimizi aliyoruz.

Daha sonra su komutla islemi dogruluyoruz:

```bash
yarn verify --network goerli
```

![image](https://user-images.githubusercontent.com/62426828/193069980-767e9773-febf-40fe-9c80-ee7801d164c8.png)

Burda zaten dogrulanmis diyor, normaldir. Cikan adresi goerli etherscan
da kontrol ediyoruz.

![image](https://user-images.githubusercontent.com/62426828/193070048-b9a61b59-e713-4c23-a472-4123ac8a79f5.png)

Daha sonra\
<https://speedrunethereum.com/challenge/simple-nft-example>

Sayfasina girip alttaki "Submit challenge" tusuna tikliyoruz.

Orda istenen bilgileri giriyoruz. Surge sayfa adresi ve az önceki goerli
etherscan adresini verecegiz.

![image](https://user-images.githubusercontent.com/62426828/193070160-410ccacd-6f78-4309-bc92-696ab0eb1a45.png)

Submit tusuna basiyoruz, kontrolu bekliyoruz. Sayfada üyelik yoksa
cüzdanimizla üye oluyoruz ve submit sonrasinda cüzdanla onay veriyoruz.

Islem tamamsa sayfanin sag üst tarafinda kendi cüzdanimiza tiklayip
sayfamiza giriyoruz orda status accepted olmasi lazim.

![image](https://user-images.githubusercontent.com/62426828/193070193-619a5f79-4ff4-4004-b13d-ebb70a047bd5.png)

Bu islemden sonra telegram kanalina giriyoruz:

<https://t.me/+Y2vqXZZ_pEFhMGMx>

Daha sonra örnekteki gibi gerekli bilgileri toplayip discord kanalina
bildiriyoruz:

![](media/image31.png){width="6.268055555555556in"
height="5.850694444444445in"}
