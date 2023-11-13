---
title: "Parts Documentation"
excerpt: ""
---

Here you will discover all the research and planning that went into finding the parts for my go-kart. Every component, from the bolts to the motor will be broken down. You will learn not only how the parts fit together, but how each part works along with pictures and facts I learned about them along the way.




<details>
<summary><b>Electrical Parts</b></summary>



<h1>DC Motor</h1>


<h2>What is a DC Motor?</h2>

A DC motor is the simplest kind of motor and has been used for decades due to their simplicity and low cost. There are two types of DC motors—the older brushed DC motors (BDC), and the newer and more efficient brushless DC motors (BLDC). First, let's understand how a BDC motor works. In the core of a BDC motor, there are permanent magnets. This is known as the stator, which remains in place. In the center, there is a commutator, which spins and has coils of wire. When current is induced into the coils, they create a magnetic field that interacts with the field of the stator. By reversing the polarity of the induced current into the coils at the right time, you can get the commutator to 'chase' the poles of the stator and thus spin. This current is controlled by the motor controller which we will discuss later. The reason the motor is brushed is that to deliver the current, metal brushes drag against the coils. This can inefficient, because over time the brushes wear down due to friction and general wear and tear, causing them to be less efficient. Thus a BDC is not as efficient as a BLDC at converting electrical energy into mechanical energy. Now let's examine how a BLDC solves the issues of a BDC. In a BLDC, the permanent magnet is now the commutator, and the coils are the stators. There are three coils. As current is induced in a coil, it will attract the magnet. At the same time, the coil behind it will energize in the opposite polarity, pushing the magnet away. As the magnet rotates, the coils are energized to carefully coordinate the rotation. To do so, a Hall Effect Sensor must be used, which is what makes BLDC motors more expensive and complicated. However, since the motor can use energy more efficiently, and does not suffer from the same energy losses that a BDC does, it is much more efficient and powerful.


<h2>The Part I Chose</h2>

When selecting an adequate motor, there were a few considerations I had to keep in mind. The first was the required voltage. I had already selected a 48V system, and thus could only choose motors that delivered peak power at 48V. Then, I had to select which company I wanted to purchase the motor from. After research, the company with a clear advantage was Motenergy. It delivered high quality and has a long history of creating innovative products. The next consideration was whether I wanted a brushed or brushless motor. In the end, cost was the deciding factor. While a BLDC would have been more powerful and efficient, the cost was very high. Just for the motor it would have cost me somewhere around 1000 dollars, and I would still have to buy almost 1000 dollars more in supporting electronics. The cost of the kart would have been too much. Selecting this motor taught me an important lesson on the impact cost has on engineering. While there may have been a better option, I had to work within my budget, and therefore had to settle for a slightly worse part. Engineers face such constraints everyday, and I was glad I learned this lesson now. Now that I had slected a 48V BDC motor from Motenergy, I had to find the right model. Eventually, I settled on the ME-0909, which delivered 4.8 continuous kW at 100 amps, and 15kW for 30 seconds. The motor cost $550, and I was happy with the balance of power and cost.





<h1>Batteries</h1>


<h2>What is a Battery?</h2>

Simply put, a battery is a store of electrical energy. The proper term would be a cell, and a battery is multiple cells put together. A cell consists of an anode (the negative side), a cathode (the positive side), and a chemical mix in between. Common chemical mixes include lithium-ion or lead acid. To create electricity, electrons must flow. To do this, the battery creates a potential difference between the anode and cathode (this is what the chemical mix is for). This causes electrons to build up at the anode. Since there is an imbalance, the electrons want to go to the cathode, but are blocked by the chemical mix. However, when you apply a load to the battery, electrons can now begin to flow, creating electricity. But as electrons flow, they interact with the chemical mix, eventually causing the battery to run out of charge. To recharge the battery, current is run backwards through the battery, reversing the chemical process. We measure the potential difference across the terminals in volts, and the amount of energy the battery can provide in amp-hours or watts.


<h2>The Part I Chose</h2>

To select my battery, I needed to balance cost, weight, and capacity requirements. Firstly, the batteries I chose had to be 48V. I could either directly purchase 48V batteries, or wire up lower voltage batteries in series to achieve 48V. To decide, I looked at the size and cost of batteries. Noticing 48V batteries were far too expensive, I decided to wire up 4 12V batteries in series. Once I had determined that, I had to decide what type of battery I wanted. While lithium based batteries were more powerful, their cost was a limiting factor, and so I settled on deep-cycle sealed lead acid AGM batteries. Finally, I needed to select an amp-hour rating. Batteries with larger amp-hour ratings would last longer, but I knew they would be heavier and more expensive. I eventually decided on buying 4 12V 35Ah batteries from Weize, as they both fit my specifications and were within my budget. 





