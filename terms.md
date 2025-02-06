📌 Ağ Bağlantıları ve İletişim Protokolleri

Seed Node: Yeni düğümlerin ağa katılmasına yardımcı olan ve mevcut düğümlerin bağlantılarını listeleyen bir node.
Peer: Bir node’un bağlantı kurduğu diğer düğümler.
P2P (Peer-to-Peer) Network: Merkezi bir sunucuya ihtiyaç duymadan node’ların birbirine doğrudan bağlanarak iletişim kurduğu ağ yapısı.
RPC (Remote Procedure Call): Node ile uzaktan iletişim kurmaya ve verileri çekmeye izin veren bir protokol.
gRPC: RPC’nin daha verimli ve hızlı bir sürümü. Genellikle veri iletiminde kullanılır.
WebSocket (WSS): Sürekli açık bir bağlantı ile gerçek zamanlı veri aktarımını sağlayan bir iletişim protokolü.
REST API: Node’larla etkileşim kurmak için kullanılan, HTTP üzerinden çalışan API türü.

📌 Konsensüs ve Blok Üretimi
Consensus Mechanism (Konsensüs Mekanizması): Ağa bağlı düğümlerin yeni blokları nasıl doğruladığını belirleyen protokol (örneğin PoS, PoW, CometBFT, Tendermint, etc.).
CometBFT (Tendermint Core): Cosmos ekosisteminde yaygın olarak kullanılan, Proof-of-Stake (PoS) tabanlı bir konsensüs mekanizması.
Finality (Kesinlik): Bir işlemin geri alınamaz hale gelmesini ifade eder. Hızlı kesinlik, bir işlemin blockchain üzerinde hızlı bir şekilde kalıcı hale gelmesi anlamına gelir.
Epoch (Çağ): Blockchain'in belirli periyotlarla validator değişiklikleri yaptığı zaman dilimi.
Slashing (Kesinti): Validator'lerin hatalı veya kötü niyetli davranışları sonucunda stake edilen varlıklarının kesilmesi (ceza alması).
Jailing (Hapsetme): Bir validator'ün ağdan belirli bir süre veya süresiz olarak çıkarılması.
Bonded Status: Validator'ün aktif olarak blok üretme ve doğrulama yetkisine sahip olduğu durum.
Unbonding Period: Validator'ün stake’ini çekmek istediğinde, varlıklarının kilidinin açılmasını beklemesi gereken süre.

📌 Node Yönetimi ve İzleme
Genesis File: Yeni bir blockchain ağı başlatırken kullanılan başlangıç yapılandırma dosyası.
State Sync: Bir node’un blockchain’in son durumunu hızlı bir şekilde senkronize etmesini sağlayan yöntem.
Fast Sync: Node’un eski blokları işlemeye gerek kalmadan son durumu alarak hızla ağa katılmasını sağlayan senkronizasyon yöntemi.
Pruning: Gereksiz blok verilerini silerek node’un disk kullanımını optimize etmesi.
Snapshot: Bir blockchain’in belirli bir noktadaki tam durumunun alınması ve saklanması.
Checkpointing: Belirli aralıklarla blockchain'in durumunun kaydedilmesi, böylece yeni node'ların hızlıca senkronize olabilmesi.
Prometheus: Node metriklerini toplayan ve analiz eden bir izleme aracı.
Grafana: Prometheus verilerini görselleştirerek node performansını izlemeye yarayan bir araç.

📌 Staking ve Delegasyon
Delegator: Token’larını bir validator'e stake eden kullanıcı.
Staking: Token’ların bir validator’e kilitlenmesi ve ağ güvenliğine katkı sağlanması karşılığında ödül kazanılması süreci.
Reward (Ödül): Validator ve delegator’lerin staking karşılığında kazandığı ödüller.
Commission Rate: Validator’ün delegatörlerden aldığı ödül yüzdesi.
Inflation: Blockchain'in yeni token üretme oranı.
APR (Annual Percentage Rate): Yıllık yüzde getiri oranı, genellikle staking ödüllerinin yüzdesi olarak gösterilir.

📌 Ağ Problemleri ve Çözümleri
Double Signing: Aynı validator'ün aynı bloğu iki kez imzalaması, bu genellikle ciddi cezalara (slashing) yol açar.
Fork: Blockchain'in iki farklı versiyona ayrılması.
Orphan Block: Ağ tarafından kabul edilmeyen blok.
Reorg (Reorganization): Blockchain’deki blokların yeniden düzenlenmesi.
Downtime: Bir node’un veya validator’ün belirli bir süre boyunca çalışmaması durumu.
Missed Block: Validator’ün bir blok üretme şansını kaçırması.
Tombstoning: Validator’ün ağır bir ceza alarak kalıcı olarak ağdan çıkarılması.

📌 Ekosistem ve Uygulamalar
IBC (Inter-Blockchain Communication): Cosmos ekosisteminde zincirler arası iletişim sağlayan protokol.
Bridging: Bir blockchain’den diğerine varlık aktarımı yapmak.
Rollup: İşlemleri ana blockchain dışında işleyip, sonucu ana zincire gönderen bir ölçeklendirme çözümü.
Oracles: Blockchain’e dış dünyadan veri getiren sistemler.
MEV (Maximal Extractable Value): Validator'lerin işlem sıralamasından elde edebileceği ekstra kazanç.
Slashing Condition: Validator’lerin hangi durumlarda ceza alacağına dair koşullar.
Dusting Attack: Küçük miktarda token göndererek bir adresin kimliğini deşifre etmeye çalışmak.
