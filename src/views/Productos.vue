<template>
<div class="mx-auto">
  <v-navigation-drawer class="red lighten-5" app permanent fixed expand-on-hover>
    <v-toolbar flat v-for="(item, name, index) in maskavo" :key="index" :class="item.color">
      <v-list-item class="px-0" @click="$vuetify.goTo('#'+name, {offset: -7})">
        <v-list-item-icon>
          <v-img height="25" width="25" :src="item.icon" alt="https://www.flaticon.com/authors/good-ware"></v-img>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-subtitle>{{ name | capitalize }}</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-toolbar>
  </v-navigation-drawer>

  <div :class="[container.color, 'pa-2']" v-for="(container, name, index) in maskavo" :key="index">
    
    <v-row class="text-center my-n4">
      <v-card-text class="font-italic purple--text text--lighten-4">{{ name | capitalize }}</v-card-text>
    </v-row>

    <v-row>
      <v-card
        class="mx-xs-0 my-xs-8 ma-sm-8"
        :id="name"
        v-for="(item, i) in container.productos" :key="i"
        width="500"
        
      >
        <v-row>
          <v-col cols="6" class="pr-0">
            <v-img class="ml-3 mr-0 pr-0" :src="require(`../assets/${item.img}`)"></v-img>
          </v-col>
          <v-col class="pl-0">
            <v-card-title>{{item.title}}</v-card-title>
            <v-card-subtitle>{{item.subtitle}}</v-card-subtitle>
            <v-card-text class="d-flex align-center py-0">Piel mixta<v-rating :value="5" color="pink lighten-1" readonly size="12" full-icon="mdi-circle"></v-rating></v-card-text>
            <v-card-text class="d-flex align-center py-0">Piel grasa<v-rating :value="5" color="pink lighten-1" readonly size="12" full-icon="mdi-circle"></v-rating></v-card-text>
            <v-card-text>{{item.descsubtitle}}</v-card-text>
            <v-card-text class="pt-1"><b>Cantidad: </b>{{item.cantidad}}gr</v-card-text>
            <v-card-text class="py-1"><b>Precio: </b>$ {{item.precio}}</v-card-text>
          </v-col>
        </v-row>
        <v-row class="px-4 py-2">
          <v-chip color="pink lighten-1" class="ma-2" dark v-for="ing in item.composicion" :key="ing">{{ing}}</v-chip>
        </v-row>
      </v-card>        
    </v-row>

  </div>
</div>
</template>

<script>

export default {
  name: 'Productos',
  data: () => ({
    opcion: 'kjlkj',
    maskavo: {
      jabones: {
        icon: 'https://image.flaticon.com/icons/svg/2911/2911565.svg',
        color: 'red lighten-5',
        productos: [
          {
            img: 'JadeRefrescante.jpeg',
            title: 'Jade Refrescante',
            subtitle: 'Jabón de menta y eucalipto',
            desctitle: 'Para piel mixta y grasa:',
            descsubtitle: 'Propiedades bactericidas y antisépticas, reduce la grasa. Es refrescante y efectivo en el tratamiento para la piel.',
            cantidad: 20,
            composicion: ['Aceite esencial de menta', 'Eucalipto', 'Hojas de Menta'],
            precio: 200,
          },
          {
            img: 'BifazRutilado.jpeg',
            title: 'Bifaz Rutilado',
            subtitle: 'Jabón de menta y eucalipto',
            desctitle: 'Para piel mixta y grasa:',
            descsubtitle: 'Propiedades bactericidas y antisépticas, reduce la grasa. Es refrescante y efectivo en el tratamiento para la piel.',
            cantidad: 20,
            composicion: ['azucar', 'flores', 'muchosColores'],
            precio: 200,
          },
        ]
      },
      shampoo: {
        icon: 'https://image.flaticon.com/icons/svg/2917/2917236.svg',
        color: 'pink lighten-5',
        productos: [
          {
            img: 'CariciaJaspe.jpeg',
            title: 'Caricia Jaspe',
            subtitle: 'Jabón de menta y eucalipto',
            desctitle: 'Para piel mixta y grasa:',
            descsubtitle: 'Propiedades bactericidas y antisépticas, reduce la grasa. Es refrescante y efectivo en el tratamiento para la piel.',
            cantidad: 20,
            composicion: ['azucar', 'flores', 'muchosColores'],
            precio: 200,
          },
          {
            img: 'BifazRutilado.jpeg',
            title: 'Bifaz Rutilado',
            subtitle: 'Jabón de menta y eucalipto',
            desctitle: 'Para piel mixta y grasa:',
            descsubtitle: 'Propiedades bactericidas y antisépticas, reduce la grasa. Es refrescante y efectivo en el tratamiento para la piel.',
            cantidad: 20,
            composicion: ['Mantecas', 'Aceites', 'Arcilla de Caolín rojo','Carbón Vegetal activado', 'vitameina E sin aroma'],
            precio: 200,
          },
        ]
      },
      acondicionador: {
        icon: 'https://image.flaticon.com/icons/svg/2431/2431467.svg',
        color: 'purple lighten-5',
        productos: [
          {
            img: 'CariciaJaspe.jpeg',
            title: 'Caricia Jaspe',
            subtitle: 'Jabón de menta y eucalipto',
            desctitle: 'Para piel mixta y grasa:',
            descsubtitle: 'Propiedades bactericidas y antisépticas, reduce la grasa. Es refrescante y efectivo en el tratamiento para la piel.',
            cantidad: 20,
            composicion: ['azucar', 'flores', 'muchosColores'],
            precio: 200,
          }
        ]
      },
      bombas: {
        icon: 'https://image.flaticon.com/icons/svg/2431/2431473.svg',
        color: 'blue lighten-5',
        productos: [
          {
            img: 'CariciaJaspe.jpeg',
            title: 'Caricia Jaspe',
            subtitle: 'Jabón de menta y eucalipto',
            desctitle: 'Para piel mixta y grasa:',
            descsubtitle: 'Propiedades bactericidas y antisépticas, reduce la grasa. Es refrescante y efectivo en el tratamiento para la piel.',
            cantidad: 20,
            composicion: ['azucar', 'flores', 'muchosColores'],
            precio: 200,
          }
        ]
      }
    }
  }),
  filters: {
    capitalize: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.charAt(0).toUpperCase() + value.slice(1)
    }
  }
}
</script>