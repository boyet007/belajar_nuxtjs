<template>
    <section class="recipes">
        <Recipe v-for="recipe in recipes" 
                :key="recipe.id" :thumbnail="recipe.thumbnail"
                :title="recipe.title" :id="recipe.id" :previewText="recipe.previewText" />
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
                                id: "1",
                                title: "Awesome Pizza",
                                previewText: "Awesome Pizza",
                                thumbnail: "https://res.cloudinary.com/hellofresh/image/upload/f_auto,fl_lossy,h_400,q_auto/v1/hellofresh_s3/5b48915430006c3a9667cc42/step-d9b1de68.jpg"
                            },
                            {
                                id: "2",
                                title: "Awesome Hamburger",
                                previewText: "Awesome Kebab",
                                thumbnail: "https://res.cloudinary.com/hellofresh/image/upload/f_auto,fl_lossy,h_400,q_auto/v1/hellofresh_s3/5b488e90ae08b5581e49f461/step-bc303e41.jpg"
                            },
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
        flex-flow: row wrap;
        justify-content: center;
        align-items: center;
    }
</style>
