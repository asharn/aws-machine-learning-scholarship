# AWS Machine Learning Scholarship
This repostory contains course work completed for phase-I and If selected then will also contains of phase-II of AWS Machine Learning where you can get a good idea of what different thing you are going to learn through the whole process of scholarship. 

## Phase I

[](phase-I/aws-mle-intro.jpg)

### Introduction of scholarship program course work that will explain different excercise that some some is going to learn about object oriented programming.

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
```python
from Generaldistribution import Distribution
```
essentially pastes the Distribution code to the top of the Gaussiandistribution file when you run the code. You'll see in the example_code.py file an example of how to use the Gaussian class.

The example_code.py file then imports the Gaussian distribution class. 

For the rest of the lesson, you'll work with modularized code rather than a Jupyter notebook. Go through the code in the modularized_code folder and understand how everything is organized.


### Pyhton pakaging 

Following the instructions from the previous video, convert the modularized code into a Python package. 

You can put your code into the 3a_python_package folder in the workspace. Inside the 3a_python_package folder, you'll need to create a few folders and files:
* a setup.py file, which is required in order to use pip install
* a folder called 'distributions', which is the name of the Python package
* inside the 'distributions' folder, you'll need the Gaussiandistribution.py file, Generaldistribution.py and an __init__.py file.

Once everything is set up, open a new terminal window in the workspace by clicking 'NEW TERMINAL'. Then type:
	
```
cd 3a_python_package
pip install .
```

If everything is set up correctly, pip will install the distributions package into the workspace. You can then start the python interpreter from the terminal typing:
	
```python```

Then within the Python interpreter, you can use the distributions package:
	
```python
from distributions import Gaussian
gaussian_one = Gaussian(25, 2)
gaussian_one.mean
gaussian_one + gaussian_one
```
etcetera...In other words, you can import and use the Gaussian class because the distributions package is now officially installed as part of your Python installation.

If you get stuck, there's a solution in the 3b_answer_python_package folder.

If you want to install the Python package locally to your computer, you might want to set up a virtual environment first. A virtual environment is a siloed Python installation apart from your main Python installation. That way you can easily delete the virtual enviornment without affecting your Python installation.

If you want to try using virtual environments in this workspace first, here is how to do it:
- There is an issue with the Ubuntu operating system and Python3 where the venv package isn't installed correctly. In the workspace, one way to fix this is by running this command in the workspace terminal: `conda update python` See: https://stackoverflow.com/questions/26215790/venv-doesnt-create-activate-script-python3 Then type `y` when prompted. It might take a couple of minutes for the workspace to update. If you are not using anaconda on your local computer, you can skip this first step\.
- now, type this command to create a virtual environment `python -m venv venv_name` where venv_name is the name you want to give to your virtual environment. You'll see a new folder appear with the Python installation named venv_name
- In the terminal, type `source venv_name/bin/activate`. You'll notice that the command line now shows (venv_name) at the beginning of the line to indicate you are using the venv_name virtual environment
- Now, you can type `pip install python_package/.` That should install your distributions Python package.
- Try using the package in a program to see if everything works!

### Binomial Packaging

In this exercise, you'll extend the distributions package with a new class called Binomial. 

Inside the folder called `4a_binomial_package`, you'll find another folder and a number of files. Here is a description of each
- distributions, which contains the code for the distributions package including Gaussiandistribution.py and Generaldistribution.py code.
- setup.py a file needed for building python packages with pip
- test.py unit tests to help you debug your code
- numbers.txt and numbers_binomial.txt are data files used as part of the unit tests
- Binomialdistribution.py and Binomialdistribution_challenge.py choose one of these files for completing the exercise. Binomialdistribution.py includes more of the code already set up for you. In Binomialdistribution_challenge.py, you'll have to write all of the code from scratch. Both files contain instructions with TODOS to fill out.

Out of all these files, you'll only need to change the following:
- __init__.py inside the distributions folder. You'll need to import the binomial package
- either Binomialdistribution.py or Binomialdistribution_challenge.py You'll also need to put your Binomialdistribution.py file into the distributions folder.

When you're ready to test out your code, you'll want to pip install your distributions package and then run the unit tests. In the terminal, assuming you are in the 4a_binomial_package directory (if not type `cd 4a_binomial_package`), type `pip install .` into the command line. Then run the unit tests by typing `python -m unittest test`. 

Modify the Binomialdistribution.py code until all the unit tests are passing. 

Note that if you change the code in the distributions folder after pip installing the package, Python will not know about the changes. You'll need to run `pip install --upgrade .` when you make changes to the package files.

