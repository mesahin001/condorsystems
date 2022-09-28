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
![](media/image1.png){width="6.268055555555556in" height="4.75in"}

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

![](media/image2.png){width="6.268055555555556in" height="0.75625in"}

Daha sonra 2 tane daha putty penceresi aciyoruz, ekranin üstünde farenin
sag tusuna tiklayip ayni baglanti icinde yeni pencereler aciyoruz,
toplam 3 tane olacak:

![](media/image3.png){width="6.268055555555556in"
height="4.855555555555555in"}

Ilk pencerede su komutlari calistiriyoruz:

cd challenge-0-simple-nft

git checkout challenge-0-simple-nft

yarn install

yarn chain

ekran bu sekilde kalacak sorun yok:\
![](media/image4.png){width="6.268055555555556in"
height="1.7569444444444444in"}

Ikinci pencerede su komutlari calistiriyoruz:

cd challenge-0-simple-nft

yarn start

bu sekilde bir ekranda kalacak:\
![](media/image5.png){width="6.268055555555556in"
height="1.2520833333333334in"}

Son olarak ücüncü pencerede bu komutlari calistiriyoruz:

cd challenge-0-simple-nft

yarn deploy

Bir internet browserden eger acilmadiysa bu sayfayi aciyoruz:\
\
<http://localhost:3000/>

Bu sekilde bir ekran gelecek:

![](media/image6.png){width="6.268055555555556in"
height="5.031944444444444in"}

Ilk adimlari basardiysak devam ediyoruz.

**Checkpoint 1 Gas & Cüzdan ayarlama:**

Bu adimda kullanmak icin bize biraz token lazim onu da sayfadaki faucet
tusuna basarak aliyoruz:

![](media/image7.png){width="3.979722222222222in"
height="1.4377001312335957in"}

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

![](media/image8.png){width="5.427841207349081in"
height="2.864983595800525in"}

Bu sekilde gerekli yerleri doldurup tokenleri yolluyoruz. Bu islemi
birkac kez yapabilirsiniz. Gizli sekme her yeni acildiginda farkli bir
adres ve faucet verecek. Ana cüzdana bakinca tokenlerin geldigini
göreceksiniz.

**Checkpoint 2 Mintleme:**

Burda sayfadaki "Mint NFT" yazan yere tiklayarak birkac tane nft
mintliyoruz.

![](media/image9.png){width="6.268055555555556in"
height="7.259027777777778in"}

Yeni bir gizli sekme acip ordan bir tane nft aliyoruz ve bunu ana
cüzdana yolluyoruz.

![](media/image10.png){width="6.268055555555556in"
height="2.8270833333333334in"}

**Checkpoint 3 Deploy:**

Bu asamada kodlarda bazi degisikler yapacagiz ve cüzdanimizla bu web
sayfasina baglanacagiz.

nano packages/hardhat/hardhat.config.js diyerek bu dosyayi aciyoruz.

![](media/image11.png){width="6.268055555555556in"
height="4.013194444444444in"}

Burdaki defaultNetwork = "localhost" olan kismi "goerli" olarak
degistiriyoruz.

![](media/image12.png){width="4.688153980752406in"
height="0.35421587926509185in"}

Bu sekilde gözükmesi lazim.

Daha sonra Ctrl+O ve Ctrl+X tusuna basarak kaydedip cikiyoruz.

Su komutla yeni bir adres olusturuyoruz:

yarn generate

![](media/image13.png){width="6.268055555555556in" height="1.1in"}

Bu adresi bir yere kaydedin, metamsktan buraya token yollayacagiz.

yarn account

yazarak bu cüzdan hakkinda bilgileri ve hesap durumunu görüntülüyoruz.

![](media/image14.png){width="6.268055555555556in"
height="2.9451388888888888in"}

Goerli tesnet faucetten biraz token alip bu adrese yolluyoruz.

![](media/image15.png){width="5.167387357830271in"
height="8.407423447069116in"}

Daha sonra tekrardan yarn account komutu ile cüzdanda gelip gelmedigini
görebiliriz.

![](media/image16.png){width="4.386029090113736in"
height="0.5938331146106737in"}

Token geldikten sonra 3. Acik olan putty penceresinden su komutu
calistiriyoruz.

yarn deploy

Bu ekranda bazi tx islemleri görmemiz lazim:

![](media/image17.png){width="6.268055555555556in"
height="1.3583333333333334in"}

