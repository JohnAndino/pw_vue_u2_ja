<template>
  <div class="contenedor_pregunta">
    <img src="https://yesno.wtf/assets/yes/5-64c2804cc48057b94fd0b3eaf323d92c.gif" alt="No puede visualizarse">
    
    <div class="pregunta_container">
    <h1>Pregunta</h1>
    <input type="text" placeholder="Hazme una pregunta">
    <p>Recuerda acabar con el signo de interrogación(?)</p>
    <h2>Sere millonario?</h2>
    <h1>Yes, No</h1>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style >
    img {
        height: 100vh;
        width: 100vw;
        max-height: 100%;
        max-width: 100%;
        position: fixed; /*Hace que la imagen se ocupa como fondo de pantalla*/ 
        left: 0px; /*Con esto hago que la imagen empiece*/ 
        top: 0px;
    }
    .pregunta_container {
        position: relative;
        min-height: 100vh; /* altura de toda la pantalla */
        /*color:white;*/
        display: flex;
        justify-content: center; /* centrado vertical */
        align-items: center; /* centrado horizontal */
        text-align: center;
        flex-direction: column;  /* elementos uno debajo del otro */
    }
    input {
        width: 250px;
        padding: 10px 15px;
        border-radius: 5px;
        border: none;
    }

    input:focus {
        outline: none;
    }

    h1,
    h2,
    p {
        color: white;
    }

    p{
        font-size: 20px;
    }

    h2 {
        margin-top: 150px
    }

</style>
