<template>
  <v-table>
    <thead>
      <tr>
        <th class="text-center">Name</th>
        <th class="text-center">Calories</th>
      </tr>
    </thead>
    <tbody>
        <tr v-for="section in sections" :key="section.id" class="gb-white text-center">
            <td> {{ section.name }} </td>
            <td> Calories </td>
        </tr>
    </tbody>
  </v-table>
</template>

<script>
import axios from 'axios';
export default {
  name: "AboutTable",
    data() {
        return {
            toggleModal: false,
            sections: [],
        };
    },
    methods: {
        async loadData() {
            // let user = localStorage.getItem("user");
            // if (!user) {
            //     this.$router.push({name: 'LoginPage'});
            // }

            axios.get('http://127.0.0.1:8000/api/sections')
                .then(response => {
                    this.sections = response.data.data;
                console.log(response.data);
                })
                .catch(error => {
                    console.log(error);
                });
        }
    },
    mounted() {
        this.loadData();
    },
};
</script>
