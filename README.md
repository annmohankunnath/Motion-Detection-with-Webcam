Motion is detected with the webcam and timestamps recorded into a csv file. This is implemented with Open CV in Python. A brief description of the process followed is below. The code in Jupyter Notebook contains headings and comments throughout.

The video is captured from the primary camera of the device and processed frame by frame. Each frame is converted to gray scale and then made blurry to reduce the noise and improve the accuracy. Then the absolute difference between each of the 2 consecutive frames is calculated. A threshold is applied to consider the differences less than 30 to be WHITE and otherwise to be black. After applying the threshold, the frames are dilated to increase the object area. Then, the contours are found from the final frames.

The contours are iterated through and for each contour that is bigger than 1000px, a bounding rectangle is drawn around the object.
All the 4 windows( Gray frames, Absolute Difference Frames, Absolute Difference Frames with Threshold Applied, Original Color Frames) are displayed . These windows remain till the time a key is pressed and close when the key pressed is 'q'.

The timestamps are written into a dataframe and the dataframe is written into a csv file called "Times.csv"

Finally, the device camera is stopped from capturing any more video and all the windows are closed and associated memory deallocated
