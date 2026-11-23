# Computer Vision Project Proposal
## Dylan Ryan and Wanning Rong

### Project Title
Gesture-based Media Controller
### Provide a short description of the project.
We will use a stationary phone camera to record hand gestures—swipe left/right, push, up and down—against a solid background. Our program will analyze the motion and communicate with an app interface (Spotify or PowerPoint) to control the program. We will test whether it can correctly identify movements and avoid false detections.
### Where will you get the data?
We will record 25 videos of movement against a blank background, 5 videos for each movement type. We will use these 3 clip per scenario for development and the remaining 2 clips for testing, along with manually labelling each type of movement. A final video will then be recorded combining all motions, and the accuracy of the application will be tested against this video.
### What will each team member code/develop?
Dylan Ryan will record the 25 data videos for training. Dylan will clean the data using segmentation (simple differencing). Dylan will then use this cleaned data to calculate the MHI of each movement. As it will be unclear when a movement starts and stops, Dylan will use temporal segmentation to build the MHI for different durations and only keep the best. After recognition has been completed, Dylan will add MHI and image type labeling to overlay on top of the video, which will help with error tracing and analysis.

Wanning Rong will record the final testing video. After the MHI algorithm is complete, Wanning will use compute the similitude moments. This will create a feature vector for each movement. Each gestures data will be stacked and the mean and covariance will be calculated from the similitude movements. Mahalanobis distance can then be used to classify each gesture. Wanning will build each gesture matrix along with mean and covariance.
### How will each team member evaluate the work/results?
Dylan Ryan will evaluate the segmentation quality by comparing the original image to the differenced. If there is extra time, he will also test hard conditions like a patterned shirt or lighting changes. Wanning Rong will test the detection rate of the algorithm, and the number of false detections. The detection threshold and kernel size can be used to maximize accuracy. Both overall and per gesture accuracy will be calculated, along with where the model gets confused. In the case of live detection, the overall latency of the program will be evaluated.
### Outside-course techniques
Possibly integration with Spotify or PowerPoint APIs to use detection algorithm in real time (stretch goal)
