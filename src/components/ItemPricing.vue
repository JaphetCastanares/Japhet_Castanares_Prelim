<script>
    export default {
        data (){
            return {
                weapons : [
                    {name: 'Throat Deeper', requirements:"Zirconium Metal", price:10000},
                    {name: 'Yudge Caulk',requirements: "Dirty Pipes", price:5000},
                    {name: 'Ice wallow come',requirements:"Holy Water", price: 69000},
                    {name: 'Zirconium Metal', price: 2000},
                    {name: 'Dirty Pipes', price:12},
                    {name: 'Holy Water',price:30000}
                ]
            };
        },
        computed: {
            totalPrice() {
                return this.weapons.reduce((sum, item) => sum + item.price, 0);
            }
        }
    };
</script>

<template>
    <div>
        <h2>Available Items: </h2>
        <ul>
            <li v-for="(weapons, index) in weapons" :key="index">
                Name: {{ weapons.name }} - Requirements to obtain: {{ weapons.requirements }} - Price: P{{ weapons.price }}
            </li>
        </ul>
        <h2>Total Price of all the Items: {{ totalPrice }}</h2>
    </div>
</template>

<style scoped>
    
</style>
