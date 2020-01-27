<template>
  <div class="phone">
    <div class="phone__header">
      <span class="header__icon"></span>
      <span class="header__text">Global Monitoring Phone</span>
    </div>
    <div class="phone__main">
      <div class="main__left">
        <div class="left__top">
          <input-simple v-model="phone" placeholder="Введите номер.." class="top__input"/>
          <span class="top__clear" @click="phone = ''"></span>
        </div>
        <div class="left__content">
          <div class="content__item" v-for="(item, i) in numbers" :key="i" @click="enterPhone(item)">
            <span class="item__text">{{ item }}</span>
          </div>
        </div>
      </div>
      <div class="main__right">
        <div class="right__buttons">
          <span class="buttons__item buttons__item_accept"></span>
          <span class="buttons__item buttons__item_hold"></span>
          <span class="buttons__item buttons__item_drop"></span>
        </div>
        <el-radio-group v-model="selectedCall" class="right__radio-group">
          <el-radio-button label="contacts" class="contacts"></el-radio-button>
          <el-radio-button label="log" class="log"></el-radio-button>
        </el-radio-group>
        <div class="right__list-wrapper">
          <vue-scroll :ops="opsList">
            <ul class="right__list">
              <li class="list__item" v-for="(item, i) in contactsList" :key="i">{{ item }}</li>
            </ul>
          </vue-scroll>
        </div>
      </div>
    </div>
    <div class="phone__footer">
      <p class="footer__text">Статус: <span>Удержание...</span></p>
    </div>
  </div>
</template>

<script>
  import InputSimple from "./InputSimple";
  export default {
    name: "Phone",
    components: {InputSimple},
    data() {
      return {
        phone: '',
        opsList: {
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
        numbers: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '*', '0', '#'],
        selectedCall: 'contacts',
        contactsList: ['Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.', 'Архипенко В.П.']
      }
    },
    methods: {
      enterPhone(item) {
        this.phone += item
      }
    }
  }
</script>

<style lang="scss">
  .phone {
    display: flex;
    flex-direction: column;

    .phone__header {
      display: flex;
      align-items: center;
      padding: 8px 20px;
      background: var(--color-primary);

      .header__icon {
        width: 20px;
        height: 20px;
        background: var(--svg-world) center no-repeat;
      }

      .header__text {
        margin-left: 14px;
        color: var(--color-text);
      }
    }

    .phone__main {
      display: flex;
      justify-content: space-between;
      height: 100%;
      background: var(--color-background);
      padding: 14px 0 16px 20px;

      .main__left {
        width: 48%;
        display: flex;
        flex-direction: column;

        .left__top {
          display: flex;
          align-items: center;

          .top__clear {
            width: 20px;
            height: 20px;
            background: var(--svg-delete) center no-repeat;
            margin-left: 10px;
            cursor: pointer;
          }
        }

        .left__content {
          margin-top: 18px;
          display: flex;
          flex-wrap: wrap;
          justify-content: space-between;

          .content__item {
            width: 50px;
            height: 50px;
            border: 1px solid var(--color-border);
            display: flex;
            border-radius: 10px;
            cursor: pointer;

            &:nth-child(n + 4) {
              margin-top: 6px;
            }

            span {
              margin: auto;
              font-size: 24px;
              color: var(--color-text);
            }
          }
        }
      }

      .main__right {
        display: flex;
        flex-direction: column;

        .right__buttons {
          display: flex;
          justify-content: space-around;
          align-items: center;
          padding-right: 20px;

          .buttons__item {
            width: 28px;
            height: 28px;
            background: var(--color-text);
            cursor: pointer;

            &.buttons__item_accept {
              background: var(--svg-call) center no-repeat;
            }

            &.buttons__item_hold {
              background: var(--svg-call-pause) center no-repeat;
            }

            &.buttons__item_drop {
              background: var(--svg-call-reset) center no-repeat;
            }
          }
        }

        .right__radio-group {
          margin-top: 15px;
          padding-right: 20px;

          .el-radio-button {
            width: 49%;

            &.contacts .el-radio-button__inner::before {
              background: var(--svg-contacts) center no-repeat;
            }

            &.contacts.is-active .el-radio-button__inner::before {
              background: var(--svg-contacts-active) center no-repeat;
            }

            &.log .el-radio-button__inner::before {
              background: var(--svg-book) center no-repeat;
            }

            &.log.is-active .el-radio-button__inner::before {
              background: var(--svg-book-active) center no-repeat;
            }

            .el-radio-button__inner {
              text-indent: 200%;
              white-space: nowrap;
              overflow: hidden;
              width: 100%;
              background: var(--color-primary);
              border: none;
              position: relative;

              &::before {
                content: '';
                width: 20px;
                height: 20px;
                position: absolute;
                top: calc(50% - 10px);;
                left: calc(50% - 10px);
              }
            }
          }
        }

        .right__list-wrapper {
          margin-top: 5px;
          height: 174px;
        }

        .right__list {
          list-style: none;
          padding: 0 20px 0 0;

          .list__item {
            color: var(--color-text);
            font-size: 15px;
            cursor: pointer;

            &:nth-child(n + 2) {
              margin-top: 10px;
            }
          }
        }
      }
    }

    .phone__footer {
      padding: 7px 25px;
      background: var(--color-primary);

      .footer__text {
        font-size: 15px;
        color: var(--color-text);
        padding-left: 12px;
        position: relative;

        &::before {
          content: '';
          position: absolute;
          top: 6px;
          left: 0;
          width: 5px;
          height: 5px;
          border-radius: 50%;
          background: var(--color-yellow);
        }

        span {
          color: var(--color-yellow);
        }
      }
    }
  }
</style>
