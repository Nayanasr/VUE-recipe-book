<template>
  <h1>Recipe Book</h1>
  <div class="flex-box">
    <div>
      <recipe-details
        v-for="recipe in recipes"
        :key="recipe.id"
        :name="recipe.name"
        :description="recipe.description"
        :id="recipe.id"
        :img="recipe.img"
        @toggleRecipeStatus="toggleRecipeStatus"
      />
    </div>
    <div>
      <full-details
        v-for="recipe in recipes"
        :key="recipe.id"
        :name="recipe.name"
        :description="recipe.description"
        :id="recipe.id"
        :img="recipe.img"
        :show="recipe.showRecipe"
      />
    </div>
  </div>
</template>

<script>
import FullDetails from "./components/FullDetails.vue";
import RecipeDetails from "./components/RecipeDetails.vue";
export default {
  name: "App",
  components: { 
      FullDetails,
      RecipeDetails
  },
  data() {
    return {
      recipes: [
        {
          id: "1",
          name: "Gulab Jamun",
          img: 
          "https://img.freepik.com/free-photo/indian-sweet-food-gulab-jamun-served-round-ceramic-bowl_466689-71954.jpg?w=2000",

          description:
          "Take required quantity of sugar and water in a deep pan.Stir and bring to boil on high flame for sugar to dissolve.Now add milk and cardamom seeds to the sugar water. Boil further and strain.Then add saffron and cardamom powder and bring the mixture to rolling boil for about 5-6 minutes until it becomes little sticky.Take the grated Khoya in a medium size deep bowl.Add baking soda and maida. Combine them thoroughly but gently using a spoon.Add a teaspoon of milk to it and knead all of them together to make a smooth and soft dough. Add another teaspoon of milk if required.Make sure that the dough is a bit softer to avoid cracking of ball while deep frying.Divide the dough into equal parts and make smooth surfaced balls out of it.Now heat ghee in a pan over medium flame and add the Jamun balls to deep-fry them. Cook evenly until it becomes golden brown.Make sure that you do not cook on high flame otherwise the balls will burn.Now drain and let them cool for few minutes.Then immerse the gulab jamuns in the warm sugar syrup for at least 30 minutes. It increases in size when it soaks the sugar syrup.Hot and tasty sweet dish is ready to serve.",
          showRecipe: true,
        },
        {
          id: "2",
          name: "Gobi Manchurian",
          img:"https://www.tablefortwoblog.com/wp-content/uploads/2022/01/gobi-manchurian-recipe-photo-tablefortwoblog-5-801x1200.jpg",
          description:
                    "Boil cauliflower florets in salted water over medium flame for 3-4 minutes. After boiling, drain excess water and pat dry florets on tissue paper.Mix maida, corn flour, 1/2 teaspoon ginger paste, 1/2 teaspoon garlic paste and salt in a bowl. Add water (approx. 1/2 cup) little by little and stir to make a batter. Make sure that batter is not too thick or not too thin. Its thickness should be similar to thickness of dosa batter. Add all florets in batter and mix well. For perfect manchurian, batter should coat florets evenly.Heat oil in kadai (frying pan) over medium flame. Carefully drop or slide 6 to 8 florets in oil and deep fry over medium flame until they turn golden brown. Drain and transfer deep fried florets over paper napkin to a plate. Deep fry remaining florets.Heat 2-tablespoons oil in a wide, thin-bottomed pan or wok on medium flame. Add 2 teaspoons ginger paste, 1½ teaspoons garlic paste, chopped green chillies, chopped capsicum and chopped onion.Sauté them on high flame for 3-4 minutes.Add soy sauce, tomato ketchup, chilli sauce and salt.Stir continuous and cook for a minuteAdd deep fried florets.Toss and mix deep fried florets with other ingredients in pan for 1-2 minutes keeping flame on high. (Tossing everything on high heat in wok or pan is must for making best Chinese gobi manchurian dry.Transfer it to a plate and garnish with spring onion. Serve it hot with tomato ketchup and chilli sauce.",
          showRecipe: false,
        },
        {
          id: "3",
          name: "Chicken Biryani",
          img: "https://wallpaperaccess.com/full/1972913.jpg",
          description:
          "Heat the oil and fry the onions until they are golden brown (approximately 5 minutes).Add the garlic, chillies, tomatoes, tomato puree, spices, and 1 cup of water and simmer on a medium heat for 5minutes. Use a potato masher if you want the sauce to be smoother.Add the chicken and simmer for 10 minutes, stirring regularly.Add the frozen peas, mushrooms, potatoes and more water if needed and simmer for 5 minutes.Put the boiling water in a saucepan, add the washed rice, boil for 5 minutes and drain.Layer the chicken mixture with the rice starting with the rice then the chicken mixture and repeat this twice.Garnish with cumin seeds, and ginger. Lower the heat and simmer for a further 10 minutes.Serve with fresh salad and yogurt dip. ",
          showRecipe: false,
        },
      ],
    };
  },
  methods: {
    // getUserShowRecipe(showRecipe) {
    //   this.userShowRecipe = showRecipe;
    toggleRecipeStatus(recipeID) {
      let identifiedRecipe = this.recipes.find(
        (recipe) => recipe.id === recipeID
      );
      identifiedRecipe.showRecipe = !identifiedRecipe.showRecipe;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}

h1 {
  background-color: #1d9819;
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
  padding: 10px 20px;
  color: white;
  box-shadow: 1px 4px lightgrey;
}

.flex-box {
  display: flex;
}
</style>