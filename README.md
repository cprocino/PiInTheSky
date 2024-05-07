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

### Code
The code in this project wasn't super difficult although it did need us to cover new concepts that we hadn't before. We used both an altimeter and accerlerometer and had them both copy values into a file held on the pico. 
Initialy we needed to make a code for the altimeter and accerlorometer seperately, We had alread done a project with an accerlometer but the altimeter needed more work. 
Here is the accerlerometer  [code](raspberry-pi/avoid1.py).





## Launching
Launch one april 30th: mixed results launch, on the one hand the rocket preformed wonderfully and the average position of the rocket was exactly were we wanted it to be. On the other the rocket split in two and one part ended up stuck in a tree and the other lost in the woods( see picture) 

![Screenshot 2024-05-07 132944](https://github.com/cprocino/PiInTheSky/assets/71406784/a22ea83e-a512-4837-898e-5f8d7d3cde0d)
the middle dot is where we launched from, the top dot is where the nose cone and electronics landed and the bottom dot is the estimated position of the bottom half is. 

here is the nose stuck in the tree






