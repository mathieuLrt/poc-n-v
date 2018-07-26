<template>
<div>
    <p>Je suis une fiche de type : {{category}}</p>
    <p>Mon slug est :  {{slug}}</p>
    <p>Cette donnée est retourné par un appel ajax : {{title}}</p>
</div>
</template>
<script>
import axios from 'axios';

export default {
  async asyncData({ params }) {
    let category = params.category;
    let slug = params.page;

    let { data } = await axios.get(`https://jsonplaceholder.typicode.com/posts?id=2`);
    return { 
        title: data[0].title,
        category: category,
        slug: slug
    };
    
  }
};
</script>
