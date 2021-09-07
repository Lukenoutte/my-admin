<template>
  <q-page>
  <div class="flex flex-center q-mb-lg">
    <q-btn-group push class="text-primary bg-white">
      <q-btn push label="Arquivos Primários" icon="timeline" />
      <q-btn push label="Auditar" icon="visibility" />
      <q-btn push label="Atualizar" icon="update" />
    </q-btn-group>
  </div>
  <q-card class="q-pa-xl">
    <div class="row">
      <q-input bottom-slots outlined class="col-md-4"
      bg-color="white" dense rounded standout placeholder="Pesquisar..."
      >
        <template v-slot:append>
          <q-btn round dense flat icon="search" color="primary" />
        </template>
      </q-input>
      <div class="q-pl-md col-md-4">
        <q-input style="width: 200px;" mask="date" :rules="['date']" dense outlined rounded standout>
          <template v-slot:append>
            <q-icon name="event" class="cursor-pointer">
              <q-popup-proxy ref="qDateProxy" transition-show="scale" transition-hide="scale">
                <q-date color="grey">
                  <div class="row items-center justify-end">
                    <q-btn v-close-popup label="Close" color="primary" flat />
                  </div>
                </q-date>
              </q-popup-proxy>
            </q-icon>
          </template>
        </q-input>
      </div>
      <div class="q-mb-md row justify-end col-md-4">
        <q-btn class="q-mr-sm" color="primary" label="Verificar" size="13px" push no-caps/>
        <q-btn class="q-mr-sm" color="negative" label="Cancelar" size="13px" push no-caps />
        <q-btn color="positive" label="Salvar" size="13px" push no-caps />
      </div>
    </div>
    <q-markup-table>
      <thead>
        <tr>
          <th class="text-left">Dessert (100g serving)</th>
          <th class="text-right">Calories</th>
          <th class="text-right">Fat (g)</th>
          <th class="text-right">Carbs (g)</th>
          <th class="text-right">Protein (g)</th>
          <th class="text-right">Sodium (mg)</th>
          <th class="text-right">Test1 (mg)</th>
          <th class="text-right">Test2 (mg)</th>
          <th class="text-right">Test3 (mg)</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="text-left">Frozen Yogurt</td>
          <td class="text-right">159</td>
          <td class="text-right">6</td>
          <td class="text-right">24</td>
          <td class="text-right">4</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
        </tr>
        <tr>
          <td class="text-left">Ice cream sandwich</td>
          <td class="text-right">237</td>
          <td class="text-right">9</td>
          <td class="text-right">37</td>
          <td class="text-right">4.3</td>
          <td class="text-right">129</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
        </tr>
        <tr>
          <td class="text-left">Eclair</td>
          <td class="text-right">262</td>
          <td class="text-right">16</td>
          <td class="text-right">23</td>
          <td class="text-right">6</td>
          <td class="text-right">337</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
        </tr>
        <tr>
          <td class="text-left">Cupcake</td>
          <td class="text-right">305</td>
          <td class="text-right">3.7</td>
          <td class="text-right">67</td>
          <td class="text-right">4.3</td>
          <td class="text-right">413</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
        </tr>
        <tr>
          <td class="text-left">Gingerbread</td>
          <td class="text-right">356</td>
          <td class="text-right">16</td>
          <td class="text-right">49</td>
          <td class="text-right">3.9</td>
          <td class="text-right">327</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
          <td class="text-right">87</td>
        </tr>
      </tbody>
    </q-markup-table>
  </q-card>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'PageIndex',
  setup () {
    return {
      tab: ref('one')
    }
  }
})
</script>