<template>


<v-layout>
    <v-flex class="text-center">
      <div class="text-center">
      <img
        src="/vv.png"
        alt="Vuetify.js"
        class="mb-4 "
        height="120"
      >
      </div>
     <v-container fluid>
       <v-layout align-center justify-center>
         <v-flex xs12 sm8 md4>
           <v-card class="elevation-20">
             <v-toolbar round color="teal darken-3">

               <v-toolbar-title>
                 Insciption

               </v-toolbar-title>
             </v-toolbar>
             <v-card-text>

               <v-form>


                <v-text-field

                   name="Nom et Prénom"
                   label="Nom et Prénom"
                   :rules="[rules.required]"
                 >
                 </v-text-field>

                 <v-text-field
                   name="Email"
                   label="Email"
                   :rules="[rules.required,rules.email]"
                   >
                 </v-text-field>



        <v-col class="d-flex" cols="15" sm="15">
        <v-select
          :items="items"
          label="Groupe"
        ></v-select>
        </v-col>

        <v-col class="d-flex" cols="15" sm="15">
        <v-select
          :items="it"
          label="utilisateur"
        ></v-select>
        </v-col>





                 <v-text-field
                   name="Motde passe"
                   label="Mot de passe"
                   :rules="[rules.required]"
                   type="password"
                   v-model="password"
                   >
                 </v-text-field>

                 <v-text-field
                   name="Motde passe"
                   label="Confirmer mot de passe"
                    type="password"
                   :rules="[rules.required]"
                    v-model="confirm_password"
                   :error="!valid()"

                   >
                 </v-text-field>
               </v-form>
             </v-card-text>
                <v-divider light></v-divider>
             <v-card-actions>
                   <v-btn round color="teal darken-3"> S'inscrire
                     <v-icon>
                        mdi-arrow-right
                      </v-icon></v-btn>
                 </v-card-actions>

           </v-card>

         </v-flex>

       </v-layout>
     </v-container>

    </v-flex>
     </v-layout>


</template>

<script>
export default {

name:"signup",
  data:()=>({
     items: ['1', '2', '3', '4', '5', '6', '7', '8'],
     it: ['Etudiant', 'Enseignant'],
    password:'',
    confirm_password:'',


    rules:{
    required :value => !!value || "required",
    email: value =>{
     const pattern=/^(([^/<>()\\\[\]\.,;:\s@\"]+(\.[^<>()\[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^/<>()\\\[\]\.,;:\s@\"]+\.)+[^/<>()\\[\]\.,;:\s@\"]{2,})$/i;
     return pattern.test(value)|| "Inalid e-mail.";
   }

   }
  }),

  methods:{
      valid(){
        return (this.password===this.confirm_password);
      }
  }

};
</script>

