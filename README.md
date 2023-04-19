# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1:

Import the necessary libraries and read the original image and save it as a image variable.

Step2:

Translate the image using M=np.float32([[1,0,20],[0,1,50],[0,0,1]]) translated_img=cv2.warpPerspective(input_img,M,(cols,rows))
###Step3:

Scale the image using M=np.float32([[1.5,0,0],[0,2,0],[0,0,1]]) scaled_img=cv2.warpPerspective(input_img,M,(cols,rows))
###Step4:

Shear the image using M_x=np.float32([[1,0.2,0],[0,1,0],[0,0,1]]) sheared_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))
###Step5:

Reflection of image can be achieved through the code M_x=np.float32([[1,0,0],[0,-1,rows],[0,0,1]]) reflected_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))
###step6:

Rotate the image using angle=np.radians(45) M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]]) rotated_img=cv2.warpPerspective(input_img,M,(cols,rows))
###Step7:

Crop the image using cropped_img=input_img[20:150,60:230]
###Step8:

Display all the Transformed images and end the program.
## Program:
```python
Developed By:YASHASWI MITTA
Register Number:212221230062
i)Image Translation
import matplotlib.pyplot as plt
inputImage=cv2.imread("jen.jpg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
M= np.float32([[1, 0, 100],
                [0, 1, 200],
                 [0, 0, 1]])
translatedImage =cv2.warpPerspective (inputImage, M, (cols, rows))
plt.imshow(translatedImage)
plt.show()


ii) Image Scaling
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("jenifer.jpg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
M = np. float32 ([[1.5, 0 ,0],
                 [0, 1.8, 0],
                  [0, 0, 1]])
scaledImage=cv2.warpPerspective(inputImage, M, (cols * 2, rows * 2))
plt.imshow(scaledImage)
plt.show()




iii)Image shearing
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("jen2.jpg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
matrixX = np.float32([[1, 0.5, 0],
                      [0, 1 ,0],
                      [0, 0, 1]])

matrixY = np.float32([[1, 0, 0],
                      [0.5, 1, 0],
                      [0, 0, 1]])
shearedXaxis = cv2.warpPerspective (inputImage, matrixX, (int(cols * 1.5), int (rows * 1.5)))
shearedYaxis = cv2.warpPerspective (inputImage, matrixY, (int (cols * 1.5), int (rows * 1.5)))
plt.imshow(shearedXaxis)
plt.show()
plt.imshow(shearedYaxis)
plt.show()


iv)Image Reflection
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("jen3.jpg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
matrixx=np.float32([[1, 0, 0],
                    [0,-1,rows],
                    [0,0,1]])
matrixy=np.float32([[-1, 0, cols],
                    [0,1,0],
                    [0,0,1]])
reflectedX=cv2.warpPerspective(inputImage, matrixx, (cols, rows))
reflectedY=cv2.warpPerspective(inputImage, matrixy, (cols, rows))
plt.imshow(reflectedY)
plt.show()




v)Image Rotation
angle=np.radians(45)
inputImage=cv2.imread("rachel.jpg")
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotatedImage = cv2.warpPerspective(inputImage,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotatedImage)
plt.show()



vi)Image Cropping
angle=np.radians(45)
inputImage=cv2.imread("friends.jpg")
CroppedImage= inputImage[80:600, 80:430]
plt.axis('off')
plt.imshow(CroppedImage)
plt.show()




```
## Output:
### i)Image Translation
![dip 5-1](https://user-images.githubusercontent.com/94619247/232986816-b5d54bd7-51aa-4571-a10b-0675a5d6fd8c.jpg)


### ii) Image Scaling
![dip 5-2](https://user-images.githubusercontent.com/94619247/232986847-444d2001-6f74-4595-b3d6-4a88d27e6656.jpg)



### iii)Image shearing
![dip 5-3](https://user-images.githubusercontent.com/94619247/232986888-d3dbbfa0-714c-4000-b9e3-89125168f14d.jpg)
![dip 5-4](https://user-images.githubusercontent.com/94619247/232987031-4d9e50fe-e254-4e21-92cd-ce823339db23.jpg)

![dip 5-5](https://user-images.githubusercontent.com/94619247/232987024-4218f444-e893-435b-a7ab-963a2e756855.jpg)



### iv)Image Reflection
![dip 5-6](https://user-images.githubusercontent.com/94619247/232987158-79fb1a5a-d0b6-4598-aa91-d1e074c470cb.jpg)




### v)Image Rotation
![dip 5-7](https://user-images.githubusercontent.com/94619247/232987204-fb398f94-718c-4719-a4bb-dca268eabd09.jpg)




### vi)Image Cropping
![dip p5-8](https://user-images.githubusercontent.com/94619247/232987237-58ea6259-b3d1-412d-8843-f40b4b89ea9e.jpg)





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
