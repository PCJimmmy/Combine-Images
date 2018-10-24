# Combine-Images
Protein challenge - I want to combine the 3 colors based on the value of the green color
import math
import numpy as np

import bpy

def np_array_from_image(img_name):
    img = bpy.data.images[img_name]
    return np.array(img.pixels[:])

pixelsA = np_array_from_image('A')
pixelsB = np_array_from_image('B')
pixelsC = np_array_from_image('C')
pixelsD = (pixelsA + pixelsB + pixelsC) / 3

image_D = bpy.data.images['D']
image_D.pixels = pixelsD.tolist()

# then click in the UV editor / to update the view..to see the pixels of `D` updated
Maybe this will give enough insight, and push towards learning some numpy.

This does 'mix' btw..

enter image description here
