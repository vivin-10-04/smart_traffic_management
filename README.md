# smart_traffic_management
The project's main objective is to give an optimized solution to smartly manage traffic in the metropolitan cities for the emergency vehicles. In this project, SDN(software defined network) is used along with image recognition and labeling of the emergency vehicles.

1.  Abstract:
In densely populated cities, emergency vehicles are not able to navigate due to improper traffic management. One of the major problems that arise when an emergency happens is minimizing the delay time in resource forwarding to reduce both human and material damages.
‘Smart cities’ now provide new applications based on ‘Internet of Things (IoT)’ technology. Moreover, ‘Software Defined Networks (SDN)’ offer the possibility of controlling the network based on application requirements which will be explained further.

1.1.  Importance of Problem and Domain:
Most of the traffic lights today feature a fixed green light sequence, thus the sequence is pre-determined without taking the presence of the emergency vehicles into account. Traffic congestion leads to increase in fuel consumption, air pollution, longer travel times, and accidents. Thus, efficient traffic management is crucial for improving the quality of life in urban areas. Emergency vehicles such as ambulances, police cars, fire engines, etc. stuck in a traffic jam get delayed in reaching their destination which can lead to loss of property and valuable lives.
This paper will include how to identify the vehicles using computer vision and audio recognition and how to control the surrounding traffic lights using SDN software defined networks to let emergency vehicles navigate through the city faster. It dives into smart cities, urban planning, traffic management, IoT, and network communication(SDN). 

1.2. Statistics and Problem Statement:
In 2020, around 1.35 million deaths were due to road traffic accidents globally (WHO). The National Highway Traffic Safety Administration (NHTSA) has collected the ground ambulance crash data for the U.S between 1992 and 2011 (20 years). There was an estimated annual mean of 4500 motor vehicle traffic crashes and 1500 injury crashes involving an ambulance. In 20 years (1992–2011), 662 persons were killed and 52,000 persons were estimated to be injured in such crashes, including ambulance drivers, passengers, non-occupants and occupants of other vehicles. From the statistics of emergency vehicle accidents in the U.S, there were roughly 31,600 accidents involving fire vehicles resulting in 645 fatalities over a 10 year period (2000–2009) and 300 fatalities that occur every year during police pursuits. 

Problem: Traffic congestion at intersections during peak hours  emergency vehicles from reaching their destinations, resulting in casualties.
Solution: Deploy IoT-enabled traffic signals with SDN and visual sensing for real-time traffic monitoring and dynamic signal control.


2. Introduction:
Most of the largest cities in the world have implemented or have been implementing smart city technologies in order to improve the efficiency of the management of their city. The traffic light control plays a vital role in any intelligent traffic management system. The green light sequence and green light duration which is 2-15 seconds minimum and 15-70 seconds maximum. These two key aspects are to be considered in traffic light control. The traffic management in most cities have fixed light length duration and sequences. This sounds perfect for normal traffic control of vehicles. But this may result in delay for the emergency vehicles at the time of action.
 
2.1. Objectives:

i)  To Detect the Emergency Vehicles and Give Clearance: Traffic congestion leads to a domino effect, causing delays and accidents. We aim to detect the emergency vehicle and clear the traffic to reach the destination faster.
Detection: The detection is monitored in real time using visual sensors and IoT-enabled devices. After the detection, the system then constantly measures the distance between the emergency vehicle and the traffic light which further leads us to the clearance by dynamically adjusting the traffic light timings. This helps in optimizing the flow of vehicles, reducing bottlenecks and idle time at intersections.
Methodology: The system employs data from cameras, vehicle counters, and environmental sensors to analyze traffic patterns and emission levels. SDN plays a key role in managing traffic by adjusting signals in real-time across multiple intersections, helping for clearance of traffic.

ii)  Enhancing Travel Time Efficiency by Optimizing Signal Timing: Traditional traffic signals with fixed timings often cause unnecessary delays at intersections. By using real-time data, this approach aims to:
Real-Time Traffic Monitoring: Cameras and sensors track vehicle flow and queue lengths at intersections. The system then adjusts the green, yellow, and red lights to match current traffic conditions.
Dynamic Signal Control: The system optimizes the sequence and duration of traffic lights to avoid delays. For example, during peak hours, if one direction has more traffic, the green light for that direction can be extended, while less busy directions receive shorter green phases.
 This reduces vehicle wait times, helping vehicles to reach their destinations faster. On a larger scale, it improves urban mobility, boosts the economy, and lowers fuel consumption across the city.

