<template>
  <div class="page">
    <BaseNotification
      v-for="notif in filteredNotifs"
      :key="notif.id"
      :icon="notif.icon"
      :title="notif.title"
      :content="notif.content"
      :class="notif.variant"
      @closeEvent="() => (notif.show = !notif.show)"
    />
    <button
      @click.prevent="
        addNotif({
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'danger',
          icon: '../assets/danger.svg',
          show: true,
        })
      "
    >
      Danger !!!
    </button>
  </div>
</template>

<script>
import BaseNotification from '../components/BaseNotification.vue'
import IconDanger from '../assets/danger.svg'
import IconSuccess from '../assets/success.svg'
import IconWarning from '../assets/warning.svg'
import IconInfo from '../assets/info.svg'

export default {
  name: 'IndexPage',
  components: {
    BaseNotification,
  },
  data() {
    return {
      /**
       * Liste des notifications à afficher pour l'étape 1
       * @example [{
       *   title // titre de la notification
       *   content // contenu de la notification
       *   variant // type de notification (sert pour déterminer quelle couleur utiliser)
       * }]
       */
      currentNotifs: [],
      notifications: [
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'danger',
          icon: IconDanger,
          show: false,
        },
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'success',
          icon: IconSuccess,
          show: false,
        },
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'warning',
          icon: IconWarning,
          show: false,
        },
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'info',
          icon: IconInfo,
          show: false,
        },
      ],
    }
  },
  computed: {
    filteredNotifs() {
      return this.currentNotifs.filter(({ show }) => show)
    },
  },
  methods: {
    addNotif(notif) {
      this.currentNotifs.push(notif)
    },
  },
}
</script>
<style lang="scss" scoped>
.page {
  position: relative;
  min-height: 100vh;
}
</style>
