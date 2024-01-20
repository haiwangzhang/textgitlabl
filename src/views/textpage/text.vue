<template>
    <div>
      <div class="textone">
        <el-row :gutter="4">
        <el-form ref="elForm" :model="formData" :rules="rules" size="small" label-width="2px"
          label-position="top">
          <el-col :span="24">
            <el-form-item label="" prop="field110">
              <el-input v-model="formData.field110" placeholder="请输入搜索内容" clearable :style="{width: '100%'}">
              </el-input>
            </el-form-item>
          </el-col>
          <el-col :span="3">
            <el-form-item label="" prop="mobile">
              <el-input v-model="formData.mobile" placeholder="请输入" clearable suffix-icon='el-icon-search'>
              </el-input>
            </el-form-item>
          </el-col>
          <el-col :span="3">
            <el-form-item label="" prop="field102">
              <el-select v-model="formData.field102" placeholder="请选择" clearable :style="{width: '100%'}">
                <el-option v-for="(item, index) in field102Options" :key="index" :label="item.label"
                  :value="item.value" :disabled="item.disabled"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="3">
            <el-form-item label="" prop="field103">
              <el-select v-model="formData.field103" placeholder="请选择" clearable :style="{width: '100%'}">
                <el-option v-for="(item, index) in field103Options" :key="index" :label="item.label"
                  :value="item.value" :disabled="item.disabled"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="3">
            <el-form-item label="" prop="field101">
              <el-select v-model="formData.field101" placeholder="请选择" clearable :style="{width: '100%'}">
                <el-option v-for="(item, index) in field101Options" :key="index" :label="item.label"
                  :value="item.value" :disabled="item.disabled"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="6">
            <el-form-item label="" prop="field107">
              <el-date-picker type="daterange" v-model="formData.field107" format="yyyy-MM-dd"
                value-format="yyyy-MM-dd" :style="{width: '100%'}" start-placeholder="开始日期"
                end-placeholder="结束日期" range-separator="至" clearable></el-date-picker>
            </el-form-item>
          </el-col>
          <el-col :span="6">
            <el-form-item size="large">
              <el-button type="primary" @click="submitForm">提交</el-button>
              <el-button @click="resetForm">重置</el-button>
            </el-form-item>
          </el-col>
        </el-form>
      </el-row>
      </div>
    </div>
  </template>
  <script>
  export default {
    components: {},
    props: [],
    data() {
      return {
        formData: {
          field110: undefined,
          mobile: '',
          field102: undefined,
          field103: undefined,
          field101: undefined,
          field107: null,
        },
        rules: {
          field110: [],
          
          field101: [],
          field107: [],
        },
        field102Options: [{
          "label": "选项一",
          "value": 1
        }, {
          "label": "选项二",
          "value": 2
        }],
        field103Options: [{
          "label": "选项一",
          "value": 1
        }, {
          "label": "选项二",
          "value": 2
        }],
        field101Options: [{
          "label": "选项一",
          "value": 1
        }, {
          "label": "选项二",
          "value": 2
        }],
      }
    },
    computed: {},
    watch: {},
    created() {},
    mounted() {},
    methods: {
      submitForm() {
        this.$refs['elForm'].validate(valid => {
          if (!valid) {
            console.log(this.formData)
          }
          // TODO 提交表单
        })
      },
      resetForm() {
        this.$refs['elForm'].resetFields()
      },
    }
  }
  
  </script>
  <style>
  .textone{
    padding: 10px 20px;
  }
  </style>
  