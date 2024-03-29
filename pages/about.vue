<script setup lang="ts">
const { data: products } = await useFetch("https://fakestoreapi.com/products?limit=3")
</script>

<template>
  <div cls="about">
    <div class="container">
      <div cls="about__promo">
        <div cls="about__promo-left">
          <r-round-button size="small">
            <svgo-info />
          </r-round-button>
          Watch the video about the new stage of the agency's evolution
        </div>
        <div cls="about__promo-right">
          <div cls="about__promo-text">
            <span> Repin Agency & </span>
            Mobicom — is an alliance of experts: managers, designers and developers who are in love
            with digital
          </div>
        </div>
      </div>
    </div>
    <div cls="about__video">
      <r-video />
    </div>
    <div cls="about__slider">
      <r-slider v-if="products" modified :products="products">
        <template #slides>
          <div v-for="img in products" cls="about__slide">
            <img :src="img.image" alt="" />
          </div>
        </template>
      </r-slider>
    </div>
    <div cls="about__full-cycle">
      <about-full-cycle />
    </div>
    <div class="container">
      <div cls="about__experts">
        <about-experts />
      </div>
    </div>
    <about-outstaff />
    <div class="container">
      <div cls="about__awards">
        <about-award />
      </div>
    </div>
    <div cls="about__photo-team">
      <about-team-photos />
    </div>
    <div class="container">
      <div cls="about__expirience">
        <reuse-expirience />
      </div>
      <div v-if="false" cls="about__open-jobs">
        <about-open-jobs />
      </div>
    </div>
  </div>
</template>

<style module lang="scss">
.about {
  &__promo {
    padding: 136px 32px 104px;
    width: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    &-left {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 16px;
      max-width: 192px;
    }
    &-right {
      max-width: 737px;
    }
    &-text {
      @include desctop-H3;
      span {
        @include desctop-H3-ram;
        font-style: italic;
      }
    }
  }
  &__slider {
    max-width: 1920px;
    width: 100%;
    padding: 104px 0 104px 80px;
    margin: 0 auto;
  }
  &__slide {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__experts {
    padding: 104px 0;
  }

  &__expirience,
  &__awards {
    padding: 104px 0;
  }
  &__open-jobs {
    padding: 104px 0 160px;
  }
}

@include tablet {
  .about {
    &__promo {
      padding: 56px 0 64px;
      gap: 40px;
      &-right {
        max-width: 623px;
      }
      &-text {
        @include mob-H2;
        span {
          @include mob-H2-ram;
          font-style: italic;
        }
      }
    }
    &__slider {
      padding: 72px 0 72px 40px;
    }
    &__experts,
    &__expirience,
    &__awards {
      padding: 72px 0;
    }
    &__open-jobs {
      padding: 72px 0 88px;
    }
  }
}
@include tablet-small {
  .about {
    &__promo {
      flex-wrap: wrap-reverse;
      &-left {
        margin-left: auto;
      }
      &-right {
        max-width: 100%;
      }
    }
  }
}
@include mobile {
  .about {
    &__promo {
      &-text {
        @include mob-H3;
        span {
          @include mob-H3-ram;
          font-style: italic;
        }
      }
    }
    &__slider {
      padding: 72px 16px;
    }
    &__expirience {
      padding: 72px 0 56px;
    }
  }
}
</style>
