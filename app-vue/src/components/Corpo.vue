<template>
    <section>
        <div>
            <input type="number" id="num1">
        </div>
        <div>
            <input type="number" id="num2">
        </div>
        <div>
            <input type="number" id="num3">
        </div>
        <div>
            <button @click="verificar" id="bnt">Enviar</button>
        </div>
        <div id="res">

        </div>
        <div>
            <img :src="imagem" alt="">
        </div>
    </section>
</template>

<script>

export default {
    name:'Corpo',
    data(){
        return{
            imagem:''
        }
    },
    methods:{
        verificar(){
            let num1=document.getElementById("num1").value;
            let num2=document.getElementById("num2").value;
            let num3=document.getElementById("num3").value;
            let res=document.getElementById("res");
            
            if((num1==num2&&num1!=num3)||(num2==num3&&num2!=num1)||(num1==num3&&num1!=num2)){
                res.innerHTML=`Com as medidas ${num1}, ${num2} e ${num3}, podemos montar um triângulo Isósceles`;
                this.imagem='/img/isosceles.png';

            }else if((num1!=num2&&num1!=num3)||(num2!=num1&&num2!=num3)||(num3!=num1&&num3!=num2)){
                res.innerHTML=`Com as medidas ${num1}, ${num2} e ${num3}, podemos montar um triângulo Escaleno`;
                this.imagem='/img/escaleno.png';

            }else if(num1==num2&&num1==num3){
                res.innerHTML=`Com as medidas ${num1}, ${num2} e ${num3}, podemos montar um triângulo Equilátero`;
                this.imagem='/img/equilatero.png'
            }
        }
    }
}
</script>

<style scoped>
section{
    text-align: center;
    border: 1px solid;
    width: 400px;
    margin-left: auto;
    margin-right: auto;
    margin-top: 10px;
}

div{
    margin: 10px;
}

img{
    width: 350px;
}
</style>