# 2025_Shivanandan
Python scripts for finding CenpA foci and quantifying intensities of CenpA and associated kinetochore proteins.

QuantifyCenpA.ipynb:  For automatically finding and quantifying all CenpA foci in a chromosome spread.  Finds foci in 3D, then subtracts background and smooths, before quantifying and plotting.

QuantifyKinetochoreProteins.ipynb:  For finding the two CenpA foci associated with each FISH labeled chromosome and quantifying kinetochore signal in the area. The dim and bright FISH signals are detected using otsu thresholding:  keeping only the two brightest objects.  CenpA foci are found as above, then pairs of foci are found based on closest distances.  The two pairs that are closest to the bright and dim are kept, and a line drawn between the foci, expanded, and used for quantification of the kinetochore protein signal and the cenpA signal.  This is done for a batch of images and the results plotted in interactive plotly/napari.

QuantifyAnnotatedLines.ipynb:  Takes images and ImageJ roi files, thresholds based on otsu, and aggregates signal for objects near the drawn line.  In the case of two lines being drawn in close proximity:  watershedding is used to divy up pixels that are near both.
