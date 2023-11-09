<template>
    <div>
    <h1>Datos del producto {{ articleId }}</h1>
    <div v-if="product">
        <img :src="getImageUrl(product.id)" alt="Imagen del producto">
      <h3>Nombre del producto: {{ product.name }}</h3>
      <div>
        <strong>Memoria:</strong> {{ product.memory.quantity }} {{ product.memory.type }}
      </div>
      <div>
        <strong>Conectores:</strong> {{ product.conectors }}
      </div>
      <div>
        <strong>Potencia:</strong> {{ product.power }}
      </div>
      <div>
        <strong>Tamaño:</strong> Altura: {{ product.size.height }}, Profundidad: {{ product.size.depth }}
      </div>
    </div>
    <div v-else>
      <p>Producto no encontrado</p>
    </div>
  </div>
</template>
<script lang="ts" setup>
    import { onMounted, ref, computed } from 'vue'; 
    import {useRoute} from 'vue-router'

    const productes = [
    {
            id: 1,
            name: 'MSI AMD Radeon RX 6650 XT GAMING X',
            memory: {
                quantity: '8gb',
                type: 'GDDR6'
            },
            conectors: 'DisplayPort x 3 (v1.4)',
            power: '175 W',
            size:{
                height: '130mm',
                depth: '278mm',
            }
        },
        {
            id: 2,
            name: 'ASUS Dual GeForce RTX 4060 Ti OC Edition',
            memory: {
                quantity: '16gb',
                type: 'GDDR6'
            },
            conectors: 'DisplayPort x 3 (v1.4a), HDMI x 1 2.1a',
            power: '200 W',
            size:{
                height: '123.2mm',
                depth: '227,2mm',
            }
        },
        {
            id: 3,
            name: 'MSI GeForce RTX 4070 VENTUS 3X E OC',
            memory: {
                quantity: '12gb',
                type: 'GDDR6'
            },
            conectors: 'DisplayPort x 3 (v1.4), hdmi X 1 2.1a',
            power: '200 W',
            size:{
                height: '120mm',
                depth: '308mm',
            }
        },
        {
            id: 4,
            name: 'Sapphire NITRO+ AMD Radeon RX 7800 XT GAMING',
            memory: {
                quantity: '16gb',
                type: 'GDDR6'
            },
            conectors: 'DisplayPort x 2 (v1.4), HDMI x 2 2.1',
            power: '288 W',
            size:{
                height: '134,8mm',
                depth: '320mm',
            }
        },
        {
            id: 5,
            name: 'Gigabyte GeForce RTX 4090 GAMING OC',
            memory: {
                quantity: '24gb',
                type: 'GDDR6X'
            },
            conectors: 'DisplayPort x 3 (v1.4), HDMI x 1 2.1',
            power: ' 360W',
            size:{
                height: '150,2mm',
                depth: '340mm',
            }
        }
    ]

    let articleId = ref();

    onMounted(()=>{
        const route = useRoute()
        articleId.value = route.params.id
    });

    const product = computed(() => {
        return productes[articleId.value - 1];
    });

    const getImageUrl = (articleId:number) => {
        return `/imagenes/tarjeta${articleId}.jpg`;
    };    
</script>

<style scoped>
    .product-details {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }

  h1 {
    text-align: center;
    color: #333;
  }

  h3 {
    margin-top: 10px;
  }

  div {
    margin-bottom: 10px;
  }

  strong {
    color: #007BFF;
  }

  img {
    width: 500px;
    height: auto;
    border-radius: 8px;
    margin-top: 10px;
  }

  .not-found {
    text-align: center;
    color: #FF0000;
  }
</style>