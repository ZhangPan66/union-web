<template>
  <div id="vip">
    <div class="title">普通个人用户</div>
    <el-form :model="personal" ref="personal" class="demo-ruleForm">
      <el-form-item
        label="姓名"
        prop="dep_name"
        :rules="[
      { required: true, message: '请输入正确的信息'},
    ]"
      >
        <el-input type="dep_name" v-model="personal.dep_name" auto-complete="off"></el-input>
      </el-form-item>
      <el-form-item
        label="所属区县"
        prop="county"
        :rules="[
      { required: true, message: '请输入正确的信息'},
    ]"
      >
        <el-input type="county" v-model="personal.county" auto-complete="off"></el-input>
      </el-form-item>
      <el-form-item
        label="联系人"
        prop="contacter"
        :rules="[
      { required: true, message: '请输入正确的信息'},
    ]"
      >
        <el-input type="contacter" v-model="personal.contacter" auto-complete="off"></el-input>
      </el-form-item>
      <el-form-item
        label="联系电话"
        prop="contacter_tel"
        :rules="[
      { required: true, message: '请输入正确的信息'},
    ]"
      >
        <el-input type="contacter_tel" v-model="personal.contacter_tel" auto-complete="off"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="submitForm('personal')">确认申请</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      personal:{
          rel_name:'',
          card_id:"",
          age:"",
      }
    };
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          alert("submit!");
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  }
};
</script>
<style lang="scss" scoped>
#vip {
  width: 100%;
  height: 100%;
}
.title {
  padding-top: 10px;
  text-align: center;
}
.el-form {
  width: 385px;
  margin: 0 auto;
  /deep/.el-input__inner {
    height: 30px;
  }
  .el-button {
    background-color: #06218a;
    color: white;
    width: 212px;
    height: 54px;
    width: 150px;
    margin: 0 auto;
    display: block;
    line-height: 13px;
    height: 35px;
    background: #06218a;
    border-radius: 27px;
    border: 1px solid #979797;
  }
  .el-form-item {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
    justify-content: flex-start;
    /deep/.el-form-item__label {
      width: 51px;
      height: 34px;
    }
  }
  .el-select{
    width:100%;
  }
}
</style>