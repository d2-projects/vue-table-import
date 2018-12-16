<template>
  <div id="app">
    <p>选择 xlsx</p>
    <input type="file" accept=".xlsx" @change="onXlsxInputChange">
    <p>选择 csv</p>
    <input type="file" accept=".csv" @change="onCsvInputChange">
  </div>
</template>

<script>
export default {
  name: 'app',
  methods: {
    onXlsxInputChange (e) {
      for (let index = 0; index < e.target.files.length; index++) {
        this.$import.xlsx(e.target.files[index])
          .then(data => {
            console.log(data)
          })
      }
    },
    onCsvInputChange (e) {
      for (let index = 0; index < e.target.files.length; index++) {
        this.$import.csv(e.target.files[index])
          .then(data => {
            console.log(data)
          })
      }
    }
  }
}
</script>
