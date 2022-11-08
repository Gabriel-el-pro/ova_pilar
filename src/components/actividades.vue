
<template>
    <div>
        <v-container>
            
  <v-card
    class="mx-auto"
    width=" 810px"
    height="450px"
  >
    <v-card-text>
      <h3 class="v-card__title headline red lighten-5" >Actividad 1</h3>
      <h2>¿Qué es Tinkercad?</h2>
      <br>
     <v-list>
       <v-list-item
      v-click-outside="{
        handler: onClickOutsideStandard,
        include: include,
      }"
      @click="models.base = true"
    >
      <v-list-item-title>Es un editor de codigos</v-list-item-title>

      <v-list-item-action>
        <v-icon :color="models.base ? 'red' : 'gray'">
          mdi-record
        </v-icon>
      </v-list-item-action>
    </v-list-item>
     <v-list-item
      v-click-outside="{
        handler: onClickOutsideStandard,
        include: include,
      }"
      @click="models.base = true"
    >
      <v-list-item-title>Es un software gratuito de
        diseño y modelado 3D</v-list-item-title>

      <v-list-item-action>
        <v-icon :color="models.base ? 'green' : 'gray'">
          mdi-record
        </v-icon>
      </v-list-item-action>
    </v-list-item>
     <v-list-item
      v-click-outside="{
        handler: onClickOutsideStandard,
        include: include,
      }"
      @click="models.base = true"
    >
      <v-list-item-title>Es una plataforma de diseño grafico</v-list-item-title>

      <v-list-item-action>
        <v-icon :color="models.base ? 'red' : 'gray'">
          mdi-record
        </v-icon>
      </v-list-item-action>
    </v-list-item>
     </v-list>
    </v-card-text>
    <br>
    <v-card-actions>
      <v-btn
           rounded
            large
        color="red accent-1"
        @click="reveal = true"
       
      >
        Siguiente
      </v-btn>
    </v-card-actions>

    <v-expand-transition>
      <v-card
        v-if="reveal"
        class="transition-fast-in-fast-out v-card--reveal"
        height="100%"
       
      >
        <v-card-text class="pb-0" >
          <h3 class="v-card__title headline red lighten-5">Actividad 2</h3>
          <h2>Arrastre el cuadrado hasta el plano de trbajo de Tinkercad</h2>
          <div style="height: 30px;"></div>
        <div class="ima">

             <div id="2" class="font" :style="{ backgroundImage:'url('+require('../assets/boca.png')+')','background-size': '100% 100%', height:'60px',width:'60px',backgroundRepeat:'no-repeta',backgroundSize:'cover'}"  draggable="true" @dragstart="drag" @dragend="end"></div>
                   </div>
         <div class="pelao">
           <div id="box-droppable" class="box-iner" @drop="drop" @dragover="allowDrop"> </div>
           
         </div>
         


    
 <v-tooltip bottom color="red"
          v-model="sh"
          top
          
        >
          <template v-slot:activator="{ on, attrs }">
            <label
            
              icon
              v-bind="attrs"
              v-on="on"
              
              >
            
            </label>
          </template>
          <span style="font-size:30px;color:blue;">Incorrecto</span>
        </v-tooltip>


    
        <v-tooltip bottom color="green"
          v-model="show"
          top
          
        >
          <template v-slot:activator="{ on, attrs }">
            <label
            
              icon
              v-bind="attrs"
              v-on="on"
              
              >
            
            </label>
          </template>
          <span style="font-size:30px;color:blue;">Correcto</span>
        </v-tooltip>
     

        </v-card-text>
        
      </v-card>
    </v-expand-transition>
  </v-card>

        </v-container>
    </div>



</template>
<script>
  export default {
    data: () => ({
      r:[],
      sh:false,
      show: false,
      reveal: false,
      models: {
        base: false,
        
      },
       
     
  
    }),
    methods: {
      impro(){
  this.r=[];
      this.sh=false;
      this.show= false;
      this.reveal= false;
      this.models= {
        base: false,
        
      };
      },
      cambio(){
this.show=false;
this.sh=false;
      },
        onDragging(ev){
      ev.dataTransfer.setData("text", ev.target.id);
      
    },
    allowDrop(ev) {
      ev.preventDefault();
     
    },
        end(ev){
	ev.target.style.opacity = ''; 	
	ev.dataTransfer.clearData("Data");			
},
    drag(ev) {
      ev.dataTransfer.setData("text", ev.target.id);
    },
    drop(ev) {
     ev.preventDefault();
  var data = ev.dataTransfer.getData("text");
  if(data==2||data==8||data==5||data==10){
this.show=true;
  }else{
this.sh=true;
  }
   setTimeout(this.cambio,2000);
   this.r.push(data);
  ev.target.appendChild(document.getElementById(data)); 
  if(this.r.length==4){
 setTimeout(this.impro,4000);
  }
    },
    },

       }
    
    
   
    
  
  
</script>
<style scoped>
.box-iner {
      margin: 5px;
         
         border-radius: 3px;
      display: flex;
    width:90px;
    height: 90px;
    padding: 1px;
    margin-top: 150px;
    margin-left:-45px;
    
  }
  .box-iner2 {
      margin: 5px;
         
         border-radius: 3px;
      display: flex;
    width:45px;
    height: 40px;
    padding: 1px;
    margin-top: -44px;
    margin-left:144px;
  }
  .box-iner3 {
      margin: 5px;
         
         border-radius: 3px;
      display: flex;
    width:45px;
    height: 40px;
    padding: 1px;
    margin-top: -176px;
    margin-left:175px;
  }
  .box-iner4 {
      margin: 5px;
        
         border-radius: 3px;
      display: flex;
    width:45px;
    height: 40px;
    padding: 1px;
    margin-top: -45px;
    margin-left:-229px;
  }
.ima{
  float:left;
max-width: 200px;
max-height:500px;
margin-left: 80px;
}
.font{
  text-align:center;

  
}
.ima2{
 float:right;
max-width: 200px;
height:200px;
border:2px solid red;
}
.pelao{
 
  margin-left: auto;
  
   width: 310px;
            height: 310px;
            background-image: url("../assets/pelao.jpg");
            background-size: 100% 100%;
            border-radius: 5px;
            border: 2px solid deeppink;
}
.v-card--reveal {
  bottom: 0;
  opacity: 1 !important;
  position: absolute;
  width: 100%;
  
}
hr{
  height: 4px;
  background-color: black;
}
.v-btn{

          position:absolute;
         left:25%;
         top:67%;
         width:50%;
         


  
}

</style>

      

     