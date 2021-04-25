# DS5010 Final Project

![GitHub top language](https://img.shields.io/github/languages/top/Linzzz81/DS5010_Final_Project.svg)

This project is designed as the final project of Northeastern University DS5010

## TeamMember

Team member:

| Name        | NuID      |
| ----------- | --------- |
| [@Lin Zhu](https://github.com/Linzzz81)     | 001066973 |
| [@Yihao Gu](https://github.com/yougugugu)   | 001305641 |

## Introduction

Our goal is to design a linear regression package, which implements most parts of a mutiple linear regression based on ordinary least square. 
This package provides caculation of each parameter and coefficient of linear regression in ```lr.py``` module including **t-test**, **f-test**, **Rsquared** and **SST, SSE, SSR**. 
It also contains functions in ```da.py``` module to help process data, like **read_data()** to read data from local, **partition()** to split dataset into training and validation set, **select_byindex(), select_byname()** to slice dataset by columns. 
Additionally, ```diagnose.py``` module provides diagnostic tools for linear regreesion including **leverage()**, **cooks_distance()** and **plot()** to help diagnose linear regression based on different plots.

## Package Structure

    DS5010_Final_Project/  
    │  
    ├── lr/  
    │     ├── __init__.py  
    │     ├── da.py  
    │     ├── lr.py  
    │     ├── diagnose.py    
    │     └── tests/  
    │         ├── __init__.py  
    │         ├── test_da.py  
    │         ├── test_lr.py  
    │         └── test_diagnose.py  
    │  
    ├── .gitignore  
    ├── README.md  
    ├── test_data.txt  
    ├── run_tests.py  
    └── setup.py  

## Example Usage

Use **``da.py`` Module** :  
```from lr import da```  
```test_data = da.read_data("test_data.txt")```  
```newdata_1 = da.select_byindex(test_data, [0, 1, 2])```  
```newdata_2 = da.select_byname(test_data, ['a', 'b', 'c'])```  
```train, valid = da.partition(test_data, 0.5, 100)```  

Use **``lr.py`` Module** :  
```from lr import lr```  
``` model = lr.lm(test_data, [0,1], [3])```  
``` model.summary()```  
```model.get_coeff()```  

Use **``diagnose.py`` Module** :  
```from lr import diagnose```  
```diagnose = diagnose.diag(model)```  
```diagnose.leverage()```  
```diagnose.plot(3)```   

## Running the Tests

Open terminals and ```cd``` to ```...\DS5010_Final_Project``` dictionary. Type ```py run_tests.py``` to run all unit tests.

## Built With

* [Python](https://www.python.org/) - The programming language to implement the program.

