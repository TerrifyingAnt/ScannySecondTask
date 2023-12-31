
# Status

Предложение. Ожидает одобрения.

# Context

Для планирования и контроля достижения целей по линейке товаров SKU и принятия управленческих решений необходим расчет индивидуальных показателей эффективности (KPI), который будет предоставлен производителю на портале.

## Use-case

<details>
<summary>KPI-100: Просмотр индивидуальных KPI по визитам для производителя</summary>

***KPI-110***
- При просмотре страницы визита производителя важно видеть достижение следующих целей:

***KPI-111***

- Для каждого товара SKU производителя, учитываемого в целях,

***KPI-112***

- Совокупно для всех товаров бренда производителя,

***KPI-113***

- Совокупно для производителя в целом.

</details>

<details>

<summary>KPI-200: Просмотр агрегированных индивидуальных KPI на странице "Оперативная аналитика" (дашборд) для производителя</summary>

</details>


## Требования для расчета и агрегации метрик

**Общая информация**

Для каждой цели определены даты начала и окончания действия, которые ограничивают использование соответствующих входных данных. Сравнение фактических данных с плановыми производится только в пределах указанного периода.

***1. OSA - Наличие ассортимента по матрице (для всех категорий)***

- Расчет для товара SKU: Данный показатель рассчитывается только для товаров, участвующих в целях. Если товар имеет хотя бы один фэйсинг, показатель равен 100%, в противном случае 0%. Если товар не участвует в целях, значение показателя считается "пустым".
- Агрегация по бренду: Среднее значение для всех товаров бренда SKU.
- Агрегация по производителю: Среднее значение для всех товаров производителя SKU.
- Цели для OSA:

| Магазин | SKU | Дата начала | Дата окончания |
| ------ | ------ | ------ | ------ |
| + | + | + | + |	

Таблица содержит:
- Магазин: Идентификатор или название магазина, для которого устанавливаются цели OSA.
- SKU: Идентификатор товара (Stock Keeping Unit), для которого устанавливаются цели OSA.
- Дата начала: Дата, с которой начинаются действовать установленные цели OSA.
- Дата окончания: Дата, до которой действуют установленные цели OSA.

В данной таблице используются символы "+", чтобы указать, что значения для каждого столбца должны быть заполнены.  Эти цели OSA задаются для определенных магазинов,  и конкретных SKU товаров, а также устанавливают период действия этих целей.

***2. Фэйсинги (для всех категорий)***

- Расчет для товара SKU: Сумма фэйсингов товара SKU / цель по фэйсингам товара SKU (значение может быть больше 100%).
- Агрегация по бренду: Сумма фэйсингов для всех товаров бренда / сумма целей по фэйсингам для бренда (значение может быть больше 100%).
- Агрегация по производителю: Сумма фэйсингов для всех товаров производителя / сумма целей по фэйсингам для бренда (значение может быть больше 100%).
- Цели для фэйсингов:

| Магазин | Тип оборудования |  SKU | Количество фэйсингов | Дата начала | Дата окончания |
| ------ | ------ | ------ | ------ | ------ | ------ |
| + | + | + | + | + | + |					

Таблица содержит:
- Магазин: Идентификатор или название магазина, для которого устанавливаются цели фэйсингов.
- Тип оборудования: Указывается тип оборудования, на котором происходит размещение товаров.
- SKU: Идентификатор товара, для которого устанавливаются цели фэйсингов.
- Количество фэйсингов: Указывается требуемое количество фэйсингов для данного товара.
- Дата начала: Дата, с которой начинают действовать установленные цели фэйсингов.
- Дата окончания: Дата, до которой действуют установленные цели фэйсингов.

В данной таблице используются символы "+", чтобы указать, что значения для каждого столбца должны быть заполнены. Эти цели фэйсингов задаются для определенных магазинов, типов оборудования и конкретных SKU товаров. Цели фэйсингов определяют требуемое количество фэйсингов для каждого SKU, а также устанавливают период действия этих целей.

***3. Наличие ценников***

- Расчет для товара SKU: Присутствие хотя бы одной ссылки на ценник для любого фэйсинга товара.
- Агрегация по бренду: Процент товаров SKU бренда, для которых присутствуют ценники.
- Агрегация по производителю: Процент товаров производителя SKU, для которых присутствуют ценники.
- Цель - 100%

***4. Уровень выкладки***

**Определения**

Зона выкладки (допустимые номера полок):
- Зона 1 (полки 2 и 3 сверху)
- Зона 2 (все полки, кроме 2 и 3, самая верхняя и самая нижняя)
- Зона 3 (самая верхняя и самая нижняя)

