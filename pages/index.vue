<template>
  <div class="page">
    <button
      class="push-button"
      @click.prevent="addNotif(notifications[Math.floor(Math.random() * 3)])"
    >
      Push!
    </button>
    <div class="notif-container">
      <BaseNotification
        v-for="notif in filteredNotifs"
        :key="notif.id"
        :title="notif.title"
        :content="notif.content"
        :variant="notif.variant"
        :class="notif.variant"
        @closeEvent="() => (notif.show = !notif.show)"
      />
    </div>
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
      currentNotifs: [],
      notifications: [
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'danger',
          show: false,
        },
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'success',
          show: false,
        },
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'warning',
          show: false,
        },
        {
          title: 'Modal Window',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor',
          variant: 'info',
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
      this.currentNotifs.push({
        title: notif.title,
        content: notif.content,
        variant: notif.variant,
        show: true,
      })
    },
  },
}
</script>
<style lang="scss" scoped>
.page {
  position: relative;
  min-height: 100vh;
}

.push-button {
  width: fit-content;
  height: fit-content;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 500;
  font-size: 15px;
  text-align: center;
  background-color: #dfdfdf;
  padding: 10px;
  border-radius: 10px;
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  cursor: pointer;

  margin: auto;
}
.push-button:hover {
  background: none;
  border: 1px solid #dfdfdf;
}
.notif-container {
  height: 100vh;
  width: 100%;
  display: table-cell;
  vertical-align: bottom;
}
</style>
