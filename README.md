# **COBWEB Web Implementation (Proposal)**

Building a new implementation of the COBWEB 2.0 (Complexity & Organized Behaviour Within Environmental Bounds) computer simulation model by rewriting codebase in TypeScript/JavaScript so that COBWEB can be run on the internet without needing to download it.

Authors: Gloria Li

# **Introduction:**

This Implementation will include all features of COBWEB 2.0, which simulates the interactions and behaviours of agents within a dynamic environment. By allowing users to customize agents, resources and environmental factors, COBWEB is used to study emergent behaviours (eg. Prisoner's Dilemma) and other system dynamics in fields including health science, economics, ecology, etc.

  

## **COBWEB 2.0 Guide:**

COBWEB short for Complexity and Organized Behaviour Within Environmental Bounds, is a piece of software that was developed to explore how components of systems (people, animals, bacteria, etc) adapt to environmental change and environmental variability. The software contains two major components:

*   (1) a population of agents that move, eat and reproduce
*   (2) the resources that the agents consume, which are also variable in location.

The agents make decisions on when to move, where to move and when to eat. In combination with optional communication between agents and memory, the population is able to adapt to some environments and fail to adapt in others. This process can result in the occurrence of surprising events, whether it is a sudden extinction after a long period of stability, a recovery from what appears to be certain extinction or a sudden change in population for no apparent reason. These surprising events can be expected in any complex system, and their occurrence in this simple abstraction of complexity is a very important aspect of COBWEB software.

  

The COBWEB agents are powered by an artificial intelligence tool called a genetic algorithm, which is a behavioural strategy. These strategies are randomly created when we initialize the model. The resources, or the environmental variability, are simulated with another common AI too, a cellular automaton. 

  

COBWEB is very interactive, allowing the user to set many parameters that either affect the agents or the resource production. Parameters such as energy expenditure, resource growth rate, energy requirements for different actions and the energy derived from different resources are all accessed through a user interface that is very easy to use. Once the parameters have been set, the environment is displayed graphically, as a two-dimensional grid populated with agents represented by triangles and resources represented by coloured squares. Barriers to movement are represented by black squares. The agents can choose to move, turn, eat or communicate to increase their chances of survival and reproduction.

  

The population evolves in a Darwinian sense, as those agents that are best adapted to the environment tend to reproduce most often, and through mutation during reproduction (the rate of which can be controlled by the user), the system can experiment with new strategies. The agents that are not well adapted to survival are eliminated during the simulation. The user has the option to change the environment in small or large increments at any time during the simulation in order to test the adaptability of the population to change.

  

COBWEB is a great educational tool for students from ages 9 and up. Students can learn how environmental changes affect social and biological systems by adjusting the initial parameters to explore themes such as survivorship, population growth, resource variability and drought, the costs of energy and cheating. Unique workshops can be developed to explore specific issues such as landscape dynamics (how different populations affect the growth of different plants), invasive species, fertilization, social isolation and the emergence of group behaviour.

  

During the workshop, the participants will be given the opportunity to run experiments, build custom environments and will be challenged to reproduce a specific environment themselves. In all cases, the students can see how well the population adapts to environmental variability or change. By working collectively with the COBWEB software, the students will be encouraged to think about how even small changes in an environment may lead to sudden and unexpected changes in the population. In addition, students will learn about research, specifically, experimentation, simulation, and predictability. COBWEB is freely distributed, and at the end of the workshop, the participants will be given an opportunity to receive the software package.

  

COBWEB was developed by Dr. Brad Bass for Environment Canada's Adaptation and Impacts Research Group at the University of Toronto. All intellectual property rests with the Crown. For further information about COBWEB or a COBWEB workshop please contact Brad Bass at 416-978-6285.

  

In order to simplify how certain features are implemented in COBWEB 2.0, I have implemented an alternative system to conduct simulations.

  

# **Functionality:**

# **Core Features**

  

## Agents

An agent is a singular entity that acts as simulates a living organism through the consumption and utilization of energy.

**Properties of Agents:**

*   Living status
*   Location on the map
*   Energy level
*   Type
*   ID

**Actions of Agents:**

*   Change energy level through consuming food or spending energy to complete tasks
*   Reproduce to create other agents

# **Genetic Algorithm**

The genetic algorithm in the provided `GeneticCode.java` class is based on the following key operations:

1. **Genetic Similarity Comparison**:
   - The `compareGeneticSimilarity` method compares two genetic sequences and returns their percentage similarity based on the number of identical bits.

2. **Genetic Code Creation (Meiosis)**:
   - **Average Method**: The `createGeneticCodeMeiosisAverage` method creates a new genetic code by averaging the genes of two parent genetic codes.
   - **Gene Swap Method**: The `createGeneticCodeMeiosisGeneSwap` method creates a new genetic code by randomly selecting genes from either parent.
   - **Recombination Method**: The `createGeneticCodeMeiosisRecomb` method creates a new genetic code by combining fragments from both parents at a random split point.

3. **Mutation**:
   - The `mutate` method flips a bit at a specified position in the genetic sequence, introducing variation.

4. **Genetic Code Management**:
   - Methods like `getNumGenes`, `getValue`, `setValue`, `getBitSet`, and `setBitSet` manage the genetic sequence, allowing for retrieval and modification of genes.

5. **Initialization and Copying**:
   - Constructors initialize genetic codes, either from scratch or by copying an existing genetic code.

These operations collectively form the basis of the genetic algorithm, enabling the simulation of genetic inheritance, variation, and evolution.

# **Cellular Automation**

  


## Environment

The environment is a grid where each cell has 4 states:

*   Empty
*   Agent-Occupied
*   Food-Occupied
*   Barrrier-Occupied


  

# **UI Elements**

WebGL and OpenCL will be used to created a shader-based visual display of the simulation.

# **Customization and Modification:**

  

# **File Operations:**