<h1>DC Motor Controller</h1>



<h2>What is a DC Motor Controller?</h2>

To control the speed and torque of a DC motor, a controller must be used. Since a DC motor's speed/torque curve is inversely linear, control is relatively simple though. Additionally, since a BDC motor does not require a Hall Effect sensor like a BLDC motor, it is even more simple. However it is still important to understand how such controllers work. To modulate the speed and torque of the motor, the controller simply regulates the amount of voltage applied to the motor depending on the position of the throttle (which we will discuss later). To run the motor in reverse, the polarity of the supplied current is simply reversed. The most simple control circuit is the H-Bridge. In the circuit, 4 switches are arranged in a square with the motor in the middle, forming a H shape. As seen in the diagram, when switches 1 and 4 are closed, current flows into switch 1, into the motor, and out of switch 4 back to the battery. However if switch 2 and 3 are closed, current flows the opposite direction through the motor. To control the voltage, a microcontroller must be used in tandem with the controller. This is called non-regenerative drive. However, to add more complexity, a more advanced controller must be used. For high amperage motors, a PWM controller must be used. PWM stands for pulse width modulation, and is used to control delivered voltage. If the controller sends the motor 12V for 2/3 of the run time, and 0V for the remaining 1/3, the motor will believe it has received 8V. This is called the duty cycle, and is controlled by switching a semiconductor on and off. By changing how long the semiconductor is on and off, the voltage of the motor can be controlled. This is much more efficient than old methods, like rheostats or potentiometers. The final control method is armature or variable resistance. By using variable resistors, the controller can vary the resistance of the circuit, and by keeping the amperage constant, the voltage will change (remember, V=IR). This method however results in high heat losses and is thus rarely used. The final point is regenerative drive. When a motor is accelerating forward, its speed (the actual movement of the motor) and its torque (the force being applied to the motor) are in the same direction. But when you brake, and switch the polarity of the motor, suddenly the direction the motor is turning and the direction the force is acting are different. This effect causes the motor's voltage to exceed its supply voltage. Since the potential difference of the circuit has now switched, current will flow backwards from the motor to the batteries. And recalling how batteries are charged, this current flow will recover energy. A more complex controller is required to conduct regenerative braking, but by having the proper circuitry, an electric vehicles battery life can be increased dramatically.  In the end, most complex controllers are mixes of different types of control circuits, and the presence of regenerative drive varies by controller. The most important thing to remember is that to control direction, and H-Bridge is used, and to control voltage (and thus speed), a PWM is used.


<h2>The Part I Chose</h2>

The controller I selected was the Alltrax SR48300. It is a high amperage controller that uses a PWM to control speed. It does not have an integrated H-Bridge to control motor direction, and relies on external circuitry to do so (we will discuss that later). I chose this controller because Alltrax has a long reputation of providing high-quality controllers. Another brand I considered was Kelly, but the support resources on their website lacked compared to Alltrax, and so I settled on Alltrax. The controller can handle a max amperage of 300 amps, well above my motor's rating. However, I chose not to select a regenerative braking option due to the excess cost. The main input to the controller are the battery and motor connections, a connection from the main contactor, and connections to the startup circuit (throttle and switch). Overall, I was happy with the quality and features of the Alltrax controller. 





<h1>Electrical Contactor</h1>



<h2>What is an Electrical Contactor?</h2>

A contactor is a large device used to switch a circuit on and off. It is similar to a relay, but able to handle much higher voltages and amperages. It is often confusingly called a solenoid. There are three main components of a contactor. The first is a coil/electromagnet. This is the component that will provide the force to open and close the contactor. The next component is the enclosure, which seals and insulates the contactor. Finally, the contacts themselves. These contacts will carry current when the contactor is closed. To activate a contactor, a potential difference is created across its terminals. This energizes the electromagnet creating a magnetic field. This magnetic force created by the filed causes the contacts to physically shut, completing the circuit. You will hear a loud click when the happens. From here, current can now flow through the contactor to the rest of the circuit. A contactor is necessary because without it, the sudden surge of current could damage the controller. By allowing current to slowly build up and pass through, the contactor ensures the right amount of current flows through the circuit. To initially energize the contactor, the startup circuit is used.


<h2>The Part I Chose</h2>

The contactor I chose is the 200A 48V JCC-200. This contactor matched the specifications for a contactor that Alltrax outlined in their data sheet, and was available for a reasonable price. 





