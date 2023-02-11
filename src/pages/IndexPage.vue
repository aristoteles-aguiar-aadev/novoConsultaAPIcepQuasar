<template>
  <q-page class="flex flex-center">
    <div class="q-pa-md" style="max-width: 400px">
      <div class="row">
        <q-form @submit="onSubmit" @reset="onReset" class="q-col-gutter">
          <div class="input">
            <q-input
              class="cep"
              rounded
              standout
              bottom-slots
              v-model="cep"
              label="CEP"
              hint="CEP"
              lazy-rules
              :rules="[
                (val) =>
                  (val && val.length > 8) || 'Insira o CEP a ser consultado',
              ]"
            >
              <template v-slot:prepend>
                <q-icon name="place" />
              </template>
            </q-input>

            <q-separator style="background-color: #96ceb4" />
            <p></p>

            <q-input
              outlined
              class="col1"
              rounded
              standout
              bottom-slots
              v-model="logradouro"
              label="Logradouro"
              hint="Avenida | Rua"
            >
            </q-input>

            <q-separator style="background-color: #96ceb4" />
            <p></p>

            <q-input
              outlined
              rounded
              standout
              bottom-slots
              v-model="complemento"
              label="Complemento"
              hint="Complemento | Referência"
            >
            </q-input>

            <q-separator style="background-color: #96ceb4" />
            <p></p>

            <q-input
              outlined
              rounded
              standout
              bottom-slots
              v-model="bairro"
              label="Bairro"
              hint="Bairro | Distrito "
            >
            </q-input>

            <q-separator style="background-color: #96ceb4" />
            <p></p>

            <q-input
              outlined
              rounded
              standout
              bottom-slots
              v-model="localidade"
              label="Localidade"
              hint="Cidade"
            >
            </q-input>

            <q-separator style="background-color: #96ceb4" />
            <p></p>

            <q-input
              class="uf"
              outlined
              rounded
              standout
              bottom-slots
              v-model="uf"
              label="UF"
              hint="UF"
            >
            </q-input>
          </div>
          <div>
            <q-btn
              label="Limpar"
              type="reset"
              color="white"
              flat
              class="q-ml-sm"
              style="background: #96ceb4"
            />
          </div>
        </q-form>
      </div>
    </div>
  </q-page>
</template>
<style>
.input {
  width: 30em;
  margin: 10px;
}
.cep {
  width: 15em;
}
.uf {
  width: 8em;
}
</style>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
});


</script>
