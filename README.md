
## Installation
1.  Clone the repository:
```bash
git clone https://github.com/diwash-9/Genetic-Algorithm.git
```
## Usage
To run the genetic algorithm, execute the main script GeneticAlgorithmImplementation.ipynb. Ensure Python 3.x is installed on your system.

## Parameters
- popn_size: Size of the population.
- mut_rate: Mutation rate, probability of a bit mutating.
- gen: Number of generations.
- length_integer: Length of the binary encoding for the integer part of the solution.
- length_fraction: Length of the binary encoding for the fractional part of the solution.

## Fitness Function
The fitness function used in this implementation is defined as:
```bash
def fitness_function(x):
    return abs(4*x**2 - 9)
```
## Encoding and Decoding
### Encoding:
Each individual in the population is represented as a binary string, where:
- The first length_integer bits represent the integer part.
- The next length_fraction bits represent the fractional part.
Use the encode and decode functions to convert between binary strings and decimal values.

## Initial Population
The initial population is generated randomly within a specified range [-5, 5] using the init_population function.

## Selection
Roulette wheel selection (roulette_wheel_selection function) is employed to select individuals based on their fitness values for reproduction.

## Crossover
Uniform crossover (uniform_crossover function) is used to combine genetic material from selected parents to produce offspring.

## Mutation
Mutation (mutate function) introduces random changes in offspring to maintain genetic diversity and explore new solutions.

## Genetic Algorithm Execution
The genetic algorithm (genetic_algorithm function) orchestrates the iterative process of selection, crossover, mutation, and fitness evaluation over multiple generations to find the optimal solution.

## Example Usage
```bash
# Example usage
from genetic_algorithm import genetic_algorithm, decode, fitness_function

# Parameters
popn_size = 10
mut_rate = 0.1
gen = 20
length_integer = 3
length_fraction = 4

# Initial population
init_population = [encode(random.uniform(-5, 5)) for _ in range(popn_size)]

# Execute genetic algorithm
best_solution = genetic_algorithm(init_population)
decoded_solution = decode(best_solution)
print(f"Best solution found: x = {decoded_solution}, Fitness = {fitness_function(decoded_solution)}")
```

```bash
Best solution found: x = 3.4375, Fitness = 38.265625
```
