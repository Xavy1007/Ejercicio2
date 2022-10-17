<template>
  <nav class="navbar navbar-expand-lg " style="background-color: gray;">
    <app-menu></app-menu>
  </nav>


  <router-view/>

<app-footer></app-footer>
</template>
<script>
    import appMenu from '@/components/appMenu.vue'
    import appFooter from '@/components/appFooter.vue'

    export default{
        name:'app',
        data(){
            return{
            }
        },
        methods:{
        },
        computed:{
          
        },
        mounted(){
        },
        components:{
          appMenu,

          appFooter
        }
        }
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.color-box {
                width: 40px;
                height: 40px;
                border-radius: 50%;
                margin: 7px;
                display: inline-block;
            }

            .clic{
                cursor: pointer;
            }

            .quantity button{
                border-radius: 50%;
                display: inline-block;
                width: 30px;
            }
            .quantity div{
                text-align: center;
                min-width: 30px;
                display: inline-block;
                font-weight: bold;
            }
            .buy-box{
                margin: 20px;
            }
            footer {
                
                text-align: center;
                padding: 30px 10px;
                margin-top: 50px;
                min-height: 100px;
            }
            .container{
                margin-top: 50px;
            }
            .producto-relacionado-precio{
                background: orangered;
                color: white;
                text-align: center;
                padding: 10px; 
            }

</style>
