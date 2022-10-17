<template>
    <div class="container-fluid">
            <a class="navbar-brand" href="#"><b>{{titulo}}</b></a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item" v-for="m in menus">
                        <a class="nav-link" href="#">{{m.etiqueta}}</a>
                    </li>
                </ul>
            </div>
        </div>
</template>
<script>
    export default{
        name:'appMenu',
        data(){
            return{
                titulo:'MegaDron',
                menus:[  {
                                etiqueta: "Inicio",
                                url: "?"
                                },
                            {
                                 etiqueta: "Tienda",
                                url: "?"
                            }
                          ]
            }
        },
        methods:{
        },
        computed:{
        },
        mounted(){
        },
        components:{
        }
        }
</script>
<style scoped>
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
          }</style>