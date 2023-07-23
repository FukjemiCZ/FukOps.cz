<template>
  <div class="push"></div>
   <div class="footer center">Vytvořeno v <a href="https://github.com/NdagiStanley/VueDN " target="_blank">VueDN</a> | AD {{ year }}</div>
</template>
<script>
const d = new Date()
const currentYear = d.getFullYear()
export default {
  data() {
    return {
      year: currentYear
    }
  }
}
</script>
