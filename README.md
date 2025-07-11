# Investment Comparison Project

## Описание проекта

Этот проект позволяет сравнивать доходность трех типов инвестиций — банковского вклада, криптовалюты (например, Bitcoin) и акций (например, Apple) — за заданный период времени. Проект включает:

- Загрузку исторических данных о ценах акций, криптовалют, курсе USD/RUB и ключевой ставке.
- Обработку данных: агрегацию по месяцам, расчет накоплений и конвертацию в рубли.
- Визуализацию: графики сравнения доходности на логарифмической шкале.
- Итоговый расчет доходности для каждого типа инвестиций.

Проект реализован в виде Jupyter Notebook (`Main.ipynb`) на языке Python.

- Скачать архив проекта с [Яндекс.Диска](https://disk.yandex.ru/d/ieoORjeb83uKpw).

---

## Требования

### Необходимые зависимости

Для работы проекта установите следующие Python-библиотеки. Вы можете установить их с помощью `pip`:

```bash
pip install pandas numpy matplotlib seaborn
```

---

## Установка и запуск

1. **Клонируйте репозиторий**:

   ```bash
   git clone <repository-url>
   cd investment-comparison
   ```

2. **Установите зависимости**:

   ```bash
   pip install -r requirements.txt
   ```

3. **Запустите Jupyter Notebook**:

   ```bash
   jupyter notebook
   ```

4. Откройте файл `Main.ipynb` в Jupyter Notebook и выполните ячейки последовательно (Shift + Enter).

---

## Настройка параметров

Перед запуском вы можете изменить следующие параметры в ячейке №3 файла `Main.ipynb`:

- `start_date`: Начальная дата периода анализа (формат: `YYYY-MM-DD`, например, `'2016-09-01'`).
- `end_date`: Конечная дата периода анализа (формат: `YYYY-MM-DD`, например, `'2017-08-31'`).
- `cryptocurrency`: Название криптовалюты для анализа (например, `'bitcoin'`). Доступные варианты:
  - tezos, binance-coin, eos, bitcoin, tether, xrp, bitcoin-cash, stellar, litecoin, ethereum, cardano, bitcoin-sv.
- `daily_investment`: Ежедневная сумма инвестиций в рублях (например, `1000`).
- `stocks`: Тикер акции для анализа (например, `'aapl'`). Доступные варианты:
  - aapl, amzn, avgo, cost, gld, goog, googl, jnj, jpm, ma, msft, nflx, nvda, orcl, pg, qqq, spy, tsla, unh, v, voo, wmt, xom.

---

## Интерпретация результатов

После выполнения всех ячеек в `Main.ipynb` вы получите два основных результата: график сравнения доходности и итоговый отчет в формате Markdown. Вот как их интерпретировать:

### 1. График сравнения доходности (comparison_plot.png)
- **Описание**: График показывает динамику накопленной стоимости инвестиций для трех активов: банковского вклада, криптовалюты (например, Bitcoin) и акций (например, Apple).
- **Оси**:
  - **Ось X**: Даты (период от `start_date` до `end_date`).
  - **Ось Y**: Сумма в рублях (накопленная стоимость инвестиций), представленная в логарифмической шкале для учета значительных различий в доходности.
- **Линии**:
  - **Зеленая линия**: Банковский вклад.
  - **Оранжевая линия**: Криптовалюта.
  - **Синяя линия**: Акции.
- **Что означает**: График позволяет визуально сравнить, как росла стоимость каждого актива с течением времени. Логарифмическая шкала помогает увидеть изменения даже при большой разнице в доходности (например, между вкладом и криптовалютой).

### 2. Итоговый отчет
Итоговый отчет выводится в формате Markdown и содержит следующие данные:

- **Общая сумма инвестиций**: Сколько рублей было инвестировано за весь период (ежедневная сумма × количество дней).
- **Количество дней**: Длительность периода инвестирования.
- **Сравнение доходности**:
  - Для каждого актива (вклад, криптовалюта, акции) указаны:
    - **Итоговая сумма**: Сколько рублей накопилось к концу периода.
    - **Доходность**: Процентный рост инвестиций относительно вложенной суммы.
  - Дополнительно:
    - Для криптовалюты: количество накопленных монет (например, `3.86 bitcoin`).
    - Для акций: количество накопленных акций (например, `31` акций Apple).

#### Пример итогового отчета:
```
Общая сумма инвестиций (руб.): 253000 руб.
Количество дней: 253 дня

Сравнение доходности:
- Вклад:
  - Итоговая сумма: 261443 руб.
  - Доходность: 3.34%
- Bitcoin:
  - Итоговое количество монет: 3.86 bitcoin
  - Итоговая сумма: 1053339 руб.
  - Доходность: 316.34%
- Apple:
  - Итоговое количество акций: 31
  - Итоговая сумма: 293842 руб.
  - Доходность: 16.14%
```

#### Как интерпретировать:
- **Доходность**: Показывает, насколько выросли ваши инвестиции. Например:
  - Доходность 3.34% для вклада означает, что вы заработали 3.34% сверх вложенной суммы.
  - Доходность 316.34% для Bitcoin означает, что ваши инвестиции выросли более чем в 3 раза.
- **Сравнение активов**:
  - В приведенном примере Bitcoin показал наивысшую доходность (316.34%), что делает его самым прибыльным активом за выбранный период.
  - Акции Apple показали доходность 16.14%, что выше, чем у вклада (3.34%), но значительно ниже, чем у Bitcoin.
- **Итоговая сумма**: Отражает, сколько денег вы бы имели на конец периода, если бы инвестировали в каждый актив. Например, инвестиции в Bitcoin принесли бы 1,053,339 рублей, в то время как вклад — только 261,443 рубля.

#### Что учитывать
- **Риск**: Проект не учитывает риск (волатильность цен). Криптовалюты, такие как Bitcoin, могут быть очень волатильными, что означает высокий риск потерь.
- **Комиссии и налоги**: Расчеты не включают биржевые комиссии и налоги, которые могут снизить реальную доходность.
- **Исторические данные**: Результаты зависят от выбранного периода. В другие периоды (например, во время кризисов) доходность может быть иной.