<template>
  <div class="q-pa-md">
    <q-stepper
      v-model="step"
      ref="stepper"
      alternative-labels
      color="primary"
      animated
    >
      <q-step
        :name="1"
        title="Datos Generales"
        icon="settings"
        :done="step > 1"
      >
        <InquiriesGeneral />
      </q-step>

      <q-step
        :name="2"
        title="Habitos"
        icon="settings"
        :done="step > 2"
      >
        An ad group contains one or more ads which target a shared set of keywords.
      </q-step>

      <q-step
        :name="3"
        title="Salud"
        icon="settings"
      >
        Try out different ad text to see what brings in the most customers, and learn how to
        enhance your ads using features like ad extensions. If you run into any problems with
        your ads, find out how to tell if they're running and how to resolve approval issues.
      </q-step>
      <q-step
        :name="4"
        title="Datos Empresa"
        icon="add_comment"
      >
        Try out different ad text to see what brings in the most customers, and learn how to
        enhance your ads using features like ad extensions. If you run into any problems with
        your ads, find out how to tell if they're running and how to resolve approval issues.
      </q-step>
      <template v-slot:navigation>
        <q-stepper-navigation>
          <q-btn @click="$refs.stepper.next()" color="primary" :label="step === 4 ? 'Finish' : 'Continue'" />
          <q-btn v-if="step > 1" flat color="primary" @click="$refs.stepper.previous()" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </template>
    </q-stepper>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import InquiriesGeneral from '../components/InquiriesGeneral.vue'

export default defineComponent({
  name: "PageIndex",
  components:{
    InquiriesGeneral
  },
  setup(){

    return{
      step: ref(1)
    }
  }
  
});
</script>

<style>

</style>

