<template>
  <div class="chat">
    <div class="chat__header">
      <span class="header__icon"></span>
      <span class="header__text">Мини-чат</span>
      <div class="header__buttons">
        <i class="el-icon-minus"></i>
        <i class="el-icon-arrow-down"></i>
      </div>
    </div>
    <div class="chat__main">
      <vue-scroll :ops="opsList">
        <div class="main__list">
          <div class="list__item" v-for="(item, i) in listMessage" :key="i">
            <avatar :src="item.avatar" :online="item.online" class="item__avatar"/>
            <div class="item__info">
              <div class="info__top">
                <div class="top__left">
                  <span class="left__fullname">{{ item.fullName }}</span>
                  <span class="left__date">{{ item.date }}</span>
                </div>
                <div class="top__right">
                  <span class="right__text">Ответить</span>
                  <i class="el-icon-chat-dot-round"></i>
                </div>
              </div>
              <div class="info__content">
                {{ item.text }}
              </div>
            </div>
          </div>
        </div>
      </vue-scroll>
    </div>
    <div class="chat__footer">
      <input-simple v-model="message" placeholder="Введите сообщение..." class="footer__input"/>
      <span class="footer__smile"></span>
    </div>
  </div>
</template>

<script>
  import InputSimple from "./InputSimple";
  import Avatar from "./Avatar";

  export default {
    name: "Chat",
    components: {Avatar, InputSimple},
    data() {
      return {
        message: '',
        listMessage: [
          {
            online: true,
            fullName: 'Калачев Евгений',
            avatar: require('~/assets/images/man.png'),
            date: '12.07.2018',
            text: 'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.'
          },
          {
            online: true,
            fullName: 'Калачев Евгений',
            avatar: require('~/assets/images/man.png'),
            date: '12.07.2018',
            text: 'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.'
          },
          {
            online: true,
            fullName: 'Калачев Евгений',
            avatar: require('~/assets/images/man.png'),
            date: '12.07.2018',
            text: 'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.'
          },
          {
            online: false,
            fullName: 'Калачев Евгений',
            avatar: require('~/assets/images/man.png'),
            date: '12.07.2018',
            text: 'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.'
          },
          {
            online: true,
            fullName: 'Калачев Евгений',
            avatar: require('~/assets/images/man.png'),
            date: '12.07.2018',
            text: 'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.'
          },
          {
            online: false,
            fullName: 'Калачев Евгений',
            avatar: require('~/assets/images/man.png'),
            date: '12.07.2018',
            text: 'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.'
          }
        ],
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
        }
      }
    }
  }
</script>

<style lang="scss">
  .chat {
    display: flex;
    flex-direction: column;
    height: 100%;

    .chat__header {
      display: flex;
      align-items: center;
      padding: 8px 20px;
      background: var(--color-primary);

      .header__icon {
        width: 20px;
        height: 20px;
        background: var(--svg-team-chat) center no-repeat;
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
        }
      }
    }

    .chat__main {
      background: var(--color-background);
      height: 294px;
      padding: 15px 0 17px 17px;

      .main__list {
        display: flex;
        flex-direction: column;
        padding-right: 42px;

        .list__item {
          display: flex;

          &:nth-child(n + 2) {
            margin-top: 14px;
          }

          .item__info {
            margin-left: 12px;
            display: flex;
            flex-direction: column;

            .info__top {
              margin-top: 8px;
              display: flex;
              justify-content: space-between;

              .top__left {
                display: flex;
                flex-direction: column;

                .left__fullname {
                  font-size: 12px;
                  color: var(--color-text);
                }

                .left__date {
                  margin-top: 2px;
                  font-size: 11px;
                  color: var(--color-primary-lighting);
                }
              }

              .top__right {
                display: flex;
                align-self: flex-end;
                color: var(--color-text);

                .right__text {
                  font-size: 11px;
                  margin-right: 12px;
                  cursor: pointer;
                }

                i {
                  cursor: pointer;
                }
              }
            }

            .info__content {
              margin: 10px 0 0 3px;
              padding: 10px 10px 14px 14px;
              font-size: 12px;
              border-radius: 10px;
              color: var(--color-text);
              background: var(--color-border-dark);
            }
          }
        }
      }
    }

    .chat__footer {
      background: var(--color-primary);
      display: flex;
      align-items: center;
      padding: 7px 16px;

      .footer__input {

      }

      .footer__smile {
        width: 20px;
        height: 20px;
        background: var(--svg-smile) center no-repeat;
        cursor: pointer;
      }
    }
  }
</style>
