# EXP-3-IoT-Based-Remote-Control-System-for-Electric-Vehicles-Using-MATLAB-ThingSpeak

## AIM
To design and implement an IoT-based remote control system for an electric vehicle (EV) using MATLAB and ThingSpeak API. The system enables remote operations such as:
•	Locking/Unlocking doors
•	Starting/Stopping the engine
•	Turning lights ON/OFF
The MATLAB script communicates with ThingSpeak, which acts as an intermediary between MATLAB and an embedded system (ESP32).
 
## THEORY
1. Internet of Things (IoT) in Electric Vehicles
IoT enables remote monitoring and control of EV systems using cloud-based communication. By integrating MATLAB with ThingSpeak, users can send control signals and retrieve the vehicle’s status remotely.
2. ThingSpeak Cloud Platform
ThingSpeak is a cloud-based IoT analytics platform that allows:
✅ Data collection from embedded devices
✅ Remote command transmission using APIs
✅ Real-time monitoring and visualization
3. Working Principle
1.	User Inputs Command in MATLAB → e.g., "Start Engine"
2.	MATLAB Sends Command to ThingSpeak API
3.	ESP32 Reads Command from ThingSpeak and performs the action
4.	ESP32 Updates Status on ThingSpeak
5.	MATLAB Reads Status from ThingSpeak and displays it
 
## PROCEDURE
🔹 Step 1: Setup ThingSpeak Account
1.	Create a Free ThingSpeak Account → https://thingspeak.com
2.	Create a New Channel and Add Two Fields: 
o	Field 1 → Control Commands
o	Field 2 → EV Status
3.	Note Down the Write & Read API Keys
🔹 Step 2: Implement MATLAB Code
1.	Open MATLAB and create a new script.
2.	Copy and paste the MATLAB code (provided earlier).
3.	Replace YOUR_WRITE_API_KEY, YOUR_READ_API_KEY, and YOUR_CHANNEL_ID with your ThingSpeak credentials.
4.	Run the script and select an action from the menu.
🔹 Step 3: ESP32 Integration (Optional)
1.	ESP32 reads the command from ThingSpeak using Wi-Fi.
2.	Executes the command (e.g., turns ON engine).
3.	Updates the EV status back to ThingSpeak.
🔹 Step 4: Display Vehicle Status in MATLAB
1.	MATLAB retrieves the latest EV status from ThingSpeak.
2.	Displays the confirmation message to the user.



## MATLAB Code (Without MQTT Client Toolbox) 
## MATLAB CODE

```matlab
clear; clc;

disp('Choose a remote function:');
disp('1 - Lock Doors');
disp('2 - Unlock Doors');
disp('3 - Start Engine');
disp('4 - Stop Engine');
disp('5 - Turn On Lights');
disp('6 - Turn Off Lights');

n = input('Enter your choice (1-6): ');

cmd = ["LOCK","UNLOCK","START","STOP","LIGHT_ON","LIGHT_OFF"];

if n >= 1 && n <= 6
    disp(['Command Sent: ', char(cmd(n))]);
    
    switch n
        case 1
            status = 'Doors Locked';
        case 2
            status = 'Doors Unlocked';
        case 3
            status = 'Engine Started';
        case 4
            status = 'Engine Stopped';
        case 5
            status = 'Lights ON';
        case 6
            status = 'Lights OFF';
    end
    
    disp(['EV Status: ', status]);
else
    disp('Invalid choice. Please enter a number between 1 and 6.');
end
```

## OUTPUT

The program displays six EV remote-control functions:

1. Lock Doors
2. Unlock Doors
3. Start Engine
4. Stop Engine
5. Turn On Lights
6. Turn Off Lights

For example, if the user selects:

```text
3
```

The output is:

```text
Command Sent: START
EV Status: Engine Started
```

## RESULT

The EV remote-control functions were successfully simulated using MATLAB. The program allows the user to select commands for door locking, engine control, and lighting control and displays the corresponding EV status.


## Output:


<img width="1917" height="985" alt="image" src="https://github.com/user-attachments/assets/88fd7557-b37f-44c6-9fdd-70fa46899584" />


## Result:

This experiment demonstrated how MATLAB can be used to remotely control an EV using ThingSpeak API. The system provides a secure, cloud-based approach to IoT-enabled vehicle automation.


