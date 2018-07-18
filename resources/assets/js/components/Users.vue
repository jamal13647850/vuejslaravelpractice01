<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card card-default">
                    <div class="card-header">Example Component</div>

                    <ul>
                        <li v-for="user in users">{{user}}</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
           return {
               users : []
           }
        },
        mounted() {
            axios.get('/username')
                .then(response => this.users = response.data)
                .catch(error => console.log(error));
        }
    }
</script>
