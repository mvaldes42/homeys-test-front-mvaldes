<template>
  <div class="notif">
    <div class="title_container">
      <div aria-hidden="true">
        <IconInfo
          v-if="variant == undefined || variant == 'info'"
          alt="Icone d'information"
          class="icon"
        />
        <IconDanger
          v-if="variant == 'danger'"
          alt="Notification d'erreur"
          class="icon"
        />
        <IconSuccess
          v-if="variant == 'success'"
          alt="icone de validation"
          class="icon"
        />
        <IconWarning
          v-if="variant == 'warning'"
          alt="Icone d'avertissement"
          class="icon"
        />
      </div>
      <h1 class="text title">{{ title }}</h1>
      <IconClose
        id="notif-close-button"
        class="icon close"
        role="button"
        tabindex="0"
        @keyup.enter.native="$emit('closeEvent')"
        @click="$emit('closeEvent')"
      />
    </div>
    <p class="text contents">{{ content }}</p>
  </div>
</template>

<script>
import IconClose from '@/assets/close.svg'
import IconDanger from '@/assets/danger.svg'
import IconSuccess from '@/assets/success.svg'
import IconWarning from '@/assets/warning.svg'
import IconInfo from '@/assets/info.svg'

export default {
  name: 'BaseNotification',
  components: { IconClose, IconDanger, IconSuccess, IconWarning, IconInfo },
  props: {
    title: {
      type: String,
      required: true,
    },
    content: {
      type: String,
      required: true,
    },
    variant: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>
@import '../assets/style/notifications.scss';
</style>
