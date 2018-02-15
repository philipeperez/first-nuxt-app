<template>
  <section class="recipes">
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :previewText="recipe.previewText"
      :id="recipe.id"/>
  </section>
</template>

<script>
  import Recipe from '@/components/Recipe'

  export default {
    components: {
      Recipe
    },

    asyncData() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve({
            recipes: [
              {
                id: '1',
                title: 'Delicious Food',
                previewText: 'Awesome Food',
                thumbnail: 'https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Good_Food_Display_-_NCI_Visuals_Online.jpg/1200px-Good_Food_Display_-_NCI_Visuals_Online.jpg'
              },
              {
                id: '2',
                title: 'Delicious Food',
                previewText: 'Awesome Food',
                thumbnail: 'http://blog.gyanlab.com/wp-content/uploads/2015/12/Credits-Miss-India-Menu-Website.jpg'
              }
            ]
          })
        }, 1500)
      })
    }
  }
</script>

<style scoped>
  .recipes {
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
  }
</style>
