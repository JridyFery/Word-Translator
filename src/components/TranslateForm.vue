<template>
  <div class="row justify-content-center" id="translateForm">
    <div class="col-md-6">
      <form id="transForm" class="form-inline" v-on:submit="formSubmit">
        <div class="well">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a Word...">
        <select class="form-control" v-model="language">
          <option value="ru">Russian</option>
          <option value="es">Spanish</option>
          <option value="fr">French</option>
          <option value="zh">Chinese</option>
        </select>
        </div>
        <input class="btn btn-primary ml-5" type="submit" value="Translate">
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data(){
    return {
      textToTranslate:'',
      language:''
    }
  },
  created() {
    this.language = 'ru';
  },
  methods: {
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
}
</script>

<style>

</style>
