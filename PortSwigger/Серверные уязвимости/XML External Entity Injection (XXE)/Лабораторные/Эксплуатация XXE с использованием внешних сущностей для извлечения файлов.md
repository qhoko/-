1. Нас встречает список товаров:

![image](https://github.com/user-attachments/assets/7732ce0b-262f-4416-aebe-a7af11b5d714)

---

2. Переходим на любой из них, включив прокси бурпа, нажимаем на кнопку "Проверить наличие на складе":

![image](https://github.com/user-attachments/assets/be6726cc-64f5-4093-b301-7923e3d88d9c)

---

3. В HTTP History полученный POST запрос перекидываем в Repeater, видим, что проверка наличия производится с помощью XML, это и будет нашим вектором атаки:

![image](https://github.com/user-attachments/assets/028c10b5-e477-45f5-8101-8a056ed72651)

---

4. Вставляем следующее определение внешней сущности между декларацией XML и stockCheck элементом: <!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>, и в productId значение меняем на &xxe;, должно получиться вот так: 

![image](https://github.com/user-attachments/assets/22cbd669-befa-4e8b-9250-da047534f851)

---

5. Получаем вывод /etc/passwd: 

![image](https://github.com/user-attachments/assets/7c506f3a-d652-4bad-820c-2b61fa561bf5)
---
