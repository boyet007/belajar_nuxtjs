<template>
    <section class="single-recipe">
        <h1>{{ recipe.title }}</h1>
        <div>
            <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
        </div>
        <p>{{ recipe.descriptionText }}</p>
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
                                id: "1",
                                title: "Awesome Pizza",
                                previewText: "Awesome Pizza",
                                descriptionText: "recipes description",
                                thumbnail: "https://res.cloudinary.com/hellofresh/image/upload/f_auto,fl_lossy,h_400,q_auto/v1/hellofresh_s3/5b48915430006c3a9667cc42/step-d9b1de68.jpg"
                            },
                            {
                                id: "2",
                                title: "Awesome Hamburger",
                                previewText: "Awesome Kebab",
                                descriptionText: "recipes description",
                                thumbnail: "https://res.cloudinary.com/hellofresh/image/upload/f_auto,fl_lossy,h_400,q_auto/v1/hellofresh_s3/5b488e90ae08b5581e49f461/step-bc303e41.jpg"
                            },
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
        flex-flow:column;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 30px;
    }

    .recipe-image {
        width: 100%;
    }
</style>
