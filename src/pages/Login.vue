<template>
  <q-page class="flex flex-center bg-grey-2">
    <q-card style="width: 450px; height: 350px;">
      <div class="q-pa-xl">
        <div class="flex flex-center q-mb-md">
          <label class="text-primary" style="font-size: 25px;">myADMIN</label>
        </div>
        <q-input bottom-slots outlined
        bg-color="white" dense rounded standout placeholder="Usuario" v-model="user"/>
        <q-input bottom-slots outlined :type="inputPasswordType"
        bg-color="white" dense rounded standout placeholder="Senha" v-model="pass">
          <template v-slot:append>
            <q-btn @click="changeTypePassInput" round dense flat icon="remove_red_eye" color="primary" />
          </template>
        </q-input>
        <div class="flex justify-between q-mb-md">
          <div>
            <q-checkbox keep-color v-model="rememberCheckBox" color="primary" dense/>
            <span class="q-ml-sm">Lembre-me</span>
          </div>
          <router-link to="/" class="link-forgot-pass text-primary">Esqueceu a senha?</router-link>
        </div>
        <q-btn to="/" class="full-width" color="primary" label="Entrar" push no-caps />
      </div>
    </q-card>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'
export default defineComponent({
  name: 'Login',

  components: {},

  setup () {
    const rememberCheckBox = ref(false)
    const inputTypes = { pass: 'password',  text: 'text' }
    const inputPasswordType = ref(inputTypes.text)
    const user = ''
    const pass = ''

    const changeTypePassInput = () => {
      if (inputPasswordType.value === inputTypes.pass) return inputPasswordType.value = inputTypes.text
      if (inputPasswordType.value === inputTypes.text) return  inputPasswordType.value = inputTypes.pass
    }
    return {
      rememberCheckBox,
      inputPasswordType,
      changeTypePassInput,
      user,
      pass
    }
  }
})
</script>

<style scoped>
  .link-forgot-pass{
    text-decoration: none;
    font-weight: bold;
  }
</style>