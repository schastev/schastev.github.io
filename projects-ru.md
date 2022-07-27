<!-- TOC start -->
- Учебные проекты
  * Разработка
    + [Дипломная работа на курсе CS50](#-cs50)
  * Автоматизированное тестирование
    + [1. Дипломная работа на курсе "Тестировщик ПО"](#1-)
    + [2. SQL](#2-sql)
    + [3. Page Objects, Behaviour Driven Development ](#3-page-objects-behaviour-driven-development)
    + [4. Patterns](#4-patterns)
    + [5. Selenide](#5-selenide)
    + [6. Тестирование веб-интерфейсов, Selenium и Selenide](#6-selenium-selenide)
  * Инструментарий для автоматизированного тестирования
    + [1. Docker, Docker Compose ](#1-docker-docker-compose)
    + [2. Репортинг: Report Portal](#2-report-portal)
  * Артефакты тестирования
    + [1. Составление плана автоматизации](#1--1)
<!-- TOC end -->
<!-- TOC --><a name="-"></a>
# Учебные проекты

<!-- TOC --><a name=""></a>
## Разработка

<!-- TOC --><a name="-cs50"></a>
### Дипломная работа на курсе CS50
<!-- TOC --><a name="--1"></a>
#### Краткое описание задачи
Разработать приложение для Android, помогающее кофейням (или любым другим заведениям, где применимы такие бонусные рпограммы) отслеживать, какой клиент сколько напитков заказал, чтобы предлагать им бесплатные напитки после покупки определенного количества напитков.

<!-- TOC --><a name="--2"></a>
#### Краткое описание решения
Приложение на Java, хранящее данные о клиентах в БД Room. Доступно на русском и английском языках.

Главный экран приложения позволяет искать клиентов по последним цифрам номера телефона и смотреть всех зарегистрированных клиентов. 
Экран добавления нового клиента позволяет ввести имя и телефон клиента и опционально сразу начислить ему один напиток. Вводимые в поля данные проходят валидацию. 

Экран информации о пользователе позволяет посмотреть, сколько у пользователя начислено напитков, зарегистрировать бесплатный напиток, отредактировать номер телефона, по нажатию переключателя также можно посмотреть даты регистрации и последнего визита. Приложение также отображает уведомления, если клиент не посещал заведение дольше заданного количества дней.

Экран настроек может быть защищен паролем, который можно задать там же. Там же можно обозначить, через сколько дней должно отображаться уведомление о том, что клиент давно не приходил, и сколько напитков нужно заказать для получения бесплатного. Этот экран также позволяет удалить запись о клиенте из БД.

[Полный список фич приложения](https://github.com/schastev/cupCounter/blob/master/features%20(ru).md)

<!-- TOC --><a name="--3"></a>
#### Использованный стек
* JUnit
* Gradle
* JavaFaker

<!-- TOC --><a name="-httpsgithubcomschastevcupcounter"></a>
#### [Репозиторий с кодом приложения](https://github.com/schastev/cupCounter)

<!-- TOC --><a name="--4"></a>
## Автоматизированное тестирование

<!-- TOC --><a name="1-"></a>
### 1. Дипломная работа на курсе "Тестировщик ПО"
<!-- TOC --><a name="--5"></a>
#### Краткое описание задачи
Автоматизированное тестирование комплексного сервиса, взаимодействующего с СУБД и API Банка: страницы покупки (по дебетовой или кредитной карте) тура по данным карты.

<!-- TOC --><a name="-httpsgithubcomnetology-codeqa-diploma"></a>
#### [Полное описание задачи](https://github.com/netology-code/qa-diploma)

<!-- TOC --><a name="--6"></a>
#### Краткое описание решения
Составлен план автоматизированного тестирования, включающий перечни автоматизируемых сценариев, необходимых инструментов, возможных рисков, оценки трудо- и времязатрат.
Проведены проверки правильности фиксации данных об оставленных заявках в базе данных. Протестирована устойчивость фронтенда приложения к вводу невалидных данных в форму.
Все компоненты тестируемой системы (приложение, БД и заглушка) разворачиваются в контейнерах Docker во время тестирования при помощи testcontainers. Тесты, предполагающие проверку взаимодействия приложения с БД, реализованы как шаблоны тестов, работающие с двумя разными БД (MySQL и PostgreSQL).
По результатам тестирования и автоматизации подготовлены отчеты с общими рекомендациями и анализом проделанной работы.

<!-- TOC --><a name="--7"></a>
#### Использованный стек
* JUnit
* Gradle
* Lombok
* Selenide
* JavaFaker
* DBUtils
* Testcontainers
* Allure

<!-- TOC --><a name="-httpsgithubcomschastevaqa-diploma"></a>
#### [Репозиторий с решением](https://github.com/schastev/aqa-diploma)

<!-- TOC --><a name="2-sql"></a>
### 2. SQL
<!-- TOC --><a name="--8"></a>
#### Краткое описание задачи
Настройка, запуск и тестирование приложения с БД (с подгрузкой схемы при запуске) в контейнере Docker/Docker-compose.
Тестирование фронтендовой части входа в личный кабинет пользователя с кодом авторизации. 
Тестирование входа, введения кода авторизации и переводов с карты на карту при помощи REST-Assured.

<!-- TOC --><a name="-httpsgithubcomnetology-codeaqa-homeworkstreemastersql"></a>
#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/sql)

<!-- TOC --><a name="--9"></a>
#### Краткое описание решения
Проведено позитивное и негативное тестирование разнообразных сценариев входа в систему и перевода с одной карты на другую.
Тестирование фронтенда реализовано при помощи Page Objects. При тестировании API были применены параметризованные тесты.
Подключена система CI (Appveyor).

<!-- TOC --><a name="--10"></a>
#### Использованный стек
* JUnit
* Gradle
* Lombok
* Selenide
* REST-assured
* Gson
* JavaFaker
* DBUtils
* Testcontainers

<!-- TOC --><a name="-1-httpsgithubcomschastevaqa3-2-ex1-2-httpsgithubcomschastevaqa3-2-ex2"></a>
#### Репозитории с решением: [1 (тестирование входа)](https://github.com/schastev/aqa3-2-ex1), [2 (тестирование входа и переводов)](https://github.com/schastev/aqa3-2-ex2)

<!-- TOC --><a name="3-page-objects-behaviour-driven-development"></a>
### 3. Page Objects, Behaviour Driven Development 
<!-- TOC --><a name="--11"></a>
#### Краткое описание задачи
Тестирование перевода с карты на карту при помощи Page Objects и [Akita](https://github.com/alfa-laboratory/akita).

<!-- TOC --><a name="-httpsgithubcomnetology-codeaqa-homeworkstreemasterbdd"></a>
#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/bdd)

<!-- TOC --><a name="--12"></a>
#### Краткое описание решения
Подготовлены Page Objects для всех страниц тестируемого приложения, проведено негативное и позитивное тестирование функции перевода с карты на карту.
Реализованы кастомные шаги для заданного тест-кейса при помощи Akita.
Подключена система CI (Appveyor).

<!-- TOC --><a name="--13"></a>
#### Использованный стек
* JUnit
* Gradle
* Lombok
* Selenide
* Akita

<!-- TOC --><a name="-1-page-objectshttpsgithubcomschastevaqa2-4-ex1-2-akitahttpsgithubcomschastevaqa2-4-ex2"></a>
#### Репозитории с решением: [1 (Page Objects)](https://github.com/schastev/aqa2-4-ex1), [2 (Akita)](https://github.com/schastev/aqa2-4-ex2)

<!-- TOC --><a name="4-patterns"></a>
### 4. Patterns
<!-- TOC --><a name="--14"></a>
#### Краткое описание задачи
Автоматизация тестирования функции переназначения встречи с представителем банка.
Тестирование функции создания пользователя через API и входа в личный кабинет через web-интерфейс.

<!-- TOC --><a name="-httpsgithubcomnetology-codeaqa-homeworkstreemasterpatterns"></a>
#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/patterns)

<!-- TOC --><a name="--15"></a>
#### Краткое описание решения
Проведено заданное тестирование web-интерфейса с использованием класса - генератора тестовых данных и data-класса.
Проведено тестирование входа в личный кабинет при различных параметрах учетной записи через web-интерфейс с предварительным созданием необходимой учетной записи.
Подключена система CI (Appveyor).

<!-- TOC --><a name="--16"></a>
#### Использованный стек
* JUnit
* Gradle
* Lombok
* Selenide
* JavaFaker
* REST-assured
* Gson

<!-- TOC --><a name="-1-web-httpsgithubcomschastevaqa2-3-ex1-2-webapihttpsgithubcomschastevaqa2-3-ex2"></a>
#### Репозитории с решением: [1 (web-интерфейс)](https://github.com/schastev/aqa2-3-ex1), [2 (web+API)](https://github.com/schastev/aqa2-3-ex2)

<!-- TOC --><a name="5-selenide"></a>
### 5. Selenide
<!-- TOC --><a name="--17"></a>
#### Краткое описание задачи
Позитивное тестирование формы заказа доставки карты: проверка соответствия данных, принимаемых полями формы, заданным требованиям. Тестирование работы виджета "календарь" и текстового поля с функцией автозаполнения.

<!-- TOC --><a name="-httpsgithubcomnetology-codeaqa-homeworkstreemasterselenide"></a>
#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/selenide)
<!-- TOC --><a name="--18"></a>
#### Краткое описание решения
Проведено позитивное тестирование заданного сценария и функционала поля с автозаполнением и календаря.
Подключена система CI (Appveyor).

<!-- TOC --><a name="--19"></a>
#### Использованный стек
* JUnit
* Gradle
* Selenide

<!-- TOC --><a name="-httpsgithubcomschastevaqa2-2"></a>
#### [Репозиторий с решением](https://github.com/schastev/aqa2-2)

<!-- TOC --><a name="6-selenium-selenide"></a>
### 6. Тестирование веб-интерфейсов, Selenium и Selenide
<!-- TOC --><a name="--20"></a>
#### Краткое описание задачи
Позитивное тестирование заданного сценария использования формы для заказа банковской карты; негативное тестирование отдельных полей с целью проверки их устойчивости к невалидным данным.
<!-- TOC --><a name="-httpsgithubcomnetology-codeaqa-homeworkstreemasterweb"></a>
#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/web)
<!-- TOC --><a name="--21"></a>
#### Краткое описание решения
Выполнено заданное тестирование сценария и валидации полей с использованием Selenide и Selenium. Подключена система CI (Appveyor).

<!-- TOC --><a name="--22"></a>
#### Использованный стек
* JUnit
* Gradle
* Selenide
* Selenium

<!-- TOC --><a name="-1-selenidehttpsgithubcomschastevaqa2-1-selenide-2-seleniumhttpsgithubcomschastevaqa2-1-selenium"></a>
#### Репозитории с решением: [1 (Selenide)](https://github.com/schastev/aqa2-1-selenide), [2 (Selenium)](https://github.com/schastev/aqa2-1-selenium)


<!-- TOC --><a name="--23"></a>
## Инструментарий для автоматизированного тестирования

<!-- TOC --><a name="1-docker-docker-compose"></a>
### 1. Docker, Docker Compose 
<!-- TOC --><a name="--24"></a>
#### Краткое описание задачи
Настройка контейнера с БД посредством `docker-compose.yml`; создание своего образа на базе openjdk с конфигурацией в `Dockerfile` и `docker-compose.yml`.

<!-- TOC --><a name="-httpsgithubcomnetology-codeaqa-homeworkstreemasterdocker"></a>
#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/docker)

<!-- TOC --><a name="--25"></a>
#### Краткое описание решения
Произведена настройка запуска БД в контейнере таким образом, чтобы тестируемое приложение могло с ней взаимодействовать. Образ приложения сконфигурирован в `Dockerfile` и собирается через `docker-compose.yml`. 

<!-- TOC --><a name="-1-docker-composehttpsgithubcomschastevaqa-3-1-ex1-2-httpsgithubcomschastevaqa-3-1-ex2"></a>
#### Репозитории с решением: [1 (docker-compose)](https://github.com/schastev/aqa-3-1-ex1), [2 (контейнеризация приложения)](https://github.com/schastev/aqa-3-1-ex2)

<!-- TOC --><a name="2-report-portal"></a>
### 2. Репортинг: Report Portal
<!-- TOC --><a name="--26"></a>
#### Краткое описание задачи
Интегрировать в существующий проект системы генерации отчетов Allure, Report Portal.

<!-- TOC --><a name="-httpsgithubcomnetology-codeaqa-homeworkstreemasterreporting"></a>
#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/reporting)

<!-- TOC --><a name="--27"></a>
#### Краткое описание решения
В созданный ранее репозиторий добавлена система отчетности Allure путем добавления зависимости в настройки проекта.

<!-- TOC --><a name="--28"></a>
#### Использованный стек
* JUnit
* Gradle
* Allure

<!-- TOC --><a name="-1-allurehttpsgithubcomschastevaqa4-1-ex1-2-report-portal-wip"></a>
#### Репозитории с решением: [1 (Allure)](https://github.com/schastev/aqa4-1-ex1), [2 (Report Portal - WIP)]


<!-- TOC --><a name="--29"></a>
## Артефакты тестирования

<!-- TOC --><a name="1--1"></a>
### 1. Составление плана автоматизации
<!-- TOC --><a name="--30"></a>
#### Краткое описание задачи
Составить план тестирования записи на курс обучения.

<!-- TOC --><a name="-httpsgithubcomnetology-codeaqa-homeworkstreemastersummary"></a>
#### [Полное описание задачи](https://github.com/netology-code/aqa-homeworks/tree/master/summary)

<!-- TOC --><a name="--31"></a>
#### Краткое описание решения
Составлен план автоматизированного тестирования, включающий перечни автоматизируемых сценариев, необходимых инструментов, разрешений/данных/допусков, возможных рисков, оценки трудо- и времязатрат.

<!-- TOC --><a name="-httpsgithubcomschastevaqa4-2"></a>
#### [Репозиторий с решением](https://github.com/schastev/aqa4-2)
