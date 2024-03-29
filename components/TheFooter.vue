<script setup lang="ts">
const scrollTop = () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  })
}
</script>

<template>
  <div cls="footer">
    <div class="container">
      <div cls="footer__wrap">
        <div cls="footer__top">
          <nuxt-link to="/" cls="footer__logo">
            <svgo-logo-white />
          </nuxt-link>
          <div cls="footer__top-block">
            <div cls="footer__contact">
              <div cls="footer__contact-title">Contact</div>
              <div cls="footer__contact-text">
                If you still have questions, contact us (<span>we answer fastest on Telegram</span
                >).
              </div>
            </div>
            <div cls="footer__links">
              <div cls="footer__links-box">
                <div cls="footer__links-title">Menu</div>
                <div class="tabs">
                  <nuxt-link to="" cls="footer__links-item">Portfolio</nuxt-link>
                  <nuxt-link to="" cls="footer__links-item">Agency</nuxt-link>
                  <nuxt-link to="" cls="footer__links-item">Consulting</nuxt-link>
                  <nuxt-link to="" cls="footer__links-item">Blog</nuxt-link>
                  <nuxt-link to="" cls="footer__links-item">Contact</nuxt-link>
                </div>
              </div>
              <div cls="footer__links-box">
                <div cls="footer__links-title">Follow us</div>
                <div class="tabs">
                  <a href="" target="_blank" cls="footer__links-item">Behance</a>
                  <a href="" target="_blank" cls="footer__links-item">Dribbble</a>
                  <a href="" target="_blank" cls="footer__links-item">Instagram</a>
                  <a href="" target="_blank" cls="footer__links-item">YouTube</a>
                  <a href="" target="_blank" cls="footer__links-item">Telegram</a>
                  <a href="" target="_blank" cls="footer__links-item">WhatsApp</a>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div cls="footer__bottom">
          <div cls="footer__bottom-box">
            <div cls="footer__bottom-text">© 2016 — 2024</div>
            <div cls="footer__bottom-text">Privacy Policy</div>
            <div cls="footer__bottom-text">Offer contract</div>
          </div>
          <div cls="footer__bottom-wrap">
            <div cls="footer__bottom-text">hello@repin.agency</div>
            <button href="/" cls="footer__bottom-to-top" @click="scrollTop">
              On top <svgo-arrow-down />
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style module lang="scss">
.footer {
  padding: 48px 0 24px;
  background: var(--Black);
  color: var(--White);
  &__wrap {
    display: flex;
    flex-direction: column;
    gap: 96px;
  }
  &__top {
    display: flex;
    flex-direction: column;
    gap: 72px;
    &-block {
      display: flex;
      justify-content: space-between;
    }
  }
  &__contact {
    display: flex;
    flex-direction: column;
    gap: 16px;
    max-width: 508px;
    &-title {
      color: rgba(255, 255, 255, 0.4);
    }
    &-text {
      @include desctop-H3;
      span {
        font-family: "Ramillas Trial";
        font-style: italic;
      }
    }
  }
  &__logo {
    svg {
      height: 30px;
      width: 148px;
    }
  }
  &__links {
    display: flex;
    flex-direction: column;
    gap: 36px;
    max-width: 491px;
    width: 100%;
    &-box {
      display: flex;
      flex-direction: column;
      max-width: 411px;
      gap: 12px;
    }
    &-title {
      color: rgba(255, 255, 255, 0.4);
    }
    &-item {
      display: flex;
      padding: 8px 20px;
      justify-content: center;
      align-items: center;
      border-radius: 32px;
      background: rgba(124, 124, 124, 0.1);
      color: var(--White);
      @include desctop-caption-17-med;
    }
  }
  &__bottom {
    display: flex;
    justify-content: space-between;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    padding-top: 24px;
    gap: 24px;
    &-box {
      display: flex;
      gap: 29px;
    }
    &-text {
      color: rgba(255, 255, 255, 0.4);
    }
    &-wrap {
      display: flex;
      justify-content: space-between;
      max-width: 491px;
      flex: 1 0 0;
      gap: 24px;
    }
    &-to-top {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      border-bottom: 2px solid var(--White);
      flex-shrink: 0;
      svg {
        transform: rotate(180deg);
        path {
          stroke: white;
        }
      }
    }
  }
}

@include tablet {
  .footer {
    padding: 40px 0 24px;
    &__wrap {
      gap: 72px;
    }
    &__top {
      gap: 56px;
      &-block {
        gap: 24px;
      }
    }
    &__contact {
      max-width: 378px;
      &-text {
        @include mob-H3;
        span {
          @include mob-H3-ram;
          font-style: italic;
        }
      }
    }
    &__links {
      max-width: max-content;
      gap: 31px;
      &-box {
        max-width: 343px;
        gap: 11px;
      }
      &-item {
        padding: 8px 16px;
        @include mob-body-14;
      }
    }
    &__bottom {
      position: relative;
      flex-wrap: wrap;
      padding-top: 16px;
      &-box,
      &-wrap {
        align-items: center;
      }
      &-to-top {
        padding: 8px 16px;
        border-radius: 32px;
        background: rgba(124, 124, 124, 0.1);
        border-bottom: none;
      }
    }
  }
}
@include tablet-small {
  .footer {
    &__contact {
      max-width: 304px;
    }
    &__top {
      &-block {
        flex-wrap: wrap;
      }
    }
  }
}
@include mobile {
  .footer {
    position: relative;
    &__top {
      &-block {
        gap: 56px;
      }
    }
    &__bottom {
      gap: 4px;
      flex-direction: column;
      align-items: flex-start;
      &-box {
        flex-direction: column;
        align-items: flex-start;
        gap: 4px;
      }
      &-to-top {
        position: absolute;
        right: 0;
        bottom: 0;
      }
    }
    &__wrap {
      gap: 88px;
    }
  }
}
</style>
