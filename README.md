# BilgisayarAglariProjesi
Cisco Packet Tracer uygulamasının 8.2.1.0118 sürümü ile yapılmıştır.
Proje readme dosyasında bulunan yapıya ve kurallara sahiptir.
Senaryo:
Bir e-ticaret firması kuruluyor. Firmanın:
Merkezi İstanbul'da,
Ankara ve Bursa'da depoları,
İzmir ve Gaziantep'te satış ofisleri bulunmaktadır.
Firmaya ait tüm ağ yapısı, bu şehirlerdeki ofisler, depolar ve merkez ofis arasında güvenli ve verimli bir iletişimi sağlamak amacıyla tasarlanacaktır. Şirketin her bir lokasyonu, belirli erişim kurallarına ve VLAN yapılandırmalarına sahip olacaktır.

1-) -Topoloji Oluşturulması:
Merkez Ofis (İstanbul):
•	Ana_Router → Multilayer Switch
•	Multilayer Switch → İstanbul Switch 1
•	Multilayer Switch → İstanbul Switch 2
•	İstanbul Switch 1 → Yönetici Bilgisayarı
•	İstanbul Switch 1 → Server
•	İstanbul Switch 2 → Kullanıcı Bilgisayarı
•	İstanbul Switch 2 → Misafir Bilgisayarı
Depolar:
•	Ana_Router → Depo_Yardımcı_Router
•	Depo_Yardımcı_Router → Ankara_Router 
•	Depo_Yardımcı_Router → Bursa_Router 
•	Ankara_Router → Ankara_Switch
•	Ankara_Switch → Ankara_PC 
•	Ankara_Switch → Ankara_Depo_Server
•	Bursa_Router → Bursa_Switch
•	Bursa_Switch → Bursa_PC 
•	Bursa_Switch → Bursa_Depo_Server
Satış Ofisleri:
•	Ana_Router → Satış_Yardımcı_Router
•	Satış_Yardımcı_Router → İzmir_Router 
•	Satış_Yardımcı_Router → Gaziantep_Router 
•	İzmir_Router → İzmir_Switch
•	İzmir_Switch → İzmir_PC 
•	İzmir_Switch → İzmir_Satis_Server 
•	Gaziantep_Router → Gaziantep_Switch
•	Gaziantep_Switch → Gaziantep_PC 
•	Gaziantep_Switch → Gaziantep_Satis_Server

2-) -IP Dağılımları ve VLAN Yapılandırması:
Merkez Ofis (İstanbul):
•	Yönetici VLAN:
IP Adresi: 10.0.10.0/24
•	Sunucu VLAN:
IP Adresi: 10.0.20.0/24
•	Kullanıcı VLAN:
IP Adresi: 10.0.30.0/24
•	Misafir VLAN:
IP Adresi: 10.0.40.0/24
Depolar:
•	Ankara Deposu (VLAN):
IP Adresi: 192.168.1.0/24
•	Bursa Deposu (VLAN):
IP Adresi: 192.168.2.0/24
Satış Ofisleri:
•	İzmir Ofisi (VLAN):
IP Adresi: 172.16.1.0/24
•	Gaziantep Ofisi (VLAN):
IP Adresi: 172.16.2.0/24

3-) HTML Dosyaları ve HTTP Sunucuları:
Ankara ve Bursa depoları:
•	-Ankara deposu, Ankara_Depo.html dosyasını barındıracak bir HTTP sunucusuna (Ankara_Depo_Server) sahiptir. 
•	-Bursa deposu, Bursa_Depo.html dosyasını barındıracak bir HTTP sunucusuna (Bursa_Depo_Server) sahiptir.
İzmir ve Gaziantep satış ofisleri:
•	-İzmir satış ofisi, İzmir_Satis.html dosyasını barındıracak bir HTTP sunucusuna (İzmir_Satis_Server) sahiptir.
•	-Gaziantep satış ofisi, Gaziantep_Satis.html dosyasını barındıracak bir HTTP sunucusuna (Gaziantep_Satis_Server) sahiptir.


4-) Erişim Kuralları:
Merkez Ofis Erişim Kuralları:
Yönetici VLAN: Tüm ağlara erişebilir.
Kullanıcı VLAN: Tüm ağlara erişebilir.
-Misafir VLAN: Merkez Ofis'e erişebilir, diğer ağlarla iletişim kuramaz. 
Depolar Erişim Kuralları:
-Ankara ve Bursa Depoları: Yalnızca Merkez Ofis'e erişebilir.

Satış Ofisleri Erişim Kuralları:
İzmir ve Gaziantep Satış Ofisleri: Yalnızca Merkez Ofis'e erişebilir.
HTTP Sunucu Erişimi:
-İstanbul merkez ofisindeki yönetici ve kullanıcı bilgisayarlarından HTTP sunucularına istek atılabilir, ancak misafir bilgisayarından HTTP sunucularına erişim engellenmiştir. 
-Ayrıca, depo ve satış ofislerinden yalnızca kendi HTTP sunucularına erişim sağlanabilir; kendilerine ait olmayan diğer HTTP sunucularına erişim kısıtlanmıştır.
