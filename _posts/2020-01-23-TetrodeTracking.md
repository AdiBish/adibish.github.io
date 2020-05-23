# *PAGE UNDER CONSTRUCTION*
## Using ImageJ(Fiji) to track tetrodes post histology

The [TrakEM2](https://imagej.net/TrakEM2) plugin in [ImageJ](https://imagej.nih.gov/ij/) allows stacking individual images and aligning them manually. [Fiji](https://fiji.sc/) includes all the necessary plugins for TrakEM2. 
There are java based algorithms which require you to mark segments to be used as reference points for automatic image alignment but i have never tried them. I prefer manual alignment over automatic as it gives me more confidence over tracks belonging to tetrodes rather than to drained blood capillaries or damages to the brain section while loading. 

For manual alignment of images, this [link](https://www.youtube.com/watch?v=-p0Jg0QKF24) can be used as a quick tutorial.



### **Some known issues and my work arounds**: 
- stacked images do not get loaded in the correct order:
add the digit 0 to the image filename as suffix and then let the image name be section number ( or any other order you want). This is more time consuming but works. 
- unable to draw more than 1 lines / curves: 
i used annotation using draw multi-points features to mark the tetrode tracks wherever i could see them. But these annotations remain 

