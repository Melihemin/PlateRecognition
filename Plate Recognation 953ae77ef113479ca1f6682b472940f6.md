# Plate Recognation

We integrate the necessary libraries into our code

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image.png)

**OpenCV** : In addition to reading and viewing frames, it also provides functions for basic video manipulation such as resizing, rotating and flipping frames. These functions can be used to pre-process frames before performing further processing or analysis.

**Random** : If you need to generate random numbers in a certain range, you can use a module called random in Python's standard library.

**OS** : Thanks to the Python OS module, you can perform operations on directories and files in the operating system from within the program you have written. You can use the system's command line from within the program as it is used by the system user.

**Numpy : It is a library for the Python programming language that supports large, multi-dimensional arrays and matrices, and adds high-level mathematical functions to work on these arrays.**

**Matplotlib : When you think of plotting and Numpy, the first library that comes to mind is Matplotlib. Matplotlib is a 2D plotting library for producing quality histograms, power spectra, bar graphs, error charts, etc.**

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%201.png)

We did a version check to make sure the OPENCV library is installed

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%202.png)

We applied black and white filtering to make the image more distinct and more suitable for training our model.

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%203.png)

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%204.png)

We created and tested a function that allows us to compare images to better understand the difference between two images.

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%205.png)

Bilateral Filter, The bilateral filter is a non-linear, edge-preserving and noise-reducing smoothing filter for images. It replaces the intensity of each pixel with weighted average intensity values from nearby pixels.

Using this method we made our car more prominent in the photo.

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%206.png)

Canny, the edge information of the image is accessed. is found. it is possible to expand/enlarge an image. a struct element of the form is used by default.

We used the canny method to read the license plate more clearly.

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%207.png)

Contours can be simply explained as a curve that connects all continuous points of the same color and intensity along the boundary. Contours are a very useful tool for shape analysis, object detection and recognition.
For more accurate results, a binary (black and white) image should be used when finding contours.
The image whose contours are found with the FindContours method is completely changed and the original image cannot be used again. For this you need to back up the image in the software.
Finding contours in OpenCV is like finding a white object on a black background.

In the cv2.findContours() operation, contours were found. When we look at this operation in the code, it is seen that there are 3 arguments;

```
 1.The first argument is the source image to find contours.
 2.The second argument is the contouring mode.
 3.The third argument is the contour approach method.

The result of this process reveals the contour and hierarchy of the image.

```

The information assigned to the “contours” variable in the code is actually a python list of the contours in the image. Each contour is a Numpy array of the coordinates (x,y) of the boundary points of the object.

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%208.png)

 The contours are drawn with the cv2.drawContours() function, where the first argument is the source image, the second argument is the python list of contours in the image, the third argument is the index of the contours, the fourth argument is the color of the drawing and the fifth argument is the thickness of the drawing.

With these methods, we have determined the boundaries of our plate and we will make it suitable for model training by cutting the image.

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%209.png)

The approximate ( **approxPolyDP** ) method we use will help us to draw clear edge lines around the shapes. a well-rendered image, whether imperfect or perfect, can produce beautiful results.

We cut our plate with the help of functions that give us certain coordinates to cut it properly.

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%2010.png)

**Tesseract** is a free optical character recognition (OCR) engine developed for various operating systems (Wikipedia).

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%2011.png)

![image.png](Plate%20Recognation%20953ae77ef113479ca1f6682b472940f6/image%2012.png)

Then, with the help of tesseract, we made it read our license plate in English and wrote our result on the screen.

If you like my project, don't forget to rate it.

Thanks.

-Melih Emin Kılıçoğlu