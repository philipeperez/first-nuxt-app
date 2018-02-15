<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{ recipe.previewText }}</p>
  </section>
</template>

<script>
  export default {
    asyncData(context) {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve({
            recipe: [
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
            ].find(el => el.id === context.params.id)
          })
        }, 1500)
      })
    }
  }
</script>

<style scoped>
  .single-recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
  }

  .recipe-image {
    width: 100%;
  }
</style>
