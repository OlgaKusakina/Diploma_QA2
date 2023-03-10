## План автоматизации тестирования к

___

### 1. Перечень автоматизируемых сценариев

___

**Тестовые данные:**

-При вводе данных карт в поля заполнения во вкладке “купить” и “купить в кредит”, корректными данными считаются:
-Поле “Номер карты”
-данные,состоящие из 16 цифр в формате **** **** **** **** , например, 4444 4444 4444 4441
-Поле “Месяц”
-ввод двухзначного числа. с первого по двенадцатый месяц (01-12), но не ранее, чем дата заполнения, например, 07
-Поле “Год”
-ввод двухзначного числа, но не ранее, чем дата заполнения (23+), например, 23
-Поле “Владелец”
-Ввод данных на латинице в формате “ФАМИЛИЯ ИМЯ” через пробел, например, Ivanov Ivan
-CVC
-ввод трехзначного числа в формате (***), например, 999

**Номера карт, предоставленные для тестирования:**

-4444 4444 4444 4441, status APPROVED
-4444 4444 4444 4442, status DECLINED





**Позитивные сценарии:**

1. а) Успешная покупка тура картой со статусом APPROVED

- Нажать "Купить"
- Ввести в поля формы валидные данные
- Нажать "Отправить"

*Ожидаемый результат:* Оплата проходит(данные об оплате появляются в базе). Появляется сообщение об успешной покупке тура.

б) Успешная покупка тура в кредит картой со статусом APPROVED

- Нажать "Купить в кредит"
- Ввести в поля формы валидные данные
- Нажать "Отправить"

*Ожидаемый результат:* Оплата проходит(данные об оплате появляются в базе). Появляется сообщение об успешной покупке тура.


**Негативные сценарии:**

2. а) Покупка тура картой со статусом DECLINED

- Нажать "Купить"
- Ввести в поля формы валидные данные
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит(в базе данных появляется информация, что покупка отклонена). Появляется сообщение об ошибке

б) Покупка тура в кредит картой со статусом DECLINED

- Нажать "Купить в кредит"
- Ввести в поля формы валидные данные
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит(в базе данных появляется информация, что покупка отклонена). Появляется сообщение об ошибке

3. а) Покупка тура с невалидным номером карты

- В поле "Номер карты" ввести 7-ми значный номер карты.
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) Покупка тура в кредит с невалидным номером карты

- В поле "Номер карты" ввести 7-ми значный номер карты.
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

4. а) Отправка формы с пустым полем "Номер карты"

- Оставить пустым поле "Номер карты"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) Отправка формы с пустым полем "Номер карты" в кредит

- Оставить пустым поле "Номер карты"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

5. а) Отправка формы с невалидным месяцем (однозначное числовое значение) при покупке тура

- В поле "Месяц" ввести данные из 1 числового значения
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) а) Отправка формы с невалидным месяцем (однозначное числовое значение) в кредит

- В поле "Месяц" ввести данные из 1 числового значения
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

6. а)Отправка формы с невалидным месяцем (неверно указан срок действия карты) при покупке тура

- В поле "Месяц" ввести значение "16"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) а)Отправка формы с невалидным месяцем (неверно указан срок действия карты) при покупке в кредит

- В поле "Месяц" ввести значение "16"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

7. а) Отправка формы с пустым полем "Месяц" при покупке тура

- Оставить пустым поле "Месяц"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) Отправка формы с пустым полем "Месяц" при покупке в кредит

- Оставить пустым поле "Месяц"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

8. а) Отправка формы с невалидным годом (однозначное числовое значение) при покупке тура

- В поле "Год" ввести данные из 1 числового значения
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) Отправка формы с невалидным годом (однозначное числовое значение) при покупке тура в кредит

- В поле "Год" ввести данные из 1 числового значения
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

9. а) Отправка формы с невалидным годом (неверно указан срок действия карты) при покупке тура

- В поле "Год" ввести значение (настоящий год - 1)
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно

б) Отправка формы с невалидным годом (неверно указан срок действия карты) при покупке тура в кредит

- В поле "Год" ввести значение (настоящий год - 1)
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно

10. а) Отправка формы с пустым полем "Год"

