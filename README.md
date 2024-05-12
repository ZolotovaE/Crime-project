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

В нашей работе представлены несколько таблиц, а затем и их визуализация, чтобы увидеть (количественно и качественно) есть ли влияние разных переменных на преступность. Мы предполагаем, что изменение демографического поведения людей, становление высокой безработицы в регионах и высокий уровень разводов относительно браков может способствовать повышение уровня преступности и определенных нападений (подробнее в основном датасете). Не менее важным изучить, в каких областях и странах, какие виды преступности присутствуют и есть ли корреляция между экономической обстановкой (годами - подъем/спад в РФ, например, в 90-е или 2008-2010 года) и миграционным потоком, который в свою очередь также мжет быть зависим от уровня занятости/безработицы в стране и оказывать влияние на неконтролируюмую преступность  снижение безопасности в регионах. Что в экономическом смысле ухудшает положение людей, их жизнь и здоровье, а также влияет на социально-психологическую состовляющую. Вследствие чего, люди боятся и начинают уезжать из региона, перестают работать и происходит "замкнтый круг". Действительно ли это так?

Гипотезы о закономерностях на основе имеющихся графиков/данных: 

Какие переменные хотели бы создать, новые признаки из имеющихся (ориентировочно): 
1) Доля особо тяжких преступлений во всех преступлениях (покажет, правда ли именно самые тяжкие преступления составляют большой процент и влияют на остальные показатели или большое количество, о мелких преступлений более значительно для общества).
2) Индекс безопасности (комбинация данных о количестве преступлений, уровне безработицы, миграционном потоке и других факторах, который позволит оценить общую безопасность региона).
3) Индекс социальной напряженности (данные о разводах + безработица + уровень общей преступности, влияющие на социальную обстановку)
Оценка корреляции между различными переменными (например, между уровнем безработицы и уровнем преступности) может помочь выявить ключевые факторы, влияющие на преступность.

Какие гипотезы будем проверять математически (с помощью чего, как подтвердим в теории):
Определени нулевую (отсутствие эффекта) и основной гипотезы (наличие различий). Определим уровень значимости (обычно берут 0.05), который покажет вероятность ошибки первого рода при отклонении нулевой гипотезы. Для сравнения средних значений можно использовать t-тест. Сравним полученное p-значение с уровнем значимости. Если p-value меньше уровня значимости, отвергнем нулевую гипотезу в пользу основной. Если нулевая гипотеза будет отвергнута, это может свидетельствовать о наличии статистически значимых различий между группами или переменными.

Какое МЛ (какая метрика, какую переменную предсказываем, для чего, что покажет, что хотели бы увидеть): 
Модели линейной регрессии или классификации могут помочь выявить влияние факторов (безработицы) на уровень преступности.
Кластерный анализ поможет выделить группы регионов с похожими характеристиками и уровнем преступности. Модель ЛогЛосс.