**Checkpoint 4 Gönderim:**

Bu asamada web sayfamizi hazirlayip internette bir yere yükleyecegiz.
Ilk önce Sayfanin standart agini degistiriyoruz:

nano packages/react-app/src/App.jsx

Burda asagi dogru inip bu satiri buluyoruz: "const targetNetwork =
NETWORKS.localhost; // \<\-\-\-\-\-\-- select your target frontend
network (localhos\>" Asagi Yukari 56. satirda olacak.

![](media/image18.png){width="6.268055555555556in" height="4.01875in"}

goerli olarak degistirip, kaydedip cikiyoruz.

![](media/image19.png){width="4.2714293525809275in"
height="0.44797900262467194in"}

yarn deploy yapiyoruz ve daha sonra <http://localhost:3000/> sayfasini
yeniden yüklüyoruz. Bu asamada goerli görmemiz lazim:

![](media/image20.png){width="4.302683727034121in"
height="0.9167946194225722in"}

Connect tusuna basip Mmask ile baglaniyoruz ve MM yi goerli tesnet agina
aliyoruz.

Orda bakiyeyi görebilmemiz lazim.

![](media/image21.png){width="4.896516841644795in"
height="0.9897211286089239in"}

Sayfadan Mint NFT yapiyoruz ve cüzdan onayi vererek bir tane nft
aliyoruz.

![](media/image22.png){width="6.268055555555556in"
height="2.7243055555555555in"}

Burda aldigimiz nft artik bizim goerli cuzdana gelmis oldu. Daha
öncekiler gecici cüzdandaydi ve silinecekler bu nft kalacaktir.

yarn build

komutu ile sayfayi hazirliyoruz. Islem bittikten sonra

yarn surge

Ile sayfamizi internete yüklüyoruz.

![](media/image23.png){width="5.4382589676290465in"
height="1.7085717410323709in"}

Burda size domain icin bir öneri sunuyor, isterseniz degistirip
istediginiz bir isim verebilirsiniz. Surge üyeliginiz yoksa hemen bir
tane olusturup daha sonra gelen emaile onay vermeniz lazim. Daha sonrasi
otomatik isliyor.

Hata vermeden yüklediyse

yarn test

ile sistemi test ediyoruz

![](media/image24.png){width="6.268055555555556in"
height="4.018055555555556in"}

Ayrica domain kisminda verilen adresi web tarayicida acip bakiyoruz.

![](media/image25.png){width="6.268055555555556in"
height="2.6152777777777776in"}

**Checkpoint 5 Kontrat dogrulama:**

nano packages/hardhat/package.json dosyasini acip kendimizin etherscan
keyini koyuyoruz.

![](media/image26.png){width="6.268055555555556in"
height="1.0541666666666667in"}

Key almak icin <https://etherscan.io/myapikey> bu sayfaya gidip login
oluyoruz ve ordan adresimizi aliyoruz.

Daha sonra su komutla islemi dogruluyoruz:

yarn verify \--network goerli

![](media/image27.png){width="6.268055555555556in"
height="0.8930555555555556in"}

Burda zaten dogrulanmis diyor, normaldir. Cikan adresi goerli etherscan
da control ediyoruz.

![](media/image28.png){width="5.104878608923885in"
height="7.428120078740157in"}

Daha sonra\
<https://speedrunethereum.com/challenge/simple-nft-example>

Sayfasina girip alttaki "Submit challenge" tusuna tikliyoruz.

Orda istenen bilgileri giriyoruz. Surge sayfa adresi ve az önceki goerli
etherscan adresini verecegiz.

![](media/image29.png){width="5.3340780839895015in"
height="3.698432852143482in"}

Submit tusuna basiyoruz, kontrolu bekliyoruz. Sayfada üyelik yoksa
cüzdanimizla üye oluyoruz ve submit sonrasinda cüzdanla onay veriyoruz.

Islem tamamsa sayfanin sag üst tarafinda kendi cüzdanimiza tiklayip
sayfamiza giriyoruz orda status accepted olmasi lazim.

![](media/image30.png){width="6.268055555555556in"
height="1.554861111111111in"}

Bu islemden sonra telegram kanalina giriyoruz:

<https://t.me/+Y2vqXZZ_pEFhMGMx>

Daha sonra örnekteki gibi gerekli bilgileri toplayip discord kanalina
bildiriyoruz:

![](media/image31.png){width="6.268055555555556in"
height="5.850694444444445in"}
