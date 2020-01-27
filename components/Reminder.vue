<template>
    <div class="reminder">
      <div class="reminder__top">
        <span class="top__text">Встреча с клиентом</span>
        <div class="top__time">
          <i class="el-icon-time"></i>
          <span>13:00</span>
        </div>
      </div>
      <div class="reminder__content">
        <i class="el-icon-location-information"></i>
        <span>г. Оренбург, ул. Степная, д. 118</span>
      </div>
    </div>
</template>

<script>
    export default {
        name: "Reminder"
    }
</script>

<style lang="scss">
  .reminder {
    display: flex;
    flex-direction: column;
    width: 100%;
    background: var(--color-background);
    padding: 7px 20px 9px 12px;
    border-left: 2px solid var(--color-red);
    color: var(--color-text);

    .reminder__top {
      display: flex;
      justify-content: space-between;
      align-items: center;

      .top__time {
        color: var(--color-red);
        display: flex;
        align-items: center;

        i {
          margin-right: 10px;
          font-size: 20px;
        }

        span {
          line-height: 16px;
        }
      }
    }

    .reminder__content {
      margin-top: 6px;
      display: flex;
      align-items: center;

      i {
        font-size: 20px;
        color: var(--color-primary-lighting);
        margin-right: 10px;
      }
    }
  }
</style>
