<!-- TOC start -->
- Тестовые задания
  * Автотестирование
    + [Автотесты Яндекса на Python с применением паттерна Page Object](#2022-07)
- Учебные проекты
  * Разработка
    + [Дипломная работа на курсе CS50](#cs50)
  * Автотестирование
    + [Дипломная работа на курсе "Тестировщик ПО"](#qa-diploma)
    + [SQL](#sql)
    + [Page Objects, Behaviour Driven Development ](#po-bdd)
  * Инструментарий для автоматизированного тестирования
    + [Docker, Docker Compose ](#docker)
  * Артефакты тестирования
    + [Составление плана автоматизации](#test-plan)
<!-- TOC end -->



# Тестовые задания

## Автотестирование

<!-- TOC --><a name="2022-07"></a>
### Автотесты Яндекса на Python с применением паттерна Page Object

#### Краткое описание задачи

Автоматизировать два тест-кейса, используя Python 3, Selenium Webdriver, Pytest с применением паттерна Page Object.

#### [Автоматизированные сценарии](https://github.com/schastev/2022_07_test_assignment/blob/main/test-cases.md)


#### Использованный стек
Python3, Selenium, Splinter, Stere, Pytest, Requests, Pillow, Allure

#### [Репозиторий с решением](https://github.com/schastev/2022_07_test_assignment)



# Учебные проекты

## Разработка

<!-- TOC --><a name="cs50"></a>
### Дипломная работа на курсе CS50

#### Краткое описание задачи
Разработать приложение для Android, помогающее кофейням (или любым другим заведениям, где применимы такие бонусные рпограммы) отслеживать, какой клиент сколько напитков заказал, чтобы предлагать им бесплатные напитки после покупки определенного количества напитков.

#### Краткое описание решения
Приложение на Java, хранящее данные о клиентах в БД Room. Доступно на русском и английском языках.

Главный экран приложения позволяет искать клиентов по последним цифрам номера телефона и смотреть всех зарегистрированных клиентов. 
Экран добавления нового клиента позволяет ввести имя и телефон клиента и опционально сразу начислить ему один напиток. Вводимые в поля данные проходят валидацию. 

Экран информации о пользователе позволяет посмотреть, сколько у пользователя начислено напитков, зарегистрировать бесплатный напиток, отредактировать номер телефона, по нажатию переключателя также можно посмотреть даты регистрации и последнего визита. Приложение также отображает уведомления, если клиент не посещал заведение дольше заданного количества дней.

Экран настроек может быть защищен паролем, который можно задать там же. Там же можно обозначить, через сколько дней должно отображаться уведомление о том, что клиент давно не приходил, и сколько напитков нужно заказать для получения бесплатного. Этот экран также позволяет удалить запись о клиенте из БД.

[Полный список фич приложения](https://github.com/schastev/cupCounter/blob/master/features%20(ru).md)

#### Использованный стек
JUnit, Gradle, Room, JavaFaker, Espresso, Mockito, Allure

#### [Репозиторий с кодом приложения](https://github.com/schastev/cupCounter)


## Автотестирование

<!-- TOC --><a name="qa-diploma"></a>
### Дипломная работа на курсе "Тестировщик ПО"

#### Краткое описание задачи
Автоматизированное тестирование комплексного сервиса, взаимодействующего с СУБД и API Банка: страницы покупки (по дебетовой или кредитной карте) тура по данным карты.

#### [Полное описание задачи](https://github.com/netology-code/qa-diploma)

#### Краткое описание решения
Составлен план автоматизированного тестирования, включающий перечни автоматизируемых сценариев, необходимых инструментов, возможных рисков, оценки трудо- и времязатрат.
Проведены проверки правильности фиксации данных об оставленных заявках в базе данных. Протестирована устойчивость фронтенда приложения к вводу невалидных данных в форму.
Все компоненты тестируемой системы (приложение, БД и заглушка) разворачиваются в контейнерах Docker во время тестирования при помощи testcontainers. Тесты, предполагающие проверку взаимодействия приложения с БД, реализованы как шаблоны тестов, работающие с двумя разными БД (MySQL и PostgreSQL).
По результатам тестирования и автоматизации подготовлены отчеты с общими рекомендациями и анализом проделанной работы.

#### Использованный стек
JUnit, Gradle, Lombok, Selenide, JavaFaker, DBUtils, Testcontainers, Allure

#### [Репозиторий с решением](https://github.com/schastev/aqa-diploma)

<!-- TOC --><a name="sql"></a>
### SQL

#### Краткое описание задачи
Настройка, запуск и тестирование приложения с БД (с подгрузкой схемы при запуске) в контейнере Docker/Docker-compose.
Тестирование фронтендовой части входа в личный кабинет пользователя с кодом авторизации. 
Тестирование входа, введения кода авторизации и переводов с карты на карту при помощи REST-Assured.

#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/sql)

#### Краткое описание решения
Проведено позитивное и негативное тестирование разнообразных сценариев входа в систему и перевода с одной карты на другую.
Тестирование фронтенда реализовано при помощи Page Objects. При тестировании API были применены параметризованные тесты.
Подключена система CI (Appveyor).

#### Использованный стек
JUnit, Gradle, Lombok, Selenide, REST-assured, Gson, JavaFaker, DBUtils, Testcontainers

#### Репозитории с решением: [тестирование входа](https://github.com/schastev/aqa3-2-ex1-sql), [тестирование входа и переводов](https://github.com/schastev/aqa3-2-ex2-sql)

<!-- TOC --><a name="po-bdd"></a>
### Page Objects, Behaviour Driven Development 

#### Краткое описание задачи
Тестирование перевода с карты на карту при помощи Page Objects и [Akita](https://github.com/alfa-laboratory/akita).

#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/bdd)

#### Краткое описание решения
Подготовлены Page Objects для всех страниц тестируемого приложения, проведено негативное и позитивное тестирование функции перевода с карты на карту.
Реализованы кастомные шаги для заданного тест-кейса при помощи Akita.
Подключена система CI (Appveyor).

#### Использованный стек
JUnit, Gradle, Lombok, Selenide, Akita

#### Репозитории с решением: [Page Objects](https://github.com/schastev/aqa2-4-ex1), [Akita](https://github.com/schastev/aqa2-4-ex2-bdd)


## Инструментарий для автоматизированного тестирования

<!-- TOC --><a name="docker"></a>
### Docker, Docker Compose 

#### Краткое описание задачи
Настройка контейнера с БД посредством `docker-compose.yml`; создание своего образа на базе openjdk с конфигурацией в `Dockerfile` и `docker-compose.yml`.

#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/docker)

#### Краткое описание решения
Произведена настройка запуска БД в контейнере таким образом, чтобы тестируемое приложение могло с ней взаимодействовать. Образ приложения сконфигурирован в `Dockerfile` и собирается через `docker-compose.yml`. 

#### Репозитории с решением: [docker-compose](https://github.com/schastev/aqa-3-1-ex1), [контейнеризация приложени](https://github.com/schastev/aqa-3-1-ex2)


## Артефакты тестирования

<!-- TOC --><a name="test-plan"></a>
### Составление плана автоматизации

#### Краткое описание задачи
Составить план тестирования записи на курс обучения.

#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/summary)

#### Краткое описание решения
Составлен план автоматизированного тестирования, включающий перечни автоматизируемых сценариев, необходимых инструментов, разрешений/данных/допусков, возможных рисков, оценки трудо- и времязатрат.

#### [Репозиторий с решением](https://github.com/schastev/aqa4-2-test-plan)
