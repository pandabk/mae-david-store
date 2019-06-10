<template>
    <div>
        <h1>Cliente</h1>
        <table>
            <tr v-for="client in clients" :key="client.id">
                <td>{{client.id}}</td>
                <td>{{client.name}}</td>
            </tr>
        </table>
    </div>
</template>
<script>
import axios from 'axios'
export default{
    data(){
        return {
            clients:[]
        }
    },
    mounted: function(){
        axios.get('http://localhost/api/home').then(response => {
            this.clients = (response.data);
            console.log(response.data);
        })
    }
}
</script>
