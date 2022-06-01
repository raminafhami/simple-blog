<template>
    <div class="add">
        <form @submit.prevent="doAdd">
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
            <button class="btn btn-primary">Add article</button>
        </form>
    </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
        title: "",
        des: "",
        content: "",
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
  },
  methods: {
      doAdd() {
          this.articles.push({
              title: this.title,
              content: this.content,
              description: this.des,
              slug: this.title.replaceAll(" ", "-").toLowerCase()
          });

          console.log(this.slug);
          this.$router.push(`/article/${this.articles[this.articles.length - 1].slug}`)
      }
  }
}
</script>
