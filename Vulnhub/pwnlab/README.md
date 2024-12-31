# PwnLab Walkthrough 🚀

Этот walkthrough описывает шаги по эксплуатации машины PwnLab на Vulnhub. Каждый этап задокументирован с использованием скриншотов, чтобы сделать процесс понятным и повторяемым. 📘

## 🛠️ Шаги

### 1. Скан портов
Выполните сканирование портов, чтобы определить открытые порты и запущенные сервисы:

![image](https://github.com/user-attachments/assets/9931d39b-9214-4fcf-8bea-084b6d681db5)

---

### 2. Доступ к цели
Перейдите по указанному URL с определённым payload:

`http://<ip>/?page=php://filter/convert.base64-encode/resource=config`

![image](https://github.com/user-attachments/assets/60118c58-6fc7-44b9-9334-16fa11f526da)

---

### 3. Декодирование данных Base64
Декодируйте полученные данные, чтобы раскрыть чувствительную информацию:

![image](https://github.com/user-attachments/assets/443a9bf9-504c-448d-928a-8b747158b0ac)

---

### 4. Извлечение информации из базы данных
Получите содержимое таблицы `Users` из базы данных:

![image](https://github.com/user-attachments/assets/3782dcfe-a1d3-4b17-8d94-a93fe2786068)

---

### 5. Формирование полезной нагрузки
Сгенерируйте полезную нагрузку с использованием `msfconsole` для эксплуатации:

![image](https://github.com/user-attachments/assets/e378db62-7abb-4c66-a1fe-21825ef3a6b7)

Преобразуйте полезную нагрузку в файл формата `.gif` для дальнейшего использования:

![image](https://github.com/user-attachments/assets/8e5eea5a-8bbc-464f-8ea4-2335e65eed39)

---

### 6. Исполнение полезной нагрузки через изменение заголовка cookie
Выполните полезную нагрузку, изменив заголовок `cookie`:

![image](https://github.com/user-attachments/assets/38b2ee46-983e-4883-92e4-31799aa200be)

---

### 7. Эскалация привилегий
Переключитесь на пользователя `kane`, используя обнаруженный пароль:

![image](https://github.com/user-attachments/assets/5fb07111-ef81-4b5a-aa57-29a9d014d821)

Измените запрашиваемый путь, чтобы использовать встроенные бинарники для эскалации привилегий:

![image](https://github.com/user-attachments/assets/0e7dcddc-c757-47a3-b572-a0be9c10367a)

Создайте кастомный файл `cat` для выполнения дальнейших шагов:

![image](https://github.com/user-attachments/assets/ee47764a-a79e-4b8d-81b3-c2a65c5e834a)

---

### 8. Доступ к root
Запустите `msgmike` для продолжения эксплуатации:

![image](https://github.com/user-attachments/assets/9df8a414-1e76-48c6-bc6c-53cbd607e57e)

Выполните `msg2root`, чтобы получить root-привилегии:

![image](https://github.com/user-attachments/assets/2dc3e832-5893-4800-826b-d64b920b5f41)

---

### Заключение
Поздравляю! Вы успешно эксплуатировали машину PwnLab. 🎉
