<template>
  <div class="notif">
    <div class="title_container">
      <img class="icon" :src="icon" />
      <span class="text title">{{ title }}</span>
      <img class="icon close" src="../assets/close.svg" />
    </div>
    <p class="text contents">{{ content }}</p>
  </div>
</template>

<script>
export default {
  name: 'BaseNotification',
  props: {
    icon: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    content: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>
.notif {
  max-width: 527px;
  max-height: 160px;
//   position: absolute;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 24px;
  gap: 8px;
  box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.1);
  border-radius: 16px;
  overflow: hidden;
}

.title_container {
  width: 100%;
  display: flex;
  flex-direction: row;
  align-content: center;
}
.icon {
  width: 32px;
  height: 32px;
  align-self: center;
  order: 0;
  flex-grow: 0;
}
.icon.close {
  width: 20px;
  height: 20px;
  order: 2;
}
.text {
  font-family: 'DM Sans';
  font-style: normal;
}
.title {
  padding-left: 19px;
  align-self: center;
  font-weight: 500;
  font-size: 20px;
  color: #424242;
  order: 1;
  flex-grow: 1;
}
.contents {
  max-width: 431px;
  max-height: 72px;
  padding-left: calc(32px + 19px);
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #757575;
  flex: none;
  order: 0;
  flex-grow: 1;
  overflow-y: auto;
}
</style>
