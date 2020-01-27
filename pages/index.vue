<template>
  <div class="page-container">
    <div class="page-container__top">
      <div class="top__user">
        <avatar class="user__avatar" :src="require('~/assets/images/man.png')" size="large" :online="true"></avatar>
        <div class="user__info">
          <span class="info__fullname">Кузнецов Алексей</span>
          <span class="info__position">Веб-дизайнер</span>
        </div>
      </div>
      <div class="top__buttons">
        <nuxt-link to="/" class="buttons__item">
          <span class="item__icon item__icon_home">
            <span class="icon__badge">1</span>
          </span>
          <span class="item__text">Текущее состояние</span>
        </nuxt-link>
        <nuxt-link to="/" class="buttons__item">
          <span class="item__icon item__icon_user"></span>
          <span class="item__text">Личный кабинет</span>
        </nuxt-link>
      </div>
    </div>
    <vue-scroll :ops="opsContent">
      <div class="page-container__content">
        <div class="content__column">
          <calendar class="column__item"/>
          <reminder class="column__item"/>
          <table-info :content="contentHistory" class="column__item"/>
        </div>
        <div class="content__column">
          <table-info :content="contentCalls" class="column__item"></table-info>
          <table-info :content="contentActions" class="column__item"/>
        </div>
        <div class="content__column">
          <phone class="column__item"/>
          <table-info :content="contentNotifications" class="column__item"/>
        </div>
        <div class="content__column">
          <chat class="column__item" />
          <text-box class="column__item"/>
        </div>
      </div>
    </vue-scroll>
  </div>
</template>

<script>
  import TableInfo from "../components/TableInfo";
  import Calendar from "../components/Calendar";
  import Reminder from "../components/Reminder";
  import Phone from "../components/Phone";
  import Avatar from "../components/Avatar";
  import Chat from "../components/Chat";
  import TextBox from "../components/TextBox";

  export default {
    components: {TextBox, Chat, Avatar, Phone, Reminder, Calendar, TableInfo},
    data() {
      return {
        contentHistory: {
          title: 'Общая история',
          icon: 'el-icon-bell',
          tableData: [
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            }
          ],
          tableHeader: [
            {
              prop: 'date',
              label: 'Дата',
              width: '100'
            },
            {
              prop: 'performer',
              label: 'Исполнитель',
              width: '150'
            },
            {
              prop: 'action',
              label: 'Действие',
              width: '120'
            }
          ],
          tableFooter: [
            {
              key: 1,
              value: 'Текущие'
            },
            {
              key: 2,
              value: 'Исполненные'
            },
            {
              key: 3,
              value: 'Просроченные'
            },
          ]
        },
        contentNotifications: {
          title: 'Уведомления',
          icon: 'el-icon-bell',
          tableData: [
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            },
            {
              date: '11.07.2018',
              time: '14:33',
              performer: 'Григоренко А.С.',
              action: 'Мониторинг'
            }
          ],
          tableHeader: [
            {
              prop: 'date',
              label: 'Дата',
              width: '100'
            },
            {
              prop: 'time',
              label: 'Время',
              width: '100'
            },
            {
              prop: 'performer',
              label: 'Исполнитель',
              width: '150'
            },
            {
              prop: 'action',
              label: 'Действие',
              width: '130'
            }
          ],
          tableFooter: [
            {
              key: 1,
              value: 'Личные'
            },
            {
              key: 2,
              value: 'Сотрудники'
            }
          ]
        },
        contentActions: {
          title: 'Действия',
          icon: 'el-icon-refresh',
          tableHeader: [
            {
              prop: 'date',
              label: 'Дата постановки',
              width: '130'
            },
            {
              prop: 'time',
              label: 'Срок исполнения',
              width: '150'
            },
            {
              prop: 'topic',
              label: 'Тема задачи',
              width: '170'
            }
          ],
          tableData: [
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            },
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            },
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            },
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            },
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            },
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            },
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            },
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            },
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            },
            {
              date: '11.07.2018',
              time: '14:22',
              topic: 'Мониторинг системы'
            }
          ],
          tableFooter: [
            {
              key: 1,
              value: 'Текущие'
            },
            {
              key: 2,
              value: 'Исполненные'
            },
            {
              key: 3,
              value: 'Просроченные'
            },
          ]
        },
        contentCalls: {
          title: 'Звонки',
          icon: 'el-icon-phone-outline',
          buttons: 'custom',
          tableHeader: [
            {
              prop: 'date',
              label: 'Постановки',
              width: '110'
            },
            {
              prop: 'time_start',
              label: 'Начало',
              width: '80'
            },
            {
              prop: 'time_stop',
              label: 'Окончание',
              width: '100'
            },
            {
              prop: 'appointed',
              label: 'Назначил',
              width: '100'
            },
            {
              prop: 'desc',
              label: 'Описание',
              width: '110'
            },
            {
              prop: 'place',
              label: 'Место',
              width: '100'
            }
          ],
          tableData: [
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            },
            {
              date: '11.07.2018',
              time_start: '14:22',
              time_stop: '16:22',
              appointed: 'Система',
              desc: 'Звонок',
              place: 'Офис'
            }
          ],
          tableFooter: [
            {
              key: 1,
              value: 'Личные'
            },
            {
              key: 2,
              value: 'От системы'
            },
            {
              key: 3,
              value: 'От руководителя'
            },
            {
              key: 4,
              value: 'Все задачи'
            },
          ]
        },
        opsContent: {
          vuescroll: {},
          scrollPanel: {},
          rail: {},
          bar: {
            background: '#fff',
            scrollingX: true,
            scrollingY: true,
            size: '6px',
          }
        },
      }
    }
  }
