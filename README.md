# Recipe-Mojo
Generative Tensorflow model to create new recipes. Input ingredients to use and start sequence of words, then generate a brand new recipe.

Lately, I have been really interested in generative deep learning models. You typically don't need a lot of labelled data as it is typically self referential and not an area I get to work in to frequently. The idea of building a recipe generator came from a Google blog post where they created a model to generate a list of ingredients. The short coming was that how you use the ingredients was out of the scope of that model. While it is tricky, it should be possible to generate the list of instructions. In addition, generating recipes should be a bit easier than a lot of other generators because recipes are very algorithmic and depedent on the 
ingredients you put in. For example, a recipe list like this:

* ½ cup unsalted butter
* ½ cup white sugar
* ¼ cup packed light brown sugar
* 1 large egg
* ½ teaspoon vanilla extract
* 1 ⅛ cups all-purpose flour
* ½ teaspoon salt
* ½ teaspoon baking soda
* ⅓ cup semi-sweet chocolate chips

Will never be a recipe for pizza. Or apple pie, or chicken soup for that matter. If you are culinarily inclined, you might even recognize this as a chocolate chip cookie recipe. And if you are *more* culinarily inclined, you could extrapolate the general set of steps. Something like this:

* Preheat Oven to 350
* Cream butter, sugar, eggs, and vanilla together till smooth.
* Mix flour, salt, baking soda together
* Slowly add flour mixture to egg mixture till smooth.
* Add chocolate chips
* Place on baking sheet and bake for 10 to 15 minutes.

Because I can extrapolate that the ingredients are for cookies, I know that 99.9% of recipes will use the creaming method in baking, which is just an algorithm for how to make cookies or cakes. So what does this mean for our generative model? It means the dimensions of possibilities are dramatically reduced given the set of ingredients. If I can learn to make cookies without a recipe, why not a computer?

## Stratgies

When I was brainstorming how to build this model, my first thought was image captioning. In image captioning problems, you start with a image classifier, a sequence model, and you merge them together to generate new sequences. Well, a list of ingredients is a little like a feature vector from a CNN. And a caption is a little like a series of steps right? So we can probably get swap out the CNN for a simple ANN, and then use the exact same strategies for our sequence model.

In my case, I started with two fully connected dense layers for the ingredients model, and a embedinging layer using pretrained GLOVE weights, and then an LSTM. So how did it turn out? 

To Be Continued...
