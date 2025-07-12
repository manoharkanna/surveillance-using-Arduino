This project uses OpenCV in Java to detect human faces using a webcam. When a face is detected, it sends a signal via Serial Communication using jSerialComm to an Arduino, which activates a buzzer (or LED) depending on face detection.

🔧 Features
🎥 Real-time face detection using webcam

🔔 Buzzer turns ON when a face is detected

🔌 Serial communication with Arduino via USB

🖼️ Face snapshot captured on first detection

🔐 Clean shutdown ensures buzzer turns OFF on exit

🖥️ Technologies Used
Java (OpenCV)

OpenCV 4.9.0 (with opencv_java490.dll)

Arduino (UNO/Nano/etc.)

jSerialComm (Serial Communication Library)

Haar Cascade Classifier (face detection)

📦 Requirements
💻 On Java Side
Java JDK 8 or later

OpenCV 4.9.0 for Java

jSerialComm Library

A working webcam

haarcascade_frontalface_default.xml file

🔌 On Arduino Side
Arduino UNO/Nano (or compatible)

Buzzer module connected to a digital pin (e.g., pin 13)

Arduino IDE

------Java Code Summary---------
Captures video from the webcam.

Converts to grayscale and applies Haar face detection.

Sends '1' over serial if a face is detected → Arduino activates buzzer.

Sends '0' if no face → Arduino turns buzzer OFF.

On ESC key press, Java app sends '0' and exits safely.

--------Folder Structure-------
FaceDetection-BuzzerControl/
│
├── native/
│   └── opencv_java490.dll
├── haarcascade_frontalface_default.xml
├── webcam.java
├── README.md
└── lib/
    └── jSerialComm-2.9.3.jar

-------Commands to run the code----------
javac -cp ".;lib/jSerialComm-2.9.3.jar;opencv-490.jar" webcam.java
java -cp ".;lib/jSerialComm-2.9.3.jar;opencv-490.jar" webcam

------com change--------
SerialPort port = SerialPort.getCommPort("ardiuno connected com");


