<template>
    <section>
        <h1>{{ title}}</h1>
        <pre>{{ html_data }}</pre>
    </section>
</template>

<script>
import axios from 'axios';

let url = "https://cat-fact.herokuapp.com/facts?animal_type=cat&amount=2"

export default {
    data: function() {
        return {
            title: 'Axios',
            message: 'message'
        }
    },
    asyncData: async function() {
        let result = await axios.get(url)
        console.log(result.data[0].text)
        return { html_data: result.data[0].text }
    }
}
</script>

