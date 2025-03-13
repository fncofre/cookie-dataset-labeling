# Cookie Dataset Labeling

# Table of Contents
- [Environment Setup](#environment-setup)
- [Download Cookies Screenshots](#download-cookies-screenshots)
- [Label-studio usage](#label-studio-usage)

## Environment Setup
```
💡 NOTES:
 - (MAC intended guide, can be easily adaped to another OS)
```

1.- Install Homebrew (a package manager for macOS):
This command installs Homebrew, which allows you to easily manage software on macOS.
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2.- Install Python 3.12 using Homebrew:
```
brew install python@3.12
```

3.- Get into your user directory:
```
cd ~
```

4.- Create a Virtual Python Environment:
This creates a new virtual environment called `3.12v`. A virtual environment helps you isolate project dependencies, so they don’t conflict with other projects.
```
python3 -m venv 3.12v
```

5.- Activate the Virtual Environment:
This command activates the virtual environment you just created. Once activated, any Python packages you install will be contained within this environment.
```
source 3.12v/bin/activate
```

6.- Install Label Studio in the Virtual Environment:
This installs Label Studio, a tool for labeling data (used to label cookies screenshots of different webpage visits), within the virtual environment.
```
pip install label-studio
```

7.- Verify the Installation:
```
label-studio --version
```

8.- Edit env variables to allow bigger images, and a larger number of images:
```
export DATA_UPLOAD_MAX_MEMORY_SIZE=524288000
export DATA_UPLOAD_MAX_NUMBER_FILES=5000
```

9.- Start Label Studio:
```
label-studio start
```

## Download Cookies Screenshots
The data lake of images w/ and w/o cookies, are divided in 5 different zips: (pw hint: project name, source of the images)

- [Datalake 1 - 0000-1917](https://drive.google.com/file/d/1-SmvTcPOPWJn-4P5eVEQgk2gfRZaNU1S/view?usp=drive_link)

- [Datalake 2 - 1918-3836](https://drive.google.com/file/d/1cd1H7AWRIJjhvC1vm9aRkNmQiaf__5fJ/view?usp=drive_link)

- [Datalake 3 - 3837-5755](https://drive.google.com/file/d/1jOHC81vIcPTAuhLJIopVBfMjSC8NHr-M/view?usp=drive_link)

- [Datalake 4 - 5756-7674](https://drive.google.com/file/d/10EWIsN16BHswO7P5qs7PdwxHWnYOglYz/view?usp=drive_link)

- [Datalake 5 - 7675-9935](https://drive.google.com/file/d/1ZDOym79G6voT0af1ATiXgK0EnhnExvZN/view?usp=drive_link)

...

## Label-studio usage

...

