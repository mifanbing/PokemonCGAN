This is my second ML project. The idea is to create a CGAN and generate new pokemons based on the input, which consists of 2 parts:\
Part 1: the type represented by a integer. In my case, it is either 0, 1 or 2, 0 for fire, 1 for grass and 2 for water.\
Part 2: A noise from normal distribution. I tested and decided the noise size is 30.\

Fire         |  Grass |   Water
:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/mifanbing/PokemonCGAN/blob/main/generateResult/result_0.png) | ![](https://github.com/mifanbing/PokemonCGAN/blob/main/generateResult/result_1.png) | ![](https://github.com/mifanbing/PokemonCGAN/blob/main/generateResult/result_2.png) 

**Data Preparation**\
For the 3 types, I have around 1k images. All of them are typical.

**Model**\
Standard CGAN: (https://machinelearningmastery.com/how-to-develop-a-conditional-generative-adversarial-network-from-scratch/) I tested and tuned the parameters in the embedding part:\

label_embedding = Embedding(self.class_num, 1024)(label)
label_embedding = Dense(3* 3* 60)(label_embedding)
label_embedding = Reshape((3, 3, 60))(label_embedding)

**Training**\
I decided that in each epoch, I update the Discriminator once and the Generator twice. If once and once, the D beats the G easily and doesn't generate good pokemons. Same issue with once and three times.\
Also, I stopped at ~1200 iterations. Generated images started to get blury after this point.

**Generate my own images**\
Wrote some code (https://github.com/mifanbing/PokemonCGAN/blob/main/generatePokemon.ipynb)

This is hard and I learned a lot. It seems that StyleGAN beats me very easily, and I want to learn about it next.
