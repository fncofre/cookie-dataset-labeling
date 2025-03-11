# Cookie Dataset Labeling

## Environment Setup
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

8.- Start Label Studio:
```
label-studio start
```
