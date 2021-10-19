# dance_generator
The aim of current project is to generate general movements of human body

Libraries used: 
    -openCV
    -Mediapipe
    -Numpy
    -OS
    -Pandas
    -matplotlib
    -imageio

Technologies used: 
    - Feature extraction from pose detection using opensource library mediapipe.
    - Future generation with deeplearning time series multivariate using: 
        -LSTM long short term memory.
        -Autoregression.
    -plotting, and animation using matplotlib and mediapipe libraries.

Main idea: 

    1-Gathering data using mp4 videos of a solo dance style (about 8 hours of dances).
    2-Extraction of data from these videos in form of coordinates (x,y,z) for every movement joint (33 joints) in each frame of the video. (24 frames per second).
    3-compilation of tabular normalized numerical data of all the videos in one csv file.
    4-Processing the data into a time series model where we took 144 (6 seconds) frames of past and predicted 24 frames of future (1 seconds), in a loop till we get the required amount of generated time in future. 
    5-For feature reduction we divided our model into smaller groups of areas moving independantly to get a better prediction and reduce dampening of the results.


How to use: 

    1-You need to download your videos (it has to be only movement videos with a human pose) and save in 'videos' folder in your directory.
    
    2-Run a python file called 'run.py' where you can also change your parameters and variables to your likings:
    
        # Folders : these are the names of the folders that are used for the file, and type of model you want to use for your generation.
        
        # run parts : these are the parts that you want to control which one to run, either it is to produce coordinates from videos or produce images of the coordinates, etc..
        
        # Model config: This are to control the hyper parameters of your model, like future and past windows, etc..
