<template>
   <q-page class="flex flex-center row">
    <!--<img
      alt="Quasar logo"
      src="~assets/quasar-logo-vertical.svg"
      style="width: 200px; height: 200px"
    >-->

    <div class="q-pa-md shadow-2 col-10">
      <form class="q-gutter-md">
        <h4 class="title" style="margin: 16px 0px 0px 20px">Datos Personales</h4>
        <div class="row q-col-gutter-sm">
          <!--Input name-->
          <q-input
            class="col-6"
            ref="nameRef"
            filled
            v-model="name"
            label="Nombre"
            lazy-rules
            :rules="nameRules"
          />
          <!--Input LastName-->
          <q-input
            class="col-6"
            ref="lastNameRef"
            filled
            v-model="lastName"
            label="Apellido"
            lazy-rules
            :rules="lastnameRules"
          />
        </div>
        <div class="row q-col-gutter-sm">
          <q-input
            class="col-5"
            v-model="date"
            filled
            type="date"
            hint="Fecha de Nacimiento"
          />
          <div class="col-1"></div>
          <q-input
            class="col-3"
            v-model="altura"
            type="number"
            filled
            label="Altura"
            mask="###"
          />
          <q-input
            class="col-3"
            v-model="peso"
            type="number"
            filled
            label="Peso"
            mask="###"
          />
        </div>
        <div class="row q-col-gutter-sm">
          <q-input
            class="col-6"
            filled
            v-model="phone"
            label="Telefono"
            mask="## #### ####"
            unmasked-value
            hint="Mask: ## #### ####"
          />
          <q-input
            class="col-6"
            filled
            v-model="mobile"
            label="Celular"
            mask="(###) ### - ####"
            unmasked-value
            hint="Mask: (###) ### - ####"
          />
        </div>
        <div class="row q-col-gutter-sm">
           <q-select
            class="col-5"
            transition-show="scale"
            transition-hide="scale"
            v-model="bloodType"
            :options="optionsBloodType"
            label="Tipo de Sangre"
            style="margin-bottom: 32px"
          />
        </div>
      </form>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'InquiriesGeneral',
    setup() {
    const name = ref(null);
    const nameRef = ref(null);
    const bloodType = ref(null);
    return {
      bloodType,
      optionsBloodType: [
        "O Positivo",
        "O Negativo",
        "A Negativo",
        "A Positivo",
        "B Negativo",
        "B Positivo",
        "AB Negativo",
        "AB Positivo",
      ],
      nameRef,
      name,
      nameRules: [
        (val) =>
          (val && val.length > 0) || "Por favor ingresa un nombre valido",
      ],
    };
  },
})
</script>

<style>

</style>

