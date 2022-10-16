**ВВЕДЕНИЕ**

В настоящие время технология чат-ботов получила широкую популярность среди пользователей. Особенно крупной популярностью при этом пользуются боты, которые встроенные в менеджер telegram. Они просты в использовании, но в тоже время обладают огромными функциональными возможностями.

После появления чат-ботов в одном из обновлений telegram, разработчики быстро поняли огромный потенциал новой технологии.

Чат-боты способны заменить собой функционал полноценных standalone  приложений при этом обладая рядом уникальных преимуществ. К ним можно отнести следующее: telegram бот всегда под рукой, его не нужно устанавливать, для его использования не требуется запускать отдельное приложение.

Также важным преимуществом telegram  бота по сравнению с обычным приложением является его кроссплатформенность, которая достигается благодаря тому, что бот встроен непосредственно в приложение telegram. Благодаря кроссплатформенности от разработчика требуется написать лишь одну версию своего приложения, что позволяет сэкономить значительное количество времени и ресурсов.

В рамках данной курсовой работы на примере бота прогноза погоды будет изучен и подробно описан процесс создания типового telegram бота.

  

**1. Создание бота**

**1.1 Описание предметной области**

_Telegram_  — кроссплатформенная система мгновенного обмена сообщениями с функциями VoIP, позволяющая обмениваться текстовыми, голосовыми и видеосообщениями, стикерами и фотографиями, файлами многих форматов[2].

_API (Application Programming Interface или интерфейс программирования приложений)_ — это совокупность инструментов и функций в виде интерфейса для создания новых приложений, благодаря которому одна программа будет взаимодействовать с другой. Это позволяет разработчикам расширять функциональность своего продукта и связывать его с другими[3].

_Боты_ — специальные аккаунты в Telegram, созданные для того, чтобы автоматически обрабатывать и отправлять сообщения. Пользователи могут взаимодействовать с ботами при помощи сообщений, отправляемых через обычные или групповые чаты. Логика бота контролируется при помощи HTTPS запросов к нашему API для ботов [5][8].

_Python_ - высокоуровневый язык программирования общего назначения с динамической строгой типизацией и автоматическим управлением памятью, ориентированный на повышение производительности разработчика, читаемости кода и его качества, а также на обеспечение переносимости написанных на нём программ. Язык является полностью объектно-ориентированным в том плане, что всё является объектами [11].

_SQL_ _-_ Декларативный язык программирования, применяемый для создания, модификации и управления данными в реляционной базе данных, управляемой соответствующей системой управления базами данных [4].

_СУБД_ — совокупность программных и лингвистических средств общего или специального назначения, обеспечивающих управление созданием и использованием баз данных [14].

_IDE (Integrated Development Environment или же интегрированная среда разработки)_ – это интегрированная, единая среда разработки, которая используется разработчиками для создания различного программного обеспечения. IDE представляет собой комплекс из нескольких инструментов, а именно: текстового редактора, компилятора либо интерпретатора, средств автоматизации сборки и отладчика [13].

  

**1.2 Процесс создания** **Telegram**  **бота**

Процесс создания нового Telegram  бот крайне тривиален, и состоит всего из нескольких простых этапов.

Для начала требуется открыть приложение телеграмм на любой удобной пользователю платформе, перейти на вкладку чатов, и набрать в поисковой строке botfather. Требуемый бот будет первым в списке приисковой выдачи.

![1 img](images/1.jpg?raw=true "Title")

Рисунок 1 – Бот botfather

Botfather  это, как следует из его название самый главный бот телеграмма, все новые пользовательские боты создаются через него. Взаимодействие с ботом производится при помощи отправки боту сообщений-команд. Экран бота Botfather показан на рисунке №1

После ввода начальной команды start, бот сразу же выводит список всех доступных команд, одной из них является команда newbot  получив которую, бот запустит процесс создания нового.

