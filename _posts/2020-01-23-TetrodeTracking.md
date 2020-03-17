## Using ImageJ(Fiji) to track tetrodes post histology
Purpose: 
In electrophysiology experiments, it is essential to know where your electrodes are
Procedure: 


Tools and how to use:
The TrackEM plugin in ImageJ allows stacking individual images and aligning them manually. 
There are java based algorithms which require you to mark segments to be used as reference points for automatic image alignment but i have never tried them. I prefer manual alignment over automatic as it gives me more confidence over tracks belonging to tetrodes rather than to blood capillaries or damages to the brain section while loading (?). 

For manual alignment of images, this link can be used as a quick tutorial.

once all the sections have been aligned, make sure your zoom is suitable for you to be able to look at all tracks by scrolling through them back and forth. 

Which tetrode is this?
It is not a good idea to 








Some known issues and my work arounds: 
- stacked images do not get loaded in the correct order:
add the digit 0 to the image filename as suffix and then let the image name be section number ( or any other order you want). This is more time consuming but works. 
- unable to draw more than 1 lines / curves: 
i used annotation using draw multi-points features to mark the tetrode tracks wherever i could see them. But these annotations remain 

