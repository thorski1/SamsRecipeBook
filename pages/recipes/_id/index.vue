<template>
    <section class="single-recipe">
        <h1> {{ recipe.title }}</h1>
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
                            title: "Pesto Chicken Casserole",
                            previewText: "Quick, Cheap, Delicious",
                            descriptionText: "This is a delicious meal",
                            thumbnail: "https://i.dietdoctor.com/wp-content/uploads/2016/05/DD-115.jpg?auto=compress%2Cformat&w=500&h=282&fit=crop"
                        },
                        {
                            id: "2",
                            title: "Hot Beef Sandwiches",
                            previewText: "Set it and Smell it",
                            descriptionText: "This is a delicious meal",
                            thumbnail: "http://www.tablefortwoblog.com/wp-content/uploads/2013/12/mississippi-roast-tablefortwoblog-3.jpg"
                        }
                        
                    ].find(el => el.id === context.params.id)
                })
            })
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
    text-align: center;
    padding: 30px;
}

.recipe-image {
    width: 100%;
}
</style>

