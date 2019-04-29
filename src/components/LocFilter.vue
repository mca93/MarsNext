<template>
<div>
    <el-row :gutter="20">
  <el-col :span="6">
	<el-input placeholder="Loc Ref" v-model="input"></el-input>
  </el-col>
  <el-col :span="6">
      <template>
    <el-select v-model="value" placeholder="Regime">
        <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value">
        </el-option>
    </el-select>
        </template>

  </el-col>
  <el-col :span="6"> 
      <template>
    <el-select v-model="value" placeholder="Loc Status">
        <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value">
        </el-option>
    </el-select>
    </template>	
    </el-col>
    <el-col :span="6">
        <el-button type="primary">Search</el-button>
    </el-col>
</el-row>
</div>
</template>

<script>
export default {
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 5px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 5px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
</style>

