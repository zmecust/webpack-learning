<template>
  <div>
    <button class="btn btn-primary" @click="click">Export</button>
  </div>
</template>

<script>
import ExcelExport from 'export-xlsx';
import { SETTINGS_FOR_EXPORT } from "../settings";

export default {
  data() {
    return {
      exportData: [
        {
          data: [
            {
              number: 1,
              name: 'Jack',
              sum: '',
              math: 1,
              physics: 2,
              chemistry: 2,
              informatics: 1,
              literature: 2,
              foreignLang: 1,
              avg: '',
            },
            {
              number: 2,
              name: 'Peter',
              sum: '',
              math: 2,
              physics: 2,
              chemistry: 1,
              informatics: 2,
              literature: 2,
              foreignLang: 1,
              avg: '',
            },
          ]
        }
      ]
    }
  },

  methods: {
    click() {
      const excelExport = new ExcelExport();
      excelExport.downloadExcel(SETTINGS_FOR_EXPORT, this.exportData);
    }
  },
}
</script>
