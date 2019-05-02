<template>
  <div>
    <LocFilter/>
    <div style="margin-top: 10px"></div>
    <LocTable/>
  </div>
</template>

<script>
import LocFilter from "../../../components/LocFilter.vue";
import LocTable from "../../../components/LocTable.vue";

export default {
  components: {
    LocFilter,
    LocTable
  }
};
</script>

<style>
</style>