iii) Traffic Patterns Detection for Better Urban Planning: Data collected by the system have very valuable insights of traffic patterns, road usage, and congestion areas, which can be used by urban planners and city authorities to make informed decisions:
Traffic Pattern Analysis: The vast amounts of data collected by the system from sensors and cameras is then analyzed to detect patterns such as peak traffic hours, frequently congested intersections, and road usage trends.
Improvement Possibilities: Improvement in the road infrastructure, rerouting traffic, or implementing new traffic laws can be achieved by studying these insights properly.
Urban Planning: With the database, the future traffic challenges can be detected and be worked upon.


2.2. Need of Networking: 

Traffic Management completely relies on the efficiency which can be only achieved by properly collecting the data, processing it and acting on it in real time. A robust network system is required for the communication of the data. Thus networking is the backbone of the system for smooth transmission of data between the cameras, sensors and the control centers. 
For this SDN i.e. Software Defined Network is used.

SDN offers:
 Increased control with greater speed and flexibility: Instead of manually programming multiple vendor-specific hardware devices, developers can control the flow of traffic over a network simply by programming an open standard software-based controller. Networking administrators also have more flexibility in choosing networking equipment, since they can choose a single protocol to communicate with any number of hardware devices through a central controller.
Customizable network infrastructure: With a software-defined network, administrators can configure network services and allocate virtual resources to change the network infrastructure in real time through one centralized location. This allows network administrators to optimize the flow of data through the network and prioritize applications that require more availability.
Robust security: A software-defined network delivers visibility into the entire network, providing a more holistic view of security threats. With the proliferation of smart devices that connect to the internet, SDN offers clear advantages over traditional networking. Operators can create separate zones for devices that require different levels of security, or immediately quarantine compromised devices so that they cannot infect the rest of the network.



3. Scenario and Architecture:
3.1. Components:
We have to consider many factors in order to properly determine the best way possible to allow the emergency vehicles to pass through. Inputs such as images and audio are to determine which vehicle has to be tagged and where the exactly are. These inputs will be taken by  pre-installed acoustic sensor-based systems that outperform the other preemption systems in terms of accuracy and installation cost. Extensive work has already been conducted on detecting emergency vehicles based on their siren sounds.The acoustic sensors collect the siren signals and forward them to the Road Side Unit (RSU). The Road Side Unit (RSU) includes a frequency measuring controller (Arduino UNO) to detect the emergency vehicles. The RSU collects the siren signals from the acoustic sensors and forwards them to the frequency measuring controller. The controller detects the emergency vehicle by its siren frequencies. The controller measures the frequencies of siren signals and computes the average of measured frequencies. The frequency measuring controller sends the alert signal to the traffic signal controller (Arduino Mega), if the frequency is between the range of yelp or wail. The traffic signal controller stops the fixed sequence and light length algorithm and executes the emergency vehicle dispatching algorithm on receipt of arriving emergency vehicle information.Similar work will be done by using the cameras and image recognition software to detect and tag vehicles calculating their distance from the traffic light. As the vehicle is flagged a request will be sent to the network for immediate access to green light till the vehicle distance reaches 0.

3.2 Distance Measurement Techniques:
We need to calculate distance from the lights so that we can give the change signal request till the distance reaches zero otherwise the request won't be retracted.There are different techniques to measure the distance between the vehicle and the camera. We perform the distance measurement by computing the Euclidean distance, Manhattan distance

3.2.1 Euclidean Distance:
It is the geometric distance in the multidimensional space. One technique that may suit a wide variety of image analysis applications is the distance transform or a Euclidean distance map. In general, if a = (a1, a2, a3,…, am) and b = (b1, b2, b3,…, bm) are the two points in m-space, then the Euclidean distance (dECD) between points a and b or b and a is as follows:


 D (a,b) = 1m (b  i  + ai)2
3.2.2. Manhattan Distance
The Manhattan distance between two points is the absolute sum of the differences of their coordinates. In general, if a = (a1, a2, a3,…, am) and b = (b1, b2, b3,…, bm) are the two points in m-space, then the Manhattan distance (dMHD) between a and b is defined as follows:

