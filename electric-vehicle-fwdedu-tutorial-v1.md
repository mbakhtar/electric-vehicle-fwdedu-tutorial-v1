# Electric Vehicle CAK V2.1 fwdEDU
```package
```
## @showhint
Add ``||cakLandServos:turn servo at P1 to degrees 35||`` block from the ``||cakLandServos:Servo||`` drawer
```blocks
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
```
## @showhint
Now add ``||cakLandServos:turn right motor + pin on||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
```
## @showhint
Set the speed of the driving motor by adding ``||cakLandMotor:turn right motor at speed 0||``
change the speed from 0 to 50
```blocks
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
```
## @showhint
Now add the following blocks under the ``||basic:forever||`` loop. 
Add ``||cakLandSonar:graph proximity max range 0 cm||``. Change the range number from 0 to 50
```blocks
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    })
```
## @showhint
In the ``||basic:forever||`` loop add a delay by nesting a ``||basic:pause||``
block before the ``||cakLandSonar:graph proximity max range 50 cm||``.
Change the ``||basic:pause||`` value to 1 sec or 1000 ms.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    })
```
## @showhint
Now nest an ``||logic:If true then||`` block after the 
``||cakLandSonar:graph proximity max range 50 cm||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (true) {
        })
```
## @showhint
Replace the ``||logic:true||`` condition with ``||cakLandsonar:sonar is closer than 0 cm||`` block
```blocks
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0, fwdSensors.thresholdDirection.under)) {
    })
```
## @showhint
When the sonar's condition is true the ``||cakLandMotor:motor||`` should stop. 
Add ``||cakLandMotor:stop motors||`` block and 
nest it under ``||logic:if then||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.3, fwdSensors.thresholdDirection.under)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
        })
```
## @showhint
Add a ``||basic:pause||`` of 1 sec or 1000ms after the ``||cakLandMotor:stop motors||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.3, fwdSensors.thresholdDirection.under)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
        basic.pause(1000)
     })
```
## @showhint
Create a ``||functions:function||`` and name it ``||functions:react||``
```blocks
function react(){
}
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.3, fwdSensors.thresholdDirection.under)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
        basic.pause(1000)
        })
```
## @showhint
Add a numeric parameter "degrees" to be passed in the ``||functions:react function||``
```blocks
function react(degrees:number){
}
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.3, fwdSensors.thresholdDirection.under)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
        basic.pause(1000)
     })
```
## @showhint
Nest ``||cakLandServos:turn servo at P1 to degrees:||`` ``||degrees||`` under
``||Functions:function react||``
```blocks
function react (degrees: number) {
    fwdMotors.servo1.fwdSetAngle(degrees)
    }
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.3, fwdSensors.thresholdDirection.under)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
        basic.pause(1000)
      })
```
## @showhint
Add two ``||basic:pause||`` blocks. One after the ``||cakLandServos:turn servo at P1 to degrees:||`` 
and another one after ``||cakLandMotor:turn left motor at speed -30||``
```blocks
function react (degrees: number) {
    fwdMotors.servo1.fwdSetAngle(degrees)
    basic.pause(1000)
    fwdMotors.turn(-30)
    basic.pause(2500)
    }
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.3, fwdSensors.thresholdDirection.under)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
        basic.pause(1000)
        if (Math.randomBoolean()) {
            react(60)
        } else {
            react(10)
        }
    }
})
```
## @showhint
Add a ``||cakLandMotor:stop motors||`` 
```blocks
function react (degrees: number) {
    fwdMotors.servo1.fwdSetAngle(degrees)
    basic.pause(1000)
    fwdMotors.turn(-30)
    basic.pause(2500)
    fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
    }
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.3, fwdSensors.thresholdDirection.under)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
        basic.pause(1000)
        if (Math.randomBoolean()) {
            react(60)
        } else {
            react(10)
        }
    }
})
```
## @showhint
Add a ``||cakLandServos:turn servo at P1 to degrees: (35)||`` block under the ``||Functions:function react||``
also add two more ``||basic:pause||`` blocks and one ``||cakLandMotor:turn left motor at speed: (50)||``
```blocks
function react (degrees: number) {
    fwdMotors.servo1.fwdSetAngle(degrees)
    basic.pause(1000)
    fwdMotors.turn(-30)
    basic.pause(2500)
    fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
    fwdMotors.servo1.fwdSetAngle(35)
    basic.pause(1000)
    fwdMotors.turn(50)
    basic.pause(1000)
}
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.3, fwdSensors.thresholdDirection.under)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
        basic.pause(1000)
        if (Math.randomBoolean()) {
            react(60)
        } else {
            react(10)
        }
    }
})
```
## @showhint
This is the final code
```blocks
function react (degrees: number) {
    fwdMotors.servo1.fwdSetAngle(degrees)
    basic.pause(1000)
    fwdMotors.turn(-30)
    basic.pause(2500)
    fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
    fwdMotors.servo1.fwdSetAngle(35)
    basic.pause(1000)
    fwdMotors.turn(50)
    basic.pause(1000)
}
fwdMotors.setupDriving(
fwdMotors.servo2,
fwdMotors.servo3
)
fwdMotors.drive(fwdMotors.drivingDirection.forward, 50)
basic.forever(function () {
    basic.pause(1000)
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.3, fwdSensors.thresholdDirection.under)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 0)
        basic.pause(1000)
        if (Math.randomBoolean()) {
            react(60)
        } else {
            react(10)
        }
    }
})
```
