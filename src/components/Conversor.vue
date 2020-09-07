<template>
  <div class="conversor">
    <h2 id="de-para">{{moedaA}} Para {{moedaB}}</h2>
    <input type="number" v-model="moedaA_value" :placeholder="moedaA" @keyup="converter">
    <button type="button" class="btn btn-success" @click="converter">
        <span class="fas fa-exchange-alt"></span>
    </button>
    <h2>{{moedaB_value}}</h2>
  </div>
</template>

<script>


export default {
  name: 'Conversor',
  props: ["moedaA", "moedaB"],
        data(){
            return{
                moedaA_value : "",
                moedaB_value : 0
            };
        },
        methods: {            
            converter(){
                if(this.moedaA_value == ""){
                    this.moedaB_value = 0;

                }
                else{
                let de_para = this.moedaA + "_" + this.moedaB;

                let url = "https://free.currconv.com/api/v7/convert?q="+
                    de_para
                +"&compact=y&apiKey=c7052d5be45cda8ce00a"

                fetch(url)
                    .then(res=>{
                        return res.json()
                    })
                    .then(json=>{
                        let cotacao = json[de_para].val;
                        this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                          });
            }
            }

        },
}
</script>

<style scoped>
#de-para {
    color: #28a745;
}
.conversor {
    margin: 0 auto;
    padding: 20px;
    max-width: 350px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    background-color: #fff;
}

.btn {
    margin-left: 10px;
}

</style>>