- Оставить пустым поле "Год"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) Отправка формы с пустым полем "Год" при  покупке тура в кредит

- Оставить пустым поле "Год"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

11. а) Отправка формы с невалидными данными владельца (значение набрано кириллицей) при покупке тура

- В поле "Владелец" ввести значение на кириллице
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) Отправка формы с невалидными данными владельца (значение набрано кириллицей) при покупке тура в кредит

- В поле "Владелец" ввести значение на кириллице
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

12. а)Отправка формы с введенными в поле "Владелец" цифровыми значениями/спец символами/иероглифами при покупе тура

- В поле "Владелец" ввести значение из цифр/спец символов/иероглифов
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) а)Отправка формы с введенными в поле "Владелец" цифровыми значениями/спец символами/иероглифами при покупе а кредит

- В поле "Владелец" ввести значение из цифр/спец символов/иероглифов
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

13. а) Отправка формы с пустым полем "Владелец" при покупке тура

- Оставить пустым поле "Владелец"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) а) Отправка формы с пустым полем "Владелец" при покупке тура в кредит

- Оставить пустым поле "Владелец"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

14. а) Отправка формы с невалидным CVC/CCV (однозначное числовое значение) при покупке тура

- В поле "CVC/CCV" ввести данные из 1 числового значения
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

б) Отправка формы с невалидным CVC/CCV (однозначное числовое значение) при кредит

- В поле "CVC/CCV" ввести данные из 1 числового значения
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

15. а) Отправка формы с пустым полем "CVC/CCV" при покупке тура

- Оставить пустым поле "CVC/CCV"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

а) Отправка формы с пустым полем "CVC/CCV" при покупке тура в кредит

- Оставить пустым поле "CVC/CCV"
- Остальные поля формы заполнить валидными данными.
- Нажать "Отправить"

*Ожидаемый результат:* Оплата не проходит. Появляется сообщение об ошибке, что поле заполнено неверно.

___

### 2. Перечень используемых инструментов с обоснованием выбора

___

1. IntelliJ IDEA - специальная среда разработки, необходимая для оптимизации работы;
2. Java 11 - язык программирования для написания автотестов;
3. Gradle - инструмент автоматизации сборки и управления зависимостями;
4. JUnit5 — платформа для написания авто-тестов и их запуска;
5. Selenide - фреймворк для автоматизированного тестирования веб-приложений на основе Selenium WebDriver, более удобный и простой в использовании, чем Selenium;
6. Docker Compose - инструмент, позволяющий запускать мультиконтейнерные приложения, чтобы не устанавливать на компьютер необходимые для работы приложения Node.js и СУБД;
7. Allure - фреймворк, предназначенный для создания отчетов, более наглядных, чем у Gradle;
8. Lombok- библиотека для сокращения количества шаблонного кода, для объявления локальной переменной вместо указания реального типа;
9. Git и GitHub для хранения кода. Git достаточно прост и удобен для управления исходным кодом, очень распространенная система контроля версий, поэтому достаточно хорошо взаимодействует с различными ОС. GitHub специализированный веб-сервис с удобным интерфейсои, интегрирован с Git.

___

### 3. Перечень и описание возможных рисков при автоматизации

___

1. Отсутствие достаточного опыта у сотрудника, занимающегося настройкой и проведением автоматизированного тестирования.
2. Отсутствие документации по описанию работы приложения и как следствие вероятность необходимости доработки или избыточность авто-тестов
3. Технические трудности при настройке инструментов, необходимых для автоматизированного тестирования.
4. Возможные проблемы с запуском приложения, подключением БД
___

### 4. Интервальная оценка с учётом рисков (в часах)

___

1. Написание плана тестирования - 5 часа
2.  Подготовка тестовой среды, настройка инструментов - 12 часов
3. Написание автотестов - 30 часов
4. Прогон автотестов - 4 часа
4. Составление баг-репортов - 5 часа
5. Составление отчета о тестировании - 8 часов

**Итого:** 64 час

___

### 5. План сдачи работ

___

- готовность автотестов - 20.01.2023
- отчет по результатам прогона автотестов - 06.02.2023
- отчет по автоматизации - 14.02.2023


