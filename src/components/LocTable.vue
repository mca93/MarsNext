<template>
  <v2-table
    :data="list4"
    border
    height="300"
    :total="total"
    :loading="loading"
    @page-change="handlePageChange"
    :pagination-info="paginationInfo"
    :shown-pagination="true"
  >
    <v2-table-column label="Customer's Number" prop="name" width="300" fixed="left"></v2-table-column>
    <v2-table-column label="Customer's Name" prop="LocRef" width="150"></v2-table-column>
    <v2-table-column label="Card Number" prop="birthDay" width="150"></v2-table-column>
    <v2-table-column label="Card Calor" prop="regime" width="150"></v2-table-column>
    <v2-table-column label="Expire on" prop="locStatus" width="150"></v2-table-column>
    <v2-table-column label="Actions" width="300" fixed="right">
      <template slot-scope="scope">
        <router-link
          class="event-link"
          :to="{ name: 'effectPayment', params: { LocRef: list4.LocRef } }"
        >
          <el-button size="mini" icon="el-icon-edit">Edit</el-button>
        </router-link>
        <router-link class="event-link" :to="{ name: 'effectPayment', params: { LocRef: LocRef } }">
          <el-button size="mini" type="success" icon="mdi mdi-cash">Effect Payment</el-button>
        </router-link>
        <router-link class="event-link" :to="{ name: 'locDetail', params: { LocRef: LocRef } }">
          <el-button size="mini" icon="el-icon-info">View</el-button>
        </router-link>
      </template>
    </v2-table-column>
  </v2-table>
</template>

<script>
export default {
  data() {
    return {
      currentPage: 1,
      total: 198,
      loading: false,
      paginationInfo: {
        text:
          "<span>Total of <strong>198</strong>, <strong>10</strong> per page</span>"
      },
      list4: [
        {
          date: "2017-12-02",
          name: "Game",
          LocRef: "190LOC90319141",
          birthDay: "1988-09-08",
          regime: "Importacao",
          locStatus: "Aprovado"
        },
        {
          date: "2017-11-02",
          name: "Anadarko",
          LocRef: "18LOC8910410",
          birthDay: "1978-09-08",
          regime: "Exportacao",
          locStatus: "Rejeitado"
        },
        {
          date: "2018-01-02",
          name: "Valter Cheque3",
          LocRef: "12LOC791410414",
          birthDay: "1998-12-08",
          regime: "Importacao",
          locStatus: "Regularizado Parcialmente"
        },
        {
          date: "2018-01-02",
          name: "Mauro Mauane4",
          LocRef: "12LOC7914190",
          birthDay: "1998-12-08",
          regime: "Importacao",
          locStatus: "Regularizado Totalmente"
        },
        {
          date: "2018-01-02",
          name: "Mario Junior5",
          LocRef: "110LOC7914190",
          birthDay: "1998-12-08",
          regime: "Exportacao",
          locStatus: "Cancelado"
        },
        {
          date: "2018-01-02",
          name: "Coca-cola6",
          LocRef: "19LOC791419313",
          birthDay: "1998-12-08",
          regime: "Importacao",
          locStatus: "Expirado"
        },
        {
          date: "2018-01-02",
          name: "Shoprite7",
          LocRef: "19LOC7914193114",
          birthDay: "1998-12-08",
          regime: "Exportacao",
          locStatus: "Submentido"
        },
        {
          date: "2018-01-02",
          name: "Eni8",
          LocRef: "28LOC0148018414",
          birthDay: "1998-12-08",
          regime: "Exportacao",
          locStatus: "Submetido"
        },
        {
          date: "2018-01-02",
          name: "Tobacco9",
          LocRef: "28LOC0148018415",
          birthDay: "1998-12-08",
          regime: "Importacao",
          locStatus: "Aprovado"
        },
        {
          date: "2018-01-02",
          name: "Stephan Jorge10",
          LocRef: "19LOC014801324",
          birthDay: "1998-12-08",
          regime: "Exportacao",
          locStatus: "Aprovado"
        }
      ]
    };
  },

  methods: {
    handlePageChange(page) {
      this.currentPage = page;
      this.loading = true;
      let start = (page - 1) * 10 + 1;

      const list = this.list4.map(item => {
        return Object.assign({}, item, {
          name: `Jenit Anantlal${start++}`
        });
      });

      setTimeout(() => {
        this.loading = false;
        this.list4 = [].concat(list);
      }, 2000);
    }
  }
};
</script> 