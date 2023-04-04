<template>
  <div>
    Hello Nuxt!
    {{ serverSideTest }}
  </div>
</template>

<script>
export default {
  setup() {
    const serverSideTest = useState('client', () => 'client')
    if (process.server) {
      serverSideTest.value = 'server'
    }
    return {
      serverSideTest
    }
  }
}
</script>
