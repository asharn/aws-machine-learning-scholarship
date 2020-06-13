# aws-machine-learning-scholarship
This reposotory has course work completed for phase-I and If selected then will add course work of phase-II as well where you can get a good idea of what different thing you are going to learn through the whole process of scholarship. 

## Phase I

### Introduction of scholarship program work work that will explain different excercise that some some is going to learn about object oriented programming.

    - Object-oriented programming syntax
        - procedural vs object-oriented programming
        - classes, objects, methods and attributes
        - coding a class
        - magic methods
        - inheritance

    - Using object-oriented programming to make a Python package
        - making a package
        - tour of scikit-learn source code
        - putting your package on PyPi


### Modulization of pyhton code with example

So far the coding exercises have been in Jupyter notebooks. Jupyter notebooks are especially useful for data science applications because you can wrangle data, analyze data and share a report all in one document; however, they're not ideal for writing modular programs, which require separating code into different files.

In the 2_modularized_code folder, you'll find three files. You can double click on the folder in the list to the left hand side of the workspace. Look at how the Distribution class and Gaussian class are modularized into different files. 

The Gaussiandistribution.py imports Distribution class from the Generaldistribution.py file. The line of code:

from Generaldistribution import Distribution

essentially pastes the Distribution code to the top of the Gaussiandistribution file when you run the code. You'll see in the example_code.py file an example of how to use the Gaussian class.

The example_code.py file then imports the Gaussian distribution class. 

For the rest of the lesson, you'll work with modularized code rather than a Jupyter notebook. Go through the code in the modularized_code folder and understand how everything is organized.

