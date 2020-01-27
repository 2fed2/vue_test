<template>
  <client-only>
    <el-calendar v-model="value" class="calendar"/>
  </client-only>
</template>

<script>
  export default {
    name: "Calendar",
    data() {
      return {
        value: new Date()
      }
    }
  }
</script>

<style lang="scss">
  .calendar {
    background: var(--color-background);

    .el-calendar__header {
      background: var(--color-secondary);
      padding: 0 0 10px;
      border: none;

      .el-calendar__title {
        color: var(--color-text);
      }

      .el-calendar__button-group {
        .el-button-group {
          .el-button {
            padding: 0;
            width: 16px;
            height: 16px;
            border: none;
            background: transparent;
            position: relative;

            &:nth-child(1)::before {
              content: '';
              width: 16px;
              height: 16px;
              position: absolute;
              top: 0;
              left: 0;
              background: var(--svg-arrow-left) center no-repeat;
            }

            &:nth-child(2) {
              display: none;
            }

            &:nth-child(3) {
              margin-left: 5px;

              &::before {
                content: '';
                width: 16px;
                height: 16px;
                position: absolute;
                top: 0;
                left: 0;
                background: var(--svg-arrow-right) center no-repeat;
              }
            }

            span {
              display: none;
            }
          }
        }
      }
    }

    .el-calendar__body {
      padding: 0;

      .el-calendar-table {
        thead th {
          padding: 10px 0;
          background: var(--color-primary);
          color: var(--color-text);
          font-size: 14px;
        }

        tbody .el-calendar-table__row td {
          border: none;

          &.prev,
          &.next {
            .el-calendar-day {
              span {
                color: var(--color-text-primary);
              }
            }
          }

          &.is-selected {
            background: var(--color-primary-light);
          }

          .el-calendar-day {
            height: 36px;

            &:hover {
              background: var(--color-primary-light);
            }

            span {
              color: var(--color-text);
              line-height: 16px;
              display: block;
              text-align: center;
            }
          }
        }
      }
    }
  }
</style>
