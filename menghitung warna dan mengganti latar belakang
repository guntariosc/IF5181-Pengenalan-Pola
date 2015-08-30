from scipy import misc
from collections import Counter
from PIL import *
import numpy as np

#load original image, convert it to numpy array
imgasli = misc.imread('c:/Users/User/Pictures/test2.jpg')
#load same image in separate var
img = misc.imread('c:/Users/User/Pictures/test2.jpg')
#reshape to 2-D
img = img.reshape(-1, img.shape[-1])
#convert numpy array to list
rgb = img.tolist()

def getBackground(rgb):

    counted = [] #stores unique colors
    counting_rgb = [] #stores color occurence

    #count unique colors and the occurence of each color
    #obtain color with the most occurence
    for n in range (0, len(rgb)):
        #check if the color already belong to the list
        if rgb[n] not in counted:
            #if not, add it to the list
            counted.append(rgb[n])
            counting_rgb.append(rgb.count(rgb[n]))

    #change the most occuring color with another color
    for n in range(0, len(rgb)):
        #if the color is the most occuring
        if rgb[n] == counted[counting_rgb.index(max(counting_rgb))]:
            rgb[n] = [255, 255, 0]

    print "Jumlah warna pada gambar: " + str(len(counted))
    return rgb

def showBackground(rgb):
    #convert list to numpy array
    imgbaru = np.asarray(rgb)
    #reshape to its original shape, get dimension from imgasli
    imgbaru = imgbaru.reshape(imgasli.shape[0], imgasli.shape[1], imgasli.shape[-1])
    #convert array to image
    im = Image.fromarray(np.uint8(imgbaru))
    #save image
    imgbaru = im.save('c:/Users/User/Pictures/test3.jpg')
    #open image
    im = Image.open('c:/Users/User/Pictures/test3.jpg')
    im.show()


if __name__ == "__main__":
    img = getBackground(rgb)
    showBackground(rgb)
