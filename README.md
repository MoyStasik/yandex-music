# Яндекс музыка

## 1. Тема и целевая аудитория

### Тема

**Яндекс музыка** - музыкальный стриминговый сервис компании Яндекс, позволяющий слушать музыкальные композиции, их подборки, альбомы и получать персональные рекомендации. 

### Целевая аудитория
+ Количество уникальных пользователей за месяц: 24млн [2] *
+ Количество посещений приложения в месяц: 81.6 миллионов [1]
+ Среднее количество страниц за посещение: 2.58 [1]
+ Среднее количество посещений одного пользователя за месяц: 21 день
+ Среднестатистический пользователь слушает около 20-30 треков в день
+ 28% пользователей слушают подкасты хотя бы раз в месяц [3]

*- Данные за декабрь 2024 года


**Веб-трафик по странам**

![image](https://github.com/user-attachments/assets/28474299-8247-4df0-a4bc-13c64783e4a7)
Рисунок 1 - веб-трафик по странам
**Демографические показатели посещаемости сайта**

![image](https://github.com/user-attachments/assets/cad65256-a375-4c5f-811c-ef3f374f86f8)
Рисунок 2 - демографические показатели посещения сайта

### Ключевой функционал
+ Регистрация/авторизация
+ Воспроизведение музыки
+ Добавление треков в плейлист, удаление из плейлиста, хранение плейлистов
+ Поиск исполнителя, трека, альбома
+ История прослушивания треков
+ Поиск музыки по жанру
+ прослушивание подкастов

### Ключевые продуктовые решения
+ Личные рекомендации под каждого пользователя
+ Выбор музыкального настроения, для воспроизведения соответствующей музыки

### Список используемых источников
1. [https://www.similarweb.com/ru/website/music.yandex.ru](https://www.similarweb.com/ru/website/music.yandex.ru)
2. [https://www.rbc.ru/technology_and_media/02/12/2024/674db2029a79474943d5748e](https://www.rbc.ru/technology_and_media/02/12/2024/674db2029a79474943d5748e)
3. [https://vc.ru/media/187539-auditoriya-podkastov-na-yandeksmuzyke-vyrosla-v-chetyre-raza-za-god-hotya-by-raz-v-mesyac-ih-slushayut-uzhe-28-podpischikov](https://vc.ru/media/187539-auditoriya-podkastov-na-yandeksmuzyke-vyrosla-v-chetyre-raza-za-god-hotya-by-raz-v-mesyac-ih-slushayut-uzhe-28-podpischikov)


## 2. Расчет нагрузки
### Продуктовые метрики
Таблица 1 - Количество активных пользователей
<table>
    <tr>
        <th>Период</th>
        <th>Количество пользователей</th>
    </tr>
    <tr>
        <td>День</td>
        <td>тк среднее количество посещений для пользователя за месяц это 21 день, то в среднем DAU = 21/30 * 24 = 16,8млн</td>
    </tr>
    <tr>
        <td>Месяц</td>
        <td>24 миллиона</td>
    </tr>
</table>

Таблица 2 - Средний размер хранилища пользователя
<table>
    <tr>
        <th>Тип хранилища</th>
        <th>Средний объем на 1 пользователя</th>
    </tr>
    <tr>
        <td>Плейлисты</td>
        <td>Проанализируем данные о количестве плейлистов в приложениях аналогах - спотифае, по данным википедии в спотифае около 2млрд плейлистов[6], учитывая, что в спотифае около 600млн уникальных пользователей за месяц, то можем грубо оценить, что на человека приходится 4 плейлиста, для нашего приложения возьмем такую же цифру, тк привычки пользователей похожи. Сколько треков в среднем на плейлист информация нигде не приводится, поэтому был проведен анализ среди знакомых, дальше будут приведена сумма треков в плелистах каждого из опрошенных: (200 + 250 + 354 + 81 + 1090 + 342 + 100 + 1038 + 34) / 9 = 387 треков в среднем пользователи добавляют в плейлисты, на 1 плейлист приходится около 387 / 4 = 97 треков, итого 1 плейлист состоит из обложки - размер фото около 30 КБ(данные из девтулз), название плейлиста - 30 байт, хранение одной песни в виде id и другой метаинформации занимает около 0.1Кб (данные из devtools). Итого: 4*(30Кбайт + 30 байт + 0,1Кбайт) + 387*0,1Кбайт = 0,12МБ + 0,04МБ = 0,16МБ </td>
    </tr>
  <tr>
        <td>История прослушиваний</td>
        <td>Данных о количество уникальных треков, которые слушает пользователь за год в публичном доступе нет, но тк есть информация что в день среднестатистический пользователь слушает около 30 разных треков и в месяц пользователь проводит на сайте 21 из 30 дней, то можем посчитать по верхней границе, если 80 процентов треков, которые пользователь слушает не повторяются, то за год пользователь в среднем слушает 30 * 21 * 12 * 0,8 = 6048 уникальных треков. Для хранения истории необходимо 0.1Кбайт метаифнормации для 1 трека. Итого:  6048 * 0,1Кбайт = 0,6МБ</td>
    </tr>
</table>

Таблица 3 - Действия пользователей по типам
<table>
    <tr>
        <th>Тип действия</th>
        <th>Среднее количество в день</th>
    </tr>
    <tr>
        <td>Воспроизведение музыки</td>
        <td>Среднестатистический пользователь прослушивает в день около 30 треков, так как всего в сутки 16,8 млн пользователей, то всего в день прослушивается 16,8 * 30 = 504 млн</td>
    </tr>
  <tr>
        <td>Авторизация</td>
        <td> 24 млн / 30 = 800 тыс</td>
    </tr>
    <tr>
        <td>Регистрация</td>
        <td> 12 тыс</td>
    </tr>
    <tr>
        <td>Добавление/удаление треков в/из плейлист</td>
        <td> 1,554 млн</td>
    </tr>
    <tr>
        <td>Прослушивание треков из истории</td>
        <td> В среднем пользователь 1 раз включает трек из истории прослушиваний, всего в сутки 16,8млн юзеров, тогда всего обращений к истории треков - 16,8 * 1 = 16,8 млн </td>
    </tr>
    <tr>
        <td>Поиск исполнителя, трека, альбома</td>
        <td> Среднее количество поисков за день - 57,6 млн</td>
    </tr>
    <tr>
        <td>Поиск треков по жанру</td>
        <td> 140 тыс </td>
    </tr>
    <tr>
        <td>Прослушивание подкастов</td>
        <td>в неделю 14% пользователей слушают подкасты хотя бы раз[2], из этих данных можем узнать, что 24*0,14 = 3,36млн в неделю хотя бы раз слушают подкасты, тк данных о количестве в сутки нет, то можем взять, что около 80 процентов из них слушают подкасты ежедневно, тогда 3,36 * 0,8 = 2,688 млн</td>
    </tr>
</table>

### Технические метрики
Битрейт песен возьмем - 128 Кбит/c.[3]

В среднем размер треков составляет 3 минуты 17 секунд[7], тогда с битрейтом 128Кбит/c размер одного трека = (197с × 128Кбит/с) / 8 / 1024 = 3,06Мб и обложка/картинка 20КБайт, итого 3,08МБ.[1]

В среднем подкасты длятся от 30 до 60минут[8], возьмем среднюю длительность 45 минут, подкасты как и треки будем хранить с битрейтом 128Кбит/c, тогда они будут занимать около 3,06МБ * 15 = 46МБ памяти + 20КБ на обложку, итого 46,02МБ на 1 подкаст.

Таблица 4 - Размер хранения в разбивке по типам данных
<table>
    <tr>
        <th>Тип хранения</th>
        <th>Размер</th>
    </tr>
    <tr>
        <td>Пользователи</td>
        <td>из таблицы 2, на одного пользователя необходимо (0,16 + 0,6) = 0,76 МБ, тогда на 24 млн пользователей, 17,4ТБ</td>
    </tr>
    <tr>
        <td>Треки</td>
        <td>на 1 трек 3,08 МБ, всего 76 млнов треков, тогда для хранения всех понадобится 223,2ТБ[5]</td>
    </tr>
    <tr>
        <td>Подкасты</td>
        <td>В Яндекс музыке около 25,9тыс подкастов, тогда все подкасты будут занимать около 1,12ТБ[4]</td>
    </tr>
</table>

Таблица 5 - Сетевые метрики
<table>
    <tr>
        <th>Тип действия</th>
        <th>Пиковое потребление в течение суток, Гбит/с</th>
        <th>Суммарный суточный, Гбайт/сутки</th>
        <th>RPS (средний)</th>
        <th>RPS (пиковый)</th>
    </tr>
    <tr>
        <td>Воспроизведение музыки</td>
        <td>140 000 * 128Кбит/с = 17 920 000Кбит/c = 17,1</td>
        <td>16,8млн * 60мин * 60с * 128 Кбит/c / 2^23 = 922 852</td>
        <td>Всего 16,8 млн юзеров, тк в сутки примерно 60 минут средний пользователь слушает музыку, и запрос на новый чанк случается раз в ~ 10 секунд, те ~ 6 раз в минуту, то средний рпс будет, rps = 16,8млн * 60мин * 6 / 86400с = 70 000</td>
        <td>В пик около 140тыс пользователей слушает музыку одновременно, rps = 140 000 </td>
    </tr>
    <tr>
        <td>Авторизация</td>
        <td>14 * 16Кбайт / 2^20 = 0,0002</td>
        <td>Сетевой трафик одного запроса - 16Кбайт, тогда 800тыс * 16Кбайт / 2^20 = 12,2</td>
        <td>Всего 24млн месячных пользователей, среднестатистический пользователь заходит в музыку 21 день из 30, авторизационный токен необходимо обновлять 1 раз в месяц, тогда средний рпс = 24млн / 30 / 86400 = 9,3</td>
        <td>Пиковый рпс на авторизацию = 14</td>
    </tr>
    <tr>
        <td>Регистрация</td>
        <td>0,20 * 16Кбайт / 2^20 = 0,0000032</td>
        <td>Всего 12 000 * 16Кбайт / 2^20 = 0,18</td>
        <td>Месячный рост новых пользователей составляет около 1,5%, тогда в месяц новых пользователей 24млн * 0,015 = 360 000, в день получается 12 000 новых пользователей, тогда средний рпс будет = 12 000 / 86400 = 0,14</td>
        <td>Пик рпс = 0,20</td>
    </tr>
    <tr>
        <td>Добавление/удаление треков в/из плейлист</td>
        <td>Пиковый rps = 30 * 1,2 Кбайт / 2^20 = 0,00003</td>
        <td>Размер одного запроса - 1,2Кбайт (информация из dev tools) => всего 1,554млн * 1,2Кбайт / 2^20 = 1,78</td>
        <td>Средний рпс = 1,554млн / 86400 = 18</td>
        <td>Пиковый рпс = 30</td>
    </tr>
    <tr>
        <td>Получение треков из истории</td>
        <td>291 * 15,5Кбайт / 2^20 = 0,004</td>
        <td>16,8млн * 1 * 15,5Кбайт (информация из dev tools) / 2^20 = 248,3</td>
        <td>rps = 16,8млн * 1 / 86400 = 194</td>
        <td>Пиковый rps = 291</td>
    </tr>
    <tr>
        <td>Поиск исполнителя, трека, альбома</td>
        <td>1000 * 15Кбайт / 2^20 = 0,014</td>
        <td>57,6млн * 15Кбайт (информация из dev tools) / 2^20 = 824</td>
        <td>rps = 57,6млн / 86400 = 667</td>
        <td>Пиковый rps = 667 * 1,5 = 1000</td>
    </tr>
    <tr>
        <td>Поиск треков по жанру</td>
        <td>2,5 * 210Кбайт / 2^20 = 0,0005</td>
        <td>140тыс * 210Кбайт (информация из dev tools) / 2^20 = 28</td>
        <td>rps = 140тыс / 86400 = 1,62</td>
        <td>Пиковый rps = 2,5</td>
    </tr>
    <tr>
        <td>Прослушивание подкастов</td>
        <td>22 400 * 128Кбит/с / 2^20 = 2,73</td>
        <td>2,688млн * 60мин * 60 * 128Кбит/c / 2^23 = 147 656</td>
        <td>rps = 2,688млн * 60мин(средняя длительность прослушивания подкастов)[2] * 6 / 86400 = 11 200</td>
        <td>Пиковый рпс = 11 200 * 2 = 22 400</td>
    </tr>
</table>

### Список используемых источников
1. [https://yandex.ru/company/news/03-21-08-2024](https://yandex.ru/company/news/03-21-08-2024)
2. [https://vc.ru/media/187539-auditoriya-podkastov-na-yandeksmuzyke-vyrosla-v-chetyre-raza-za-god-hotya-by-raz-v-mesyac-ih-slushayut-uzhe-28-podpischikov](https://vc.ru/media/187539-auditoriya-podkastov-na-yandeksmuzyke-vyrosla-v-chetyre-raza-za-god-hotya-by-raz-v-mesyac-ih-slushayut-uzhe-28-podpischikov)
3. [https://www.amplifier.ru/news/2024/06/12/yandeks-muzyka-110624.html#:~:text=Пользователям%20будут%20доступны%20три%20опции,без%20потерь%20в%20формате%20Lossless.](https://www.amplifier.ru/news/2024/06/12/yandeks-muzyka-110624.html#:~:text=Пользователям%20будут%20доступны%20три%20опции,без%20потерь%20в%20формате%20Lossless.)
4. [https://yandex.ru/company/researches/2021/podcasts#:~:text=В%20каталоге%20Яндекс.Музыки%2011,запускалось%20более%20500%20новых%20проектов.](https://yandex.ru/company/researches/2021/podcasts#:~:text=В%20каталоге%20Яндекс.Музыки%2011,запускалось%20более%20500%20новых%20проектов.)
5. [https://ru.wikipedia.org/wiki/Яндекс_Музыка#:~:text=По%20состоянию%20на%202023%20год,пользуется%20около%2020%20млн%20человек.](https://ru.wikipedia.org/wiki/Яндекс_Музыка#:~:text=По%20состоянию%20на%202023%20год,пользуется%20около%2020%20млн%20человек.)
6. [https://ru.wikipedia.org/wiki/Spotify#:~:text=В%20настоящее%20время%20в%20«Спотифай,как%20пользователями%2C%20так%20и%20кураторами.](https://ru.wikipedia.org/wiki/Spotify#:~:text=В%20настоящее%20время%20в%20«Спотифай,как%20пользователями%2C%20так%20и%20кураторами.)
7. [https://daily.afisha.ru/news/58899-srednyaya-dlina-pesen-s-godami-sokraschaetsya/#](https://daily.afisha.ru/news/58899-srednyaya-dlina-pesen-s-godami-sokraschaetsya/#)
8. [https://roistat.com/rublog/podkast/#:~:text=В%20среднем%20подкасты%20длятся%20от%2030%20минут%20до%201%20часа.](https://roistat.com/rublog/podkast/#:~:text=В%20среднем%20подкасты%20длятся%20от%2030%20минут%20до%201%20часа.)

## 3. Глобальная балансировка нагрузки
### Функциональное разбиение по доменам
Высокая нагрузка на сайт Яндекс Музыка исходит только с прослушиванием музыки, то не имеет смысла выделять много функциональных доменов, поэтому принято решение выделить один функциональный домен для авторизации пользователей и домен для действий связанных с музыкой:
+ music.yandex.ru - данный домен будет использоваться для прослушивание музыки, подкастов, добавление/удаление треков в плейлист, история пользователя и поиск треков/исполнителей
+ auth.music.yandex.ru - данный домент будет служить для авторизации и регистрации пользователей Яндекс Музыки

### Расположение ДЦ
Учитывая веб трафик пользователей яндекс музыки на рисунке 3 и учитывая магистральные сети связи в России[1], можно выделить следующие города с ДЦ:
+ Москва
+ Санкт-Петербург
+ Минск
+ Астана
+ Краснодар
+ Казань
+ Новосибирск
+ Хабаровск
![image](https://github.com/user-attachments/assets/28474299-8247-4df0-a4bc-13c64783e4a7)
Рисунок 3 - веб трафик по странам

**Пояснение:**

ДЦ в Минске будет обслуживать пользователей из Беларуси и из Европы(Нидерланды и другие).

Необходимо поставить ДЦ, который будет обслуживать пользователей из Казахстана и Узбекистана, поэтому было решено поставить ДЦ в Астане. 

### Расчет распределение запросов из секции "Расчет нагрузки" по типам запросов по датацентрам
+ auth.music.yandex.ru - данных запросов в день относительно немного, к тому же данный запрос не требует слишком быстрого ответа, поэтому датацентров, обслуживающих этот домен, можно расположить мало: в Москве и Санкт-Петербурге.
+ music.yandex.ru - запросы на этом домене требуют больше всего трафика, поэтому все датацентры будут обслуживать этот домен

Авторизация/регистрация требует 9,44 запросов в секунду, из этого можно построить таблицу 6.

Таблица 6 - Распределение запроса "Авторизация/регистрация" по датацентрам
<table>
    <tr>
        <th>Датацентры</th>
        <th>Средний рпс</th>
    </tr>
    <tr>
        <td>Москва</td>
        <td>5,64</td>
    </tr>
    <tr>
        <td>Санкт-Петербург</td>
        <td>3,8</td>
    </tr>
</table>

Воспроизведение музыки требует 70 000 запросов в секунду, из этого можно построить таблицу 7.

Таблица 7 - Распределение запросов "воспроизведение музыки", "воспроизведение подкастов", "поиск" и др по датацентрам
<table>
    <tr>
        <th>Датацентры</th>
        <th>Средний рпс</th>
    </tr>
    <tr>
        <td>Москва</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Санкт-Петербург</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Минск</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Астана</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Краснодар</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Казань</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Новосибирск</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Хабаровск</td>
        <td>-</td>
    </tr>
</table>

### Схема DNS балансировки
Тк ДЦ географически удалены друг от друга, будет логично использовать Geo-based DNS. Однако из-за того, что почти все ДЦ расположены в России могут возникать проблемы с резолвингом. Поэтому в данном случае решил воспользоваться Latency-based DNS, тк при загрузке музыки необходима скорость, обеспечивающаяся за счет наименьшего latency.

### Схема Anycast балансировки
Тк больше всего пользователей яндекс музыки находится в Москве и Санкт-Петербурге, то ДЦ расположенные в этих городах будут испытывать наибольшую нагрузку. Поэтому будет разумно объединить эти ДЦ под одним IP и использовать BGP Anycast. Для балансированки нагрузки между ними можно использовать hash.

### Список используемых источников
1. [https://www.comnews.ru/content/230456/2023-12-20/2023-w51/1180/magistralnye-seti-svyazi-rossii-2023#map-section](https://www.comnews.ru/content/230456/2023-12-20/2023-w51/1180/magistralnye-seti-svyazi-rossii-2023#map-section)
