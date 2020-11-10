# Jarkom_Modul2_Lapres_A02
Lapres Praktikum Jarkom Modul 2

## Soal 1
Website utama dengan alamat http://semerua02.pw
### Jawab
Mengisi konfigurasi domain pada file /etc/bind/named.conf.local pada UML Malang.

~~~
zone "semerua02.pw" {
        type master;
        notify yes;
        also-notify { 10.151.73.27; };
        allow-transfer { 10.151.73.27; };
        file "/etc/bind/jarkom/semerua02.pw";
};
~~~
Selanjutnya membuat folder jarkom pada /etc/bind kemudian mengcopy file db.local pada /etc/bind ke /etc/bind/jarkom dengan nama semerua02.pw.
File tersebut diisi sebagai berikut.
~~~
$TTL    604800
@       IN      SOA     semerua02.pw. root.semerua02.pw. (
                        2020111002      ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      semerua02.pw.
@       IN      A       10.151.73.28 
~~~
Di mana NS adalah adalah Name Server yaitu semerua02.pw dan record A mengarah pada IP Probolinggo.

## Soal 2
http://semerua02.pw memiliki alias http://www.semerua02.pw
### Jawab
Menambahkan record CNAME pada file /etc/bind/jarkom/semerua02.pw
~~~
www     IN      CNAME   semerua02.pw.
~~~