</script>

<style lang="scss">
  .page-container {
    display: flex;
    flex-direction: column;

    .page-container__top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 25px;

      .top__user {
        display: flex;

        .user__info {
          display: flex;
          flex-direction: column;
          margin: auto 0 auto 20px;

          .info__fullname {
            font-size: 16px;
            color: var(--color-text);
          }

          .info__position {
            margin-top: 15px;
            font-size: 12px;
            color: var(--color-text);
          }
        }
      }

      .top__buttons {
        display: flex;
        align-items: center;
        margin-right: 55px;

        .buttons__item {
          display: flex;
          align-items: center;
          text-decoration: none;

          &:nth-child(n + 2) {
            margin-left: 130px;
          }

          .item__icon {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            border: 4px solid var(--color-border);
            background: var(--color-gradient-icon);
            position: relative;

            &.item__icon_home::before {
              content: '';
              width: 18px;
              height: 18px;
              position: absolute;
              top: 9px;
              left: 9px;
              background: var(--svg-home) center no-repeat;
            }

            &.item__icon_user::before {
              content: '';
              width: 18px;
              height: 18px;
              position: absolute;
              top: 9px;
              left: 9px;
              background: var(--svg-user) center no-repeat;
            }

            .icon__badge {
              position: absolute;
              top: -10px;
              right: -10px;
              width: 22px;
              height: 22px;
              border-radius: 50%;
              text-align: center;
              line-height: 22px;
              font-size: 12px;
              color: var(--color-text);
              background: var(--color-primary-lighting);

              &::after {
                content: '';
                position: absolute;
                bottom: 0;
                right: -4px;
                width: 5px;
                height: 5px;
                border-radius: 50%;
                background: var(--color-primary-lighting);
              }
            }
          }

          .item__text {
            margin-left: 12px;
            font-size: 14px;
            color: var(--color-text);
          }
        }
      }
    }

    .page-container__content {
      display: flex;
      height: calc(100vh - 298px);
      padding-right: 30px;

      .content__column {
        display: flex;
        flex-direction: column;
        width: 100%;

        &:nth-child(n + 2) {
          margin-left: 14px;
        }

        &:nth-child(1) {
          width: 312px;
        }

        &:nth-child(2) {
          width: 450px;
        }

        &:nth-child(3) {
          width: 380px;
        }

        .column__item {
          height: 364px;
          flex-shrink: 0;

          &:nth-child(n + 2) {
            margin-top: 14px;
          }

          &.calendar {
            height: 286px;
          }

          &.reminder {
            height: 64px;
          }
        }
      }
    }
  }
</style>
