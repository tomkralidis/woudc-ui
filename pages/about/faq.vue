<template>
  <v-container>
    <h1>{{ $t('about.faq.title') }}</h1>
    <p>{{ $t('about.faq.blurb') }}</p>
    <v-row>
      <v-col>
        <div v-for="(question, index) in $t('about.faq.questions')" :key="index">
          <h4>{{ question.text }}</h4>
          <i18n :path="'about.faq.questions[' + index + '].answer'" tag="p">
            <template v-slot:policy>
              <nuxt-link :to="localePath('about-datapolicy')">
                {{ $t('common.policy') }}
              </nuxt-link>
            </template>
            <template v-slot:submission>
              <nuxt-link :to="localePath('contributors-submission')">
                {{ $tc('common.submission', 1) }}
              </nuxt-link>
            </template>
            <template v-slot:registration-form>
              <nuxt-link :to="localePath('contributors-registration')">
                {{ $t('common.registration-form') }}
              </nuxt-link>
            </template>
            <template v-slot:access>
              <nuxt-link :to="localePath('about-dataaccess')">
                {{ $t('common.access') }}
              </nuxt-link>
            </template>
            <template v-slot:search>
              <nuxt-link :to="localePath('data-explore')">
                {{ $t('common.search') }}
              </nuxt-link>
            </template>
            <template v-slot:products>
              <nuxt-link :to="localePath('data-products')">
                {{ $t('common.products') }}
              </nuxt-link>
            </template>
            <template v-slot:contributors-page>
              <nuxt-link :to="localePath('contributors')">
                {{ $t('common.contributors-page') }}
              </nuxt-link>
            </template>
            <template v-slot:accessibility>
              <a :href="accessibilityURL" target="_blank">
                {{ $t('common.accessibility') }}
              </a>
            </template>
            <template v-slot:usability>
              <a :href="usabilityURL" target="_blank">
                {{ $t('about.faq.usability') }}
              </a>
            </template>
            <template v-slot:w3c>
              <a :href="w3cURL" target="_blank">
                {{ $t('common.w3c') }}
              </a>
            </template>
          </i18n>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      accessibilityURL: 'https://www.tbs-sct.gc.ca/pol/doc-eng.aspx?id=23601',
      usabilityURL: 'https://www.tbs-sct.gc.ca/pol/doc-eng.aspx?id=24227',
      w3cURL: 'https://www.w3.org/WAI/intro/wcag'
    }
  },
  nuxtI18n: {
    paths: {
      en: '/about/faq',
      fr: '/a-propos/faq'
    }
  }
}
</script>
