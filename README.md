# GeneticAlgorithm
A genetic algorithm is an optimization technique inspired by natural selection, used to evolve solutions to complex problems by mimicking the process of genetic evolution.

## Introduction
The Genetic Algorithm: Nature-Inspired Optimization
Discover how the Genetic Algorithm harnesses the power of evolution to solve complex problems. Mimicking nature's selection, recombination, and mutation processes, this computational technique iteratively refines solutions, offering a versatile approach to optimization in various fields. Join us in exploring this innovative bridge between computer science and biology, where the principles of survival and adaptation lead us to optimal problem-solving outcomes.

The Genetic Algorithm stands as a prominent cornerstone in the realm of computational optimization, widely adopted across diverse fields from engineering to artificial intelligence. It's a potent technique inspired by the forces of evolution, designed to tackle intricate problems by mimicking the gradual refinement of biological organisms.

At its core, the Genetic Algorithm employs a metaphorical gene pool, starting with an initial population of potential solutions to a problem. Just as in nature, these solutions undergo a process of selection, recombination, and mutation. The fittest solutions, akin to the well-adapted species, dominate the gene pool and contribute to the next generation.

Two primary concepts drive the Genetic Algorithm:

1. **Fitness Function**: This gauges the quality of each solution, analogous to the adaptation of organisms to their environment. Solutions demonstrating better performance receive higher fitness scores.

2. **Genetic Operators**: Like nature's recombination and mutation, these operators create new solutions from existing ones. Crossover blends genetic information from two parent solutions, while mutation introduces small changes, fostering diversity.

By iteratively applying these operators, the Genetic Algorithm navigates the vast landscape of potential solutions. Over generations, it converges towards optimal or near-optimal answers, adapting its search strategy much like organisms evolve to thrive.

Much like A* search, the Genetic Algorithm strikes a balance between exploration and exploitation. It explores new areas of the solution space while exploiting promising regions to refine solutions further. As the algorithm advances, solutions evolve, adapt, and ultimately converge towards improved outcomes.

Intriguingly, this blend of computational and biological inspiration allows the Genetic Algorithm to unravel solutions to complex problems that traditional methods might overlook. Join us on this journey as we dissect the genetic makeup of this algorithm, revealing how its evolutionary prowess propels it to the forefront of optimization and problem-solving techniques.

## Problem Scenario
Run Chase Problem: Suppose, you have a run-predictor for cricket matches and the predictor can predict the target run for batting innings. Now you need to find out the match-winning combination of batsmen for your favorite team given the average runs of different batsmen. You need to find out a combination of batsmen where the total of average runs equals exactly the runs predicted as the target score by the predictor. 
The input contains the number of batsmen available, the target run predicted by the predictor, and the names and average runs of the respective batsman. 
Assume, the predictor predicted 300 runs as the target and there are 7 batsmen in your favorite team with their corresponding average scores, you need to find out the binary combination (1 denoting batsman selected, 0 denotes batsman not selected) of those 7 batsmen in order to find the winning combination.

Your task is to use a genetic algorithm to solve this Run-Chase problem.
Task Breakdown:
a)	Model the selected batsman array in a way suitable for the problem.
b)	Write a fitness function. Hint: It is the sum of the total runs of the selected batsmen.
c)	Write the crossover function.
d)	Write the mutation function.
e)	Create a population of randomly generated selected-batsman-array.
f)	Run genetic algorithms on the population until the highest fitness has been reached and/or the number of maximum iterations has been reached.

Input:
The first line has a number N and T denoting the number of batsmen available and target score respectively followed by N lines each starting with the batsman's name and a number R denoting the average run of the batsman. Here:
N (1 ≤ N ≤ 18)
T (1 ≤ T ≤ 1000)
R (1 ≤ R ≤ 401)

Output:
The output contains a list of all the players and the following row contains a binary string denoting 1 for the selected batsmen and 0 for the not selected batsmen where average runs of selected batsmen sums up equal to the target or -1 if such a string cannot be formed. 

