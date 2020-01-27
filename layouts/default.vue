<template>
  <el-container>
    <el-header class="header" height="125px">
      <nuxt-link class="header__logo" to="/">
        <img src="~/assets/images/logo.png" alt="" class="logo__image">
      </nuxt-link>
      <ul class="header__menu">
        <li class="menu__item">
          <span class="item__icon item__icon_folder"></span>
          <span class="item__text">Открыть</span>
          <ul class="item__submenu">
            <li class="submenu__el">
              Дочерний пункт меню
            </li>
            <li class="submenu__el">
              Дочерний пункт меню
            </li>
            <li class="submenu__el">
              Дочерний пункт меню
            </li>
            <li class="submenu__el">
              Дочерний пункт меню
            </li>
          </ul>
        </li>
        <li class="menu__item">
          <span class="item__icon item__icon_add"></span>
          <span class="item__text">Открыть</span>
        </li>
        <li class="menu__item">
          <span class="item__icon item__icon_copy"></span>
          <span class="item__text">Открыть</span>
        </li>
        <li class="menu__item">
          <span class="item__icon item__icon_edit"></span>
          <span class="item__text">Открыть</span>
        </li>
        <li class="menu__item">
          <span class="item__icon item__icon_view"></span>
          <span class="item__text">Открыть</span>
        </li>
        <li class="menu__item">
          <span class="item__icon item__icon_team"></span>
          <span class="item__text">Открыть</span>
        </li>
        <li class="menu__item">
          <span class="item__icon item__icon_instruction"></span>
          <span class="item__text">Открыть</span>
        </li>
        <li class="menu__item">
          <span class="item__icon item__icon_lock"></span>
          <span class="item__text">Открыть</span>
        </li>
      </ul>
      <div class="header__info">
        <div class="info__item">
          <div class="item__icon item__icon_date">
            <i class="el-icon-date"></i>
          </div>
          <span class="icon__text">06.07.2018</span>
        </div>
        <div class="info__item">
          <div class="item__icon item__icon_time">
            <i class="el-icon-time"></i>
          </div>
          <span class="icon__text">15:51</span>
        </div>
        <nuxt-link to="/" class="info__item info__item_support">
          <div class="item__icon item__icon_support">
            <i class="el-icon-phone-outline"></i>
          </div>
          <span class="icon__text">Техническая поддержка</span>
        </nuxt-link>
      </div>
    </el-header>
    <el-main>
      <nuxt/>
    </el-main>
  </el-container>
</template>

<style lang="scss">
  @import "../assets/color";
  @import "../assets/svg";

  html {
    font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
    font-size: 16px;
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
  }

  *,
  *:before,
  *:after {
    box-sizing: border-box;
    margin: 0;
  }

  .header {
    display: flex;
    align-items: center;
    background: var(--color-primary);

    .header__logo {
      width: 220px;
      height: 50px;

      .logo__image {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }

    .header__menu {
      margin-left: 100px;
      display: flex;
      list-style: none;
      padding: 0;

      .menu__item {
        display: flex;
        flex-direction: column;
        align-items: center;
        position: relative;
        cursor: pointer;
        padding: 25px;

        &:hover {
          .item__icon {
            position: relative;

            &::before {
              content: '';
              position: absolute;
              top: -1px;
              right: -4px;
              width: 12px;
              height: 12px;
              background: var(--color-primary-lighting);
              border-radius: 50%;
            }

            &.item__icon_folder {
              background: var(--svg-folder-active) center no-repeat;
            }

            &.item__icon_add {
              background: var(--svg-add-active) center no-repeat;
            }

            &.item__icon_copy {
              background: var(--svg-copy-active) center no-repeat;
            }

            &.item__icon_edit {
              background: var(--svg-edit-active) center no-repeat;
            }

            &.item__icon_view {
              background: var(--svg-view-active) center no-repeat;
            }

            &.item__icon_team {
              background: var(--svg-team-active) center no-repeat;
            }

            &.item__icon_instruction {
              background: var(--svg-instruction-active) center no-repeat;
            }

            &.item__icon_lock {
              background: var(--svg-lock-active) center no-repeat;
            }
          }

          .item__text,
          .item__submenu {
            display: block;
          }
        }

        .item__icon {
          width: 22px;
          height: 22px;

          &.item__icon_folder {
            background: var(--svg-folder) center no-repeat;
          }

          &.item__icon_add {
            background: var(--svg-add) center no-repeat;
          }

          &.item__icon_copy {
            background: var(--svg-copy) center no-repeat;
          }

          &.item__icon_edit {
            background: var(--svg-edit) center no-repeat;
          }

          &.item__icon_view {
            background: var(--svg-view) center no-repeat;
          }

          &.item__icon_team {
            background: var(--svg-team) center no-repeat;
          }

          &.item__icon_instruction {
            background: var(--svg-instruction) center no-repeat;
          }

          &.item__icon_lock {
            background: var(--svg-lock) center no-repeat;
          }
        }

        .item__text {
          margin-top: 6px;
          font-size: 12px;
          color: var(--color-text);
          display: none;
          position: absolute;
          top: 46px;
        }

        .item__submenu {
          display: none;
          position: absolute;
          left: -20px;
          top: 86px;
          list-style: none;
          margin: 0;
          padding: 10px 14px 14px;
          background: var(--color-secondary);
          width: 200px;
          border: 1px solid var(--color-border);

          &::before {
            content: '';
            position: absolute;
            top: -17px;
            left: 38px;
            width: 0;
            height: 0;
            border-left: 17px solid transparent;
            border-right: 17px solid transparent;
            border-bottom: 17px solid var(--color-border);
          }

          &::after {
            content: '';
            position: absolute;
            top: -15px;
            left: 40px;
            width: 0;
            height: 0;
            border-left: 15px solid transparent;
            border-right: 15px solid transparent;
            border-bottom: 15px solid var(--color-secondary);
          }

          .submenu__el {
            color: var(--color-text);
            font-size: 12px;
            padding: 6px 0;
            border-bottom: 1px solid var(--color-text);
          }
        }
      }
    }

    .header__info {
      display: flex;
      align-items: center;
      margin-left: auto;

      .info__item {
        display: flex;
        align-items: center;
        text-decoration: none;

        &:nth-child(n + 2) {
          margin-left: 34px;
        }

        &.info__item_support {
          margin-left: 100px;
        }

        .item__icon {
          width: 22px;
          height: 22px;
          border-radius: 50%;
          background: var(--color-primary-lighting);
          display: flex;

          i {
            font-size: 16px;
            margin: auto;
            text-align: center;
            color: var(--color-text);
          }
        }

        .icon__text {
          font-size: 14px;
          color: var(--color-text);
          margin-left: 10px;
        }
      }
    }
  }

  .el-main {
    background: var(--color-secondary);
    padding: 25px 0 25px 30px !important;
  }
</style>
