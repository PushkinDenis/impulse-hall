<template>
  <div class="membership-table-1">
    <h2 class="title">Абонементы</h2>
    <table class="table-1" id="priceTable1">
        <thead>
            <tr>
                <th>Кол-во занятий</th>
                <th>1 тренировка</th>
                <th>4 тренировки</th>
                <th>8 тренировок</th>
                <th>12 тренировок</th>
            </tr>
        </thead>
        <tbody>
          <tr>
            <td>Персональный тренинг с инструктором</td>
            <td>700 руб.</td>
            <td>2600 руб.<br>(действителен в <br>течении 3 недель)</td>
            <td>5200 руб.<br>(действителен в <br>течении 6 недель)</td>
            <td>7200 руб.<br>(действителен в <br>течении 10 недель)</td>
          </tr>
          <tr>
            <td>Самостоятельные тренировки в тренажерном зале</td>
            <td>250 руб.</td>
            <td>—</td>
            <td>1500 руб.<br>(действителен в <br>течении 30 дней)</td>
            <td>2000 руб.<br>(действителен в <br>течении 45 дней)</td>
          </tr>
          <tr>
            <td>Зал групповых программ</td>
            <td>300 руб.</td>
            <td>—</td>
            <td>2000 руб.<br>(действителен в <br>течении 30 дней)</td>
            <td>2750 руб.<br>(действителен в <br>течении 45 дней)</td>
          </tr>
        </tbody>
    </table>
  </div>
</template>

<script setup>
  import { onMounted, nextTick } from "vue";

  onMounted(async () => {
    await nextTick();   // гарантирует что таблица уже в DOM

    const table = document.getElementById("priceTable1");
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
    font-weight: bold;
    height: 100px;
  }
  .membership-table-1 {
    padding-top: 100px;
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