D (a,b) = im ai - bi

3.2.3. Distance Based Emergency Signal Algorithm
In order to achieve traffic light control to provide clearance for any emergency vehicle and to shorten its travel time, a distance-based emergency vehicle dispatching algorithm can be used. We assume only one emergency vehicle per direction.The proposed algorithm has mainly six steps:
The sensor senses the presence of emergency vehicles. The emergency vehicles are ambulances, fire engines, police cars and officials.
Calculates the distance between the emergency vehicle and the intersection (traffic light).
The controller checks that the arriving emergency vehicles are at the same distance or not. If they are at the same distance, the controller stays as is. Else, it chooses to request a signal to change for the direction set in descending order with the distance.
Determine the green light duration based on the measured distance values and send these values to the traffic lights.
Verify the passage of the emergency vehicle and measure the speed of the emergency vehicle and count the vehicles moving along with the emergency vehicle towards the next intersection. The system sends the measured data to the next intersection.
The controller checks for the presence of the emergency vehicle. If no vehicle, then it resumes normal operation. Else, it continues repeats from step 2 to step 6.

3.3. Software Defined Network:
SDN is currently being employed in a wide variety of contexts. It is employed with artificial intelligence, for throughput allocation, video streaming or mobile networks among other uses. In the context of smart cities, it is starting to be utilized for smart homes and IoT information management. However, it is yet to be a common technology in smart city applications. Employing SDN in smart cities enables control of the network utilizing software in order to communicate and give orders to the IoT nodes.

3.3.1.  Architecture and Algorithm: 
The IOT network is composed of nodes that provide the data to the network. The SDN network is composed of virtual devices such as Openflow Switches. The cameras , acoustic network and traffic signals are IOT nodes providing the data whereas the OpenFlow switch is managed by an SDN controller that can make decisions about the behavior of the nodes on the IoT networks. The SDN network is in charge of gathering data from all IoT networks and distributes this information along the rest of the OpenFlow switches. Additionally, the SDN controller communicates with a cloud service which is capable of requiring actions from the controller in order to make changes in the SDN network and in the IoT networks. 

When an emergency event is registered onto the network the controller receives the information from openflow switch and it allocates resources across the network as well as the location (by area ID’s) of each IOT node. At this moment the Openflow switch allows communication to allow communication between the IoT nodes that have to collaborate in order to divert urban traffic and make decisions so as to obtain the fastest paths for the emergency services.
The proposed algorithm is given below that allows the SDN controller to make changes to the nodes via Openflow switches.

ALGORITHM:

Given: ALERT_ID , ALERT_AREA,RESOURCES

Alert_Type = Get_Type(ALERT_ID)
If Alert_Type = Emergency_Vehicle_Incoming do
	Local_Resources = Ask for Resources from Local_Security_Service
	Resources_With = RESOURCES  U Local_Resources 
Send Openflow Modification Message (ALERT_AREA,DIRECTION)
Open_path(Alert_Type, time = Till_exit )
Else Send Openflow Modification Message(ALERT_OVER,DIRECTION,ALERT_AREA)

The local resources refer to the acoustic input  , current traffic signal and emergency vehicle distance and type.

The resources refer to the admin access to modify the IOT nodes.

  

4. Conclusions
In this paper, we combine two technologies in order to tackle the problems of this increasing traffic and propose a new application to manage emergency resources. SDNs offer the possibility to control the network based on application requirements.  This application uses the adaptability of the SDN in order to forward urban traffic using intelligent traffic lights and other traffic elements that are connected to IoT networks. The SDN controller communicates with cloud and local services so as to gather the data needed to make the best changes in order to manage the emergency. The other approaches by combining  the measurement of distance between the emergency vehicle and intersections using visual sensing methods, vehicle counting and time sensitive alert transmission within the sensor network. The distance between the emergency vehicle and the intersection is calculated from visual data using Euclidean distance, Manhattan distance and Canberra distance techniques for comparison. A complete description of the use of visual sensing techniques in vehicle detection and counting is also presented. The measured information like vehicle count, distance and speed are very useful for a traffic management center to manage emergency traffic efficiently.



