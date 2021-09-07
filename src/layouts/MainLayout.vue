<template>
  <q-layout view="hHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="justify-between">
        <div class="row items-center">
          <q-btn
            flat
            dense
            round
            icon="menu"
            aria-label="Menu"
            @click="toggleLeftDrawer"
          />

          <q-toolbar-title>
            myADMIN
          </q-toolbar-title>

          <q-input v-if="$q.screen.gt.sm"
          class="q-ml-sm" :input-style="{ color: 'black', fontSize: '14px' }"
          standout bg-color="white" dense rounded placeholder="Pesquisar...">
            <template v-slot:append>
              <q-btn round dense flat icon="search" color="primary" />
            </template>
          </q-input>
        </div>
        <div class="row items-center">
          <div class="q-mr-md">
            <q-btn color="white" class="q-mr-sm" dense push>
              <q-badge floating color="negative" rounded> 1 </q-badge>
              <q-avatar size="27px" icon="notifications_none" text-color="primary"/>
              <q-menu
                :offset="[100, 15]"
                transition-show="jump-down"
                transition-hide="jump-up"
                class="q-mt-lg"
              >
                <q-list style="min-width: 100px">
                  <q-item>
                    <q-item-section>1 Notificação</q-item-section>
                  </q-item>
                  <q-separator />
                </q-list>
              </q-menu>
            </q-btn>
            <q-btn color="white" dense class="q-mr-sm" push>
              <q-avatar size="27px" icon="person_outline" text-color="primary"/>
              <q-menu
                :offset="[0, 15]"
                transition-show="jump-down"
                transition-hide="jump-up"
                class="q-mt-lg"
              >
                <q-list style="min-width: 100px">
                  <q-item clickable>
                    <q-item-section>Editar</q-item-section>
                  </q-item>
                  <q-item clickable to="/login">
                    <q-item-section>Sair</q-item-section>
                  </q-item>
                  <q-separator />
                </q-list>
              </q-menu>
            </q-btn>
          </div>
          <div class="column">
            <span>
              Lucas Lima
            </span>
            <q-badge  rounded color="white" text-color="primary">
              <div class="text-center full-width">ROOT</div>
            </q-badge>
          </div>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      :mini="miniState"
      show-if-above
      bordered
      :width="200"
      class="bg-grey-2"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          <q-chip color="primary" text-color="white" icon="bookmark" v-if="!miniState">
            Navegação
          </q-chip>
        </q-item-label>

        <LeftMenu
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <div class="flex flex-center bg-grey-1">
        <router-view class="q-pt-xl" style="width: 90%;" />
      </div>
    </q-page-container>
  </q-layout>
</template>

<script>
import LeftMenu from 'src/components/LeftMenu.vue'
import { useQuasar } from 'quasar'
const linksList = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  }
];

import { defineComponent, ref } from 'vue'
export default defineComponent({
  name: 'MainLayout',

  components: {
    LeftMenu
  },

  setup () {
    const $q = useQuasar()
    const leftDrawerOpen = ref(false)
    const miniState = ref(false)

    const toggleLeftDrawer =  () => {
      miniState.value = !miniState.value
      if ($q.screen.sm || $q.screen.xs) leftDrawerOpen.value = !leftDrawerOpen.value
    }

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      miniState,
      toggleLeftDrawer
    }
  }
})
</script>