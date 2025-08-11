# Read-RTSTRUCT-to-matlab_MIM

Read rtstruct set from MIM into matlab as binary mask to apply for post-processing of MRI scans. 
Will generate the mat file that has binary masks, and will create the 3D volume of MRI scans. 
Updated to include the following functions, and be runable with one line of code within a function

Mira Liu August 2025 



To read the RTSTRUCT into matlab, collect your images and RTstruct in a study subject folder (e.g. StudyA_Subject1). 
Put the single RTSTRUCT file and dicom image files in the same subfolder (e.g. StudyA_Subject1/FolderA), then put only the dicom image files in a folder named Dicoms in that same study subject folder (e.g. StudyA_Subject11/Dicoms)


% Specify the targetpath of the study folder

directory='users/desktop/Exports'
Study_folder = 'StudyA_Subject1';
Sub_folder = 'FolderA';
ROI_wanted = 'Contour_of_interest';

% now run the function

You should see the .mat file saved in the same folder. It could take a few minutes to get the output depending on the number of CT slices and structures.

[images, mask, contours] = ImportRTstruct(targetpath,Study_folder,Sub_folder, ROI_wanted);

Should output a [x,y,slice] image stack with corresponding [x,y,slice] binary mask from the contours as well as the contours themselves from RT-struct. 

imagestack is called, which should show a MATLAB APP designed by Mira to be able to view slices volumetrically. 



Forked from https://github.com/viswanath-lab/Read-RTSTRUCT-to-matlab 
https://www.mathworks.com/matlabcentral/answers/120098-how-to-read-dicom-rt-structure




