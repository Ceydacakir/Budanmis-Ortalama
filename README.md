#Veri listesi oluştur ve veri adedi değişkeni tanımla.
veriler = []
veri_adedi = 0

#Kullanıcıdan "x" veya "X" girene kadar değer iste.
while True:
  veri=((input("Bir sayı giriniz.Durmak için 'x' veya 'X'  giriniz:")))
#'x' veya 'X' girildiğinde döngünün durmasını sağlayan koşulu yaz.
  if veri == 'x' or veri == 'X':
    break
  else:
#Girilen verileri listeye ekle ve veri girildikçe veri adedini 1 arttır.
    veriler +=[float(veri)]
    veri_adedi +=1

#Verileri küçükten büyüğe sıralamak için birbirleriyle karşılaştır.
for i in range(len(veriler)):
    for veri in range(0, len(veriler)-i-1):
        if veriler[veri] > veriler[veri+1]:
#Verileri yer değiştir
            veriler[veri], veriler[veri+1] = veriler[veri+1], veriler[veri]

#Veri adedinin %5'inin tam sayı kısmını hesapla.
y=(int((veri_adedi)*0.05))

#Listenin başından ve sonundan hesapladığımız sayı kadar veri çıkart, eğer %5'i 0 ederse budanamayacağı için direkt verilere eşitle.
if y > 0:
  budanmis_veriler = veriler[int(y):int(-y)]

else:
  budanmis_veriler=veriler
  print("\033[1;31mVerilerin budanabilmesi için en az 20 adet veri girmeniz gerekmektedir.\033[0;32m")

#Budanmış veri listesindeki verileri topla.
toplam = 0
for sayi in budanmis_veriler:
    toplam += sayi

#Girilen veri adedi 0 değilse listenin toplamını, listedeki veri adedine bölüp ortalamayı bul.0 ise hesaplanamadığını yazdır.
if len(budanmis_veriler) != 0:
  budanmis_veri_ortalaması=toplam/len(budanmis_veriler)

  print(veri_adedi, "adet veri girdiniz")
  print("Budanmamış liste:", veriler)
  print("Budanmış liste:",budanmis_veriler)
  print("\033[1;31mBudanmış listenin ortalaması:\033[1;32m", budanmis_veri_ortalaması)

else:
  print("Veri girilmediği için hesaplanamadı.")
