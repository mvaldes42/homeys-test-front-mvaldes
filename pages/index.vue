<template>
  <div class="page">
    <BaseNotification
      v-for="notif in notifications"
      :key="notif.id"
      :icon="notif.icon"
      :title="notif.title"
      :content="notif.content"
      :class="notif.variant"
    />
  </div>
</template>

<script>
import BaseNotification from '../components/BaseNotification.vue'

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
      notifications: [
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'danger',
          icon: '../assets/danger.svg',
        },
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'success',
          icon: '../assets/success.svg',
        },
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'warning',
          icon: '../assets/warning.svg',
        },
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'info',
          icon: '../assets/info.svg',
        },
      ],
    }
  },
}
</script>
<style lang="scss" scoped>
.page {
  position: relative;
  min-height: 100vh;
}
</style>
