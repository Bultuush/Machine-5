# Machine-5 "NULLY CYBERSECURITY:1(Vulnhub)"
**1.** Эхлээд бид **netdiscover** ашиглан хохирогч машиныхаа IP хаягийг шалгах болно.

![image](https://github.com/Bultuush/Machine-5/assets/129934501/f034e4c4-93a0-4274-a617-6aa4efc4b681)

**2.** Дараа нь бид nmap ашиглан нээлттэй портуудыг олох хэрэгтэй.

![image](https://github.com/Bultuush/Machine-5/assets/129934501/6f41cd21-0f0c-4702-933b-62b70bcc047f)

Порт 80 нээлттэй байна, вэб сайтыг шалгацгаая!

![image](https://github.com/Bultuush/Machine-5/assets/129934501/2808bae1-3912-42ec-87a4-7b246eba4df9)

Вэб хуудасны доод хэсэгт бид зарим мэдээллийг авдаг

![image](https://github.com/Bultuush/Machine-5/assets/129934501/1657232d-ed7b-4a08-8823-7c7abce8a033)


**Bruteforcing and exploitation**
Дээрх мэдээлэл болон сорилтын тайлбараас бид эхний сервер дээр root хандалт авсны дараа та бусад серверүүд рүү шилжиж, тус бүрд нь root хандалт авах шаардлагатай болно гэдгийг хэлж чадна. За ингээд хакердацгаая :)

![image](https://github.com/Bultuush/Machine-5/assets/129934501/3f8ad154-7349-4d80-a29e-08229eee65fe)

Бидэнд ирсэн захидалд дараах зүйлийг бичсэн байна.

![image](https://github.com/Bultuush/Machine-5/assets/129934501/607768b6-6665-4294-9744-d3d4f8ca017c)

Сайхан, мэдээллээс харахад мэйл серверийн хэрэглэгчийн нэр нь bob, bobsmith, smith, bobS, Bob... гэх мэт байж болохыг хэлж чадна. Би тайлбар дээрх зөвлөмжийн дагуу нууц үгийн жагсаалтыг үүсгэж, ssh дахь bob хэрэглэгчийн эсрэг хүчирхийлсэн. .

![image](https://github.com/Bultuush/Machine-5/assets/129934501/5a1a7a66-f944-4061-9622-a06509f98fae)

**ssh**-ээр нэвтэрж орсон байдал

![image](https://github.com/Bultuush/Machine-5/assets/129934501/023f49ef-9689-4a57-8c0a-290dd381cbfe)

Бид ssh-ээр нэвтэрч ороод эргэн тойрноо харвал todo нэртэй дараах мэдээлэлтэй файл байна

![image](https://github.com/Bultuush/Machine-5/assets/129934501/36d9f627-8b5d-46f5-a01e-fc0f2f807289)

# Давуу эрхийг нэмэгдүүлэх

![image](https://github.com/Bultuush/Machine-5/assets/129934501/98590060-c9b6-4df9-90ec-1b4f1939a2fe)

Дээрхээс харахад my2user хэрэглэгч check.sh файлыг root хэлбэрээр ажиллуулах боломжтой гэдгийг хэлж болно. Энэ нь хэрэв тэр файлыг sudo ашиглан ажиллуулбал энэ нь my2user файлыг ажиллуулж байгаатай тэнцэнэ гэсэн үг. Мөн NOPASSWD нь файлыг ажиллуулах явцад нууц үг асуухгүй гэдгийг зааж өгдөг.

Эхлээд бид check.sh файлыг дээд талд нь /bin/bash -p-г нэмж өөрчилнө (-p сонголт нь my2user байх ёстой эхлүүлсэн үр дүнтэй хэрэглэгчийн ID-аа bash-д хадгалах боломжийг олгоно). Дараа нь sudo ашиглан скриптийг ажиллуул. Бид давуу эрхээ хэвтээ байдлаар нэмэгдүүлж, my2user болно

![image](https://github.com/Bultuush/Machine-5/assets/129934501/b7999e14-ec9e-4354-8464-fc79a3601932)

Үүнтэй ижил үйлдлийг давтан хийснээр my2user нь zip командуудыг root хэлбэрээр ажиллуулж чадна гэдгийг бид харж байна.

![image](https://github.com/Bultuush/Machine-5/assets/129934501/4b2ee7db-bc3b-476f-a9ca-3d8dcad6f7dc)

Бид үүнийг ашиглаж бүрхүүлд үндэс болгон буулгаж чадна! GTFobins нь ашиглах боломжтой хоёртын файлуудад зориулсан сайн онлайн нөөц юм.

![image](https://github.com/Bultuush/Machine-5/assets/129934501/9e7f6478-c6c6-42ea-a5e5-9943ec24080b)
