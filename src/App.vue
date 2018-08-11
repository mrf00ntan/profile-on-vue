<template>
  <div id="app">
    <h1 class="title over">
      {{name}} {{username}} {{surname}}&nbsp;
      <a class="mdi mdi-approval" href="#" data-toggle="popover" data-placement="bottom" data-content="Подтверждённая страница" data-original-title="" title=""></a>
    </h1>
  </div>
</template>

<script>
export default {
  name: 'profile',
  data () {
    return {
      name: '',
      surname: '',
      username: ''
    }
  },
  methods: {
    getSessions(){
      this.name = this.$session.get('name');
      this.surname = this.$session.get('surname');
      this.username = this.$session.get('username');
    }
  },
  created: function(){
    this.getSessions();
  }
}
</script>

<style lang="scss">
#app{
  color: white;
}
</style>
