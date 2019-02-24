# GAClusterKriging

This project refers to the scripts used in the paper
"A New Methodology for Automatic Cluster-Based Kriging using K-Nearest Neighbour and Genetic Algorithms"

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for testing purposes.

### Prerequisites

It is advisable that the user download the RSTUDIO Desktop Version, which is FREE and OPEN-SOURCE LICENSED, available in the link:
https://www.rstudio.com/

The version 1.2.931 was used in the development of the scripts.

### Installing
The installation is simple and can be done with all default selections by pressing the Next Button.
After the installation is complete, it is necessary to install the packages included in the scripts of the project.

To install packages, select the "Tools" option in the menu and "Install Packages". 
In the text field "Packages", type the following packages and press the button "Install". 
Wait for the installation to finish before installing another package.

 -- gstat   
 -- sp  
 -- automap
 
 -- GA
 -- reshape
 -- NISTunits
 -- SearchTrees
 -- RGeostats
 -- fpc
 -- outliers
 -- scales

After all packages are installed, the databases must be prepared/downloaded.

Meuse -> Available in the "sp" package
Coalash -> Available in the "gstat" package
Broomsbarn ->  http://www.kriging.com/datasets/ (Arquivo BroomsBarn.dat)
Wolfcamp -> http://www.kriging.com/datasets/ (Arquivo Wolfcamp.dat)
Walkerlake -> Available in the "gstat" package

"Broomsbarn.dat" and "Wolfcamp.dat" must be included in the same path/directory of the script (GAClusterKriging.R) file

After theses steps, you may run the code!

## Running the tests

Open the script (GAClusterKriging.R) File in the RSTUDIO software.

BEFORE RUNNING ANY TESTS, MAKE SURE TO FOLLOW THESE STEPS:

 --> In the toolbar select "Session", "Set Working Directory", "To Source File Location";
 --> In the toolbar select "Session", "Clear Workspace";

To RUN the tests, first the database must be selected in the section bellow!

############ DATABASE SELECT ###############
# 1 - Meuse, 2 - Wolfcamp, 3 - Broomsbarn, 4 - Coalash, 5 - WalkerLake
databases = c("meuse","wolfcamp","broomsbarn","coalash","walkerlake")
databaseSelected = databases[1]

Next, type the name of the output file and the number of tests that will be applied to each cluster.

######### VARIABLES INIT ###########
outputFileName = "TestLog.txt"
nTestsForEachCluster = 5

Next, select the size of the Genetic Algorithm Population and Number of Iterations.

############ AG PARAMETERS #################
gaPopulation = 100
gaIter = 10

Next, select the number of neighbours considered in the KNN method.
Is important to note that the number is N-1, because the closest point, is the point itself.
So if you want 3 neighbours, you must type 4.

############ KNN PARAMETERS ################
# Neighbours = 4 means 3 neighbours ########
# Cause the closes is the point itself #####
nNeighbours = 4  

Finally, select the number of clusters of the K-Means Method.

############ K-MEANS PARAMTERS #############
kmeansClusters = 6

### Tests Results

The tests will be avaiable in the 

CLUSTER ---------- 1
                   GA --- GA2 -- LS1 -- ILS -- ILS2           
Iteration: 1              0.3455 0.3604 0.3797 0.3896 0.3806                
Iteration: 2              0.3503 0.3606 0.3797 0.3896 0.3806                
Mean:   0.3479 0.3605 0.3797 0.3896 0.3806
Stand. Deviation:   0.0035 1e-04 0 0 0
CLUSTER ---------- 2
                   GA --- GA2 -- LS1 -- ILS -- ILS2           
Iteration: 1              0.3315 0.3717 0.398 0.3872 0.3872                
Iteration: 2              0.3323 0.3717 0.398 0.3872 0.3872                
Mean:   0.3319 0.3717 0.398 0.3872 0.3872
Stand. Deviation:   6e-04 0 0 0 0

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
