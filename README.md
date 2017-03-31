# Project Title

Probability of subsequent product's purchase after purchase of a product

## Project Description

### Input:
Input folder: input/input<br />
Text file containing customer name and all the product IDs bought by that customer in the following format:<br />
Mary 34 56 29 12 34 56 92 29 34 12<br />
Kelly 92 29 12 34 79 29 56 12 34 18<br />

### Output:
For each product, the probability of occurance of next product is found. More description of outputs is found on Programming Approaches section.

### Programming Approaches

#### Pairs Approach
Pairs approach consists of in-mapper combiner algorithm. The mapper and reducer output is in pairs.<br />
Output Folder: output/CrystalBallPair<br />
Output: Part file containing “Pairs” of product Id and the frequencies of the bought products until the original product is bought. The output would be in the following format:<br />
[12, 18]	0.09090909090909091<br />
[12, 29]	0.18181818181818182<br />
[12, 34]	0.36363636363636365<br />
... and so on.

#### Stripes Approach 
The mapper and reducer output of stripes approach is in Stripes.<br />
Output Folder: output/CrystalBallStripe<br />
Output: Part file containing “Stripes” of product Id and the frequencies of the bought products until the original product is bought. The output would be in the following format:<br />
12	{(56, 0.18181818181818182), (92, 0.09090909090909091), (34, 0.36363636363636365), (18, 0.09090909090909091), (79, 0.09090909090909091), (29, 0.18181818181818182), }<br />
29	{(56, 0.15384615384615385), (92, 0.07692307692307693), (34, 0.3076923076923077), (18, 0.07692307692307693), (79, 0.07692307692307693), (12, 0.3076923076923077), }<br />
... and so on.

#### Hybrid Approach
The mapper output of hybrid approach is in Pairs and reducer output is in stripes. This is the most efficient apporach.<br />
Output Folder: output/CrystalBallHybrid<br />
Output: Part file containing “Stripes” of product Id and the frequencies of the bought products until the original product is bought. The output would be in the following format:<br />
12	{(56, 0.18181818181818182), (92, 0.09090909090909091), (34, 0.36363636363636365), (18, 0.09090909090909091), (79, 0.09090909090909091), (29, 0.18181818181818182), }<br />
29	{(56, 0.15384615384615385), (92, 0.07692307692307693), (34, 0.3076923076923077), (18, 0.07692307692307693), (79, 0.07692307692307693), (12, 0.3076923076923077), }<br />
... and so on.

## Getting Started

Change directory to project source directory and run these bash commands:<br />
./build.sh<br />
./run.sh

### Prerequisites

- Install platform for Cloudera. This may be VMWare, Docker or VirtualBox.<br />
- Install Cloudera CDH 5.8 into the platform. <br />
- This can be downloaded from : https://www.cloudera.com/downloads/quickstart_vms/5-8.html
  
## Author

* **Bishal Paudel** - [BishalPaudel](https://github.com/bishalpaudel)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details