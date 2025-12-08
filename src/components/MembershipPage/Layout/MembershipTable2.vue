<template>
  <div class="membership-table-2">
    <h2 class="title">Абонемент по времени</h2>
    <table class="table-1" id="priceTable2">
        <thead>
            <tr>
                <th>Тип карты</th>
                <th>12 месяцев</th>
                <th>6 месяцев</th>
                <th>3 месяца</th>
                <th>1 месяц</th>
            </tr>
        </thead>
        <tbody>
          <tr>
            <td>Индивидуальная,<br>полная без ограничения<br>в посещении / 8:00 – 23:00</td>
            <td>18000<br>(+200 мин. солярия)</td>
            <td>12000</td>
            <td>7000</td>
            <td>2500</td>
          </tr>
          <tr>
            <td>Индивидуальная,<br>дневная / 8:00 – 17:00</td>
            <td>—</td>
            <td>9500</td>
            <td>5500</td>
            <td>2000</td>
          </tr>
        </tbody>
    </table>
  </div>
</template>

<script setup>
  import { onMounted, nextTick } from "vue";

  onMounted(async () => {
    await nextTick();   // гарантирует что таблица уже в DOM

    const table = document.getElementById("priceTable2");
    if (!table) {
      console.warn("Таблица не найдена");
      return;
    }

    const thead = table.querySelector("thead");
    if (!thead) {
      console.warn("Нет THEAD в таблице");
      return;
    }

    table.addEventListener("mousemove", (e) => {
      const cell = e.target.closest("td, th");
      if (!cell) return;

      const row = cell.parentElement;
      const colIndex = cell.cellIndex;

      // удалить подсветку
      table.querySelectorAll(".highlight-row-start, .highlight-head")
          .forEach(el => el.classList.remove("highlight-row-start", "highlight-head"));

      // первая ячейка строки
      if (row.parentElement.tagName === "TBODY") {
        row.children[0]?.classList.add("highlight-row-start");
      }

      // заголовок колонки
      const headRow = thead.rows[0];
      const headCell = headRow?.children[colIndex];
      headCell?.classList.add("highlight-head");
    });

    table.addEventListener("mouseleave", () => {
      table.querySelectorAll(".highlight-row-start, .highlight-head")
          .forEach(el => el.classList.remove("highlight-row-start", "highlight-head"));
    });
  });
</script>

<style scoped>
  .highlight-row-start {
    color: var(--color-orange) !important;
  }

  .highlight-head {
    color: var(--color-orange) !important;
  }
  * {
    border-spacing: 0px;
  }
  .title {
    text-align: center;
    font-size: 25px;
    font-weight: bold;
    height: 100px;
  }
  .membership-table-2 {
    padding-top: 30px;
    padding-left: 150px;
    padding-right: 150px;
  }
  .table-1 {
    width: 100%;

    > thead {
      height: 60px;
      border-bottom: 3px solid var(--color-orange);
    }
    > thead > tr > th {
      width: 300px;
      border-bottom: 2px solid var(--color-grey)
    }
    > tbody > tr > td:not(:first-child) {
      text-align: center;
    }
    > tbody > tr > td:first-child {
      font-weight: bolder;
    }
    > tbody > tr {
      height: 100px;

      > td:hover {
        font-weight: bolder !important;
      }
    }
  }
</style>