# Tsunami-Alert-System
Tsunami Alert System based on Satellite imagery - Smart India Hackathon 2019 winning project

### Ashwamedha team banner:<br/>
![alt text](https://github.com/sidvsukhi/Tsunami-Alert-System/blob/master/pictures/team_Ashwamedha.JPEG "ASHWAMEDHA TEAM BANNER")

### Winning Team:<br/>
![alt text](https://github.com/sidvsukhi/Tsunami-Alert-System/blob/master/pictures/winner.JPEG "Winning Team")


## Problem statement from Ministry of Micro, Small and Medium Enterprises of India (MSME India)  

We have taken the source of satellite imagery as the indian oceanographic site  
[Source site](https://www.incois.gov.in/portal/osf/osfCoastal.jsp?region=coastal&area=westbengal&param=swh&ln=en)

Source image:<br/>
![alt text](https://github.com/sidvsukhi/Tsunami-Alert-System/blob/master/util/seawaves.JPG "MH sea waves")

The project comprises of 2 components for alerting the Tsunami:- 
1. The image processing part which is based on image processing on the web scrapped image from the source site. It detects the tsunami tides using color analysis. The colors of waves basically represent the height of the sea waves. An alert is generated for tsunami whenever a yellow color (height of sea waves=3m) and beyond are used to show the sea waves.  
2. The Machine learning part which recognizes the probability of tsunamis caused due to remote earthquakes. The basic condition for an earthquake to cause Tsunami are that the depth of earthquake should be less than 70km and minimum Ritcher scale magnitude of 7.5 

Workflow:<br/>
![alt text](https://github.com/sidvsukhi/Tsunami-Alert-System/blob/master/util/workflow.JPG "Project workflow")

Prerequisites-
1. smtp lib
2. openCV lib
3. extcolors
4. pyrebase
5. twilio

How to use the repository?
1. flaskml/theapp- The website along with the ML part
2. Earthquake.csv- The dataset used for classification
3. Tsunami DA.py- The code for preprocessing and Random Forest implementation on dataset 
4. random_forest.pkl- The trained model for remote Tsunami detection
5. app.py- The python file to compile the random_forest.pkl file using Flask for website
6. realtime.py- The image processing runnable code for extracting image from the source site and detecting colors
7. alert_detect.py- The most important python file which consists of the firebase connectivity, image processing on the tsunami sample videos(util/Tsunami_MH and util/Tsunami_WB), smtp module and also the twilio alert connectivity.
