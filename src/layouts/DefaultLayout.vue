<template lang="pug">
v-app
  HeaderComponent(:links='links', @drawer:clicked='drawer = !drawer')
  DrawerComponent(:links='links', v-model='drawer')

  v-main
    router-view

  FooterComponent
</template>

<script>
export default {
  components: {
    HeaderComponent: () => import('@components/HeaderComponent.vue'),
    DrawerComponent: () => import('@components/DrawerComponent.vue'),
    FooterComponent: () => import('@components/FooterComponent.vue')
  },

  data: () => ({
    drawer: false,

    links: [
      { text: 'sign in', icon: 'lock_open', link: '/login' },
      { text: 'sign up', icon: 'person_add', link: '/register' },
      { text: 'about', icon: 'info', link: '/about' },
      { text: 'users', icon: 'supervised_user_circle', link: '/users/all' }
    ]
  })
}
</script>