Далее бот попросит пользователя указать имя (так бот будет называется в списке чатов), а также username (прямая ссылка на чат-бота в рамках телеграмм.

В заключительном сообщении botfather  сообщает пользователю об успешном создании нового бота. Также стоит обратить внимание на то, что в этом сообщении содержится секретный token  бота, благодаря которому скрипт, который будет отвечать за работу бота сможет получить к нему доступ.

![2 img](images/2.jpg?raw=true "Title")

Рисунок 2 – Список команд BotFather

Список всех команд доступных пользователю в Botfather  представлен на рисунке №2

![3 img](images/3.jpg?raw=true "Title")

Рисунок 3 – Процесс создания нового пользовательского бота

Для заверения создания бота создадим на компьютере Python  скрипт с называнием “bot.py”. Далее подключим библиотеку aiogram для удобной работы c  API  телеграмм ботов, после чего создадим экземпляр нового бота.

Процесс создания нового пользовательского бота представлен на рисунке №3

В рамках данного скрипта будут обрабатывается все запросы, поступающие от пользователей бота. Окно файла, ответственного за обработку команд, поступающих от бота представлен на рисунке №4

![4 img](images/4.jpg?raw=true "Title")

Рисунок 4 – Файл, обрабатывающий сообщения, поступающие от бота

**1.3 Выбор среды разработки**

Отдельно отметим, что рамках данной курсовой работы, написание всего программного кода бота будет осуществятся в программе Visual  Studio  Code.

Эта IDE  была выбрана по целому ряду причины, основные среди которых следующие:

* Быстрый и удобный процесс установки и первоначальной настройки

* Быстрая скорость работы

* Малый объем занимаемого дискового пространства

* Удобная и быстрая возможность установки плагинов, для огромного количества языков программирования (среди которых есть также и Python)

* Удобная работа с системой контроля версий Git

**2. Первоначальная настройка бота**

Бот был успешно создан, но на данный момент он абсолютно пустой. Если какой-нибудь пользователь телеграмм случайно найдет данного бота, он скорее всего даже не сможет понять зачем он нужен и как им пользоваться.

Для исправления этой ситуации следует добавить боту фото профиля, а также заполнить информацию о нем в блоке “ What can this bot do?” (что умеет делать этот бот?), а также в блоке “About  text” (короткая справка о боте в разделе информации о профиле).

Для этого также, как и ранее нужно использовать команды Botfather. Список необходимых команд и их описание:

* /setuserpic – для установки фото профиля

* /setdescription – описание бота. Отображается в информационном блоке “What  can  this  bot  do”?”

* /setabouttext – короткое описание бота в разделе информации о профиле пользователя

![5 img](images/5.jpg?raw=true "Title")

Рисунок 5 – Заполнение информации о боте

![6 img](images/6.jpg?raw=true "Title")

Рисунок 6 – Заполнение информации о боте

Пошаговый процесс заполнения информации о боте представлен на рисунках №5 и №6.

**3. Обработка команд**

На данный момент бот абсолютно ничего не умеет. В этом можно убедится, отправив ему любое сообщение, или команду.

![7 img](images/7.jpg?raw=true "Title")

Рисунок 7 – Бот ничего не умеет

Как видно на рисунке №7 на данный момент ничего не умеет. Для начала давайте научим бота обрабатывать команды. Для этого пропишем встроенный декоратор message_handler, при этом указав в его круглых скобах массив команд, ввод которых он будет отсаживать. Также создадим асинхронную функцию к декоратору с названием start_command, внутри которой будет происходить обработка этих команд.

![8 img](images/8.jpg?raw=true "Title")

Рисунок 8 – Обработка пользовательских команд

![9 img](images/9.jpg?raw=true "Title")

Рисунок 9 – Бот обрабатывает команду start, выводя сообщение

Как можно увидеть на рисунке №9, теперь бот может обрабатывать пользовательские команды, отправляя ответное сообщение.

**4. Обработка пользовательских сообщений**

После того, как бот научился обрабатывать, команды и отвечать пользователю на них, следует продумать и разработать логику, ответственную за обработку обычных текстовых сообщений, которые намного понятнее простому пользователю чем команды.

Простые текстовые запросы позволят сделать коммуникацию с ботом более дружелюбной и понятной. Для обработки текстовых сообщений, также, как и для обработки команд, используется декоратор message_handler и функция обработчик к нему.

![10 img](images/10.jpg?raw=true "Title")

Рисунок 10 – Обработка текстовых сообщений

На рисунке №10 представлен код для обработки пользовательских сообщений поступающих боту.

Проверим получившейся результат, отправив боту сообщение с текстом “Привет, как дела?”

![11 img](images/11.jpg?raw=true "Title")

Рисунок 11 – Бот обрабатывает текстовые сообщения

Как мы можем увидеть на рисунке №11, теперь бот отвечает на сообщение, повторяя написанное пользователем сообщение.

**5. Получение** **API** **прогноза погоды**

После того, как была произведена базовая настройка бота, а также протестирована его общая работоспособность, следует подумать о том, откуда бот будет брать информацию о таком быстро меняющемся явлении как погода.

В настоящее время есть большое количество сервисов, которые предоставляют своим пользователям доступ к своим данным (например, данным о погоде) в удобном формате API.

Одним из таких сервисов является openweathermap.org. Выбор пал именно на этот сервис, поскольку в отличии от своих конкурентов он предлагает до 1 миллиона бесплатных запрос к своему API, что более чем достаточно для целей создаваемого бота.

![12 img](images/12.jpg?raw=true "Title")

Рисунок 12 – Главная страница openweathermap.org

На данном ресурсе требуется получить пользовательский API  погоды, для того, чтобы в дальнейшем бот мог, используя этот API  получать данные о погоде. На рисунке №12 показана главная страница сайта openweathermap.org

Для этого, требуется зарегистрироваться, после чего сгенерировать API  в личном кабинете.

![13 img](images/13.jpg?raw=true "Title")

Рисунок 13 –  Генерация ключа

На рисунке №13 показана генерация нового API  ключа на странице личного кабинета сайта openweathermap.org

После успешного получение API  погоды, попробуем воспользоваться этим API. Давайте отправим запрос и посмотрим на те данные, которые даёт сервис.

![14 img](images/14.jpg?raw=true "Title")

Рисунок 14 – Получение данных о текущей погоде в Воронеже

На рисунке №14 показан массив, который мы получаем при отправке запроса к API  сайта openweathermap.org.

В полученном от сервиса массиве мы можем увидеть множество данных, среди которых есть:

* Температура

* Температура по ощущению

* Давление

* Скорость Ветра

* Влажность

**6. Создание информационной системы “Прогноз погоды”**

Поскольку максимальное количество запросов, которое бот может направить к API  openwathermap  ограниченно, имеет смысл задумается о системе кеширования данных о погоде. Для этих целей отлично подойдет база данных.

Бот будет обращается непосредственно к API только раз в 10 минут, при этом когда пользователи будут запрашивать у бота текущее состояние погоды, он будет брать сводку из таблицы базы данных, а не напрямую через API.

Данный механизм позволит значительно сократить количество обращений к API, что в свою очередь позволит обслужить больше пользователей, не выходя при этом за лимиты бесплатного плана API  openwathermap

  

**6.1** **Концептуальная модель базы данных**

![15 img](images/15.jpg?raw=true "Title")

Рисунок 15 – Концептуальная модель

На рисунке №15 показана концептуальная модель базы данных информационной системы. На основе данной модели происходит создание логической модели базы данных. Концептуальная модель помогает нам определить сущности и их атрибуты.

**6.2 Логическая модель**

![16 img](images/16.jpg?raw=true "Title")

Рисунок 16 – Логическая модель

На рисунке №16 показана логическая модель базы данных информационной системы. В дилогической модели представлены сущности и их атрибуты. Для атрибутов также указывается типы данных. На основе логической модели будет создана физическая т.е реальная база данных.

**6.3 Физическая модель**

![17 img](images/17.jpg?raw=true "Title")

Рисунок 17 – Физическая модель в СУБД MySQL

На рисунке №17 показана созданная при помощи СУБД MySQL  база данных.

Для завершения данного этапа, произведем подключение к созданной базе данных и выведем записанную в таблице запись в консоль.

![18 img](images/18.jpg?raw=true "Title")

Рисунок 18 – Проверка корректности базы данных

Как можно увидеть на рисунке №17, скрипт корректно выводит в консоль информацию из базы данных.

**7. Чат-бот прогноза погоды**

Теперь, используя знания, полученные в пунктах 1-6, мы можем создать бота, который будет сообщать своему пользователю текущую погоду в городе, который он указал.

Дополнительно бот сможет сообщать пользователю о допущенной опечатке в названии города, а также уведомлять его о возникновении ошибке в программном коде скрипта-обработчика (например, если скрипту не удалось подключится к базе данных)

![19 img](images/19.jpg?raw=true "Title")

Рисунок 19 – Программный код чат-бота

![20 img](images/20.jpg?raw=true "Title")

Рисунок 20 – Программный код чат-бота

![21 img](images/21.jpg?raw=true "Title")

Рисунок 21 – Программный код чат-бота

На рисунках 19-21 представлен программный создаваемого бота.

![22 img](images/22.jpg?raw=true "Title")

Рисунок 22 – Заполнение БД в ходе работы бота

На рисунке №22 показано то, как заполняется база данных информационной системы в ходе работы чат-бота.

  

Посмотрим на получившейся результат непосредственно в Telegram

![23 img](images/23.jpg?raw=true "Title")

Рисунок 23 – Пример работы с ботом

![24 img](images/24.jpg?raw=true "Title")

Рисунок 24 - Пример работы с ботом

На рисунках №23 и №24 представлен процесс взаимодействия с созданным ботом

**ЗАКЛЮЧЕНИЕ**

Результатом выполнения данной курсовой работы стал чат-бот на платформе мессенджера телеграмм, который умеет сообщать своему пользователю информацию о текущей погоде в интересующем его городе.

Бот имеет простой и понятный интерфейс взаимодействия, который состоит из команд, которые указываются через / (слеш) а также обычных текстовых сообщений.

Для создания данного бота был использован язык программирования Python. Данный языке программирования был из-за того, что он обладает большим количеством подключаемых пользовательских библиотек (в том числе для Python  написан целый ряд библиотек для работы с API  телеграмм), что позволяет значительно упростить процесс программирования, а также сэкономить время.

Также стоит отдельно отметить, что логика скрипта-обработчика была написана с идеей о user-friendly программе. Это значит, в процессе взаимодействия пользователя с программой (в данном случае ботом) все ошибки “ловятся” и обрабатываются. Благодаря этому факту даже при возникновении критических программных ошибок бот будет способен сообщить о них пользователю, а не просто завершать свою работу, оставляя при этом пользователя в недоумении.

В ходе выполнения данной курсовой работы были изучены и на практике протестированы следующие моменты:

* Создание и первоначальная настройка телеграмм бота

* Наделение телеграмм-бота различными функциональными возможностями (обработка пользовательских запросов и ответная реакция на них)

* Процесс работы с API  (как API  самого телеграмм, так и стронных сервисов)

* Способы работы форматом JSON

* Проектирование и разработка базы данных

* Механизмы связи Python скрипта и удаленной базы данных

* Базовые запросы языка SQL (Insert, Delete, Update)

**СПИСОК ИСПОЛЬЗУЕМЫХ ИСТОЧНИКОВ**

* Справочник по Bot API - Режим доступа: [https://tlgrm.ru/docs/bots/api](https://tlgrm.ru/docs/bots/api)

* PyMySQL 1.0.2 - Режим доступа: [https://pypi.org/project/PyMySQL/](https://pypi.org/project/PyMySQL/)

* OpenWeather. Weather forecasts, nowcasts and history in fast and elegant way - Режим  доступа: [https://openweathermap.org/](https://openweathermap.org/)

* MySQL Documentation - Режим  доступа: [https://dev.mysql.com/doc/](https://dev.mysql.com/doc/)

* Всё, о чём должен знать разработчик Телеграм-ботов - Режим доступа: [https://habr.com/ru/post/543676/](https://habr.com/ru/post/543676/)
