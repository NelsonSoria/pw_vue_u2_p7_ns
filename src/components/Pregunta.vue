<template>
  <img
    :src="imagen"
    alt="No se puede ver"
  />
  <br />
  <input v-model="pregunta" type="text" placeholder="hazme una pregunta" />
  <p>Recuerda que cuando finalices tu pregunta dar un ?</p>
  <h1>{{ pregunta }}</h1>
  <h2>{{ respuesta }}</h2>
</template>

<script>
export default {
    data(){
        return{
            pregunta:'Hola Mundo',
            respuesta:'',
            imagen:'https://yesno.wtf/assets/yes/14-b57c6dc03aa15a4b18f53eb50d6197ee.gif',
        }
    },
    watch:{
        // mismo nombre que la propiedad reactiva, pero con un metodo
        pregunta(value,oldValue){
            console.log(value)  ;
            console.log(oldValue)  ;
            if(value.includes('?')){
                //programar la llama a la api para obtener
                // el SI o el NO,y la imagen
                console.log('Aqui llamo a la api');
                this.fachada();
            }
        }
    },
    methods:{  
         async llamaApi(){
            //await espera la respuesta de la api, y tengo que poner a mi metodo como async
            // cuano no se le pone el await, la promesa se queda pendiente
           const data = await fetch('https://yesno.wtf/api').then(response=>response.json());
           this.respuesta = data.answer;
           this.imagen = data.image;
           console.log(data);
        },
         async fachada(){
           await this.llamaApi();
        }
    }
};
</script>

<style>
</style>