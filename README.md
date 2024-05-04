# Project Sesam

# Introduction

What do you take with you when you leave your home?



Maybe it is your smartphone.

Did it ever happen to forget your keys?



Then I have a solution for you:



## SESAM

**![](https://lh7-us.googleusercontent.com/E0-pl3nL3ExOdZMx_6eUwDSNWeXVjAr6NyuGaziviQgEORJ94R4GOSuau362Q4mj20f0jqfF1VBBzLraezxc-N_-5-97KIrGAReMbwJmBoBMYeGQLM2C4lQ92mxeK5RLCsC6u716JBGNAEaCJs5Ltio22wuNKXWt=s2048)**

Open your door with smartphone or face recognition



### Requirements

NodeMCU, Relay, Electrical Door Opener

Accessible server (e.g. Raspberry Pi)

Camera



### Electrical Circuit

Pin D0 -> Relay Module

Relay Module -> 5-12V 

Relay Module -> Electrical Opener Vin (5-12 V)

![](C:\Users\bscharnagl\Downloads\img.jpg)

### Code

[Code for NodeMCU](https://github.com/BastianSch/Sesam/src/mqtt_relay)

[Code for face_recognition](https://github.com/BastianSch/Sesam/src/face_recognition)

[Code for Smartphone App](https://github.com/BastianSch/Sesam/src/smartphone_app)

### Instructions

#### NodeMCU

Change your credentials for wifi and mqtt in mqtt_relay.ino

Connect the electrical circuit and flash your NodeMCU

#### Raspberry Pi

```shell
pip3 install face_recognition face_recognition_models Click dlib numpy Pillow scipy
```

Install and configure Mosquitto Broker [Documentation | Eclipse Mosquitto](https://mosquitto.org/documentation/)

Make it accessible and add users.

Change your credentials for wifi and mqtt in auth.py

Add images to the folder faces

Download dlib shape_predictor_68_face_landmarks.dat model and put it under src/face_recognition/blink_detection/model_landmarks

Run auth.py

```shell
cd src/face_recognition
python auth.py
```

#### Smartphone

Build the [Xamarin](https://visualstudio.microsoft.com/de/xamarin/) Project and install it on your Smartphone.

It consists of a QuickSettingsTile and a Button within your app to open the door