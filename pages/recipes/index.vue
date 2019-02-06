<template>
    <section class="recipes">
        <article class="recipe">
            <div class="thumbnail"></div>
            <h1>Title</h1>
            <p>Some nice recipes</p>
        </article>
         <article class="recipe">
            <div class="thumbnail"></div>
            <h1>Title</h1>
            <p>Some nice recipes</p>
        </article>
    </section>
</template>

<style scoped>
.recipes{
    display:flex;
    flex-flow:row wrap;

}

.recipe{
    box-sizing:border-box;
    width: 280px;
    padding:8px;
    border: 1px solid #ccc;
    box-shadow: 0 2px 2px #aaa;
}
</style>
