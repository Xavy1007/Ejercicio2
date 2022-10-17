<template>
    <div class="container">
 
 <div class="row">
     <h3>{{producto.nombre}}</h3>
 </div>
 <div class="row">
     <div class="col-12 col-sm-6 col-md-4 ">
         <img :src="producto.imagen" alt="" id="imagen_p">
     </div>
     <div class="col-12 col-sm-6  col-md-8">
         <h6>{{producto.descripcion}}</h6>
         <div class="p-3 mb-2 text-white" style="background-color: orangered;">
             Precio: {{producto.precio}} BOB
         </div>
         <h5>Color</h5>
            {{colorseleccionado}} 
         <div>
            <div v-for="color of producto.colores"
            @click="seleccionarColor(color)"
            class="color-box clic"
            :style="`background: ${color}`"
             ></div>
             
         </div>
         <h5>Cantidad</h5>
         <div class="quantity">
             <button @click="reducir()">-</button> <div>{{contar}}</div> <button @click="agregar()">+</button>
         </div>
         <div class="buy-box">
             <button type="button" class="btn btn-primary" @click="comprar(producto.id, producto.nombre)">Comprar</button>
         </div>
         
     </div>
 </div>
 </div>
 
<!--Prodcutos Seleccionados-->
<div class="container ">

<div class="row">
    <h4>Productos relacionados</h4>
</div>
<div class="row">
    
    <div class="col" v-for="p in productos" >
       
        <div class="card" style="width: 18rem;"  @click="detalle(p.id, p.nombre, p.descripcion)" >
            <div class="card-body">
                <h5 class="card-title">{{p.nombre}}</h5>
                <img :src="p.imagen" alt=""  id="imagen_p">
                <p class="card-text">{{p.descripcion}}</p>
                <div class="producto-relacionado-precio" >Precio:{{p.precio}} BOB</div>
                
        <div>
            <div>
            <div v-for="col in p.colores" class="color-box" :style="`background:${col}`" ></div>
        </div>
                </div>
            </div>
        </div>
    
    </div>
    
   
</div>
</div>







 </template>
 <script>
     export default{
         name:'ProductoView',
         data(){
             return{
                producto:{
                    id:null,
                    nombre:null,
                    descripcion:null,
                    imagen:null
                },
                productos:[],
                lista:[],
                contar:0,
                colorseleccionado:null,
                color:""
               
             }
         },
         methods:{
            getProductos(){
                axios({
                    method: "get",
                    url:"http://localhost:4444/Productos" ,
                    })
                .then(response => {
                    this.producto=response.data[0]
                    
                    console.log(response.data);
                    console.log(this.prod)
                    this.productos=response.data;
                })
                .catch(e => console.log(e));
            },
            agregar(){
               this.contar++;     
            },
            reducir(){
                if(this.contar>0){
                    this.contar--
                }
            },
            seleccionarColor(color){
                let a="";
                switch(color){
                    case "blue":
                        a="azul";
                        break;
                    case "black":
                        a="negro";
                        break;
                    case "yellow":
                        a="amarrillo";
                        break;
                    case "red":    
                        a="rojo";
                        break;
                    default:
                        a="";
                        break;
                }
                this.colorseleccionado=a;
                this.color=this.colorseleccionado
            },
            comprar(id, nombre){
                alert("Id:"+id+", Nombre: "+nombre+" Cantidad : "+this.contar+" , Color: "+this.color)
            },
            detalle(id, nombre, descripcion){
                alert("Id: "+id+",\nNombre : "+nombre+",\nDescripcion : "+descripcion)
            }
            
         },
         computed:{
         },
         mounted(){
            this.getProductos()
         },
         components:{
         }
         }
 </script>
 <style scoped>
#imagen_p{
    width:100% ;
    
}
</style>