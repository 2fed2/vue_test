<template>
  <div class="table-info" v-if="content">
    <div class="table-info__header">
      <i class="header__icon" :class="content.icon"></i>
      <span class="header__text">{{ content.title }}</span>
      <div v-if="content.buttons !== 'custom'" class="header__buttons">
        <i class="el-icon-minus"></i>
        <i class="el-icon-arrow-down"></i>
      </div>
      <div v-if="content.buttons === 'custom'" class="header__buttons">
        <i class="el-icon-circle-plus-outline green"></i>
        <i class="el-icon-edit yellow"></i>
        <i class="el-icon-circle-close red"></i>
      </div>
    </div>
    <div class="table-info__main">
      <vue-scroll :ops="opsTable">
        <div class="main__table">
          <el-table
            :data="content.tableData"
            style="width: 100%">
            <el-table-column
              v-for="item in content.tableHeader"
              :key="item.prop"
              :prop="item.prop"
              :label="item.label"
              :width="item.width">
            </el-table-column>
          </el-table>
        </div>
      </vue-scroll>
    </div>
    <div class="table-info__footer">
      <vue-scroll :ops="opsRadio">
        <div class="footer">
          <el-radio-group v-model="radio" class="footer__radio-group">
            <el-radio v-for="item in content.tableFooter" :key="item.key" :label="item.key">{{ item.value }}</el-radio>
          </el-radio-group>
        </div>
      </vue-scroll>
    </div>
  </div>
</template>

<script>
  export default {
    name: "TableInfo",
    props: {
      content: {
        type: Object,
        required: true
      }
    },
    data() {
      return {
        radio: 1,
        opsTable: {
          vuescroll: {},
          scrollPanel: {},
          rail: {},
          bar: {
            background: '#fff',
            scrollingX: true,
            scrollingY: true,
            keepShow: true,
            size: '2px',
          }
        },
        opsRadio: {
          vuescroll: {},
          scrollPanel: {},
          rail: {},
          bar: {
            background: '#000',
            opacity: 0,
            scrollingX: true,
            scrollingY: false,
            keepShow: true
          }
        }
      }
    }
  }
</script>

<style lang="scss">
  .table-info {
    display: flex;
    flex-direction: column;
    height: 100%;

    .table-info__header {
      display: flex;
      align-items: center;
      padding: 8px 20px;
      background: var(--color-primary);

      .header__icon {
        font-size: 20px;
        color: var(--color-text);

        &.notify {
          background: var(--color-border);
        }

        &.actions {
          background: var(--color-text);
        }
      }

      .header__text {
        margin-left: 14px;
        color: var(--color-text);
      }

      .header__buttons {
        display: flex;
        align-items: center;
        margin-left: auto;

        i {
          font-size: 16px;
          color: var(--color-text);
          cursor: pointer;

          &:nth-child(n + 2) {
            margin-left: 12px;
          }

          &.yellow {
            color: var(--color-yellow);
          }

          &.green {
            color: var(--color-green);
          }

          &.red {
            color: var(--color-red);
          }
        }
      }
    }

    .table-info__main {
      background: var(--color-background);
      height: 294px;

      .main__table {
        padding: 0 25px;
      }

      .__rail-is-vertical {
        right: -2px !important;
      }

      .el-table {
        &::before {
          display: none;
        }

        tr,
        th {
          background: var(--color-background);
        }

        td,
        th.is-leaf {
          border-bottom: 1px solid var(--color-border-dark);
        }

        .el-table__row:last-child {
          td {
            border-bottom: none;
          }
        }

        tr {
          &:hover > td {
            background: transparent;
          }

          td:first-child,
          th:first-child {
            .cell {
              padding-left: 0;
            }
          }
        }

        .cell {
          white-space: nowrap;
        }

        .el-table__header {
          tr {
            color: var(--color-text-primary);
          }
        }
      }
    }

    .table-info__footer {
      padding: 6px 25px;
      background: var(--color-primary);

      .__panel {
        overflow: hidden !important;
      }

      .__bar-is-horizontal {
        top: 10px !important;
      }

      .footer__radio-group {
        white-space: nowrap;
        width: 100%;

        .el-radio {
          .el-radio__input {
            .el-radio__inner {
              width: 5px;
              height: 5px;
              margin: 5px 0;

              &::after {
                display: none;
              }
            }
          }
        }
      }
    }
  }
</style>
