<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title> Consulta CEP </q-toolbar-title>

        <div style="height:5em"></div>
        <q-avatar>
          <img src="../assets/consultaCEPwhite.png" alt="consultaCepWhite">
        </q-avatar>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <img style="margin: 4em 0 0 8em;" src="../assets/consultaCEP.png"
      />
      <q-list>
        <q-item-label header style="margin: 3em 0 2em 2em; color: #96CEB4; font-size: 20px;">Links - Portfólio</q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
          style="color:#96CEB4"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
{
    title: 'Portfólio',
    caption: 'Portfólio',
    icon: 'pages',
    link: 'https://portfolio-aristotelesaguiar.netlify.app/'
  },
  {
    title: 'Linkedin',
    caption: 'in/aristoteles-aguiar',
    icon: 'face',
    link: 'https://www.linkedin.com/in/aristoteles-aguiar/'
  },
  {
    title: 'GitHub',
    caption: 'aristoteles-aguiar-aadev',
    icon: 'code',
    link: 'https://github.com/aristoteles-aguiar-aadev'
  },

  {
    title: 'Contatos',
    caption: 'Telefone | Whatsapp',
    icon: 'phone',
    link: 'https://api.whatsapp.com/send?phone=5585981066622'
  },
]


export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>

