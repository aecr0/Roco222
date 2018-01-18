# Heading 
## Sub Heading
### Another deeper heading

Paragraphs are seperated by a blank line

two spaces at the end  
of a line leaves  
a line break

text Attributes
_italic_, *italic*, __bold__, **bold**

horisontal rule:
---
Bullet L:ist
*apples
*oranges
*pears

numbered list:
1. apples
2.ornages
3.pears


  
#  Lab 1


### $ls
ls- is a list of directory contents

### $ cd /tmp
tmp- place of temporary files

### $ HOME
home- exits what folder/file your in and goes back to 
main folder, home

### $ mkdir
mkdir- makes a directory e.g $ mkdir ROCO222
 
### $ echo "Hello" >hello.md
echo- makes file called hello.md in which ever folder you are currently in and then in the file writes hello
  
### $ cp hello.md hello-again.md
cp- copys contents of one file into another

### $ mv hello-again.md hello-hello.md

### $ rm hello.md
rm- removes file

### $ rm -rf
rm -rf - removes folder

### $ cat /proc/cpuinfo
displays computer informations 
  
$ cat hello.md
cat- prints what the file says

# Motor

  The first motor we made was from cork, copper wire/tape, paperclips, magnets and a board to mount it on. To build the commutator we    wrapped copper wire around the cork, the total number of turns was around 100. We then added a armature on the end of this and soldered the wires to it. 
    
 The basic purpose of commutator is to ensure that the torque acting on the armature is always in the same direction.

 ![Photo of communtator](https://github.com/aecr0/Roco222/blob/master/ipad%2012102017%20068.JPG "Photo of cummuntator")    
  
 The support shaft is what the motor is mounted on. depending on the material if may even help its magnetic fluz and thus increase the torque when the motor is rotating.

 The armature interacts with the magnetic field (magnetic flux).
 ![Photo of armature coil](https://github.com/aecr0/Roco222/blob/master/ipad%2012102017%20069.JPG "photo of armature coil")
         
![photo of complete motor](https://github.com/aecr0/Roco222/blob/master/ipad%2012102017%20071.JPG "complete motor")
  
  The problems with the armature was because it was not attached to anything solid it meant that if anysort of pressure was applied the tape got damaged so when we finished constructing the motor when trying to make it spin of its own occured it got stuck in the the crumpled tape.
  
 ![photo of motor](https://github.com/aecr0/Roco222/blob/master/20180118_165955.jpg "photo of motor") 
  
  To solve this we remade the armature using 2 cork pieces. this meant that the armamture could be mounted on one and the coils could be on the other. To the connectinos for the motor e used the cooper tape as it was flexible and had a large surface area so had a greater chance of staying connected to the armature to carry the current. this motor also had to coils which meant it would also self start though it still had some problems with starting as the shaft that went throguh it was not aligned. 
  
![photo of motor](https://github.com/aecr0/Roco222/blob/master/20180118_170037.jpg "photo of motor")
![photo of motor](https://github.com/aecr0/Roco222/blob/master/20180118_170030.jpg "photo of motor")
  ### improved motor
   To improve our motor we added more coils and and greater amounts of turns. this allowed the motor to start from any position and have the torque generated to be high enough for it to move without any interferance. we designed the communator in solidworks and then 3d printed it 
        
Our motor has 7 coils and each coil has around 100 turns. we also have a ferrous core runnning through it this increases th emagnetic flux and would therefore also increase the torgue 

![Photo of motor](https://github.com/aecr0/Roco222/blob/master/20180118_170150.jpg "photo of motor")
![Photo of motor](https://github.com/aecr0/Roco222/blob/master/20180118_170145.jpg "photo of motor")
![photo of motor](https://github.com/aecr0/Roco222/blob/master/20180118_170132.jpg "photo of motor")
  

# Incremental Encoder

## Part 1 introduction principle of operation
  
  An motor encoder is a rotary encoder which is attach to a motor, this create a feed back loop to provide  
  inforamtion on the speed or position od the motor shaft.
  
  For the coursework the enocder we used was a disc with cut out even segments which when an light source was  
  used it would pass through the gaps and hit a photo detector this would then shown that it had been hit.  
  when this occurs continusly a code would be able to pin point the rough speed and shaft position.
  
  ![solidworks of motor](https://github.com/aecr0/Roco222/blob/master/assemably%20of%20motor.png "solidworks of motor")
      
For own encoder we designed it in solidworks and then 3d printed it 
An encoder works becasue when the light is blockd the tranasistor will turn off and the voltage across the emitter and collector will rise to almost the supply voltage. This volage will be read by the arduino which will then count and work out the location/speed of the motor.

### further improvements

The first improvement we could have made was to finish the motor, so better time management. however in the side of consturciton and programming. we could of reduced the size or the commuter as it doesnt have to be as big as we made it. we could alos have thought about how we were going to mount it and also the brushes as our orginal plan was to use the copper tape just rest agaist it like in the previous motor but that is also not very stable or strong. 

## ROBOT ARM
 
We chose to have 4 degrees of movemtn for our arm, the base would rotate using a stepper motor, the lower arm would be able to rotate as would the fore arm and also one side of the gripper for the hand.
     
We built the arm in autodesk fusion 360 and 3d printed the parts and then used the stl files for the urdf description file so we could have a working 3d representation in rviz using the ROS software. 

To reduce the weight of the arm so that the servos do not have to work as hard we removed parts of the material in the the arms. this lattice meant that the arm was strong but beacuse of the lack o materials was also lightweight.

![solidworks of arm](https://github.com/aecr0/Roco222/blob/master/arm%20part.png "solidworks of arm")

When putting the robot together we had some differculties as there were some aread which had to be filed down as they were to large fit. We also descovered a problem that when attaching the servos to the outside of the arm they would not fit flush as we forgot to antisapate the distance from the connector to the servo, this meant the limbs were a bit tight and would not fit in properly. 

After putting the robot together we used the arduino and ros to control the finger joint in the terminal using rostopic pub, once we know it worked we stared to develop the URDF description file.

When working on the URDF we first attempted to put all the robot files in at once, this didnt work beacuse if you have a small problem witht he code it was hard to workout what went wrong. after that we decided to ge tth ehand working as that contained the smallet amount of peces and joints. 

Using the template the ROS lab give us we manage to get a shape and used that to base of what the rest of our code needed to look like. after talking with other groups we then used the idea of a mesh so that we could use our stl files from the 3d printed model is meant that we has a 3D reprenstaiton for our hand. 


```xml

  <link name="Hand_finger">  
    <visual>
      <geometry>
         <!-- box size="0.040 0.005 0.125"/> -->	
         <mesh filename="file:///home/student/ROCO222_ROS/Robot_project/models/STL_files/Fingery_part.STL" scale="0.01 0.01 0.01" />
      </geometry>      
         <origin rpy="0 1.57 0" xyz="0.015 0.525 -0.1" />   
         <material name="red"/>   
    </visual> 
  </link>


  <joint name="Finger" type="revolute">
     <axis xyz="0 0 -1" />
     <limit effort="1000" lower="-3.14" upper="3.14" velocity="0.5" />
    <parent link="Hand_back"/>
     <child link="Hand_finger"/> 
     <origin xyz="0.015 0.525 -0.1" />
  </joint>

```


![RVIZ of hand](https://github.com/aecr0/Roco222/blob/master/hand_in%20Rviz.png "RVIZ of hand")
[Link to rviz for hand code](https://github.com/aecr0/Roco222/blob/master/robot-finger.urdf)

However when trying to get the revolute to work it rotated on the wrong plane or axis so it would rotate the wrong way we were not able to work out the reason for this so continued with the rest of the arm. this went smother as we could develop one bit make ure it was correct then move on to the next untill we have most of the srm in RVIZ, how however we also had problems in that sometimes the compuntents form the file would say that the link was incorrect or that there was "no transform from [] to []" thi delayed us in our project. 

![RVIZ of hand,forearm and lower arm](https://github.com/aecr0/Roco222/blob/master/Screenshot%20from%202018-01-18%2014-56-29.png "RVIZ of hand, forearm and lower arm")
[link to rviz for arm code](https://github.com/aecr0/Roco222/blob/master/robot-arm2-0.urdf)

Due to not finishing the project we were not able to connect our robot to the arduino or finih its construction in real life or on RVIZ


 
      
    
