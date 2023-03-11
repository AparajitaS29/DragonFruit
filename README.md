# DragonFruit
The DragonFruit Ai challenge

README:

There are multiple ways to view and solve the given Dragonfruit assessment problem.
I believe that it all turns towards the fact of how we computer aficionados view an image.

My interpretation of an image:
For many people, an image is a pixel or RGB value, as for me, especially for this problem, I'm viewing it as a binary array full of zeros and ones.
One (1) represents the presence of an image.

The logic behind the code:
Before I answer the questions I want to be clear about my interpretations and assumption from which I built my logic.

Assuming that the 3D image given in the future can be made flat and turned into 0s and 1s using opencv, python, or any other supporting image tool. (Which is possible).
I'm rescaling the image to 1000* 1000 and it will just compromise resolution while making sure the space is optimized because of the rescaling.
The first numpy array represents the microscope image that has 0 for outside of a micro-organisms body and 1 where it is present. In the future, we can use image processing techniques to achieve this, for now, I'm just assuming a BitSet called "organism" which is a 25% zoomed body of a micro-organism.

Question 1:
An efficient way to store dye and organism image.
Microscope image:
The image is created in the shape of a polygon blob where I define the number of vertices at random and then defined a radius for it. The worst-case scenario might lead to alternating pixels leading to a 20GB+ storage space. But my image is a binary image with only values as mentioned above, which efficiently reduces the size of the storage required as we need to focus only on the part of the blog (around 2 GB).

From the program perspective, I have used numpy arrays for visualization. There are many efficient storages such as BitSet for Java coding or Bitvector for C++. The dictionary can be used with key-value pairs for further optimization.

Dye Sensor:
The above polygon represents a parasite for the dye sensor we randomly inject dye ( as a numeric value to this array) along with some leak.
Here Dye is represented with the number 2.
For clear understanding :
3 represents the parasite pixel with dye in it.
1 represent the parasite pixel.
2 represent the dye pixel.
The storage situation is the same as above as it is initially just a binary array and later I gave the values to show them separately for a good visual.
 
Note:
I chose python to show the image visually though I prefer java for more practical and faster implementation.

2 Fake Simulation of Parasite and Dye image

Parasite Image:
To make the image look as realistic as possible I have used a black-and-white color gradient to achieve it.

Initially, I drew a polygon blob which represents a parasite image indicated by a black and white binary image. The blob is black since it is a parasite and has a value of 1.

The radius was defined proportionally to the image size considered with the center of the polygon being in the center of the binary array.

The minimum number of 1 representing the parasite must be at least 25% of the canvas as it is required.

Dye Image:

Now we select the parasite image that we want to induce with a dye and create a separate dye image.

The Dye image is represented using a 2 along with some leaks so that we can cover that scenario.

Overlapping:
The area of dye in the insect is calculated after running an overlapping code.
Now the dye inside the parasite is represented using 3 and the dye outside the parasite, which is a leak is represented by 2.

3 Cancer Detection.
Now we get the ratio of Dye inside the parasite and the space covered by the parasite itself and check if it is 10% or not to declare the cancer status.
This is handled by the function that is used to detect cancer in the parasite and recreates the image as shown.

4 Optimization
There are various ways to optimize this function further.
To detect and maintain data we do not need to create an image but rather just use the number calculation which reduces the time a lot.

The best way is to use 2 BitSet to represent the 1 in the parasite and the dye using java which essential can be applied to a real-life image of 100000*100000 image and can represent it very elegantly as just 0s and 1s thus storing the data required with the image(encoded as 0 and 1).

The current program takes 0.01 to 0.1 sec, the optimization takes less than 0.005 secs to run.

My optimization here:
I used logical and instead bitwise to make it extremely faster as it is a numpy array.


