There is also a solution in the 4b_answer_binomial_package. Try not to look at the solution until your code is passing all of the unit tests.


### Putting Code on PyPi

In this part of the lesson, you'll practice uploading a package to PyPi. 

The Python package is located in the folder 5_exercise_upload_to_pypi

You'll need to create a setup.cfg file, README.md file, and license.txt file. You'll also need to create accounts for the pypi test repository and pypi repository. 

Don't forget to keep your passwords; you'll need to type them into the command line.

Once you have all the files set up correctly, you can use the following commands on the command line (note that you need to make the name of the package unique, so change the name of the package from distributions to something else. That means changing the information in setup.py and the folder name):

```
cd 5_exercise_upload_to_pypi
python setup.py sdist
pip install twine
```

*commands to upload to the pypi test repository*
```
twine upload --repository-url https://test.pypi.org/legacy/ dist/*
pip install --index-url https://test.pypi.org/simple/ distributions
```
*command to upload to the pypi repository*
```
twine upload dist/*
pip install distributions
```
Check the uploaded one: https://pypi.org/project/general-gaussian-and-binomial-distributions/


## AWS Composer

#### AWS Composer and Generative AI

AWS Deep Composer uses Generative AI, or specifically Generative Adversarial Networks (GANs), to generate music. GANs pit 2 networks, a generator and a discriminator, against each other to generate new content.

The best way we’ve found to explain this is to use the metaphor of an orchestra and conductor. In this context, the generator is like the orchestra and the discriminator is like the conductor. The orchestra plays and generates the music. The conductor judges the music created by the orchestra and coaches the orchestra to improve for future iterations. So an orchestra, trains, practices, and tries to generate music, and then the conductor coaches them to produced more polished music.
Orchestra and Conductor as a metaphor for GANS

#### AWS DeepComposer Workflow

- Use the AWS DeepComposer keyboard or play the virtual keyboard in the AWS DeepComposer console to input a melody.
- Use a model in the AWS DeepComposer console to generate an original musical composition. You can choose from jazz, rock, pop, symphony or Jonathan Coulton pre-trained models or you can also build your own custom genre model in Amazon SageMaker.
- Publish your tracks to SoundCloud or export MIDI files to your favorite Digital Audio Workstation (like Garage Band) and get even more creative.


#### How AWS Deep Composor Works

- Input melody captured on the AWS DeepComposer console
- Console makes a backend call to AWS DeepComposer APIs that triggers an execution Lambda.
- Book-keeping is recorded in Dynamo DB.
- The execution Lambda performs an inference query to SageMaker which hosts the model and the training inference container.
- The query is run on the Generative AI model.
- The model generates a composition.
- The generated composition is returned.
- The user can hear the composition in the console.
- The user can share the composition to SoundCloud.

#### Generative AI

Generative AI has been described as one of the most promising advances in AI in the past decade by the MIT Technology Review.

Generative AI opens the door to an entire world of creative possibilities with practical applications emerging across industries, from turning sketches into images for accelerated product development, to improving computer-aided design of complex objects.

For example, Glidewell Dental is training a generative adversarial network adept at constructing detailed 3D models from images. One network generates images and the second inspects those images. This results in an image that has even more anatomical detail than the original teeth they are replacing.
Glidewell Dental is training GPU powered GANs to create dental crown models

Generative AI enables computers to learn the underlying pattern associated with a provided input (image, music, or text), and then they can use that input to generate new content. Examples of Generative AI techniques include Generative Adversarial Networks (GANs), Variational Autoencoders, and Transformers.

#### What are GANs?

GANs, a generative AI technique, pit 2 networks against each other to generate new content. The algorithm consists of two competing networks: a **generator** and a **discriminator**.

A **generator** is a convolutional neural network (CNN) that learns to create new data resembling the source data it was trained on.

The discriminator is another convolutional neural network (CNN) that is trained to differentiate between real and synthetic data.

The generator and the discriminator are trained in alternating cycles such that the generator learns to produce more and more realistic data while the discriminator iteratively gets better at learning to differentiate real data from the newly created data.

#### Introduction to U-Net Architecture

##### Training a machine learning model using a dataset of Bach compositions

AWS DeepComposer uses GANs to create realistic accompaniment tracks. When you provide an input melody, such as twinkle-twinkle little star, using the keyboard U-Net will add three additional piano accompaniment tracks to create a new musical composition.

The U-Net architecture uses a publicly available dataset of Bach’s compositions for training the GAN. In AWS DeepComposer, the generator network learns to produce realistic Bach-syle music while the discriminator uses real Bach music to differentiate between real music compositions and newly created ones