

#Linux 50,5


###man 
Manuel ifadesinin kısaltmasıdır.Bir komut veya yazılım hakkında bilgi almayı sağlar

=> “ man cd “

###pwd 

 Print working directory. Bulunduğumuz dizini ekrana basar.

=> “ pwd “

###cd  

Change Directory. Dizin veya klasörler arası geçişi sağlar.

=> “cd /root/Desktop “

###ls 

Dosya ve dizin listelemeyi sağlar

=> “ls -la “

> -a => Gizli dosyaları gösterir 	
> -l => Detayli listeleme sağlar

> Ayrıntılı bilgi için “man ls “

###touch 

Dosya oluşturmayı sağlar

=> “touch test.txt “
###uname 

sistem bilgilerini listeler

=> “uname -a “

> -a => sistem hakkındaki bütün bilgileri listeler

###mkdir 

Dizin oluşturmayı sağlar

=> “mkdir pausiber “

###cat 

Dosya içeriğini okumak ve görüntülemek için kullanılır

=> “ cat pausiber.txt “

###echo 
Kendinden sonra yazılan ifade veya değişkeni ekrana yazdır.

=> “ echo PAUSIBER “

###nano 

text editörüdür.

=> “nano pausiber.txt “

###vi 

text editörüdür.

=> “vi pausiber.txt “

> Detaylı bilgi için https://www.cs.colostate.edu/helpdocs/vi.html

###cp 

kopyalama

=> “cp -r /root/Desktop/pausiber /tmp/ “

> -r => dizin içindeki herşeyi taşır

###mv 

ismini değiştirmek veya taşımayı sağlar.

=> “mv -f pausiber/ /tmp “

> -f => kaynak dosyanın hedef dosyaya taşınmasını sağlar.

###rm 

Dosya,klasör silmeye yarar.

=> “rm -r dosya1 “  -> Dosyanın içindeki herşeyi siler.

###exit && logout 

Terminalden çıkmayı sağlar.

###grep 

arama komutudur.

=> “grep -i “pausiber“ pausiber.txt “

> -i => büyük küçük harf (case sensetive) olarak arar.

#Network Ayarları (Sanal kullananlar için )
###Nat mode
 Kullandığınız sanal işletim sistemine ip’yi sanal ağ kartının ataması işlemidir.Kısaca sanal network atanması
###Briged Mode 
Ip, sanal ağ katından değilde fiziksel işletim sistemine ip veren DHCP sunucundan verilir.
###Host Only 
Sanal makineler için yalıtılmış bir ağ ortamı sunar. İnternetee çıkışı yok ve sanal olarak kurulmuş tüm makineler birbirleri ile iletişim sağlayabilirler
###ifconfig 
network ayarını ve ip adresini verir.
#Servisler
####service apache2 start|stop|restart 
=> apache servisi başlat|durdur|yeniden başlat

####service ssh start|stop|restart 
=> ssh servisi başlat|durdur|yeniden başlat

####service vsftpd start|stop|restart 
=> ftp servisi başlat|durdur|yeniden başlat

#GENEL TERİMLER
###Exploit =>
açık bulduk o acıgı kullanarak sisteme bizi sokacak araç
###Payload =>
exploit kullandık ıcerdeyız sımdı ne yapıcaz sılmek atese vermek dınlemek bunlar payload lardır.
###Hacking=>
Bir sistemi doğası dışında çalıştırabilme kabiliyetine hacking denir.
###Tehtid =>
Zarar verebilecek kisi, bilgi veya bot(?) 
###Zafiyet =>
bir sistemin tasarımının dışında işleri yapabilmenizi sağlayan,tehtid ve risk oluşturabilicek ve karşı tarafta olmaması gereken problem(bug)lerdir.
###Risk =>    
Tehdit ve zafiyetin kesistiği noktadır. 
###TCP/IP => 
internet üzerinde iletişimi sağlayan protokoller kümesidir.Ağlara dahil olan bilgisayarlar belirli kurallar çerçevesinde ağlara dahil olan cihazlar birbirleri ile iletişim kurabilirler.

#####İletişim kurabilmek için; 
######Hostname (Bilgisayar Adı) 
######Ip adresi (Cihazların birbiriyle iletişimde kullandıkları adrestir) 
######Mac adresi (Ağ kartlarının sahip olduğu adrestir.6 oktetden oluşur.)

###Osi Katmanları 

#Pasif Bilgi Toplama(OSINT)
###Ip tespiti
ping
nslookup
whois
ipinfo.io
###Subdomain tespiti
fierce -dns <domain-name>
dnsmap <domain-name>
dig -x <ip>
###Virtualhost Tespiti
Bing arama motoruna IP:<ip-adress> search edilir
Email 
the harvester -d <domain-name> -b all
###İndirilebilir dosya tespiti
FOCA (windowsta çalışır)
metagoofil (stabil çalışmayabilir.)
###Location Tespiti
ipinfo.io
ip2location.com
whois.domaintools.com
###Shodan
###Google Dork(google hacking database hacking)
######Giriş panelleri tespiti
######indirilebilir dosyaa tespiti “filetype:pdf <domain-name> “
######pastebin bilgi toplama
###İş ilanları Tespiti
###Sosyal Medya Tespiti
###Kaynak kod ve geliştirici firma analizi
#Aktif Bilgi Toplama
##Nmap
###Hedef
#####nmap 192.168.10.20 => Tek bir IP için tarama 
#####nmap 192.168.10.13-25 =>  13 ile 20 ipleri dahil tarama
#####nmap pausiber.xyz => Domain için gerçekleştirilecek tarama
#####nmap –iL list.txt => list.txt adlı dosyadaki ipleri için tarama
###Syn Scan (Port Tarama)
#####nmap -sS 192.168.10.20
#####nmap –sS -F 192.168.10.13 => En yaygın 100 portu tarar. 
#####nmap –sS –p1,100,102 192.168.10.12 => 1,100 ve 102. portları tarar.
#####nmap –sS –p- 192.168.10.12 => 65535 portun hepsini tarar.
###Versiyon
#####nmap –sS -sV 192.168.10.20
###İşletim Sistemi
#####nmap –sS -O 192.168.5.20
###Hem versiyon hem işletim sistemi
#####nmap –sS -A 192.168.5.20
###Script kullanma
#####nmap –sC 192.168.23.22 => Bütün scriptler
#####nmap –script “http*” 192.168.23.22 => http ile başlayan scriptler
###Çıktı verme
#####nmap –sS –oA filename 192.168.2.1 =>bütün formatlarda verir
###Update
#####nmap-update
###Daha Fazlası için
#####nmap -h
#Exploit Aşaması
###Metasploit Framework




 

 







