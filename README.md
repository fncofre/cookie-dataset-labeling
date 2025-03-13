# Cookie Dataset Labeling

# Table of Contents
- [Environment Setup](#environment-setup)
- [Download Cookies Screenshots](#download-cookies-screenshots)
- [Label-studio usage](#label-studio-usage)
  - [Initiliaze Label Studio](#initiliaze-label-studio)
  - [Start labeling images](#start-labeling-images)
  - [Export the labeled images](#export-the-labeled-images)
  - [Labeling video example](#labeling-video-example)


## Environment Setup
```
💡 NOTES:
 - (MAC intended guide, can be easily adaped to another OS)
 - Open your "terminal" to insert all the commands below.
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

7.- Edit env variables to allow bigger images, and a larger number of images:
```
export DATA_UPLOAD_MAX_MEMORY_SIZE=524288000
export DATA_UPLOAD_MAX_NUMBER_FILES=5000
ulimit -n 50000
```

8.- Start Label Studio:
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

### Initiliaze Label Studio

- Now at your browser, after doing the step `Start Label Studio` you should see the Label studio webpage (if not, then just go to http://localhost:8080/). It will ask for an account, that can be created there (doesn't require any confirmation).
- After this you will be in the main page of Label Studio. (http://localhost:8080/projects/)
- Then you need to create a new project.
- Set as name `datalake-1` (change the number, depending of your datalake used). Description, can be ommited.
- Then at Data Import click `upload files`, and go to your images folder, and select all of them. (you can use `cmd + a` to select all).
- After all the images are loaded, click the upper right button `Save`.
- Now click the first image of the list and u will receive a pop up to set the labeling configuration, click `Go to setup`.
- There u will have a text editor to write code, at the moment just have `<View></View>` delete it, and put the following code:
```
<View>
  <Image name="image" value="$image" />
  
  <RectangleLabels name="label" toName="image">
    <Label value="Accept Button" background="#34c759" />
    <Label value="Cookie Popup" background="#ff9500" />
  </RectangleLabels>
</View>
```
- Finally click the `Save` button below, and then click your project name at top to return to the homepage.
- Now you're all set and ready to go, to start labeling images!

### Start labeling images
- To label images is really simple one is all set up, you just click the first image at the list, and u will get into the labeling menu:
<details>
<summary> Click to see labeling menu screenshot </summary>
 
 ![image](https://github.com/user-attachments/assets/f85097f3-4401-4664-9ee3-f4a087d673a8)

</details>

- Then you can zoom the image, or do whatever is necessary to be easier to select the areas to find in the image. At the following example using the button (`Accept Button` below or just key `1`, you will be able to select the Accept (Agree, Accept All, Acepto, ...) button of cookies)

<details>
<summary> Click to see the labeling of the Accept Button </summary>

 ![image](https://github.com/user-attachments/assets/855eb3a1-033d-44a2-8bda-812255e48755)

</details>

- Same process to select the popup of the cookies. (`Cookie Popup` or key `2`, this is all the modal that contains all related to the cookies)

<details>
<summary> Click to see the labeling of the Cookie Popup </summary>

![image](https://github.com/user-attachments/assets/2db8f238-ba3a-45f7-8e7e-d1f021bc1b35)

</details>

- (⚠️ **IMPORTANT**) **After making the needed labeling for the image, make sure at the right that the `Cookie Popup` element and the `Accept button`, are selecting the right element. (you can click them, to see that are selecting the right part of the image)**
- Finally, click `Submit`, then u can jump to the next image at the left.
- If the image doesn't contain any kind of cookie popup, or accept button related to the cookies, just click `Submit`

<details>
<summary> Click to see the Image example with out Cookies popup or accept related to cookies </summary>
 
![image](https://github.com/user-attachments/assets/d9512d34-cf0e-4048-848f-f4081fd07c88)

</details>

```
💡 NOTES:
 - An image can contain the cookie popup and the accept button, but there can be cases that just the cookie popup is visible, in those just select the one visible.
 - Is not needed that u need to perfectly select the box, but should make sense and wrap all the desired element closely enough.
 - If part of any of the elements is not fully visible, just select the part that u know is from the element and is visible.
 - There can be a maximum of only 1 for each of the labels per image.
 - 😊 Any question just ask!
```

### Export the labeled images
- When you finish labeling all the images, go to the project menu (click your project name).
- Click the `Export` button, and select `YOLO with Images` and click `Export` again.

<details>
<summary> Click to see the Export example of the labeled images </summary>
 
![image](https://github.com/user-attachments/assets/16e05acc-326f-4234-aaaf-dd1a4f37f34b)

</details>

- This will download a `.zip` file, save it and wait for the instructions to send it.

### Labeling video example

https://github.com/user-attachments/assets/6143bcd3-ded5-490b-8bd3-4beb394bbb15

