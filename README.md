<p align="center">
  <img width="25%" src="./docs/CRICK_Primary_Logo_CMYK High res.png" alt="Crick Logo">
</p>

# CBIAS napari workshop 2026
CBIAS napari workshop 2026 - run as part of the Crick Bioimage Analysis Symposium 2026

25-26 November 2026 <br>
Organized by The Francis Crick Institute

Location: The Francis Crick Institute


This training is developed and delivered by [Rocco D’Antuono](https://github.com/RoccoDAnt) (the Francis Crick Institute), [Giulia Paci](https://github.com/giuliapaci) (University College London) and [Marie Held](https://github.com/Marien-kaefer) (the University of Liverpool). Additional speakers include [Ana Stojiljkovic](https://github.com/StojiljkovicVetAna) (University of Bern), [Stefania Marcotti](https://github.com/stemarcotti) (The Francis Crick Institute), [Sara Salgueiro Torres](https://github.com/sara-st) (The Francis Crick Institute), [Cameron Shand](https://github.com/sea-shunned) (the Francis Crick Institute), [Alessandro Felder](https://github.com/folterj) (Sainsbury Wellcome Centre), and [Olatz Niembro Vivanco](https://www.researchgate.net/profile/Olatz-Niembro) (University of Manchester).

For more info, please contact: rocco.dantuono@crick.ac.uk

# Installation of the software
During the workshop we will extensively try and retry the software installation with conda environments, however to gain some practice and proceed smoothly to more interesting topics, please proceed with the following homework before the workshop

1. Install Anaconda Navigator
2. Install napari within conda prompt

Please make sure to have at least 10-15 GB free on the laptop you will bring with you for participating in the workshop. Please let us know well in advance if you cannot bring a laptop with you, we might be able to get a loan; however, this is not guaranteed and you might risk to not have a machine to follow along during the workshop.

### 1. Install Anaconda Navigator
This is a method that use the graphical user interface to download and install Anaconda Navigator.
Please visit https://docs.anaconda.com/ and click on the green button "Download Anaconda". You will be asked to provide an email address and will receive the link to the download page, where you will choose the version for your OS.

Before installing Anaconda Navigator, please identify a folder in your computer over which you have full permission of read and write file: we will create and update many times conda environments, this means that the software will install and remove files all the times. Please avoid folders which contain spaces or special characters in the path.

### 2. Install napari within conda prompt
The successful installation of Anaconda Navigator will make available an app called "Anaconda prompt". This is the terminal that we will use to create and work with conda environments.

a) Update conda, by typing the following line and pressing Enter.
```
conda update -n base -c conda-forge conda
```

b) create a new environment with a meaningful name: substitute with your choice the string "mymeaningfulname". E.g. "cbias-workshop-env". Please do not simplify with "napari-env", as half of the tutorial use that and you might risk to overwrite a previous environment which contain packages used in previous analyses.

```
conda create -n mymeaningfulname-env python=3.14
```

c) activate the new environment

```
conda activate mymeaningfulname-env
```
You should notice a change in the prompt, where the name base at the beginning of the prompt has been changed to "mymeaningfulname-env" in parentheses. This confirms that it is safe to install new packages, as you are not altering the base environment (safe choice is not to touch "base").

d) install napari

```
conda install -c conda-forge napari pyqt6
```

e) check that napari opens
At this point, if no error appears in the terminal as result of the operations above, you are ready to open napari executing
```
napari
```

> [!NOTE]
> If you encounter issues, it may help to install Napari via a different method instead. Within your conda environment you can install via pip with `pip install "napari[all]"` and see if that helps.

### Create a conda environment with a recipe
If a working environment cannot be created through the commands above, the following recipe can be used to create an environment with napari

a) Download the file [cbias2026-napari-env.yml](https://github.com/FrancisCrickInstitute/CBIAS_napari_workshop_2026/tree/main/envs/cbias2026-napari-env.yml) into a local folder

b) use the Anaconda prompt to navigate to the local folder and execute
```
conda env create -f cbias2026-napari-env.yml
```
This should create an environment with the same name of the .yml file unless otherwise specified.

c) check that napari opens
At this point, if no error appears in the terminal as a result of the operations above, you are ready to open napari executing
```
napari
```

# Day 1 - instructions and links
#### 10:00 – 10:10 - Welcome and introduction to the course
Access to the [https://imagesc.zulipchat.com/](https://imagesc.zulipchat.com/) channel for communications during the workshop. Log in with GitHub account, or register. Message any trainer to be added to [https://imagesc.zulipchat.com/#narrow/channel/655671-CBIAS-napari-workshop-2026](https://imagesc.zulipchat.com/#narrow/channel/655671-CBIAS-napari-workshop-2026)

#### 10:10 – 10:30 - Participants self-introduction
Fill in 1-slide introduction (link sent via email to participants).

#### 10:30 – 12:30 - Installation and napari GUI - Rocco D’Antuono and Sara Salgueiro Torres

Install napari with options 1 and 2 above or the provided recipe (.yml file).

#### 12:30 – 13:30 - Lunch 

#### 13:30 – 15:00 - napari plugin showcase:
* Basic 3D image segmentation with napari-zelda (Rocco D’Antuono)
Follow Option D in the [napari-zelda plugin repository](https://github.com/RoccoDAnt/napari-zelda/tree/main) or download this [cbias2026-napari-zelda.yml](https://github.com/FrancisCrickInstitute/CBIAS_napari_workshop_2026/tree/main/envs/cbias2026-napari-zelda.yml) file, use the Anaconda prompt to navigate to the local folder and execute
  ```
  conda env create -f cbias2026-napari-zelda.yml
  ```

Download slides: [Napari Zelda (3D segmentation and Parent-Child Relation in napari) - plugin presentation - Rocco D'Antuono](https://zenodo.org/records/8238682)

* Mitochondria segmentation in EM data with napari-empanada (Marie Held)

  Check for the most recent installation instructions on the [napai hub page for the empanada plugin](https://napari-hub.org/plugins/empanada-napari.html)

  Either execute the following conda instructions (note the python version must be >=3.12 and napari >= 0.9)

  ```
  conda create -n empanada-ws-env python=3.12
  conda activate empanada-ws-env
  conda install -c conda-forge napari pyqt6
  pip install empanada-napari
  ```

* Interactive pixel classification using pretrained neural networks with [napari-convpaint](https://github.com/guiwitz/napari-convpaint) (Ana Stojiljkovic)<br>
Once you have installed napari in your environment using Option 1 and 2 above, you can install the napari convpaint plugin from PYPI:
  ```
  pip install napari-convpaint
  ```

* Easy movie creation with [napari-animation](https://github.com/napari/napari-animation) (Ana Stojiljkovic)<br>
To easely create movies to document your image analysis results (.mp4, .gif, .mov, .mkv), add the napari-animation plugin to your napari environement. We recommend installing it from conda-forge, especially if you are using macOS. For detailed installation instructions, visit the [napari-animation repository](https://github.com/napari/napari-animation?tab=readme-ov-file#installation).
  ```
  conda install -c conda-forge napari-animation
  ```
  If you prefer please use the [cbias25-napari-convpaint.yml](https://github.com/FrancisCrickInstitute/CBIAS_napari_workshop_2025/blob/main/envs/cbias25-napari-convpaint.yml) file to   install a napari environment containing both plugins, napari-convpaint & napari-animation.<br>
  [Slides](https://docs.google.com/presentation/d/1klbcgt98qLBLfnAeWP9qvpMF1yXmSp5gIaLIE6yHtpo/edit?usp=sharing) for the napari-convpaint & napari-animation showcase.

#### 15:00 – 15:30 - Coffee break
#### 15:30 – 17:30 - First steps to customise napari GUI (hands-on session):
  * Introduction to Jupyter notebooks for bioimage analisis with python (Sara Salgueiro Torres) <br>

  You can find the slides for this session [here](https://docs.google.com/presentation/d/1kiXEtY1vHEyz1ZEFIZAisauelGEYfspe/edit?usp=sharing&ouid=114387269887423928889&rtpof=true&sd=true). <br>

  We will be using the environment created in the morning *Installation* session. To activate the environment:

  ```
  conda activate cbias-workshop-2026
  ```
  Then open *jupyter*:
  
  ```
  jupyter-lab
  ```  
  You will then be able to navigate to the [*intro_to_jupyter.ipynb* notebook](/notebooks/intro_to_jupyter.ipynb).

  * Delving into Napari layer types (Rocco D'Antuono)
  After a short navigation of napari layers type, trainees will make two exercise to fix existing code and get 3D segmentation, starting from this notebook: [*Delving_into_napari_layers-CBIAS_2026_napari_workshop_UnsolvedExercises*](/notebooks/Delving_into_napari_layers-CBIAS_2026_napari_workshop_UnsolvedExercises.ipynb).
  
    Solutions will be provided during the practical session.

  * Napari widgets and plugin creation with magicgui and plugin template (Cameron Shand)
  Instruction on the plugin creation demo: [https://github.com/FrancisCrickInstitute/cbias2026_napari_demo](https://github.com/FrancisCrickInstitute/cbias2026_napari_demo)

#### 17:30 – 18:00 - Brainstorming on trainees projects

#### 18:00 – 18:30 - End of Day 1

#### 18:30 - Drinks and nibbles reception (Crick canteen)

# Day 2 - instructions and links
#### 10:00 – 10:15 - Quick SOP for image.sc forum (Marie Held)
 Visit [https://forum.image.sc/]() and create an account.

#### 10:15 – 10:30 - "From napari to You and Back: How to Contribute" - Tim Monko (napari Community Manager)

#### 10:30 – 12:30 - Work on projects - Olatz Niembro-Vivanco and Alessandro Felder

#### 12:30 – 13:30 - Lunch

#### 13:30 – 14:00 - Check on project progress (all the trainers)

#### 14:00 – 15:00 - Work on projects - Stefania Marcotti and Rocco D'Antuono

#### 15:00 – 15:30 - Coffee break

#### 15:30 – 16:45 - Work on projects

#### 16:45 – 17:00 - Feedback questionnaire

#### 17:00 – 18:00 - Project presentations

#### 18:00 - End of Day 2
