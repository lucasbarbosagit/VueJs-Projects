<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote" :style="{backgroundColor: corfinal}">
                <slot></slot>
            </div>
            <div class="colornome">{{ corfinal }}</div>
        </div>
    </div>
</template>
 
<script>

 export default {
        props: ['corfinal'],
        components: {
        },
        methods: {
        }
    }

</script>

<style>
     
    .panel-default {
        border-radius: 25px;
        height: 200px;
        width: 200px;
        margin-bottom: 50px;
        margin-right: auto;
        margin-left: auto;
    } 

    .panel-body {
        border-radius: 25px;    
        height: 200px;
        width: 200px;  
        margin-bottom: 10px;
    }

    .quote {
        cursor: pointer;
    }

    .colornome {
        text-align: center;
    }

</style>