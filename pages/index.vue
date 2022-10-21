<template>
  <div class="page"></div>
</template>

<script>
export default {
  name: 'IndexPage',
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
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor",
          variant: 'danger',
        },
        {
          title: 'Modal Window',
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor",
          variant: 'success',
        },
        {
          title: 'Modal Window',
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor",
          variant: 'warning',
        },
        {
          title: 'Modal Window',
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor",
          variant: 'info',
        }
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
