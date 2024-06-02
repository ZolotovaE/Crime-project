# Crime-project
Какие данные используем и почему их выбрали: 
Изначально мы хотели найти данные, показывающие преступность с разной стороны: найти факторы, влияющие на количество преступлений в разных областях, какие бывают преступления, в какие годы и в каких странах, из-за чего такой высокий или низкий процент преступности, на что может повлиять сама преступность и тд. Преступность до сих пор очень актуальный показатель, который можно изучать, чтобы определить как и на что он сможет влиять в долгосрочном периоде и нужно (если да, то как) ли его снижать, как это отразится на экономической обстановке в стране, сможем ли мы ее улучшить или наоборот, более благоприятный экономический климат будет способствовать снижению преступности. 

1. Основной датасет https://hubofdata.ru/dataset/crime-rate
2. Парсинг 2 таблиц https://proza.ru/2023/04/01/1612?ysclid=lw0jh2jc99760797084
3. Разводы  https://russia.duck.consulting/maps/98.csv
5. Безработица https://rosstat.gov.ru/storage/mediabank/Trud-1_15-s.xlsx
6. Возможно будут использованы далее (+создание совместных таблиц и их визуализация+анализ): 
7. Число людей за границей бедности https://rosstat.gov.ru/storage/mediabank/tab_2-3.xlsx
8. Численность населения https://rosstat.gov.ru/storage/mediabank/Popul_1897+.xls
9. Наркотики https://www.protivnarko.ru/v-rossii-sostavlen-antinarkoticheskiy-reyting-regionov/?ysclid=lusnzm32z651405951

   
Парсинг данных ютуб-канала:
Изначально мы пробовали спарсить данные через чтение кода сайта, но достать данные полноценно не получалось, выходили отрывки.
Дальше, мы самостоятельно изучили вопрос и нашли информацию про API, далее мы создали ключ API и получили данные о некоторых видео с канала, но спарсить полноценный сет не вышло, тогда мы обратились к ассистенту и пробовали сами копаться в интернете, но к сожалению спарсить больше данных не вышло

В нашей работе представлены несколько таблиц, а затем и их визуализация, чтобы увидеть (количественно и качественно) есть ли влияние разных переменных на преступность. Мы предполагаем, что изменение демографического поведения людей, становление высокой безработицы в регионах и высокий уровень разводов относительно браков может способствовать повышение уровня преступности и определенных нападений (подробнее в основном датасете). Не менее важным изучить, в каких областях и странах, какие виды преступности присутствуют и есть ли корреляция между экономической обстановкой (годами - подъем/спад в РФ, например, в 90-е или 2008-2010 года) и миграционным потоком, который в свою очередь также мжет быть зависим от уровня занятости/безработицы в стране и оказывать влияние на неконтролируюмую преступность  снижение безопасности в регионах. Что в экономическом смысле ухудшает положение людей, их жизнь и здоровье, а также влияет на социально-психологическую состовляющую. Вследствие чего, люди боятся и начинают уезжать из региона, перестают работать и происходит "замкнтый круг". Действительно ли это так?

Промежуточный результат: Виолончель (как и ящик с усами) пока не построили, так как для этого надо таблицу перестроить в другой вид (создать отдельно колонку с дифференцированным жанром, нам было бы прикольно такое сделать по видам преступлений, пока в раздумьях как в принципе переформатировать в необходимый формат).
С облаками рассеивания можно сделать до и после какого-то момента, пока пытаемся определить границы и необходимость данного графика. Анализирауем дальше таблицы, какие графики необходимо идейно взять, планируем еще доделать анализ, доописывать уже имеющиеся данные и чуть точнее подумать над прогнозами. 

Гипотезы о закономерностях на основе имеющихся графиков/данных: (до промежуточного дедлайна)
1. В период с 2003 по 2020 год мы можем увидеть общую тенденцию на снижение количества преступлений к ближе к текущему моменту времени
2. Раз в год можно увидеть резкий скачок количества и затем после этого резкое падение
Гипотеза: это может быть связано с закрытием годовой отчётности на местах, благодаря чему возбуждается большее количество преступлений
3. На графике мы можем увидеть, что сильная существует прямая связь между общим количеством преступлений и преступлениями, относящимися к категориям тяжких или особо тяжких
4. Частота количества преступлений, причинивших особо крупный ущерб не напрямую зависит от их количества, так как мы можем увидеть на гистограмме два максимума: абсолютный и локальный, причём около себя они организуют два различных распределения со смещением влево и вправо


Гипотезы (итоговая версия)

1. Мы считали, что существует связь между количеством преступлений и миграцией, но на уровне общего количества преступлений связи не было выявлено, однако вот, что было замечено: существует положительная связь между миграционным приростом и количеством преступлений, связанных с наркотиками и экстремизмом, а также отрицательная связь между миграционном приростом и количеством убийств, изналований, а также преступлениями террористического характера
Посчитано это было с помощью приведения от ежемесячного формата общей, главной, таблицы к ежегодному, а также добавления к нему переформатированной прежде таблицы с миграцией

2. Наши гипотезы насчёт количества разводов и безработицы не удалось проверить ввиду того, что данные представлены в различных форматах, поэтому привести их к общему виду не удалось

Какие переменные хотели бы создать, новые признаки из имеющихся (ориентировочно): 
1) Доля особо тяжких преступлений во всех преступлениях (покажет, правда ли именно самые тяжкие преступления составляют большой процент и влияют на остальные показатели или большое количество, о мелких преступлений более значительно для общества).
2) Индекс безопасности (комбинация данных о количестве преступлений, уровне безработицы, миграционном потоке и других факторах, который позволит оценить общую безопасность региона).
3) Индекс социальной напряженности (данные о разводах + безработица + уровень общей преступности, влияющие на социальную обстановку)
Оценка корреляции между различными переменными (например, между уровнем безработицы и уровнем преступности) может помочь выявить ключевые факторы, влияющие на преступность.

Какие гипотезы будем проверять математически (с помощью чего, как подтвердим в теории):
Определим нулевую (отсутствие эффекта) и основную гипотезы (наличие различий). Определим уровень значимости (обычно берут 0.05), который покажет вероятность ошибки первого рода при отклонении нулевой гипотезы. Для сравнения средних значений можно использовать t-тест. Сравним полученное p-значение с уровнем значимости. Если p-value меньше уровня значимости, отвергнем нулевую гипотезу в пользу основной. Если нулевая гипотеза будет отвергнута, это может свидетельствовать о наличии статистически значимых различий между группами или переменными.

Какое МЛ (какая метрика, какую переменную предсказываем, для чего, что покажет, что хотели бы увидеть): 
Модели линейной регрессии или классификации могут помочь выявить влияние факторов (безработицы) на уровень преступности.
Кластерный анализ поможет выделить группы регионов с похожими характеристиками и уровнем преступности. Модель ЛогЛосс.
