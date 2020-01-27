<template>
  <div class="text-box">
    <div class="text-box__header">
      <span class="header__icon"></span>
      <span class="header__text">Рабочее поле</span>
      <div class="header__buttons">
        <i class="el-icon-minus"></i>
        <i class="el-icon-arrow-down"></i>
      </div>
    </div>
    <div class="text-box__main">
      <vue-scroll :ops="opsList">
        <div class="main__text">
          <span class="text__title">Текстовая информация</span>
          <div class="text__content">
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat.</p>
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper
              suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in
              vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et
              accumsan
              et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla
              facilisi.</p>
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat.</p>
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper
              suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in
              vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et
              accumsan
              et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla
              facilisi.</p>
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat.</p>
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper
              suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in
              vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et
              accumsan
              et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla
              facilisi.</p>
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat.</p>
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper
              suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in
              vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et
              accumsan
              et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla
              facilisi.</p>
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat.</p>
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut
              laoreet
              dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper
              suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in
              vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et
              accumsan
              et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla
              facilisi.</p>
          </div>
        </div>
      </vue-scroll>
    </div>
  </div>
</template>

<script>
  export default {
    name: "TextBox",
    data() {
      return {
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
  .text-box {
    display: flex;
    flex-direction: column;

    .text-box__header {
      display: flex;
      align-items: center;
      padding: 8px 20px;
      background: var(--color-primary);

      .header__icon {
        width: 20px;
        height: 20px;
        background: var(--svg-agenda) center no-repeat;
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

    .text-box__main {
      background: var(--color-background);
      padding: 15px 0 15px 20px;
      display: flex;
      flex-direction: column;
      height: 327px;

      .main__text {
        padding-right: 18px;

        .text__title {
          font-size: 14px;
          color: var(--color-text);
        }

        .text__content {
          margin-top: 18px;
          font-size: 14px;
          color: var(--color-text);
        }
      }
    }
  }
</style>
