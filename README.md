# Project Title

Probability of subsequent product's purchase after purchase of a product

## Project Description

### Input:
Input folder: input/input
Text file containing customer name and all the product IDs bought by that customer in the following format:
Mary 34 56 29 12 34 56 92 29 34 12
Kelly 92 29 12 34 79 29 56 12 34 18

### Output:
For each product, the probability of occurance of next product is found. 

### Programming Approaches

#### Pairs Approach
Pairs approach consists of in-mapper combiner algorithm. The mapper and reducer output is in pairs.
Output Folder: output/CrystalBallPair
Output: Part file containing “Pairs” of product Id and the frequencies of the bought products until the original product is bought. The output would be in the following format:
[12, 18]	0.09090909090909091
[12, 29]	0.18181818181818182
[12, 34]	0.36363636363636365
... and so on.

#### Stripes Approach 
The mapper and reducer output of stripes approach is in Stripes.
Output Folder: output/CrystalBallStripe
Output: Part file containing “Stripes” of product Id and the frequencies of the bought products until the original product is bought. The output would be in the following format:
12	{(56, 0.18181818181818182), (92, 0.09090909090909091), (34, 0.36363636363636365), (18, 0.09090909090909091), (79, 0.09090909090909091), (29, 0.18181818181818182), }
29	{(56, 0.15384615384615385), (92, 0.07692307692307693), (34, 0.3076923076923077), (18, 0.07692307692307693), (79, 0.07692307692307693), (12, 0.3076923076923077), }
... and so on.

#### Hybrid Approach
The mapper output of hybrid approach is in Pairs and reducer output is in stripes. This is the most efficient apporach.
Output Folder: output/CrystalBallHybrid
Output: Part file containing “Stripes” of product Id and the frequencies of the bought products until the original product is bought. The output would be in the following format:
12	{(56, 0.18181818181818182), (92, 0.09090909090909091), (34, 0.36363636363636365), (18, 0.09090909090909091), (79, 0.09090909090909091), (29, 0.18181818181818182), }
29	{(56, 0.15384615384615385), (92, 0.07692307692307693), (34, 0.3076923076923077), (18, 0.07692307692307693), (79, 0.07692307692307693), (12, 0.3076923076923077), }
... and so on.

## Getting Started

Change directory to project source directory and run these bash commands:
./build.sh
./run.sh

### Prerequisites

- Install platform for Cloudera. This may be VMWare, Docker or VirtualBox.
- Install Cloudera CDH 5.8 into the platform. 
- This can be downloaded from : https://www.cloudera.com/downloads/quickstart_vms/5-8.html
  
## Author

* **Bishal Paudel** - [BishalPaudel](https://github.com/bishalpaudel)

## License

This project is licensed under the MIT License