<!--
Modal component with customizable slots and CSS transitions.
-->

<script setup>
import Modal from './Modal.vue'
import { ref } from 'vue'

const showModal = ref(false)
</script>

<template>
  <button id="show-modal" @click="showModal = true">Show Modal</button>

  <Teleport to="body">
    <!-- use the modal component, pass in the prop -->
    <modal :show="showModal" @close="showModal = false">
      <template #header>
        <h3>custom header</h3>
      </template>
    </modal>
  </Teleport>
</template>

<!-- モーダル:閉じるまで親ウィンドウの操作ができない子ウィンドウのこと。
<Teleport> コンポーネント: モーダルコンポーネントを <Teleport> でラップしています。
to="body" 属性により、モーダルを <body> 要素に移動させることができます。
これにより、モーダルが他のコンポーネントの外側に描画されることが保証されます。
-->