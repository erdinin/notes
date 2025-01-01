Cosmovisor, Cosmos SDK tabanlı blokzincir ağları için geliştirilen bir süreç yöneticisidir. Temel amacı, blockchain uygulamalarını daha kolay bir şekilde yükseltmek ve bakım süreçlerini otomatize etmektir. Özellikle zincir yükseltmeleri sırasında manuel müdahale ihtiyacını azaltarak, validatörlerin ve node operatörlerinin iş yükünü hafifletir.

Cosmovisor'ın Ana Özellikleri
Otomatik Yükseltmeler:

Zincir üzerinde bir governance teklifi ile bir yükseltme duyurulduğunda, Cosmovisor bu yükseltmeyi belirli bir blok yüksekliğinde otomatik olarak uygular.
Gerekli dosyaları otomatik olarak çalıştırır, böylece manuel olarak yazılım değiştirme veya yeniden başlatma ihtiyacını ortadan kaldırır.
Esnek Sürüm Yönetimi:

İki anahtar dizin üzerinden çalışır:
Current (Güncel sürüm): Halihazırda çalışan uygulama.
Upgrade (Yükseltilecek sürüm): Bir sonraki sürüm için gerekli ikili dosyalar (binaries).
Geriye Dönük Uyumluluk:

Bir yükseltmenin başarısız olması durumunda, Cosmovisor önceki sürüme kolayca dönebilir.
Kolay Entegrasyon:

Cosmos SDK ile uyumlu herhangi bir blokzincir için kullanılabilir.
Cosmovisor'ın Çalışma Mantığı
Cosmovisor, blockchain uygulamanızın başlatılmasını ve güncellenmesini yöneten bir wrapper (sarma) uygulamasıdır. Aşağıdaki adımlarla çalışır:

Kurulum:

Cosmovisor, node’unuzun ana uygulamasını yönetir. Örneğin, gaiad veya osmosisd gibi bir Cosmos SDK uygulaması için Cosmovisor kullanılabilir.
Blok Yüksekliğini İzleme:

Zincirde bir yükseltme duyurusu yapıldığında, Cosmovisor, belirlenen blok yüksekliğini izler.
Yeni Sürümün Çalıştırılması:

Belirlenen blok yüksekliğine ulaşıldığında:
Mevcut uygulamayı durdurur.
Yeni uygulama sürümünü (binary) başlatır.
Sorunsuz Çalışma:

Tüm süreç sorunsuz bir şekilde gerçekleşir, validatör veya node operatörünün yalnızca gerekli binary dosyalarını doğru şekilde yüklemesi yeterlidir.
Cosmovisor Kullanımı: Adım Adım Rehber
1. Cosmovisor'ı Kurun
Gerekli Bağımlılıkları Kurun:

Go dilini kurun:
bash
Kodu kopyala
sudo apt update
sudo apt install -y golang
Cosmovisor Binary Dosyasını Derleyin:

bash
Kodu kopyala
git clone https://github.com/cosmos/cosmos-sdk.git
cd cosmos-sdk/cosmovisor
make install
2. Dizin Yapısını Ayarlayın
Cosmovisor aşağıdaki dizin yapısını kullanır:

bash
Kodu kopyala
~/.chain_name
├── cosmovisor
│   ├── genesis
│   │   └── bin
│   │       └── <application_binary>
│   ├── upgrades
│   │   └── upgrade-name
│   │       └── bin
│   │           └── <application_binary>
Genesis Binary Dosyasını Ekleyin:

bash
Kodu kopyala
mkdir -p ~/.chain_name/cosmovisor/genesis/bin
cp <current_binary> ~/.chain_name/cosmovisor/genesis/bin/
Yükseltme İkili Dosyasını Ekleyin: Örneğin, "v2-upgrade" adında bir yükseltme için:

bash
Kodu kopyala
mkdir -p ~/.chain_name/cosmovisor/upgrades/v2-upgrade/bin
cp <new_binary> ~/.chain_name/cosmovisor/upgrades/v2-upgrade/bin/
3. Cosmovisor'ı Başlatın
Cosmovisor, environment variable (ortam değişkenleri) ile çalıştırılır:

bash
Kodu kopyala
export DAEMON_NAME=<application_binary>
export DAEMON_HOME=~/.chain_name
cosmovisor start
4. Yükseltme Teklifi Ekleyin ve Süreci İzleyin
Zincir üzerinde bir yükseltme teklifi sunduğunuzda, Cosmovisor otomatik olarak belirtilen blok yüksekliğinde yeni sürümü çalıştıracaktır.
Cosmovisor'ın Avantajları
Manuel İşlemleri Azaltır:

Yükseltme sırasında node’u manuel olarak yeniden başlatma ihtiyacını ortadan kaldırır.
Hata Toleransı:

Yükseltmenin başarısız olması durumunda önceki sürüme dönebilir.
Zaman Kazandırır:

Validatörlerin ve node operatörlerinin bakım sürelerini önemli ölçüde azaltır.
Sektör Standardı:

Birçok Cosmos SDK tabanlı blockchain tarafından kullanılmaktadır.
Hangi Durumlarda Cosmovisor Kullanılır?
Zincir Yükseltmeleri:
Governance teklifleri ile yapılan zincir yükseltmelerinde.
Testnet Süreçleri:
Yükseltme prosedürlerini test etmek için.
Validatör Operatörleri:
Sürekli güncellemelerle uğraşmak istemeyen operatörler için.
