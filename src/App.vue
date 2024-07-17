<template>
  <div class="q-pa-md" style="max-width: 400px">

    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="name"
        label="ชื่อ-นามสกุล *"
        hint="ชื่อ และ นามสกุล"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'กรุณาพิมพ์ชื่อ']"
      />

      <q-input
        filled
        type="number"
        v-model="age"
        label="อายุ *"
        lazy-rules
        :rules="[
          val => val !== null && val !== '' || 'กรุณาใส่อายุ',
          val => val > 0 && val < 100 || 'กรุณาใส่อายุจริง'
        ]"
      />

      <q-toggle v-model="accept" label="I accept the license and terms" />

      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>

  </div>
</template>

<script setup>
defineOptions({
  name: 'App'
});
</script>
