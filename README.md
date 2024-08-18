# Project: Determining the Best-Fit Line/Parabola on Data using GA and PSO

This project aims to determine the best-fit line or parabola on a given dataset using Genetic Algorithm (GA) and Particle Swarm Optimization (PSO). The project involves implementing both algorithms from scratch, detailing their design, and visualizing the optimization process through graphs.
**Note:** The project will be evaluated using the dataset provided in `/res/data_file.csv`. Ensure that the file is correctly placed in the project directory.

## Project Objective

The given dataset provides an `x` input corresponding to a `y` output. The goal is to find the best-fitting line or parabola that accurately represents this data, and to optimize the coefficients of this curve. Two different approaches are implemented using Genetic Algorithm and PSO.

## Methods Used

### 1. Genetic Algorithm (GA)
- **Approach:** The Genetic Algorithm is inspired by the principles of natural selection and genetics. Initially, an attempt was made to fit a line (`ax + b`). If this was insufficient, the process was repeated for higher-order polynomials: `ax^2 + bx + c`, `ax^3 + bx^2 + cx + d`, and finally `ax^4 + bx^3 + cx^2 + dx + e`. The best-fitting parabola identified was `ax^3 + bx^2 + cx + d`, and the goal was to determine the optimal four coefficients for this polynomial.
- **Libraries Used:** pandas, numpy, matplotlib.pyplot, and random.
- **Data Loading and Visualization:** Data is loaded from `data_file.csv` using pandas and visualized with a scatter plot using matplotlib.
- **GA Functions:**
  - **Population Creation:** An initial population of random individuals is generated.
  - **Fitness Function:** Fitness is calculated as the mean squared error between the predicted and actual values.
  - **Tournament Selection:** Selects the best individual among a subset of the population.
  - **Crossover:** Combines two parents to produce two new children.
  - **Mutation:** Randomly alters genes with a small probability.
  - **GA Operation:** The population evolves over several generations. The best individual and fitness value are updated and stored.
  - **Results Visualization:** Fitness values are plotted over iterations. The best-fitting parabola is plotted with the data points.
- **Validation:** Results were verified by comparing with the DEAP library for Genetic Algorithms.
- **Implementation File:** `GA_solve.ipynb`

### 2. Particle Swarm Optimization (PSO)
- **Approach:** The PSO algorithm aims to find the best-fit line or parabola by iteratively updating the position of particles in the search space. Initially, an attempt was made to fit a line (`ax + b`). If this was insufficient, the process was repeated for higher-order polynomials: `ax^2 + bx + c`, `ax^3 + bx^2 + cx + d`, and finally `ax^4 + bx^3 + cx^2 + dx + e`. The best-fitting parabola identified was `ax^3 + bx^2 + cx + d`, and the goal was to determine the optimal four coefficients for this polynomial.
- **Libraries Used:** pandas, numpy, matplotlib.pyplot, and random.
- **Data Loading and Visualization:** Data is loaded from a CSV file and visualized with a scatter plot.
- **Fitness Function:** Defines how well the parameters fit the data, calculated as the mean squared error (MSE) between predicted and actual values.
- **Particle Class Definition:** Defines particle properties (position, velocity, best position, and best fitness) and behaviors (velocity and position updates). Initial positions and velocities are randomized.
- **PSO Algorithm:**
  - **PSO Function:** Performs particle swarm optimization.
  - **Swarm Creation:** Creates a specified number of particle objects.
  - **Global Best Position and Fitness:** Initially set to the position and fitness of the first particle.
  - **Iteration Loop:** Calculates fitness values for each particle, updates personal and global bests, and adjusts velocities and positions. Fitness values are recorded over iterations.
  - **Results Visualization:** The model with the best parameters is visualized on a scatter plot.
- **Validation:** Results were verified by comparing with the pyswarm library for Particle Swarm Optimization.
- **Implementation File:** `PSO_solve.ipynb`

## Important Notes

After implementing the algorithms from scratch, the same algorithms were later re-implemented using the DEAP library for Genetic Algorithms and the pyswarm library for Particle Swarm Optimization. The results from these implementations were then compared.

## Results

At the end of the project, the performance of the Genetic Algorithm and PSO on the dataset is compared. This comparison is based on solution convergence, fitness value, and computational cost.

### Comparison of Algorithms

- **Genetic Algorithm (GA):** 
  - **Population-Based:** GA operates with a population and evolves it over generations. Uses crossover and mutation to generate new individuals. Tournament selection is used to choose the best individuals. It generally requires more iterations to reach the optimal solution.
  - **Advantages:** More flexible, can search a wider solution space due to crossover and mutation.
  - **Best Fitness Value:** 289.69235703926427

- **Particle Swarm Optimization (PSO):** 
  - **Swarm-Based:** PSO operates with a swarm and updates particle positions based on individual and global best positions. It converges faster and typically requires fewer iterations. Simple to implement with fewer parameters to adjust.
  - **Advantages:** Faster convergence, simpler to implement with fewer parameter settings.
  - **Best Fitness Value:** 400.31918672637187

Both algorithms have their strengths and weaknesses. For this dataset, Particle Swarm Optimization provided faster results, while Genetic Algorithm achieved a better overall fitness value for the third-order polynomial parameters.
