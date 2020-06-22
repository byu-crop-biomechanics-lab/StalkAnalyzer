Stalk Analyzer 

To be analyzed, the pictures have to be RGB color images, and they can be in the formats 'TIF','TIFF','BMP'or 'GIF'. 
The tool is optimized to work on TIF images with 800 dpi.
To analyze the image by quadrants, they should be around 5000 pixels wide and 3850 pixels high.

If the image is to be analyzed as a whole and not per quadrant:
- The user has to comment out the lines 50 - 64 and the respective 'end' of the for loop in line 1684.
- Additionally, in line 47 'rgb0' has to be replaced with 'rgb'.

The software assumes that the scanning is performed as recommended in the paper and with the above specifications. Therefore, 1 centimeter is assumed to correspond to 316 pixels.
If the user prefers to have the results being presented in pixels, or if other units than centimeters ar to be used, the respectie lines to comment out / change are:
503, 583, 584, 585, 836, 1377, 1378, 1379, 1380, 1633.

The user gets asked by the software, whether s/he wants to accept the way the program would crop the image automatically, or if s/he wants to crop her/himself.
This is reason, why in the following for each operation two lines in the code are mentioned in which to find the operation being done.
 
NOTE: After the bundles are identified, the user gets asked whether s/he agrees with the choice of the program which spots are bundles and which ones are ot, or whether the user wants one more try . If the user decides to run the program again, this time the user HAS to crop her/himself. This is assumed, as the success rate will likely ncrease if dark spots or sharp edges (do to the cutting) or cracks in the stalk are not analyzed because they are not on the cropped image.
The respective lines are 510 - 544 and 1307 - 1341.

If the user wants to omit the detemination of the bundle size completely, s/he has to comment out the lines 607 - 871 and 1405 - 1668.
If the user wants to keep the determination of bundle size (e. g.  as a quality control), but does not want to save this information to disk, s/he has to omit the lines 852 and 1649.
To limit the number of bundles that are measured, the user has to replace the total number of found bundles (size( Z, 1)) in the lines 607 and 1405 with the respective number s/he wants to analyze and / or save.

The important variables for the anisotropic diffusion filtering are niter (lines 413 and 1209) , kappa (lines 414 and 1210) and lambda (lines 415 and 1211). Change this accordingly, if e. g. you have different lighting conditions or different qualities of cuts and want to adjust the rigidity or accuracy of the fit in order to find all the bundles.