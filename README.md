# College-Projects
Collection of college projects 
Problem Statement

   Sam has been given a project to renovate a building and he needs a program
   which will help him to identify the color code from a sample picture which he took.

About the Python Project
In this color detection Python project, we are going to build an application through which you can automatically get the name of the color by clicking on them. So, for this we will have a data file that contains the color name and its values. Then we will calculate the distance from each color and find the shortest one.


The Dataset
Colors are made up of three primary colors: red, green, and blue. In computers, we define each color value within a range of 0 to 255. So, in how many ways we can define a color? The answer is 256*256*256 = 16,581,375. There are approximately 16.5 million different ways to  represent  a  color.  In  our  dataset,  we  need  to  map  each  color’s  values  with  their corresponding names. But don’t worry, we don’t need to map all the values. We will be using a dataset that contains RGB values with their corresponding names. The colors.csv file used in the program includes 865 color names along with their RGB and hex values.


Prerequisites
OpenCV, Pandas, and numpy are the Python packages that are necessary for this project in Python. To install them, simply run this pip command in your terminal window type,
pip install opencv-python numpy pandas

The project folder contains below three files:

1.	Color_detection.py – main source code of our project.
2.	Colorpic.jpg – sample image for experimenting.
3.	Colors.csv – a file that contains our dataset.

Code Explained

1.	TAKING AN IMAGE FROM THE USER
We are using argparse library to create an argument parser. We can directly give an image path from the command prompt

2.	NEXT, WE READ THE CSV FILE WITH PANDAS
The pandas library is used to perform various operations on data files like CSV. pd.read_csv() reads the CSV file and loads it into the pandas DataFrame. We have assigned each column with a name for easy accessing.

3.	SET A MOUSE CALLBACK EVENT ON A WINDOW
First, we created a window in which the input image will display. Then, we set a callback function which will be called when a mouse event happens. The draw_function() is called whenever a mouse event occurs.

4.	CREATE THE DRAW_FUNCTION
It will calculate the rgb values of the pixel which we double click. The function parameters have the event name, (x,y) coordinates of the mouse position, etc. In the function, we check if the event is double-clicked then we calculate and set the r,g,b values along with x,y positions of the mouse.

5.	CALCULATE DISTANCE TO GET COLOR NAME
We have the r,g and b values. Now, we need another function which will return us the color name from RGB values. To get the color name, we calculate a distance(d) which tells us how close we are to color and choose the one having minimum distance.

Distance is calculated by formula:

   d = abs(Red – ithRedColor) + (Green – ithGreenColor) + (Blue – ithBlueColor)

6.	DISPLAY IMAGE ON THE WINDOW
Whenever a double click event occurs, it will update the color name and RGB values on the window. Using the cv2.imshow() function, we draw the image on the window. When the user double clicks the window, we draw a rectangle and get the color name to draw text on the window using cv2.rectangle and cv2.putText() functions.

7.	RUN PYTHON FILE
Run the Python file from the command prompt or terminal window. Make sure to give an image path using ‘-i’ argument. If the image is in another directory, then you need to give full path of the image:
