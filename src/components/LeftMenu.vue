<template>
  <div style="max-width: 350px">
    <div style="max-width: 250px">
    <q-list padding class="rounded-borders text-primary">
      <q-item
        clickable
        v-ripple
        to="/"
        :active="link === 'inbox'"
        active-class="my-menu-link"
      >
        <q-item-section avatar>
          <q-icon name="home" />
        </q-item-section>

        <q-item-section>Início</q-item-section>
      </q-item>

      <q-item
        clickable
        to="/arquivos"
        v-ripple
        :active="link === 'outbox'"
        active-class="my-menu-link"
      >
        <q-item-section avatar>
          <q-icon name="send" />
        </q-item-section>

        <q-item-section>Arquivos</q-item-section>
      </q-item>

      <q-item
        clickable
        v-ripple
        :active="link === 'trash'"
        active-class="my-menu-link"
      >
        <q-item-section avatar>
          <q-icon name="delete" />
        </q-item-section>

        <q-item-section>Trash</q-item-section>
      </q-item>

      <q-separator spaced />

      <q-item
        clickable
        v-ripple
        :active="link === 'settings'"
        active-class="my-menu-link"
      >
        <q-item-section avatar>
          <q-icon name="settings" />
        </q-item-section>

        <q-item-section>Settings</q-item-section>
      </q-item>

      <q-item
        clickable
        v-ripple
        :active="link === 'help'"
        active-class="my-menu-link"
      >
        <q-item-section avatar>
          <q-icon name="help" />
        </q-item-section>

        <q-item-section>Help</q-item-section>
      </q-item>
    </q-list>
  </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'LeftMenu',
  props: {
    title: {
      type: String,
      required: true
    },

    caption: {
      type: String,
      default: ''
    },

    link: {
      type: String,
      default: '#'
    },

    icon: {
      type: String,
      default: ''
    }
  }
})
</script>
