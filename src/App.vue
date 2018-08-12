<template>
  <div v-if="signed">
    <div class="profile__header-top" style="background-image: url(/img/header-demo.png);">
        <figure class="logo img-circle"><img class="img-circle" alt="" title="Игорь Noobburner Шуберт" src="/img/demo-ava.jpg" /></figure>
        <div class="profile__header-info">
            <h1 class="title over">{{email}}&nbsp;<a class="mdi mdi-approval" href="#" data-toggle="popover" data-placement="bottom" data-content="Подтверждённая страница"></a></h1>
            <ul>
                <li>Рейтинг: 5608</li>
            </ul>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'profile',
  data () {
    return {
      signed: false,
      email: ''
    }
  },
  methods: {
    getSessions(){
      var email = this.$session.get('email');
      if(email != undefined){
        this.email = email;
        this.signed = true;
      }
      
    }
  },
  created: function(){
    this.getSessions();
  }
}
</script>

<style lang="sass">
/** COLORS **/

$color-primary: #325d88
$color-success: #4CAF50
$color-info: #29abe0
$color-warning: #f47c3c
$color-danger: #d9534f

$color-primary-light: #5588bc
$color-primary-semilight: #3a6793

$color-success-light: #60c364
$color-success-semilight: #56bb5a

$color-info-light: #3abbef
$color-info-semilight: #42b6e5

$color-warning-light: #ff9055
$color-warning-semilight: #f6874b

$color-danger-light: #ef706c
$color-danger-semilight: #ea625e


$color-btn-primary-active: #244363
$color-btn-success-active: #388E3C
$color-btn-info-active: #1b8dbb
$color-btn-warning-active: #ef5c0e
$color-btn-danger-active: #c9302c

$color-btn-primary-activefocus: #1b3249
$color-btn-success-activefocus: #388E3C
$color-btn-info-activefocus: #17759c
$color-btn-warning-activefocus: #ce4f0c
$color-btn-danger-activefocus: #ac2925

$color-bg: #e7e7e4
$color-border: #ddd
$color-activetab: #ececec


$color-extralightgrey: #f9f9f9
$color-lightgrey: #9d9d9d
$color-semigrey: #e0e0e0
$color-grey: #3e3f3a
$color-black: #141414
$color-mineshaft: #1d1d1d
$color-white: #fafafa

$color-gold: #ffbb61
$color-darkgold: #d09652


$color-silver: #999999
$color-bronze: #a46628


/** COLORS **/

.profile__header
  overflow: hidden
  background-color: $color-white
  border-bottom: 1px solid $color-border
  margin-top: -15px
  margin-left: -15px
  margin-right: -15px
h1 .title
  color: white
.profile__header-top
  padding-bottom: 20px
  border-bottom: 1px solid #e5e5e5
  .logo

    img
      width: 124px
      height: 124px

    float: left
    width: 124px
    height: 124px
    -webkit-box-shadow: 0 1px 2px rgba(0, 0, 0, 0.12)
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.12)
    margin-right: 25px
    position: relative
    z-index: 1

.profile__header .profile__header-top
  padding: 20px
  padding-top: 115px
  border-bottom-width: 0
  position: relative
  -webkit-box-shadow: 0 1px 2px rgba(0, 0, 0, 0.12)
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.12)
  background-repeat: no-repeat
  background-position: right top
  -webkit-background-size: cover
  background-size: cover
  color: #fff
  &:after
    content: ""
    position: absolute
    left: 0
    top: 50%
    bottom: 0
    width: 100%
    background-image: -webkit-linear-gradient(top, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.3) 100%)
    background-image: -moz-linear-gradient(top, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.3) 100%)
    background-image: -ms-linear-gradient(top, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.3) 100%)
    background-image: -o-linear-gradient(top, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.3) 100%)
    background-image: linear-gradient(top, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.3) 100%)

.profile__header-info
  //overflow: hidden
  position: relative
  z-index: 1

  a
    color: white
  a:hover
    color: white
  a:focus
    color: white
  a:active
    color: white

  > .title
    @media (min-width: 467px)
      max-width: 942px
      overflow: hidden
      white-space: pre
      text-overflow: ellipsis
    text-shadow: 1px 0 2px #141414
    color: white
    margin-top: 4px
    margin-bottom: 4px
    font-size: 2em

.profile__header-top ul
  list-style: none
  padding: 0
  margin: 0

  li:only-child
    text-shadow: 1px 0 2px #141414
    font-family: Evolventa, 'Helvetica Neue', Arial, sans-serif
    font-size: 17px


  > li
    text-shadow: 1px 0 2px #141414
    display: inline-block
    margin-right: 2%
    &:last-child
      margin-left: 0
    i:before
      margin: -2px 10px 0 0
    a
      color: $color-white
      text-decoration: underline
      &:hover
        color: $color-gold
        text-decoration: none
      &:focus
        color: $color-gold
        text-decoration: none
      &:active
        color: $color-gold
        text-decoration: none

</style>
