# Pi in the Sky
## Objective
To measure and record flight data using a flying machine
## Planning
See planning file
## Weekly updates
### January
Week 1 (2-5)
- Finalized two-stage rocket design and what sensors we are using.
- Decided on rocket motors and proportions of the rocket.
- Began CAD design for nose cone that will house electronics.  

Week 2 (8-12)

- Ordered fuselage tube and parachute
- Worked on nose cone design to house electronics
- Began writing code for altimeter and mpu 6050.
Week 3 (16-19)

### febuary 

Weeks 1-2 (2-16)
- got the 3D printed internals designed and tested
- finished the initial code and began to plan the sodering and final electronics
- started simulations for the rocket and mesured ideal performance.

  ### march-april 
  
## Design

our design was conceptualy easy but did require a lot of leg work partitularly from Zach who took lead in researching and designing each individual part. Besides the cardboard tube and the rocket motor all of the pieces to our rocket were 3D printed and hand painted. 
here is the nose cone:
![Nose Cone](https://github.com/cprocino/PiInTheSky/assets/71406784/3916ed05-9fa9-40af-bbda-e4bccf8393e1)

 the curve that the tip follows was researched for maximum effiency 

 
 here are the fins:

![Screenshot 2024-05-07 125457](https://github.com/cprocino/PiInTheSky/assets/71406784/a1230d67-b44f-4315-bab6-531f5cdd9991)


this is the whole thing:

![Stage Assembly](https://github.com/cprocino/PiInTheSky/assets/71406784/ce8ea952-96d6-46b2-8c5d-56e5270974b4)




### CAD

## Code
### Code
``` python
# type: ignore 


import adafruit_mpl3115a2
import time
import board # importing the board and and all the nessecary starting bits
import digitalio
import adafruit_mpu6050
import busio

sda_pin = board.GP14   # setting up the pin for SDA
scl_pin = board.GP15   #  setting up the pin for Scl
i2c = busio.I2C(scl_pin, sda_pin)    # setting up the i2c var
mpu = adafruit_mpu6050.MPU6050(i2c)  # setting up the mpu var
alt = adafruit_mpl3115a2.MPL3115A2(i2c)
#alt.sealevel_pressure = 103040 

with open("/data.csv", "a") as datalog:
    #this line opens the file data.txt and appends info to the end of it
        while True:
           
            datalog.write(alt)
            
            datalog.flush()
            time.sleep(0.25)
            print(f"X: {mpu.acceleration[0]} m/s^2")   #prints the x values
            print(f"Y: {mpu.acceleration[1]} m/s^2")   #prints the y values
            print(f"Z: {mpu.acceleration[2]} m/s^2")  #prints the z values
            time.sleep(1)
            print()
            
            altitude = alt.altitude
            print('Alt: {0:0.3f} meters'.format(alt.altitude))
        

            # x = round(mpu.acceleration[0],3)
            #y = round(mpu.acceleration[1],3)
            #z = round(mpu.acceleration[2],3)

            #print(f"x:{ x} y:{y} z:{z}") # This is an F string which lets us put a variable that is changing in our serial monitor or in a OLED or LCD
            time.sleep(.1)

  

    

```
The code in this project wasn't super difficult although it did need us to cover new concepts that we hadn't before. We used both an altimeter and accerlerometer and had them both copy values into a file held on the pico. Some problems that i did run into were making the boot file work so that there would be a code and data mode and having both the accelerometer and altimeter work onj the same SCL and SDA. 
Initialy we needed to make a code for the altimeter and accerlorometer seperately, We had alread done a project with an accerlometer but the altimeter needed more work. 

### wiring 
the wiring was probably the simplest  part of this and only required minimal knowledge to complete but took a few attempts to solder. 
Here it is on paper:


![WIN_20240222_13_32_27_Pro](https://github.com/cprocino/PiInTheSky/assets/71406784/fc46c44f-9fdc-4f43-b80d-ba51456fbb50)

the one problem that i did run into was making it all solder the way in which Matthew Miller wanted it to be.



## Launching
Launch one april 30th: mixed results launch, on the one hand the rocket preformed wonderfully and the average position of the rocket was exactly were we wanted it to be. On the other the rocket split in two and one part ended up stuck in a tree and the other lost in the woods(see picture) 

![Screenshot 2024-05-07 132944](https://github.com/cprocino/PiInTheSky/assets/71406784/a22ea83e-a512-4837-898e-5f8d7d3cde0d)
the middle dot is where we launched from, the top dot is where the nose cone and electronics landed and the bottom dot is the estimated position of the bottom half is. 

here is the nose stuck in the tree

![Nose Cone](https://github.com/cprocino/PiInTheSky/assets/71406784/453c5cd9-f169-4225-b33a-6bcbe4705468)