<h1>Fuse</h1>


<h2>What is a Fuse?</h2>

A fuse is an electrical component that stops too much current from flowing through a circuit. It can be though of as an intentional weak point in a circuit that will break in the event of over-current or abnormal temperatures. A fuse consists of a strip of metal that spans a glass body. When the current is too high, the metal will melt, thus breaking the connection. However, some fuses have time delays built in. This is for circuits where a momentary over-current is acceptable (like starting up a motor). This is achieved by having a small connector attached to a spring. The spring is stretched and the connector is soldered in place. When there is a momentary overload, nothing happens, but if the overload persists, the solder melts and the fuse becomes a normal fuse, and will blow as normal.


<h2>The Part I Chose</h2>

The part I chose is a 300A Bussmann Forklift Fuse. Since there is an option with my motor to provide 300 amps for 30 seconds, I had to choose a fuse with such a rating. This is the main fuse protecting the drive circuit. However, I also needed to integrate a smaller fuse to protect the startup circuit. For this I chose a small 100A fuse. This would prevent the control circuit from burning out, thus preventing me from turning the kart on and off.





<h1>Pre-Charge Resistor</h1>



<h2>What is a Pre-Charge Resistor?</h2>

All controllers have built in capacitors. When a circuit is powered on, these capacitors will attempt to draw the maximum available currents in order to charge, thus causing damage to the controller. To prevent this, a pre-charge resistor must be used as a sort of valve. When a resistor and capacitor are wired together, they create an RC circuit. When charging, the capacitor will now follow an exponential charging curve dictated by the expression V<sub>c</sub> = V(1-e<sup>-t/τ</sup>). Where V<sub>c</sub> is the charge voltage, V is the supplied voltage, t is the charge time, and τ is the time constant calculated by resistance times capacitance. So by adding an appropriately sized resistor to the drive circuit, the capacitors will now take around five time constants to charge to the steady state system voltage of 99.33%. This steady rate of charge prevents any damage to the circuit, whether that be the controller or contactor.


<h2>The Part I Chose</h2>

The resistor I chose was rated at 10W 470Ω. this resistor fit the specifications required by the Alltrax controller.





<h1>Diode</h1>



<h2>What is a Diode?</h2>

A diode is a semiconductor that has basically infinite resistance when current is run through it in one direction, and basically no resistance in the other direction (I say basically because nothing is perfect). It essentially acts as a gate for current. When the motor is running, the battery pack has a higher voltage rating, and thus the potential difference causes current to flow to the motor and through the open side of diode. However when the circuit is shut off, the motor still has some inductive energy. This creates a potential difference in the opposite direction causing current to flow back the other way. While this is okay when controlled (ie. when used in regenerative braking), if it is not controlled the circuit could be damaged. The diode essentially holds back this 'backwash' current. To ensure proper wiring, the diode should be wired in parallel to the motor, and should be oriented in the right direction.


<h2>The Part I Chose</h2>

I selected a 3 amp coil suppression diode for the project. Again, as with the contactor and resistor, the diode met the required specifications for the controller. To mount it, I attached it to the corresponding poles on the contactor.





<h1>Fuse Holder</h1>



<h2>What is a Fuse Holder?</h2>

While electrical fuses can be wired straight into a circuit, it is often not the safest idea. Fuses can get very hot when nearing their highest rated current and so could damage other components. Additionally, if not wired in properly, the flow of current may be restricted, generating excess heat. Rather, we should use fuse holders. These holders have an integrated area to hold the fuse, and connection points to the rest of the circuit. This isolates the fuse in case of failure and prevents current or voltage leakage. While not a critical electrical component, increasing the robustness of the circuit is always a good idea, and so fuse holders should be used.


<h2>The Part I Chose</h2>

Since there were two fuses, I needed two separate holders. For the startup circuit fuse, I simply found a fuse holder in the shop where I was working. However, the main drive fuse had a 'forklift' design, and thus required me to order a specialized forklift fuse holder from Amazon. 





<h1>Throttle</h1>



<h2>What is a Pot Box Throttle?</h2>

A throttle is any device used to control the speed of a motor. For small scale electric vehicle projects, the industry standard is to use what is known as a pot-box throttle. This type of throttle has an integrated 0-5V potentiometer. When the throttle is actuated, the potentiometer is turned, thus varying the voltage the throttle sends to the controller. Additionally, the throttle often has an integrated microswitch that breaks the circuit when the throttle isn't pushed down, adding another layer of safety to the circuit.


