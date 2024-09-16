<template>
    <section>
        <h1>{{ title}}</h1>
        <div>
            <input type="text" v-model="msg">
            <button @click="doClick">Click</button>
        </div>
        <table>
            <tbody>
                <tr>
                    <th>ID</th>
                    <td>{{ json_data.id}} </td>
                </tr>
                <tr>
                    <th>Title</th>
                    <td>{{ json_data.title}} </td>
                </tr>
            </tbody>
        </table>
    </section>
</template>

<script>
import axios from 'axios';

let url = "https://jsonplaceholder.typicode.com/posts/"

export default {
    data: function() {
        return {
            title: 'Axios',
            message: 'message',
            msg: '',
            json_data: {}
        }
    },
    // コンポーネント生成時に実行
    // asyncData: async function() {
    //     let id = 1
    //     let result = await axios.get(url + id)
    //     console.log(result.data)
    //     console.log(result.data.id)
    //     return { json_data: result.data }
    // }
    methods: {
        doClick: function(event) {
            axios.get(url + this.msg).then((res) => {
                this.message = 'get ID= ' + this.msg
                this.json_data = res.data
            })
        }
    }
}
</script>

