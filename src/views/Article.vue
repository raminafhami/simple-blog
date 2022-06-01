<template>
  <div class="article">
    <article v-if="!edit">
      <h3>{{article.title}}</h3>
      <div>{{article.content}}</div>
    </article>
    <div v-if="$store.state.isAuthenticated">
      <button class="btn btn-warning mx-2 my-2" @click="edit = !edit">Edit</button>
      <button class="btn btn-danger mx-2 my-2" @click="doRemove">Delete</button>
      <hr>


      <form @submit.prevent="doEdit" class="p-2" v-if="edit">
        <div class="form-group">
            <label for="title">Title</label>
            <input type="text" class="form-control" id="title" placeholder="title" v-model="title">
        </div>
        <div class="form-group">
            <label for="description">Description</label>
            <textarea class="form-control" id="description" rows="3"  v-model="des"></textarea>
        </div>

        <div class="form-group">
            <label for="content">content</label>
            <textarea class="form-control" id="content" rows="8"  v-model="content"></textarea>
        </div>
        <button class="btn btn-primary my-2">Edit article</button>
      </form>


    </div>
  </div>
</template>

<script>
export default {
  name: 'Article',
  data() {
       let articles =  [
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
    let article = articles.find(x => x.slug === this.$route.params.slug);

    return {
        articles,
        article,
        title: article.title,
        content: article.content,
        des: article.des,
        edit: false
    }
  },
  methods: {
    doEdit() {
      let articleIndex = this.articles.findIndex(x => x.slug === this.$route.params.slug); 
      this.articles[articleIndex] = {
        title: this.title,
        content: this.content,
        description: this.des,
        slug: this.title.replaceAll(" ", "-").toLowerCase()
      }

      this.article = this.articles[articleIndex];
      this.edit = !this.edit;
      console.log(this.articles);
    },
    doRemove() {
      let articleIndex = this.articles.findIndex(x => x.slug === this.$route.params.slug); 
      this.articles.splice(articleIndex, 1);
      console.log(this.articles);
    }
  }
}
</script>
