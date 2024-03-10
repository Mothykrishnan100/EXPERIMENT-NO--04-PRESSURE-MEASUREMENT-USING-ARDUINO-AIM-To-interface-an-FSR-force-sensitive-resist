# EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resistor


## AIM: 
To interface an FSR(force sensitive resistor) and scale the output voltage obtained to pressure applied 
 
### COMPONENTS REQUIRED:
1.	FSR  (force sensitive resistor)
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
FSRs are basically a resistor that changes its resistive value (in ohms Ω) depending on how much it is pressed. These sensors are fairly low cost, and easy to use. They also vary some from sensor to sensor perhaps 10%. FSR's resistance changes as more pressure is applied. When there is no pressure, the sensor looks like an infinite resistor (open circuit), as the pressure increases, the resistance goes down. This graph indicates approximately the resistance of the sensor at different force measurements.
 

![image](https://user-images.githubusercontent.com/36288975/163532939-d6888ae1-4068-4d83-86a7-fc4c32d5179e.png)

### FIGURE 01 GRAPH OF FORCE vs RESISTANCE **




![image](https://user-images.githubusercontent.com/36288975/163532957-82d57567-a1c3-48c5-8a87-7ea66d6fca49.png)




### FIGURE 02 FORCE SENSITIVE RESITOR FOIL DISC TYPE  

FSRs are often a polymer with conductive material silk-screened on. That means they're plastic and the connection tab is crimped on somewhat delicate material. The best way to connect to these is to simply plug them into a breadboard.

The easiest way to measure a resistive sensor is to connect one end to power and the other to a pull-down resistor to ground. Then the point between the fixed pull down resistor and the variable FSR resistor is connected to the analog input of a microcontroller such as an Arduino The way this works is that as the resistance of the FSR decreases, the total resistance of the FSR and the pull down resistor decreases from about 100Kohm to 10Kohm. That means that the current flowing through both resistors increases which in turn causes the voltage across the fixed 10K resistor to increase.

 ![image](https://user-images.githubusercontent.com/36288975/163532972-2b909551-12c9-485d-adb1-d1e988d557bd.png)

### TABLE -01 FORCE AND OUTPUT VOLTAGES**
	
  Table -01 indicates the approximate analog voltage based on the sensor force/resistance w/a 5V supply and 10K pull down resistor.

### Vo = Vcc ( R / (R + FSR) )								Eq-01

****Where R= 1KΩ in this experiment 
****That is, the voltage is proportional to the inverse of the FSR resistance.










![image](https://user-images.githubusercontent.com/36288975/163532979-a2a5cb5c-f495-442c-843e-bebb82737a35.png)


###CIRCUT DIGRAM:


  
### FIGURE-03 CIRCUIT DIAGRAM
   ![309343475-010516e4-8084-4a23-ad4e-2e61c411cd1e](https://github.com/Mothykrishnan100/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/160512502/dda240ef-f4d0-4669-b319-abb65689ecd0)

   ![image](https://github.com/Mothykrishnan100/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/160512502/1aabb12d-5b30-4f28-b11e-e98532fadc04)




### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 
 *your roll no 212221080051
 * your name mothy krishnan R D
 * department and year mech 3 year

     * int LED = 7;
	int FSR;

	void setup()
{	
  	pinMode(LED, OUTPUT);
  	Serial.begin(9600);
}

	void loop()
{
 	 FSR = analogRead(A0);
  	Serial.print("Raw Value = ");
  	Serial.println(FSR);
  	delay(500);
	int m;
  	m=map(FSR,0,159,0,10);
  	Serial.print("Mapped Value = ");
  	Serial.println(m);
  
  	if(FSR>50)
   {
    	digitalWrite(LED,LOW);
    	delay(500);
    	digitalWrite(LED,HIGH);
    	delay(500);
   }
}

 
 ###Comparison of Applied and mapped forces :

      ![309342976-8c7b1979-fd68-4c3f-bc0d-9443e6df76bc](https://github.com/Mothykrishnan100/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/160512502/dd29aed0-8756-4893-8afe-eb2994732c71)
      ![309343028-b322fcfe-a72c-4d34-87c5-f0bbee741518](https://github.com/Mothykrishnan100/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/160512502/f1453dc3-2205-4978-b325-46a8a47bdae2)


 
 
 
 
 
 
 
 
 
 
 
 



### TABLE -02 standard deviation table 
### Population Standard Deviation
The population standard deviation, the standard definition of σ, is used when an entire population can be measured, and is the square root of the variance of a given data set. In cases where every member of a population can be sampled, the following equation can be used to find the standard deviation of the entire population:



Where
xi is an individual value
μ is the mean/expected value
N is the total number of values

For those unfamiliar with summation notation, the equation above may seem daunting, but when addressed through its individual components, this summation is not particularly complicated. The i=1 in the summation indicates the starting index, i.e. for the data set 1, 3, 4, 7, 8, i=1 would be 1, i=2 would be 3, and so on. Hence the summation notation simply means to perform the operation of (xi - μ)2 on each value through N, which in this case is 5 since there are 5 values in this data set.

EX:           μ = (1+3+4+7+8) / 5 = 4.6        
σ = √[(1 - 4.6)2 + (3 - 4.6)2 + ... + (8 - 4.6)2)]/5
σ = √(12.96 + 2.56 + 0.36 + 5.76 + 11.56)/5 = 2.577


###Sample Reading :
    

μ = ( 1.05 + 2.05 + 3.09 + 4.03 + 5.09 + 6.12 + 7.09 + 8.12 + 9.22 + 10) / 10
  = 5.586

σ = √[(2 - 5.586)^2 + (3 - 5.586)^2 + ... + (10 - 5.586)^2]/10
σ = √(456.859396)/10 = 2.137426948

### SIMULATION AND OUTPUT :
      ![309343099-5a0bd174-cfa1-476e-b3c5-80f94299ff2c](https://github.com/Mothykrishnan100/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/160512502/3e9c548b-299f-41f2-9252-108d922f21f1)
     
      ![309343136-24899851-5920-46da-a636-261b5bec619f](https://github.com/Mothykrishnan100/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/160512502/d3facaec-cf24-4f75-b4d1-8618bb863d64)












### RESULTS : Arduino uno is interfaced with FSR and output values are indicated on a graph.
