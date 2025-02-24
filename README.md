# Яндекс музыка

## 1. Тема и целевая аудитория

### Тема

**Яндекс музыка** - музыкальный стриминговый сервис компании Яндекс, позволяющий слушать музыкальные композиции, их подборки, альбомы и получать персональные рекомендации. 

### Целевая аудитория
+ Количество уникальных пользователей за месяц: 24млн [2] *
+ Количество посещений приложения в месяц: 81.6 миллионов [1]
+ Среднее время пребывания пользователя на сайте: 3 минуты 56 секунд [1]
+ Среднее количество страниц за посещение: 2.58 [1]
+ Среднее количество посещений одного пользователя за месяц: 21 день
+ Среднестатистический пользователь слушает около 20-30 треков в день
+ 28% пользователей слушают подкасты хотя бы раз в месяц [3]

*- Данные за декабрь 2024 года


**Веб-трафик по странам**

![image](https://github.com/user-attachments/assets/28474299-8247-4df0-a4bc-13c64783e4a7)

**Демографические показатели посещаемости сайта**

![image](https://github.com/user-attachments/assets/cad65256-a375-4c5f-811c-ef3f374f86f8)

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
        <td>14,4 миллиона</td>
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
        <td>в среднем на пользователя 8 плейлистов, в среднем пользователи добавляют 1000 треков в плейлисты, 
          на 1 плейлист приходится около 125 треков, итого 1 плейлист состоит из обложки - размер фото около 3 МБ, название плейлиста - 30 байт, хранение одной песни в виде id - 8 байт. Итого: 8*(3МБ + 30 байт) + 1000*8байт = 32МБ </td>
    </tr>
  <tr>
        <td>История прослушиваний</td>
        <td>За год пользователь в среднем слушает 3300 уникальных треков для хранения истории необходимо 8байт памяти для id 1 трека. Итого:  3300 * 8байт = 25,8МБ</td>
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
        <td>Среднестатистический пользователь прослушивает в день около 30 треков, так как всего в сутки 14,4 млн пользователей, то всего в день прослушивается 14,4 * 30 = 432 млн</td>
    </tr>
  <tr>
        <td>Авторизация/регистрация</td>
        <td> 38,88 млн</td>
    </tr>
    <tr>
        <td>Добавление/удаление треков в/из плейлист</td>
        <td> 1,554 млн</td>
    </tr>
    <tr>
        <td>Прослушивание треков из истории</td>
        <td> В среднем пользователь 1 раз включает трек из истории прослушиваний, всего в сутки 14,4млн юзеров, тогда всего прослушанных треков из истории - 14,4 * 1 = 14,4 млн </td>
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
        <td>в день 7% пользователей слушают подкасты, 14,4 * 0,07 = 1,008 млн </td>
    </tr>
</table>

### Технические метрики
1 трек хранится в трек режимах качества: превосходное(lossless), оптимальное и экономичное, в первом режиме трек занимает около 40 МБ, в оптимальном режиме 7 МБ, в Экономичном около 3 МБ, итого на 1 трек приходится 50 МБ данных для хранения.

В среднем подкасты длятся около 30 мин и занимают около 70 МБ памяти.
Таблица 4 - Размер хранения в разбивке по типам данных
<table>
    <tr>
        <th>Тип хранения</th>
        <th>Размер</th>
    </tr>
    <tr>
        <td>Пользователи</td>
        <td>из таблицы 2, на одного пользователя необходимо (25,8 + 32) = 57,8 МБ, тогда на 24 млн пользователей, 1322ТБ</td>
    </tr>
    <tr>
        <td>Треки</td>
        <td>на 1 трек 50 МБ, всего 76 млнов треков, тогда для хранения всех понадобится 3624ТБ</td>
    </tr>
    <tr>
        <td>Подкасты</td>
        <td>В Яндекс музыке около 165тыс подкастов, тогда все подкасты будут занимать около 11ТБ</td>
    </tr>
</table>

Битрейт песен лежит в диапазоне от 24 до 320 Кбит/c. Для вычислений возьмем средний - 128 Кбит/c.
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
        <td>10 000 000 * 128Кбит/с = 1 280 000 000Кбит/c = 1220</td>
        <td>14,4млн * 148мин * 60с * 128 Кбит/c = 15 609 375</td>
        <td>Всего 14,4 млн юзеров, тк в сутки примерно 148 минут средний пользователь слушает музыку, и запрос на новый чанк случается раз в ~ 10 секунд, те ~ 6 раз в минуту, то средний рпс будет, rps = 14,4млн * 148мин * 6 / 86400с = 148 000</td>
        <td>В пик около 10 млн пользователей слушает музыку одновременно, rps = 10 000 000 </td>
    </tr>
    <tr>
        <td>Авторизация/регистрация</td>
        <td>100тыс * 16Кбайт / 2^20 = 1,5</td>
        <td>Сетевой трафик одного запроса - 16Кбайт, тогда 38,88млн * 16Кбайт / 2^20 = 592</td>
        <td>Всего 38,88млн авторизаций/регистраций, тогда средний рпс = 38,88 / 86400 = 449</td>
        <td>Пиковый рпс на авторизацию = 100 000</td>
    </tr>
    <tr>
        <td>Добавление/удаление треков в/из плейлист</td>
        <td>Пиковый rps = 100 * 5,2 Кбайт / 2^20 = 0,0005</td>
        <td>Размер одного запроса - 5,2Кбайт => всего 1,554млн * 5,2Кбайт / 2^20 = 7,7</td>
        <td>Средний рпс = 1,554млн / 86400 = 18</td>
        <td>Пиковый рпс = 100</td>
    </tr>
    <tr>
        <td>Прослушивание треков из истории</td>
        <td>201 000 * 128Кбит/c / 2^20 = 24,5</td>
        <td>14,4млн * 3мин(средняя длительность трека) * 60с * 128Кбит/c / 2^20 = 316 406</td>
        <td>rps = 14,4млн * 3мин * 6 / 86400 = 3000</td>
        <td>Пиковый rps = 3000 * 67 = 201 000</td>
    </tr>
    <tr>
        <td>Поиск исполнителя, трека, альбома</td>
        <td>2000 * 1500Кбайт / 2^20 = 2,86</td>
        <td>57,6млн * 1500Кбайт / 2^20 = 82 397</td>
        <td>rps = 57,6млн / 86400 = 667</td>
        <td>Пиковый rps = 2000</td>
    </tr>
    <tr>
        <td>Поиск треков по жанру</td>
        <td>100 * 1500Кбайт / 2^20 = 0,14</td>
        <td>140тыс * 1500Кбайт / 2^20 = 200</td>
        <td>rps = 140тыс / 86400 = 1,62</td>
        <td>Пиковый rps = 100</td>
    </tr>
    <tr>
        <td>Прослушивание подкастов</td>
        <td>211 050 * 128Кбит/с / 2^20 = 25,8</td>
        <td>1,008млн * 45мин * 60 * 128Кбит/c / 2^20 = 332 226</td>
        <td>rps = 1,008млн * 45мин(средняя длительность прослушивания подкастов) * 6 / 86400 = 3150</td>
        <td>Пиковый рпс = 3150 * 67 = 211 050</td>
    </tr>
</table>
