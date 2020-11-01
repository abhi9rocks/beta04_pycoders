# Anti Cheating Software Using AI

Project to create an automated monitoring system where the user can be monitored automatically through the webcam and microphone. The project is divided into two parts: vision and audio based functionalities. 


## Vision Feature

It has six vision based functionalities right now:
1. Find if the candidate opens his mouth by recording the distance between lips at starting.
2. Track eyeballs and report if candidate is looking left, right or up. 
3. Instance segmentation to count number of people and report if no one or more than one person detected.
4. Find and report any instances of mobile phones.
5. Head position estimation to find where the person is looking.
6. Face spoofing detection

### Face detection

It is implemented in `face detector.py` and is used for tracking eyes, mouth opening detection, head pose estimation, and face spoofing.

An additional quantized model is also added for face detector.
It is implemented in `face landmarks.py` and is used for tracking eyes, mouth opening detection, and head pose estimation.

### Eye tracking
`eye detector.py` is to track eyes. 
![Screenshot (742)](https://user-images.githubusercontent.com/48823353/97790593-d1726180-1bef-11eb-81fe-bf38aabb2386.png)



### Mouth Opening Detection
`mouth detector.py` is used to check if the candidate opens his mouth during the exam after recording it initially. 
![Screenshot (749)](https://user-images.githubusercontent.com/48823353/97790635-18f8ed80-1bf0-11eb-8c47-7e29abeb20ff.png)
![Screenshot (750)](https://user-images.githubusercontent.com/48823353/97790645-2ca45400-1bf0-11eb-9529-f30baf92d1e3.png)


### Person counting and mobile phone detection
`face on phone.py` is for counting persons and detecting mobile phones. YOLOv3 is used in Tensorflow 2 
![person counting and phone detection]()

### Head position estimation
`head pose detect.py` is used for finding where the head is facing.


### Face spoofing
`fake face detection.py` is used for finding whether the face is real or a photograph or image.
![Screenshot (758)](https://user-images.githubusercontent.com/48823353/97790611-f1098a00-1bef-11eb-9d3a-2f90fd22ed5a.png)

### FPS obtained

Functionality | On Intel i5
--- | ---
Eye Tracking | 7.1
Mouth Detection | 7.2
Person and Phone Detection | 1.3
Head Pose Estimation | 8.5
Face Spoofing | 6.9


## Audio
It is divided into two parts:
1. Audio from the microphone is recording and converted to text using Google's speech recognition API. A different thread is used to call the API such that the recording portion is not disturbed a lot, which processes the last one, appends its data to a text file and deletes it.
2. NLTK we remove the stopwods from that file. The question paper (in txt format) is taken whose stopwords are also removed and their contents are compared. Finally, the common words along with its number are presented to the proctor.


### Problems
1. Collection of dataset and the training was the major challange that we faced in such short period of time
2. Speech to text conversion which might not work well for all languages.