Examples:
Sample Input 1
8 330
Tamim 68
Shoumyo 25
Shakib 70
Afif 53
Mushfiq 71
Liton 55
Mahmudullah 66
Shanto 29
Sample Output 1
['Tamim', 'Shoumyo', 'Shakib', 'Afif', 'Mushfiq', 'Liton', 'Mahmudullah', 'Shanto']
10101110
Explanation: Here, the sum of the average runs of Tamim, Shakib, Mushfiq, Liton and Mahmudullah adds up to 68+70+71+55+66 = 330.

Sample Input 2
5 240
Bradman 120
Tendulkar 90
Sangakkara 70
Kallis 65
Lara 80
Sample Output 2
['Bradman', 'Tendulkar', 'Sangakkara', 'Kallis', 'Lara']
01101

Sample Input 3
4 100
Ralph 80
John70
Tom40
Young50
Sample Output 3
['Ralph', 'John', 'Tom', ‘Young']
-1

## Code explanation.
The provided code implements a Genetic Algorithm to find an optimal combination of binary values that minimizes the absolute difference between the sum of weighted binary values and a given target value. Let's break down the code step by step:

1. **Import Libraries:**
   - `random as rd`: Importing the `random` library and renaming it as `rd`.
   - `math`: Importing the `math` library for mathematical functions.

2. **GeneticAlgorithm Class:**
   - The class defines the Genetic Algorithm and its operations.
   - `__init__`: The constructor initializes various attributes like the initial data (`run_pair`), the target value (`run_target`), population size, and other control variables.
   - `finding_final_combination`: This method is the core of the algorithm. It initializes a population of potential solutions and iteratively performs selection, crossover, and mutation operations on the population to evolve towards an optimal solution.

3. **Fitness, Selection, Crossover, and Mutation Functions:**
   - `fitness_func`: Computes the fitness of each individual in the population based on their difference from the target value. The fitness is higher for solutions that are closer to the target.
   - `select_fit`: Sorts the population based on fitness values, placing more fit individuals at the beginning of the population.
   - `crossover_func`: Performs crossover between two parent individuals to create new offspring individuals. The crossover point is randomly selected.
   - `mutation_func`: Introduces random mutations in the population by flipping individual binary values.

4. **Reading and Processing Input File:**
   - `read_input_file`: Reads the input from a file, extracting the target value and pairs of player names and player counts.

5. **Main Part:**
   - The code reads input data from a file (`input2.txt`), extracts player data, and initializes an instance of the `GeneticAlgorithm` class.
   - It then calls the `finding_final_combination` method to start the algorithm and find an optimal solution.

In summary, this code implements a Genetic Algorithm to find a binary combination that closely matches a target value by iteratively evolving a population of potential solutions through selection, crossover, and mutation operations. The algorithm aims to minimize the absolute difference between the sum of weighted binary values and the target value.

## Conclusion
In conclusion, the Genetic Algorithm stands as a remarkable testament to the fusion of nature's guiding principles and computational innovation. Rooted in the concept of evolution, this algorithm transcends traditional problem-solving boundaries, offering a versatile and powerful tool for optimization.

By emulating the process of natural selection, recombination, and mutation, the Genetic Algorithm navigates complex solution spaces, uncovering optimal or near-optimal answers that might remain concealed by conventional methods. It has found applications across diverse fields, from engineering and biology to artificial intelligence and beyond.

The Genetic Algorithm's ability to adapt and evolve solutions mirrors the dynamic nature of real-world problems. Its inherent balance between exploration and exploitation captures the essence of problem-solving, where refinement and innovation go hand in hand.

As we bid adieu to this exploration of the Genetic Algorithm, let us carry forth the inspiration drawn from nature's ingenious mechanisms and computational prowess. With each generation of algorithms, we move closer to unraveling the mysteries of complex optimization landscapes, guided by the same forces that have shaped life's intricate diversity.
