# Isodyn
Version: 1.0

![Logo](text3923.png)

## Short Description

“C++”-program simulating the dynamics of metabolites and their isotopic isomers in central metabolic network using a corresponding kinetic model

## Description

“Isodyn” is a C++-program that performs an analysis of stable isotope tracer data to assess metabolic flux profiles in living cells. Isodyn simulates the dynamics of isotopic isomer (isotopomer) distribution in central metabolic pathways, and, by changing its parameters, which reflect the characteristics of corresponding biochemical reactions, fit the simulated dynamics of mass isotopomers to that observed experimentally. The simulated metabolic fluxes that correspond to the best fit are assumed to reproduce the real fluxes in the analyzed biological object and conditions. Isodyn contains tools that check the goodness of fit and perform a statistical analysis of obtained metabolic fluxes.

## Key features

- simulation of concentrations of 13C isotopomers originated from artificially 13C enriched substrates, obtained using mass spectrometry and corrected for natural occurring isotopes and peaks overlapping

## Functionality

- Post-processing
- Statistical Analysis
- Workflows

## Approaches

- Isotopic Labelling Analysis / 13C
    
## Data Analysis

- simulation of the mass isotopomer data, fitting them using a kinetic nodel, evaluation of metabolic fluxes corresponding to the best fit

## Instrument Data Types

- MS

## Tool Authors

- Vitaly Selivanov (Universitat de Barcelona)

## Container Contributors

- [Pablo Moreno](EBI)

## Website

- N/A

## Git Repository

-https://github.com/seliv55/wf/tree/master/isodyn

## Installation

- "IsoDyn" does not require installation. To run it in local computer it is sufficient to copy (clone) the repository. 
- If some of .cpp or .h files are modified, run ''' make clean && make '''

## Usage Instructions

Isodyn can run in several modes:

- The following command forces Isodyn to perform just one simulation of the data presented in "experimental_data_file" with a set of parameters presented in "parameters_file" and stop:
 
```
  ./isodyn.out experimental_data_file parameters_file 
```

- The addition of parameter "s" forces to calculate the confidence intervals for all fluxes, based on the previously saved in the output directory files with model parameters and metabolic fluxes, and save the results in file "statfl":
 
```
 ./isodyn.out experimental_data_file parameters_file s 
```

- The addition of parameter "x" forces to recalculate the χ2 for the parameters sets previously saved in the output directory as files "1", "2", etc:
 
```
 ./isodyn.out experimental_data_file parameters_file x 
```

- The addition of integer forces to perform optimization using Simulated Annealing algorithm minimizing χ2 and stop after saving "int_number" of files with optimized parameters in the output directory:
 
```
 ./isodyn.out experimental_data_file parameters_file int_number 
```


 
## The provided examples:
 
The provided set of multipeak CDF files contain the mass isotopomer distributions measured for various metabolites for three cell lines A549, BEAS2B, and NCIH460. Moreover the presented set of monopeak CDF files contains the mass isotopomer distributions measured for HUBEC cells. All these data, extracted by RaMID and corrected by midcor serve as examples of data that Isodyn uses for simulations. An initial set of parameters presented in the file "out/1". Below are the examples of commands to run Isodyn in several modes.

Single simulation:

```
 ./isodyn.out A549 out/1 
```

screenshot of a simulation of input data, shown only for unlabeled fraction (m0)

![screenshot](Screenshot.png)

 
- Statistics for fluxes, saved in the files  "1", "2", etc, in the directory /out:

```
 ./isodyn.out A549 out/1 s 
```
 
- recalculating χ2 for the parameters sets previously saved in the output directory out/1 as files "1", "2", etc:
 
```
 ./isodyn.out  A549 out/1 x 
```

- performing optimization using Simulated Annealing algorithm minimizing χ2 and stop after saving 33 files with optimized parameters in the output directory:
 
```
 ./isodyn.out  A549 out/1 33 
```

## Publications

- 1: Selivanov VA, Vizán P, Mollinedo F, Fan TW, Lee PW, Cascante M.
Edelfosine-induced metabolic changes in cancer cells that precede the
overproduction of reactive oxygen species and apoptosis. BMC Syst Biol. 2010, 4:135.

- 2: de Mas IM, Selivanov VA, Marin S, Roca J, Orešič M, Agius L, Cascante M.
Compartmentation of glycogen metabolism revealed from 13C isotopologue
distributions. BMC Syst Biol. 2011, 5:175.

- 3: Selivanov VA, Marin S, Lee PW, Cascante M. Software for dynamic analysis of
tracer-based metabolomic data: estimation of metabolic fluxes and their
statistical analysis. Bioinformatics. 2006, 22(22):2806-12.

- 4: Selivanov VA, Meshalkina LE, Solovjeva ON, Kuchel PW, Ramos-Montoya A,
Kochetov GA, Lee PW, Cascante M. Rapid simulation and analysis of isotopomer
distributions using constraints based on enzyme mechanisms: an example from HT29 
cancer cells. Bioinformatics. 2005, 21(17):3558-64.

- 5: Selivanov VA, Puigjaner J, Sillero A, Centelles JJ, Ramos-Montoya A, Lee PW,
Cascante M. An optimized algorithm for flux estimation from isotopomer
distribution in glucose metabolites. Bioinformatics. 2004, 20(18):3387-97. 

