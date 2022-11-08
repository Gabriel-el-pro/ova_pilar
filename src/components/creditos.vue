<template>
    <div>
        <v-container>
            
<div class="v-dialog v-dialog--active" style="max-width: 400px;">
<div class="v-card v-sheet theme--light">
<div class="v-card__title  primary red accent-2 v-card__title--primary">
<h2 class="text-uppercase headline">Integrantes del Proyecto</h2>
</div>
<div class="v-card__text ">
<div role="list" class="v-list transparent theme--light">
<div role="listitem">
<div class="v-list__tile v-list__tile--avatar theme--light">
<div class="v-list__tile__content">
<div class="v-list__tile__title font-weight-bold"><h2> Pilar Ortega Montes</h2></div>
</div>
<div class="v-list__tile__avatar">
    <div class="v-avatar" style="height: 40px; width: 40px;">
 
 </div>
 <v-dialog
            v-model="persona"
            :overlay="false"
            max-width="500px"
            transition="dialog-transition"
          >
            <v-card :img="info.avatar" width="500" height="500">
              
            </v-card>
          </v-dialog>
    </div>
     </div>
           </div>


     <hr class="v-divider theme--light">
     <div role="listitem" class="primary red accent-2 mt-4">
     <div class="v-list__tile theme--light">
<div class="v-list__tile__content">
 <div class="v-list__tile__title"><h2> Docente: Dalia Madera Doval</h2></div>
 </div><div class="v-list__tile__avatar">
 <div class="v-avatar" style="height: 40px; width: 40px;">

       </div>
       <v-dialog
            v-model="persona"
            :overlay="false"
            max-width="500px"
            transition="dialog-transition"
          >
            <v-card :img="info.avatar" width="500" height="500">
              
            </v-card>
          </v-dialog>
       </div>
       </div>
       </div>
 <div class="v-list__tile__content"> 
<img src="../../public/unicor.png" class="ml-4 mt-4" width="200px" height="80px">

                </div>
                </div>
                </div>
                </div>
                </div>
        </v-container>
    </div>
</template>
<script>
export default {
    name:"App",
    data: () =>{
       return {
      info: {},
      dialog: false,
      persona: false
    }
    },
   
}
</script>

 




