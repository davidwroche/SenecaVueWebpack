<template>
    <div id="first">
        <h1>Red</h1>
        <input v-model="msg">
        <button v-on:click="act">Act</button>
        <button v-on:click="show">Show</button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                msg: 'a:1,x:3',
            }
        },
        methods: {

            act: function() {
              var seneca = this.$root.$options.seneca
                seneca.act(this.msg, function(err, out) {
                    this.act({
                        cm: 'blue',
                        res: out
                    })
                })
            },

            show: function() {
              var seneca = this.$root.$options.seneca
                seneca.act({
                    ann: 'show',
                    show: this.msg
                })
            },
        }


    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h1,
    h2 {
        font-weight: normal;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
    #first{
        background-color: #FF3333;
    }
</style>
