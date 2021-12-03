<template>
  <v-footer
    height="auto"
    fixedfir
    class="hidden-sm-and-down ma-0"
    :class="this.$vuetify.theme.dark == true?'grey darken-4':'white'"
  >
  <!-- style="border-color:#e0e0e0;border-width: 1px;border-style: solid;border-bottom: 0;border-left:0;border-right:0" -->
    <v-container fluid >
      <v-row align="center" justify="center" class="my-0 py-0">
        <v-col cols="12" md="10" lg="10" sm="11" class="py-0 my-0">
          <v-divider v-if="!this.$vuetify.theme.dark"></v-divider>
          <!-- {{socialLinks}} -->
          <CommunitySocialInfo :config="config"/>
          <v-divider></v-divider>
        </v-col>
      </v-row>

      <v-row align="center" justify="center" class="mt-3">
        <v-col cols="12" md="10" lg="10" sm="11" class="my-0 py-0">
          <v-container fluid class="pa-0 my-0">
            <!-- Links Section -->

            <v-row justify="start" class="">
              <v-col cols="12" md="3" lg="3" sm="3" class="py-2" >
                  <p class="google-font mb-0" style="font-size: 140%;font-weight: 300;"><b>Acerca de</b></p>
                  <div >
                        <a href="#" rel="noreferrer" :class="$vuetify.theme.dark?'darkThemeTextLink':'lightThemeTextLink'" class="google-font my-3" target="_blank" style="text-decoration: none;font-size:110%">Los Asistentes de Voz más comunes</a><br>
                  </div>
              </v-col>

              <v-col cols="12" md="3" lg="3" sm="3" class="py-2" >
                  <p class="google-font mb-0" style="font-size: 140%;font-weight: 300;"><b>Componentes</b></p>
                  <div >
                        <a href="#" rel="noreferrer" :class="$vuetify.theme.dark?'darkThemeTextLink':'lightThemeTextLink'" class="google-font my-3" target="_blank" style="text-decoration: none;font-size:110%">El asistente virtual está formado por dos componentes independientes,  la interfaz de usuario (IU) (aspecto), y la base de conocimientos en el interior (inteligencia). La apariencia visual (IU) de los asistentes virtuales pasa por una foto hasta una imagen 3D con emociones.</a><br>
                  </div>
              </v-col>

              <v-col cols="12" md="3" lg="3" sm="3" class="py-2" >
                  <p class="google-font mb-0" style="font-size: 140%;font-weight: 300;"><b>Facilidades</b></p>
                  <div >
                        <a href="#" rel="noreferrer" :class="$vuetify.theme.dark?'darkThemeTextLink':'lightThemeTextLink'" class="google-font my-3" target="_blank" style="text-decoration: none;font-size:110%">Información sin limites, Agenda y Calendario, Temporizador, Reproductor de Música, Conexión con otros dispositivos</a><br>
                  </div>
              </v-col>
            </v-row>

            <!-- Links Section -->
          </v-container>
        </v-col>
      </v-row>

      <v-row align="center" justify="center" class="mb-0">
        <v-col cols="12" md="10" lg="10" sm="11" class="px-0 mx-0"> 
          <v-divider></v-divider>
          <v-toolbar text class="pa-0 px-0 mt-3 mx-0 elevation-0" style="padding:0 !important" :class="this.$vuetify.theme.dark == true?'grey darken-4':'white'">
            <v-toolbar-title class="google-font pl-0 ml-0 mr-3" style="font-size:200%">{{config.generalConfig.shortName || config.generalConfig.name || ''}}</v-toolbar-title>
            <v-btn
                v-for="(item,i) in config.footerConfig['Footer End Session Link']" 
                :key="i"
                rel="noreferrer"
                :href="item.link" target="_blank" 
                class="ml-0 google-font hidden-sm-and-down"
                style="text-transform: capitalize;font-size:110%" 
                text
                aria-label="Footer Bottom Button"
              >
                {{ item.linkname }}
            </v-btn>
            <v-spacer></v-spacer>
           <span class="subtitle-2 google-font"> Assistentes de 
          <a
            href="https://github.com/gdg-x/aura/"
            target="_blank"
            rel="noreferrer"
            style="text-decoration:none"
          > Voz</a></span>
          </v-toolbar>
        </v-col>
      </v-row>

    </v-container>
  </v-footer>
</template>

<script>
import { mapState } from 'vuex'
  export default {
    components:{
      CommunitySocialInfo : ()=>import('@/components/common/CommunitySocialInfo'),
    },
    data:()=>({
    }),
    computed:{
      ...mapState(['config'])
    },
  }
</script>

<style scoped>
  .darkThemeTextLink{
    color: #1a73e8
  }
  .lightThemeTextLink{
    color: #070707
  }
</style>