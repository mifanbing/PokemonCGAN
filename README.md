This is my second ML project. The idea is to create a CGAN and generate new pokemons based on the input, which consists of 2 parts:
Part 1: the type represented by a integer. In my case, it is either 0, 1 or 2, 0 for fire, 1 for grass and 2 for water.
Part 2: A noise from normal distribution. I tested and decided the noise size is 30.

Fire         |  Grass |   Water
:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/mifanbing/PokemonCGAN/blob/main/generateResult/result_0.png) | ![](https://github.com/mifanbing/PokemonCGAN/blob/main/generateResult/result_1.png) | ![](https://github.com/mifanbing/PokemonCGAN/blob/main/generateResult/result_2.png) 
