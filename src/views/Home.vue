<template>
  <div class="home">
    <h1 class="text-center mb-5">Home</h1>
    <article v-for="article in articles">
      <h3><router-link :to="`/article/${article.slug}`">{{article.title}}</router-link></h3>
      <div>{{article.des}} <router-link :to="`/article/${article.slug}`">+ more</router-link></div>
      <hr>
    </article>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      articles: [
        {
          title: "title 1",
          slug: "title-1",
          des: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                a consectetur culpa quaerat ad voluptates.`,
          content: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates.`
        },
        {
          title: "title 2",
          slug: "title-2",
          des: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                a consectetur culpa quaerat ad voluptates.`,
          content: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates.`
        },
        {
          title: "title 3",
          slug: "title-3",
          des: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                a consectetur culpa quaerat ad voluptates.`,
          content: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates.`
        },
        {
          title: "title 4",
          slug: "title-4",
          des: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                a consectetur culpa quaerat ad voluptates.`,
          content: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates.`
        },
        {
          title: "title 5",
          slug: "title-5",
          des: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                a consectetur culpa quaerat ad voluptates.`,
          content: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non molestias, possimus incidunt 
                     reiciendis quam accusamus sequi sint molestiae ab dicta repudiandae, delectus magni quasi 
                     a consectetur culpa quaerat ad voluptates.`
        }
      ]
    }
  }
}
</script>
