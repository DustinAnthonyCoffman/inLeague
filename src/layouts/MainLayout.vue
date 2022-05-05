<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title>
          InLeague Take Home
        </q-toolbar-title>
        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import '../assets/tailwind.css'



export default defineComponent({
  name: 'MainLayout'
})
</script>
