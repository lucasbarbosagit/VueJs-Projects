<template>   
    <div class="row">
        <div class="quadrados">
        <div class="quadrado" :style="{backgroundColor: cor1}"> </div>
        </div>
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <input type="text" class="form-control" rows="1" placeholder="Digite uma cor em Hexadecimal" v-model="cor1">
               <button class="btn btn-primary botaoadd" @click.prevent="createNew">Add Cor</button>
            </div>
        </form>      
   </div>
</template>
 
<script>

    export default {
        data: function() {
            return {
                cor1: ''
            };
        },
        methods: {
            createNew() {
                this.$emit('quoteAdded', this.cor1);
                this.cor1 = '';
            }
        }
    }
</script>

<style>

.quadrado {

    border-radius: 15px;
    height: 100px;
    width: 100px;
    background-color: gray;
    display: inline-block;
    margin-right: 5px;
    margin-bottom: 20px;
    
}

.quadrados {
    
    display: block;
    width: 100px;
    margin: auto;

}

.form-control {
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 20px;
}

.botaoadd {
    margin-bottom: 20px;        
}


</style>