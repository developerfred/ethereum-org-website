<template>
  <div>
    <div class="headline-text-container">
      <h1 class="headline-title">{{content['page-home-title']}}</h1>
      <div class="headline-subtitle">{{content['page-home-subtitle']}}</div>
      <router-link to="/beginners/" class="button headline-button">Learn more</router-link>
    </div>

    <div class="intro-blocks">

      <div class="intro-block" v-if="isEnglish">
        <h3 class="header">
          <span class="arrow">→</span>{{content['page-home-section-individuals-title']}}
        </h3>
        <ul>
          <li class="highlight highlight-small">
            <router-link :to="content['page-home-section-individuals-item-one-link']" class="black">
              {{content['page-home-section-individuals-item-one']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-individuals-item-two-link']" class="black">
              {{content['page-home-section-individuals-item-two']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-individuals-item-three-link']" class="black">
              {{content['page-home-section-individuals-item-three']}}
            </router-link>
          </li>
        </ul>
      </div>

       <div class="intro-block-nonenglish" v-if="!isEnglish">
        <h3>
          <router-link :to="content['path'] + 'beginners/'">
            <span class="arrow">→</span>{{content['page-home-section-beginners-title']}}
          </router-link>
        </h3>
        <ul>
          <li class="highlight">
            <router-link :to="content['path'] + 'beginners/'" class="black">
              {{content['page-home-section-beginners-item-one']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['path'] + 'beginners/'" class="black">
              {{content['page-home-section-beginners-item-two']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['path'] + 'beginners/'" class="black">
              {{content['page-home-section-beginners-item-three']}}
            </router-link>
          </li>
        </ul>
      </div>

      <div class="intro-block-nonenglish" v-if="!isEnglish">
        <h3>
          <router-link :to="content['path'] + 'use/'">
            <span class="arrow">→</span>{{content['page-home-section-use-title']}}
          </router-link>
        </h3>
        <ul>
          <li>
            <router-link :to="content['page-home-section-use-item-one-link']" class="black">
              {{content['page-home-section-use-item-one']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-use-item-two-link']" class="black">
              {{content['page-home-section-use-item-two']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-use-item-three-link']" class="black">
              {{content['page-home-section-use-item-three']}}
            </router-link>
          </li>
        </ul>
      </div>

      <div class="intro-block-nonenglish" v-if="!isEnglish">
        <h3>
          <router-link :to="content['path'] + 'learn/'">
            <span class="arrow">→</span>{{content['page-home-section-learn-title']}}
          </router-link>
        </h3>
        <ul>
          <li>
            <router-link :to="content['page-home-section-learn-item-one-link']" class="black">
              {{content['page-home-section-learn-item-one']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-learn-item-two-link']" class="black">
              {{content['page-home-section-learn-item-two']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-learn-item-three-link']" class="black">
              {{content['page-home-section-learn-item-three']}}
            </router-link>
          </li>
        </ul>
      </div>

      <div v-bind:class="{ 'intro-block': isEnglish, 'intro-block-nonenglish': !isEnglish }">
        <h3>
          <router-link :to="content['path'] + 'developers/'">
            <span class="arrow">→</span>{{content['page-home-section-developers-title']}}
          </router-link>
        </h3>
        <ul>
          <li>
            <router-link :to="content['page-home-section-developers-item-one-link']" class="black">
              {{content['page-home-section-developers-item-one']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-developers-item-two-link']" class="black">
              {{content['page-home-section-developers-item-two']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-developers-item-three-link']" class="black">
              {{content['page-home-section-developers-item-three']}}
            </router-link>
          </li>
        </ul>
      </div>

      <div class="intro-block" v-if="isEnglish">
        <h3>
          <router-link :to="content['path'] + 'enterprise/'">
            <span class="arrow">→</span>{{content['page-home-section-enterprise-title']}}
          </router-link>
        </h3>
        <ul>
          <li>
            <router-link :to="content['page-home-section-enterprise-item-one-link']" class="black">
              {{content['page-home-section-enterprise-item-one']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-enterprise-item-two-link']" class="black">
              {{content['page-home-section-enterprise-item-two']}}
            </router-link>
          </li>
          <li>
            <router-link :to="content['page-home-section-enterprise-item-three-link']" class="black">
              {{content['page-home-section-enterprise-item-three']}}
            </router-link>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
  import { translate } from '../theme/utils/translations'

  export default {
    computed: {
      // TODO there must be a better way...
      // How to use translate() within Vue component template??
      content() {
        return {
          'path': translate('path', this.$lang),
          'page-home-title': translate('page-home-title', this.$lang),
          'page-home-subtitle': translate('page-home-subtitle', this.$lang),
          'page-home-section-individuals-title': translate('page-home-section-individuals-title', this.$lang),
          'page-home-section-individuals-item-one': translate('page-home-section-individuals-item-one', this.$lang),
          'page-home-section-individuals-item-two': translate('page-home-section-individuals-item-two', this.$lang),
          'page-home-section-individuals-item-three': translate('page-home-section-individuals-item-three', this.$lang),
          'page-home-section-individuals-item-one-link': translate('page-home-section-individuals-item-one-link', this.$lang),
          'page-home-section-individuals-item-two-link': translate('page-home-section-individuals-item-two-link', this.$lang),
          'page-home-section-individuals-item-three-link': translate('page-home-section-individuals-item-three-link', this.$lang),
          'page-home-section-beginners-title': translate('page-home-section-beginners-title', this.$lang), // TODO remove once translations are updated
          'page-home-section-beginners-item-one': translate('page-home-section-beginners-item-one', this.$lang), // TODO remove once translations are updated
          'page-home-section-beginners-item-two': translate('page-home-section-beginners-item-two', this.$lang), // TODO remove once translations are updated
          'page-home-section-beginners-item-three': translate('page-home-section-beginners-item-three', this.$lang), // TODO remove once translations are updated
          'page-home-section-use-title': translate('page-home-section-use-title', this.$lang), // TODO remove once translations are updated
          'page-home-section-use-item-one': translate('page-home-section-use-item-one', this.$lang), // TODO remove once translations are updated
          'page-home-section-use-item-two': translate('page-home-section-use-item-two', this.$lang), // TODO remove once translations are updated
          'page-home-section-use-item-three': translate('page-home-section-use-item-three', this.$lang), // TODO remove once translations are updated
          'page-home-section-use-item-one-link': translate('page-home-section-use-item-one-link', this.$lang), // TODO remove once translations are updated
          'page-home-section-use-item-two-link': translate('page-home-section-use-item-two-link', this.$lang), // TODO remove once translations are updated
          'page-home-section-use-item-three-link': translate('page-home-section-use-item-three-link', this.$lang), // TODO remove once translations are updated
          'page-home-section-learn-title': translate('page-home-section-learn-title', this.$lang),
          'page-home-section-learn-item-one': translate('page-home-section-learn-item-one', this.$lang),
          'page-home-section-learn-item-two': translate('page-home-section-learn-item-two', this.$lang),
          'page-home-section-learn-item-three': translate('page-home-section-learn-item-three', this.$lang),
          'page-home-section-learn-item-one-link': translate('page-home-section-learn-item-one-link', this.$lang),
          'page-home-section-learn-item-two-link': translate('page-home-section-learn-item-two-link', this.$lang),
          'page-home-section-learn-item-three-link': translate('page-home-section-learn-item-three-link', this.$lang),
          'page-home-section-developers-title': translate('page-home-section-developers-title', this.$lang),
          'page-home-section-developers-item-one': translate('page-home-section-developers-item-one', this.$lang),
          'page-home-section-developers-item-two': translate('page-home-section-developers-item-two', this.$lang),
          'page-home-section-developers-item-three': translate('page-home-section-developers-item-three', this.$lang),
          'page-home-section-enterprise-title': translate('page-home-section-enterprise-title', this.$lang),
          'page-home-section-developers-item-one-link': translate('page-home-section-developers-item-one-link', this.$lang),
          'page-home-section-developers-item-two-link': translate('page-home-section-developers-item-two-link', this.$lang),
          'page-home-section-developers-item-three-link': translate('page-home-section-developers-item-three-link', this.$lang),
          'page-home-section-enterprise-title': translate('page-home-section-enterprise-title', this.$lang),
          'page-home-section-enterprise-item-one': translate('page-home-section-enterprise-item-one', this.$lang),
          'page-home-section-enterprise-item-two': translate('page-home-section-enterprise-item-two', this.$lang),
          'page-home-section-enterprise-item-three': translate('page-home-section-enterprise-item-three', this.$lang),
          'page-home-section-enterprise-item-one-link': translate('page-home-section-enterprise-item-one-link', this.$lang),
          'page-home-section-enterprise-item-two-link': translate('page-home-section-enterprise-item-two-link', this.$lang),
          'page-home-section-enterprise-item-three-link': translate('page-home-section-enterprise-item-three-link', this.$lang)
        }
      },

      isEnglish() {
        return this.$lang === 'en-US'
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @require '../theme/styles/config'

  .headline-button
    margin-top 2rem
    font-size $fsRegular

  .header
    color $accentColor

.highlight-small
    background-size 240px !important

  #wrapper.dark-mode
    .header
      color $accentColorDark

</style>