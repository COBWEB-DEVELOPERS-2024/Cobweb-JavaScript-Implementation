# **COBWEB Web Implementation (Proposal)**

Building a new implementation of the COBWEB 2.0 (Complexity & Organized Behaviour Within Environmental Bounds) computer simulation model by rewriting the codebase in TypeScript/JavaScript so that COBWEB can be run on the internet without needing to download it.

Authors: Gloria Li

# **Introduction:**

This implementation will include all features of COBWEB 2.0, which simulates the interactions and behaviours of agents within a dynamic environment. By allowing users to customize agents, resources, and environmental factors, COBWEB is used to study emergent behaviours (e.g., Prisoner's Dilemma) and other system dynamics in fields including health science, economics, ecology, etc.

# **Tech stack**
- **Backend:** NodeJS / Postgres DB to store users and their simulations, results
- **Frontend:** NextJS / WebGL to run shaders, possibly WASM for running simulations

## **COBWEB 2.0 Guide:**

COBWEB, short for Complexity and Organized Behaviour Within Environmental Bounds, is a piece of software developed to explore how components of systems (people, animals, bacteria, etc.) adapt to environmental change and variability. The software contains two major components:
1. A population of agents that move, eat, and reproduce
2. The resources that the agents consume, which are also variable in location.

The agents make decisions on when to move, where to move, and when to eat. With optional communication between agents and memory, the population can adapt to some environments and fail in others. This can result in surprising events, such as sudden extinction after stability, recovery from near extinction, or sudden population changes for no apparent reason. These events are expected in any complex system and are a crucial aspect of COBWEB software.

The COBWEB agents are powered by a genetic algorithm, a behavioural strategy randomly created when initializing the model. The resources are simulated with a cellular automaton.

COBWEB is very interactive, allowing users to set many parameters that affect the agents or resource production. Parameters like energy expenditure, resource growth rate, energy requirements for different actions, and energy derived from different resources are all accessible through an easy-to-use interface. The environment is displayed graphically, as a 2D grid with agents represented by triangles and resources by coloured squares. Barriers to movement are represented by black squares. The agents can choose to move, turn, eat, or communicate to increase their survival and reproduction chances.

The population evolves in a Darwinian sense, with the best-adapted agents reproducing most often. Through mutation during reproduction (user-controlled rate), the system experiments with new strategies. Poorly adapted agents are eliminated. Users can change the environment during the simulation to test the population's adaptability.

COBWEB is a great educational tool for students aged 9 and up, teaching how environmental changes affect social and biological systems. It allows exploration of themes such as survivorship, population growth, resource variability and drought, energy costs, and cheating. Workshops can explore specific issues like landscape dynamics, invasive species, fertilization, social isolation, and group behaviour emergence.

During workshops, participants can run experiments, build custom environments, and reproduce specific environments. They can see how populations adapt to environmental changes, learning about research, experimentation, simulation, and predictability. COBWEB is freely distributed, with participants offered the software package at the workshop's end.

COBWEB was developed by Dr. Brad Bass for Environment Canada's Adaptation and Impacts Research Group at the University of Toronto. All intellectual property rests with the Crown. For more information about COBWEB or workshops, contact Brad Bass at 416-978-6285.

To simplify certain features in COBWEB 2.0, an alternative system for conducting simulations has been implemented.

# **Functionality:**

## **Core Features**

### Agents

An agent simulates a living organism through energy consumption and utilization.

**Properties of Agents:**
- Living status
- Location on the map
- Energy level
- Type
- ID

**Actions of Agents:**
- Change energy level through consuming food or spending energy to complete tasks
- Reproduce to create other agents

### Genetic Algorithm

The genetic algorithm in `GeneticCode.java` includes:

1. **Genetic Similarity Comparison**:
   - `compareGeneticSimilarity` compares two genetic sequences and returns their percentage similarity based on identical bits.

2. **Genetic Code Creation (Meiosis)**:
   - **Average Method**: `createGeneticCodeMeiosisAverage` averages genes of two parent genetic codes.
   - **Gene Swap Method**: `createGeneticCodeMeiosisGeneSwap` randomly selects genes from either parent.
   - **Recombination Method**: `createGeneticCodeMeiosisRecomb` combines fragments from both parents at a random split point.

3. **Mutation**:
   - `mutate` flips a bit at a specified position in the genetic sequence.

4. **Genetic Code Management**:
   - Methods like `getNumGenes`, `getValue`, `setValue`, `getBitSet`, and `setBitSet` manage the genetic sequence.

5. **Initialization and Copying**:
   - Constructors initialize genetic codes, either from scratch or by copying an existing genetic code.

These operations form the genetic algorithm's basis, enabling simulation of genetic inheritance, variation, and evolution.

### Cellular Automation

## Environment

The environment is a grid where each cell has 4 states:
- Empty
- Agent-Occupied
- Food-Occupied
- Barrier-Occupied

# **UI Elements**

WebGL and OpenCL will be used to create a shader-based visual display of the simulation. [WebGL Shader](https://developer.mozilla.org/en-US/docs/Web/API/WebGLShader)

(Holosense plugin can possibly be integrated into the visualizer)

**Superscalar Simulation System**
A genetic algorithm or simple neural network can be implemented in a vertex shader, with agents as vertices in a rendering scene.
- **Physics Systems**: Will use a numerical integrator, possibly Euler method, but Verlet or Runge-Kutta numerical methods could also work.
- **Particle's Properties**: Position, velocity, potential energy, etc., will be calculated. Other properties could generate a force field, computed over a 3D hash-table or KD tree, acting on other particles in the next iteration.

Dynamic positional encoding data structures may or may not be parallelizable.

**Visualizers**
Holosense integration: Since it's all shaders, the simulation and visualization elements can be unified, increasing efficiency and frame rate.

# **Customization and Modification:**

# **File Operations:**

Better organize the tech docs and write more into them.

