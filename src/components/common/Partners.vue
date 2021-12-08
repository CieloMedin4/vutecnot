<template>
    <v-container fluid >
        <v-row align="center" justify="center" class="mb-0">
            <v-col cols="12" md="12" lg="12" sm="12" class="mb-0">
                <p class="google-font mb-1" style="font-weight: 350;font-size:200%"><b>
                    <span style="color: #1a73e8;">Tecnología</span> </b> 
                </p>
                <p class="google-font mt-1 mb-0" style="font-size:100%">Electrodomésticos</p>
                <p class="google-font mt-0 mb-0" style="font-size:100%">Actualmente podemos encontrar que algunos de los electrodomésticos cuentan con  <a style="color:#1565C0;text-decoration: none;" :href="`mailto:${config.generalConfig.email}`">{{config.generalConfig.email}}</a> inteligencia de este tipo (con asistentes)</p>
            </v-col>
        </v-row>

        

       
     
    </v-container>
</template>

<script>
import service from '@/services/appservices'
import { mapState } from "vuex";
export default {
    data:()=>({
        partnersData:[]
    }),
    computed:{
        ...mapState(["config"])
    },
    mounted(){
        this.getPartner()
    },
    methods:{
        getPartner(){
            service.getAllPartners().then(res=>{
                if(res.success){
                    this.partnersData = res.data.filter(data=>data.visible)
                }
            })
        },
    }
}
</script>

<style scoped>
.client-logo{
    height: 90px;
    padding: 12px 12px;
    border-radius: 7px;
    background: white;
    border: 1px solid #ebebeb;
    text-align: center;
}
</style>