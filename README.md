# image-processing-techniques
Course Assignment

# Basic Algorithms
## Drone Positioning
1. Read the image and resize it to appropriate size (here, 600 x 600).
2. Get the vertices of the object (here, flag) in the original image using the 'vertices' function.
3. The function converts the image into gray-scale, starts finding the contours and returns the vertices with the largest possible quadrilateral area.
4. Then we arrange the vertices to the 4 corners of the flag and crop the image accordingly to remove any extra spaces from around it.
5. We then again get the vertices of the flag in this cropped image.
6. The top_left, top_right, bottom_left and bottom_right corners are selected based on the linear distance of the four vertices of the quadrilateral found.
7. Based on these, the correct orientation of the flag is found using the colours of the flag.
8. We can then generate a flag with the correct orientation based on this information.

## Audio Classification
1. The audio path is given as an input to the function.
2. The wave_form and samp_rate is found out using the librosa library.
3. I then used the mel-spectrogram technique to get the power of the audio.
4. This is then converted to decibles.
5. The spectrogram image is saved and then read to generate the edges in the image.
6. Based on a threshold, it is decided if the audio is 'metal' or 'cardboard'.

## Text Alignment
1. The image path is given as an input to the function.
2. The image is then converted to gray-scale and I applied gaussian blur to it so that only the most intense edges are detected.
3. The Canny technique is used to detect the edges in the image and then HoughLines algorithm is applied to get straight lines in the image from the detected edges.
4. Based on these straight lines and the angle they make with the horizontal (0 degrees), the alignment of the text is known and then the text is rotated in the opposite direction by the same angle to straighten it.
5. If the angle (say, theta) is negative (clockwise), then it is rotated in the opposite direction and by an angle of (360+theta).
