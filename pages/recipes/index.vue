<template>
    <section class="recipes">
        <Recipe
            v-for="recipe in recipes"
            :key="recipe.id" 
            :thumbnail="recipe.thumbnail"
            :title="recipe.title"
            :id="recipe.id"
            :previewText="recipe.previewText"
        />
        
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
                            title: "Pesto Chicken Casserole",
                            previewText: "Quick, Cheap, Delicious",
                            thumbnail: "https://i.dietdoctor.com/wp-content/uploads/2016/05/DD-115.jpg?auto=compress%2Cformat&w=500&h=282&fit=crop"
                        },
                        {
                            id: "2",
                            title: "Hot Beef Sandwiches",
                            previewText: "Set it and Smell it",
                            thumbnail: "http://www.tablefortwoblog.com/wp-content/uploads/2013/12/mississippi-roast-tablefortwoblog-3.jpg"
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
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
}



</style>