**Расчет**

- Расчет для товара SKU: Процент фэйсингов, находящихся в указанной зоне.
- Агрегация по бренду: Среднее значение для всех товаров бренда SKU.
- Агрегация по производителю: Среднее значение для всех товаров производителя SKU.
- Цели для выкладки:

| Магазин | Тип оборудования |  SKU | Зона выкладки | Дата начала | Дата окончания |
| ------ | ------ | ------ | ------ | ------ | ------ |
| + | + | + | + | + | + |						

Таблица содержит:
- Магазин: Идентификатор или название магазина, для которого устанавливаются цели выкладки.
- Тип оборудования: Указывается тип оборудования, на котором происходит размещение товаров.
- SKU: Идентификатор товара (Stock Keeping Unit), для которого устанавливаются цели выкладки.
- Зона выкладки: Указывается требуемая зона, в которой должны находиться фэйсинги (например, зона 1, зона 2, зона 3).
- Дата начала: Дата, с которой начинают действовать установленные цели выкладки.
- Дата окончания: Дата, до которой действуют установленные цели выкладки.

В данной таблице используются символы "+", чтобы указать, что значения для каждого столбца должны быть заполнены. Цели выкладки задаются для конкретных магазинов, типов оборудования и SKU товаров. Цели определяют требуемую зону выкладки для каждого SKU и устанавливают период действия этих целей.


***5. Бренд-блок***

- Выбираются все товары бренда в категории.
- Соединяются товары в граф (?).
- Проверяется количество товаров внутри графа (?), не относящихся к выбранной комбинации бренда/категории. Если количество таких товаров превышает 1, то бренд-блок отсутствует. Можно использовать проверку на количество товаров (больше 2).
- Для двух товаров условием бренд-блока является их размещение рядом на одной полке. Для одного товара бренд-блока не существует.

# Decision

 1. После получения целей от клиента, операционная команда обрабатывает их и формирует данные (в формате xlsx) для сохранения в базе данных с учетом внутренних параметров (sku_id, store_id, equipment_type_id).
 2. Данные сохраняются в базе данных с помощью соответствующего скрипта.
 3. Пользователь должен быть привязан к производителю в базе данных.
 4. Если у пользователя-производителя есть цели (в таблице целей в базе данных), на портале на странице визита может быть отображена информация о выполнении целей в разрезе SKU-бренд-производитель в отдельном блоке с кастомными KPI.
 5. Изучается возможность использования представлений для агрегирования информации по кастомным KPI.

# Глоссарий

- KPI - ключевой показатель эффективности (Key Performance Indicator) - метрика, используемая для измерения и оценки выполнения целей и успеха бизнеса.
- SKU - артикул товара (Stock Keeping Unit) - уникальный идентификатор, присвоенный каждому отдельному товару в инвентаре.
- OSA - наличие ассортимента (On-Shelf Availability) - метрика, используемая для измерения наличия товаров на полке магазина.
- Фэйсинг - размещение товара на полке (Facings) - количество видимых экземпляров товара на полке магазина.
- Дашборд - информационная панель (Dashboard) - визуальный инструмент, предоставляющий сводную информацию и аналитику в удобной форме.
- Ценник - ярлык с ценой товара (Price Tag) - информационная метка, указывающая цену товара.
- Выкладка - расположение товаров на полке магазина (Merchandising) - организация и представление товаров для привлечения внимания покупателей.
- Бренд-блок - группировка товаров одного бренда на полке (Brand Block) - размещение товаров одного бренда вместе для повышения узнаваемости и эффективности продаж.
- Расчет - процесс определения значений метрик и показателей на основе имеющихся данных и целей.
- Агрегация - сводный расчет значений метрик для группы товаров, брендов или производителей.
- БД - база данных (Database) - организованная коллекция данных, доступная для хранения и управления.
- Портал - веб-сайт или приложение, предоставляющее доступ к информации и функциональности для конкретного пользователя или группы пользователей.
- Разрез - разделение данных или информации на отдельные категории или аспекты для более детального анализа.
- XLSX - формат файлов электронных таблиц Microsoft Excel.
- Скрипт - программа или команды, выполняющие автоматические операции или обработку данных.
- Производитель - компания или организация, производящая товары или продукцию.
- Вью - представление (View) - виртуальная таблица или представление данных, полученных из одной или нескольких таблиц базы данных.
- Метрика - это качественный или количественный показатель, который отражает ту или иную характеристику и уровень успешности продукта.
