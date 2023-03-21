<template>
    <div class="main">
        <Header :Title="title"/>
            <div class="center" style="margin-bottom: 2000px">
            <p><b><br><br>HortaTech</b><br><br> O objetivo deste portal é ser o meio remoto de monitoramento de sua horta.<br>
                nele será possível administrar as temperaturas e umidades do solo,<br> assim como ter um feedback
                diário de como sua horta está se comportando,<br> onde gráficos irão ser gerados para auxiliar na 
                manutenção.<br><br><br><br>

                Materiais utilizados:<br>
            Arduino UNO (ATMEGA328P);<br>
            ● Placa protoboard;<br>
            ● Válvula solenoide;<br>
            ● Tubulação hidráulica;<br>
            ● Reservatório de água;<br>
            ● Vaso com cebolinha;<br>
            ● Sensor de temperatura do solo (Salipt S-901);<br>
            ● Sensor de temperatura e umidade do ambiente (AM2302);<br>
            ● Sensor de umidade do solo (LM393)<br>
            </p>
            
            </div> 
    </div>

    <div class="center" style="margin-top: 10rem">
        
                <img src="../../public/imgs/Planta.jpeg" width="500" height="500" >
                <img src="../../public/imgs/Sistema.jpeg" width="500" height="500">
               
            </div>

</template>

<script>
import Header from "../components/Header.vue"

export default {
    data(){
        return{
            title:"Apresentação"
        }
    },
    components:{
    Header}
    

}
</script>

<style>
    .center {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
</style>