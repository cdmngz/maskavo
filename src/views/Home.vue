<template>
<div>
  <v-navigation-drawer
    expand-on-hover
    permanent
    clipped
    absolute
  >
    <v-list>
      <v-list-item
        v-for="item in items"
        :key="item.nombre"
        link
      >
        <v-list-item-icon>
          <v-icon color="green lighten-1">{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.nombre }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>

  <v-row class="ml-14">
    <v-card
      class="mx-xs-0 my-xs-8 ma-sm-5"
      :key="index"
      max-width="474"
      v-for="(item, index) in productos"
      >
      <v-row>
        <v-col cols="6" class="pr-0 pt-3 ml-3">
          <v-img class="mx-0 pr-0" height="313" :src="require(`@/assets/${item.img}`)"></v-img>
        </v-col>
        <v-col class="pl-0">
          <v-card-title class="py-0">{{item.nombre}}</v-card-title>
          <v-card-text class="py-0">{{item.principales}}</v-card-text>
          <v-card-subtitle class="pt-0">{{item.tipo}}</v-card-subtitle>
          <v-card-text class="d-flex align-center py-0">Piel mixta<v-rating length="3" :value="3" color="green darken-1" readonly size="14" full-icon="mdi-flower-poppy"></v-rating></v-card-text>
          <v-card-text class="d-flex align-center py-0">Piel grasa<v-rating length="3" :value="3" color="green darken-1" readonly size="14" full-icon="mdi-flower-poppy"></v-rating></v-card-text>
          <v-card-text class="py-1 my-1 green darken-1 white--text">{{item.desctipo}}</v-card-text>
          <v-card-text class="py-0"><b>Cantidad: </b>{{item.cantidad}} gr</v-card-text>
          <v-card-text class="py-0"><b>Precio: </b>{{item.precio}} $</v-card-text>
        </v-col>
      </v-row>
      <v-row class="px-2 py-0 my-0 d-flex justify-center">
        <v-chip color="green darken-1 white--text" class="ma-2" v-for="ing in item.composicion" :key="ing">{{ing}}</v-chip>
      </v-row>
    </v-card> 
  </v-row>

</div>
</template>

<script>
  export default {
    data () {
      return {
        productos: [
          {
            img: 'JadeRefrescante.jpeg',
            nombre: 'Jade Refrescante',
            tipo: 'Jabón Facial',
            principales: 'Menta y eucalipto',
            piel: 'Para piel mixta y grasa:',
            descrip: 'Propiedades bactericidas y antisépticas, reduce la grasa. Es refrescante y efectivo en el tratamiento para la piel.',
            cantidad: 20,
            composicion: ['Aceite esencial de menta', 'Eucalipto', 'Hojas de Menta'],
            precio: 200,
          },
          {
            img: 'BifazRutilado.jpeg',
            nombre: 'Bifaz Rutilado',
            tipo: 'Jabón Corporal',
            principales: 'Menta y eucalipto',
            piel: 'Para piel mixta y grasa:',
            desctipo: 'Propiedades bactericidas y antisépticas, reduce la grasa. Es refrescante y efectivo en el tratamiento para la piel.',
            cantidad: 120,
            composicion: ['Arcilla Caolín Roja', 'Carbón Activo'],
            precio: 200,
          },
          {
            img: 'CariciaJaspe.jpeg',
            nombre: 'Caricia Jaspe',
            tipo: 'Champú',
            principales: 'Arcilla y Aceite de Coco',
            piel: 'Para piel mixta y grasa:',
            desctipo: 'Propiedades bactericidas y antisépticas, reduce la grasa. Es refrescante y efectivo en el tratamiento para la piel.',
            cantidad: 50,
            composicion: ['Arcilla Caolín Roja', 'Aceite de Coco'],
            precio: 200,
          },
        ],
        drawer: true,
        items: [
          { nombre: 'Jabones', icon: 'mdi-spa' },
          { nombre: 'Acondicionadores', icon: 'mdi-sprout' },
          { nombre: 'Champú', icon: 'mdi-flower-tulip' },
          { nombre: 'Bombas', icon: 'mdi-flower-poppy' },
        ],
        mini: true,
      }
    },
  }
</script>