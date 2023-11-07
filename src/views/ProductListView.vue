<template>
    <h1>Aquí va el llistat de productes</h1>
    <ul>
        <li v-for="producto in productes" :key="producto.name">
            <router-link :to="{name: 'product',params:{id:producto.id}}" :name="producto.name" 
            :memoria="producto.memory.quantity" :memoriaTipus="producto.memory.type"
            :conectors="producto.conectors" :power="producto.power" 
            :height="producto.size.height" :depth="producto.size.depth">Ver detalles del producto {{ producto.name }}</router-link>
        </li>
    </ul>
</template>

<script lang="ts" setup>
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
</script>