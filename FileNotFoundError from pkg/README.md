Agar siz test1.py ni ishga tushursangiz my_module.py'ni shunchaki ko'chirib oladi
va my_module.py o'qishga urinayotgan data.txt testpkg'dan emas,
balki test1.py'ga ildiz bo'lgan katolog ichidan izlaydi: root/data.txt va bu xato.
Siz buni root/testpkg/data.txt ga o'zgartirishingiz kerak,
buning uchun open'ga testpkg/data.txt ni bering: data.txt => testpkg/data.txt (ildiz ichidan yuring)

Siz test2.py ni yurgizganingizda ham baribir ildiz o'zgarmaydi,
agar testpkg/test2.py shaklida run bo'lsa. VS codeda root ochilsa => root/testpkg/test2.py

Bu holot ilova, yani app'lar uchun to'g'ri keladi. Asosiy modul (test1.py misolida) ma'lumotlarni o'quvchi modul import qilinsa yuqoridagi yechim to'g'ri, chunki asosiy modul hech qayerga siljimaydi.

Agar loyihangiz biron-bir paket, kutubxona yoki framework bo'lsa u holda boshqacha yondashish kerak:
1. qo'shimcha local modul (my_module.py) ichidan __file__ ni chaqiring.
Bu sizga my_module.py ga olib boruvchi yo'lni ko'rsatadi.
2. Shundan oxirgi katologdagi faylni olib tashlang, => my_module.py
3. Va uni qo'shimcha ma'lumot (data.txt) yo'liga ulang
4. Natijani open'ga bering
SUCCESS