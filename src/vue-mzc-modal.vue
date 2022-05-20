<script>
export default /*#__PURE__*/ {
  name: "VueMzcModal",
  props: {
    title: {
      type: String,
      default: "",
    },
  },
  created() {
    this.$nextTick(function () {
      this.$refs.modal.focus();
    })
  },
};
</script>

<template>
  <div class="vue-mzc-modal">
    <div class="vue-mzc-modal__container">
      <div class="vue-mzc-modal__middle">
        <div class="vue-mzc-modal__box">
          <div class="vue-mzc-modal__overlay" aria-hidden="true" @click="$emit('close')"></div>
          <div class="vue-mzc-modal-box" aria-modal="true" ref="modal" @keydown.esc="$emit('close')" tabindex="-1">
            <div class="vue-mzc-modal-box__header">
              <div class="vue-mzc-modal-box__title">{{ title }}</div>
              <button
                class="vue-mzc-modal-box__close"
                @click="$emit('close')"
                tabindex="0"
              ></button>
            </div>
            <slot />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
:root {
  --vue-mzc-modal-overlay-color: rgba(0,0,0, 0.5);
  --vue-mzc-modal-box-gap: 30px;
  --vue-mzc-modal-box-width: 410px;
  --vue-mzc-modal-box-border-radius: 10px;
  --vue-mzc-modal-box-title-size: 1.25em;
  --vue-mzc-modal-box-text-color: #000000;
  --vue-mzc-modal-box-background-color: #ffffff;
  --vue-mzc-modal-box-close-image: url("data:image/svg+xml,%3Csvg width='14' height='14' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M7 8.4 1.4 14 0 12.6 5.6 7 0 1.4 1.4 0 7 5.6 12.6 0 14 1.4 8.4 7l5.6 5.6-1.4 1.4L7 8.4Z' fill='%23000'/%3E%3C/svg%3E");
}
.vue-mzc-modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0, 0.5);
  background-color: var(--vue-mzc-modal-overlay-color);
  z-index: 9999;
  overflow-y: auto;
  overflow-x: hidden;
  -webkit-overflow-scrolling: touch;
  animation: vue-mzc-modal-fade 0.25s 1;
}
.vue-mzc-modal::-webkit-scrollbar {
  width: 4px;
}
.vue-mzc-modal::-webkit-scrollbar-thumb {
  background-color: rgba(255,255,255,0.66);
}
.vue-mzc-modal__container,
.vue-mzc-modal__middle {
  height: 100%;
}
.vue-mzc-modal__container {
  margin-left: auto;
  margin-right: auto;
  padding-left: 16px;
  padding-right: 16px;
}
.vue-mzc-modal__middle,
.vue-mzc-modal__box {
  width: 100%;
}
.vue-mzc-modal__middle {
  display: table;
}
.vue-mzc-modal__box {
  padding-top: 16px;
  padding-bottom: 16px;
  display: table-cell;
  vertical-align: middle;
}
.vue-mzc-modal__overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.vue-mzc-modal-box {
  margin-left: auto;
  margin-right: auto;
  padding: 30px;
  padding: var(--vue-mzc-modal-box-gap);
  display: block;
  max-width: 410px;
  max-width: var(--vue-mzc-modal-box-width);
	color: #000000;
	color: var(--vue-mzc-modal-box-text-color);
  background-color: #ffffff;
  background-color: var(--vue-mzc-modal-box-background-color);
  border-radius: 10px;
  border-radius: var(--vue-mzc-modal-box-border-radius);
  animation: vue-mzc-modal-popup 0.25s 1;
  position: relative;
}
.vue-mzc-modal-box__header {
  margin-bottom: 40px;
  padding-right: 20px;
}
.vue-mzc-modal-box__title {
	font-size: 1.25em;
	font-size: var(--vue-mzc-modal-box-title-size);
  font-weight: 700;
}
.vue-mzc-modal-box__close {
  cursor: pointer;
  display: block;
  width: 24px;
  height: 24px;
  position: absolute;
  top: 16px;
  right: 16px;
  background-color: transparent;
	background-image: url("data:image/svg+xml,%3Csvg width='14' height='14' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M7 8.4 1.4 14 0 12.6 5.6 7 0 1.4 1.4 0 7 5.6 12.6 0 14 1.4 8.4 7l5.6 5.6-1.4 1.4L7 8.4Z' fill='%23000'/%3E%3C/svg%3E");
	background-image: var(--vue-mzc-modal-box-close-image);
	background-size: 14px 14px;
	background-position: center center;
	background-repeat: no-repeat;
  border: none;
}
@keyframes vue-mzc-modal-fade {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes vue-mzc-modal-popup {
  from {
    opacity: 0;
    transform: scale3d(0.95, 0.95, 0.95);
  }
  to {
    opacity: 1;
    transform: scale3d(1, 1, 1);
    visibility: visible;
  }
}
</style>