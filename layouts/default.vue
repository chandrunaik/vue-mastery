<template lang='pug'>
  .container(:class="openNav ? 'open-nav': ''")
    // Announcement
    PageHeader(:class='$route.name')
    nuxt
    VuePodcast(v-if="$route.name !== 'thank-you-annual' && $route.name !== 'thank-you-monthly' && $route.name !== 'pricing'" v-cloak)
    PageFooter
    AuthForm
</template>

<script>
import { mapGetters } from 'vuex'
// import Announcement from '~/components/static/Announcement.vue'
import PageHeader from '~/components/header/Header.vue'
import VuePodcast from '~/components/static/VuePodcast.vue'
import PageFooter from '~/components/footer/Footer.vue'
import AuthForm from '~/components/account/Accountmodal.vue'

export default {
  name: 'default-layout',

  components: {
    // Announcement,
    PageHeader,
    VuePodcast,
    PageFooter,
    AuthForm
  },

  computed: {
    ...mapGetters([
      'openNav'
    ])
  }
}
</script>