<h2>The Part I Chose</h2>
The throttle I chose was the Curtis PB-6 throttle. It is a lever actuated pot-box throttle. I chose a lever actuated version because the go-kart frame already had an integrated pedal. Thus, by connecting the pedal with the throttle I now had a working throttle. The throttle had four wire connections to the rest of the circuit. The two pole microswitch runs to the ends of the startup circuit. The main output wires run to the controller, which is used to modulate motor speed.





<h1>Wiring</h1>



<h2>What is Wiring?</h2>

Wiring is what joins the electrical components in a circuit. It is a relatively simple process, but there are some considerations that must be taken into account when wiring. First is the size of the wire. Depending on the amperage of the circuit, a wire size must be chosen. If the wire is too small, there will be more resistance, and it could damage the circuit. After that, you must understand what kind of connectors you need. There are many connectors, like spade, ring, or block connectors. Making sure you have the right equipment is very important. To create a wire, you first measure the length needed, then strip a small length of the insulating material off of each end. Then you crimp the appropriate connector to both ends before applying heat shrink wrap to the ends. 



<h2>The Part I Chose</h2>

I chose to use 4 AWG wire for my circuit. This size of wire can adequately carry the currents in my circuit. I used mainly ring connectors, but for some connections into the controller, I had to use spade connectors.





<h1>Switch</h1>



<h2>What is a Switch?</h2>

An on/off switch is a simple electrical component used to open or close a circuit. It is important to keep the circuit open when not in use to prevent current from flowing,, and thus a switch is very important.


<h2>The Part I Chose</h2>

I chose a very simple on/off switch which I wired into the circuit according to the wiring diagram provided with the controller.
</details>






<details>
<summary><b>Mechanical Parts</b></summary>



<h1>Frame</h1>



<h2>What is a Go-Kart Frame?</h2>

The frame of a go-kart is very important. It holds all the components and provides a solid base for you to sit in. The frame consists of the main baseplate, the steering assembly, tires, engine mounting plate, and seat.


<h2>The Part I Chose</h2>

The frame I chose was a 1990 Manco go-kart. I found the frame on Facebook Marketplace, and after inspection, I was happy with the build quality. The frame was setup in the racing style of go kart, with a wide back and tapered front end. The integrated components were small, but the weight was quite low. Overall, it was a solid frame to build the go-kart on.





<h1>Steering Assembly</h1>



<h2>What is a Steering Assembly?</h2>

The steering assembly of a go-kart is surprisingly complicated. It all starts with the steering column. With a fixed wheel at one end, the whole column rotates with any steering input. At the end of the column, there are two 'pitman arms' which are just flat bars of metal welded to the column that stick down. Attached to these pitman arms are 'tie rods'. The tie rods attach to another set of pitman arms on the wheel assembly. So for example, when the column is turned to the right, the right tie rod will pull the right wheel in, causing it to turn right. Subsequently, the left tie rod will push the left wheel out, causing it to turn right. 






<h1>Gear Assembly</h1>



<h2>What is a Gear Assembly?</h2>

The gear assembly on a go-kart is what translates power from the motor to the wheel. Some go-karts are considered 'live-axle' where the rear axle is one long axle. So when the axle is driven, it drives both rear wheel. However, my kart has a hub-drive. This means each wheel has its own independent hub, and thus only the rear left wheel is driven. On the motor, a small sprocket is attached. A chain then runs to a larger sprocket on the rear left wheel assembly. When the motor turns it drives this chain assembly, turning the wheel. 


<h2>The Part I Chose</h2>

On my kart, there is a 15 tooth drive sprocket (the sprocket on the motor). This drives a 60 tooth driven sprocket (on the wheel) via #35 chain. This gives the kart a final transmission ratio of 4:1. 





<h1>Brakes</h1>



<h2>What are Brakes?</h2>

The brakes in a vehicle allow the kart to stop. In an electric vehicle, there are tow options for braking—mechanical brakes and regenerative braking. Since my kart does not have regen braking, we will only focus on mechanical brakes. There are two options for brakes on a kart this size—friction or hydraulic. Hydraulic brakes use brake fluid to aid in clamping a caliper around a brake disc, thus stopping the kart. Friction brakes simply tighten a brake shoe around a brake drum with the pressure of your foot to stop the kart. 


<h2>The Part I Chose</h2>

The Manco frame came with friction brakes. Upon inspection, we found the parts to be very old, and decided to fully replace the system with OEM parts. Looking back, it would have been a better idea to simply purchase hydraulic brakes, as they have far superior braking power. However, the brakes are not really required on my kart as I mostly use it for pleasure, and so I will save the brake upgrade for a future time.
</details>







