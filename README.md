# Person Recognition arduinoUNOQ #

# this repo contains one hands on project for recognising the person #
1. the outline of this project is to detect the Person in our case it is me and draw a outbound square
2. requirements
   - Arduino UNO Q
   - Edge impulse account to train the model
   - Arduino app lab and VS code
3. create a account in edge impulse website free account
4. this impulse will be used to
   - collect an label audio data samples, extract features from video samples
   - split data and create edge impulses
   - train and evaluate model
   - build a simple app lab project
5. after that that created model can be run on Arduino UNO for real time interference
6. data collection
   - can be split into 2 types
   - self image capture: for this project you need to collect 40 images of yourself with the help of impulse.
     go to data acquisition and start collecting images. remember to name it as your_name(label) and set set as training
   - noise collection: for noise you can take random images .
     remember to name it as person and set set as training
   - also remember in your dashboard to set as outbound
7. after collecting you will have 40 images of yourself and 10 of others in my case.
8. now split the data as train and test in the impulse website itself
9. start drawing the bounding boxes for each image
10. go to impulse design -> create impulse set processing block as image and learning block as object detection also remember to keep the image size as 320 x 320 check output feature has 2 labels your_name and person. save impulse
11. new tabs will come below create impulse as image and Object detection 1st click on image and go down and click on save parameters, go to object detection and click select model and select mobile net v2, and change the no of training cycles to 40 for more accuracy and then click save and train.
12. after training completes you can see related graphs like ROC curve, confusion matrix and accuracy etc.
13. after training go for testing and test your model if it is above 90% also then the model will work mine came out as 98%
14. go below the tabs and select deployment and select Arduino UNO Q export the model.
15. to deploy you need to have both Arduino app lab + and vs code
16. in app lab + you will select a already present model and edit the detect objects as person_recognition and update the yaml file in vs code and then we can see a web interface which we have copiede from app lab +. to run this we need to be in sbc or network mode.
17. if you do not have the board to test your model you can also test your model in your browser also to know is it detecting the wake word or not

this project was a part of course I got free from QUALCOMM 
link: https://academy.qualcomm.com/course-catalog/AI-Upskilling-Certificate-Development-from-Model-to-App
this is a free course in this we have 3 projects in those this is one of the project

author
@tunder00
