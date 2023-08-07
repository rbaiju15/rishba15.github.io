---
title: "Parts Documentation"
excerpt: ""
---

Here you will discover all the research and planning that went into finding the parts for my go-kart. Every component, from the bolts to the motor will be broken down. You will learn not only how the parts fit together, but how each part works along with pictures and facts I learned about them along the way.




<details>
<summary><b>Electrical Parts</b></summary>

<details>
<summary>DC Motor</summary>

<details>
<summary>What is a DC Motor?</summary>
A DC motor is the simplest kind of motor and has been used for decades due to their simplicity and low cost. There are two types of DC motors—the older brushed DC motors (BDC), and the newer and more efficient brushless DC motors (BLDC). First, let's understand how a BDC motor works. In the core of a BDC motor, there are permanent magnets. This is known as the stator, which remains in place. In the center, there is a commutator, which spins and has coils of wire. When current is induced into the coils, they create a magnetic field that interacts with the field of the stator. By reversing the polarity of the induced current into the coils at the right time, you can get the commutator to 'chase' the poles of the stator and thus spin. This current is controlled by the motor controller which we will discuss later. The reason the motor is brushed is that to deliver the current, metal brushes drag against the coils. This can inefficient, because over time the brushes wear down due to friction and general wear and tear, causing them to be less efficient. Thus a BDC is not as efficient as a BLDC at converting electrical energy into mechanical energy. Now let's examine how a BLDC solves the issues of a BDC. In a BLDC, the permanent magnet is now the commutator, and the coils are the stators. There are three coils. As current is induced in a coil, it will attract the magnet. At the same time, the coil behind it will energize in the opposite polarity, pushing the magnet away. As the magnet rotates, the coils are energized to carefully coordinate the rotation. To do so, a Hall Effect Sensor must be used, which is what makes BLDC motors more expensive and complicated. However, since the motor can use energy more efficiently, and does not suffer from the same energy losses that a BDC does, it is much more efficient and powerful.
</details>
<details>
<summary>The Part I Chose</summary>
When selecting an adequate motor, there were a few considerations I had to keep in mind. The first was the required voltage. I had already selected a 48V system, and thus could only choose motors that delivered peak power at 48V. Then, I had to select which company I wanted to purchase the motor from. After research, the company with a clear advantage was Motenergy. It delivered high quality and has a long history of creating innovative products. The next consideration was whether I wanted a brushed or brushless motor. In the end, cost was the deciding factor. While a BLDC would have been more powerful and efficient, the cost was very high. Just for the motor it would have cost me somewhere around 1000 dollars, and I would still have to buy almost 1000 dollars more in supporting electronics. The cost of the kart would have been too much. Selecting this motor taught me an important lesson on the impact cost has on engineering. While there may have been a better option, I had to work within my budget, and therefore had to settle for a slightly worse part. Engineers face such constraints everyday, and I was glad I learned this lesson now. Now that I had slected a 48V BDC motor from Motenergy, I had to find the right model. Eventually, I settled on the ME-0909, which delivered 4.8 continuous kW at 100 amps, and 15kW for 30 seconds. The motor cost $550, and I was happy with the balance of power and cost.
</details>

</details>

<details>
<summary>Batteries</summary>

<details>
<summary>What is a Battery?</summary>
Simply put, a battery is a store of electrical energy. The proper term would be a cell, and a battery is multiple cells put together. A cell consists of an anode (the negative side), a cathode (the positive side), and a chemical mix in between. Common chemical mixes include lithium-ion or lead acid. To create electricity, electrons must flow. To do this, the battery creates a potential difference between the anode and cathode (this is what the chemical mix is for). This causes electrons to build up at the anode. Since there is an imbalance, the electrons want to go to the cathode, but are blocked by the chemical mix. However, when you apply a load to the battery, electrons can now begin to flow, creating electricity. But as electrons flow, they interact with the chemical mix, eventually causing the battery to run out of charge. To recharge the battery, current is run backwards through the battery, reversing the chemical process. We measure the potential difference across the terminals in volts, and the amount of energy the battery can provide in amp-hours or watts.
</details>
<details>
<summary>The Part I Chose</summary>
To select my battery, I needed to balance cost, weight, and capacity requirements. Firstly, the batteries I chose had to be 48V. I could either directly purchase 48V batteries, or wire up lower voltage batteries in series to achieve 48V. To decide, I looked at the size and cost of batteries. Noticing 48V batteries were far to expensive, i decided to wire up 4 12V batteries in series. Once I had determined that, I had to decide what type of battery I wanted. While lithium based batteries were more powerful, their cost was a limiting factor, and so I settled on deep-cycle sealed lead acid AGM batteries. Finally, I needed to select an amp-hour rating. Batteries with larger amp-hour ratings would last longer, but I knew they would be heavier and more expensive. I eventually decided on buying 4 12V 35Ah batteries from Weize, as they both fit my specifications and were within my budget. 
</details>

</details>

<details>
<summary>DC Motor Controller</summary>

<details>
<summary>What is a DC Motor Controller?</summary>
To control the speed and torque of a DC motor, a controller must be used. Since a DC motor's speed/torque curve is inversely linear, control is relatively simple though. Additionally, since a BDC motor does not require a Hall Effect sensor like a BLDC motor, it is even more simple. However it is still important to understand how such controllers work. To modulate the speed and torque of the motor, the controller simply regulates the amount of voltage applied to the motor depending on the position of the throttle (which we will discuss later). To run the motor in reverse, the polarity of the supplied current is simply reversed. The most simple control circuit is the H-Bridge. In the circuit, 4 switches are arranged in a square with the motor in the middle, forming a H shape. As seen in the diagram, when switches 1 and 4 are closed, current flows into switch 1, into the motor, and out of switch 4 back to the battery. However if switch 2 and 3 are closed, current flows the opposite direction through the motor. To control the voltage, a microcontroller must be used in tandem with the controller. This is called non-regenerative drive. However, to add more complexity, a more advanced controller must be used. For high amperage motors, a PWM controller must be used. PWM stands for pulse width modulation, and is used to control delivered voltage. If the controller sends the motor 12V for 2/3 of the run time, and 0V for the remaining 1/3, the motor will believe it has received 8V. This is called the duty cycle, and is controlled by switching a semiconductor on and off. By changing how long the semiconductor is on and off, the voltage of the motor can be controlled. This is much more efficient than old methods, like rheostats or potentiometers. The final control method is armature or variable resistance. By using variable resistors, the controller can vary the resistance of the circuit, and by keeping the amperage constant, the voltage will change (remember, V=IR). This method however results in high heat losses and is thus rarely used. The final point is regenerative drive. When a motor is accelerating forward, its speed (the actual movement of the motor) and its torque (the force being applied to the motor) are in the same direction. But when you brake, and switch the polarity of the motor, suddenly the direction the motor is turning and the direction the force is acting are different. This effect causes the motor's voltage to exceed its supply voltage. Since the potential difference of the circuit has now switched, current will flow backwards from the motor to the batteries. And recalling how batteries are charged, this current flow will recover energy. A more complex controller is required to conduct regenerative braking, but by having the proper circuitry, an electric vehicles battery life can be increased dramatically.  In the end, most complex controllers are mixes of different types of control circuits, and the presence of regenerative drive varies by controller. The most important thing to remember is that to control direction, and H-Bridge is used, and to control voltage (and thus speed), a PWM is used.
</details>
<details>
<summary>The Part I Chose</summary>
The controller I selected was the Alltrax SR48300. It is a high amperage controller that uses a PWM to control speed. It does not have an integrated H-Bridge to control motor direction, and relies on external circuitry to do so (we will discuss that later). I chose this controller because Alltrax has a long reputation of providing high-quality controllers. Another brand I considered was Kelly, but the support resources on their website lacked compared to Alltrax, and so I settled on Alltrax. The controller can handle a max amperage of 300 amps, well above my motor's rating. However, I chose not to select a regenerative braking option due to the excess cost. The main input to the controller are the battery and motor connections, a connection from the main contactor, and connections to the control circuit (throttle and switch). Overall, I was happy with the quality and features of the Alltrax controller. 
</details>

</details>

<details>
<summary>Electrical Contactor</summary>

<details>
<summary>What is an Electrical Contactor?</summary>
A contactor is a large device used to switch a circuit on and off. It is similar to a relay, but able to handle much higher voltages and amperages. It is often confusingly called a solenoid. There are three main components of a contactor. The first is a coil/electromagnet. This is the component that will provide the force to open and close the contactor. The next component is the enclosure, which seals and insulates the contactor. Finally, the contacts themselves. These contacts will carry current when the contactor is closed. To activate a contactor, a potential difference is created across its terminals. This energizes the electromagnet creating a magnetic field. This magnetic force created by the filed causes the contacts to physically shut, completing the circuit. You will hear a loud click when the happens. From here, current can now flow through the contactor to the rest of the circuit. A contactor is necessary because without it, the sudden surge of current could damage the controller. By allowing current to slowly build up and pass through, the contactor ensures the right amount of current flows through the circuit. To energize the contactor, the control circuit is used.
</details>
<details>
<summary>The Part I Chose</summary>
The contactor I chose is the 200A 48V JCC-200. This contactor matched the specifications for a contactor that Alltrax outlined in their data sheet, and was available for a reasonable price. 
</details>

</details>

<details>
<summary>Fuse</summary>

<details>
<summary>What is a Fuse?</summary>
A fuse is an electrical component that stops too much current from flowing through a circuit. It can be though of as an intentional weak point in a circuit that will break in the event of over-current or abnormal temperatures. A fuse consists of a strip of metal that spans a glass body. When the current is too high, the metal will melt, thus breaking the connection. However, some fuses have time delays built in. This is for circuits where a momentary over-current is acceptable (like starting up a motor). This is achieved by having a small connector attached to a spring. The spring is stretched and the connector is soldered in place. When there is a momentary overload, nothing happens, but if the overload persists, the solder melts and the fuse becomes a normal fuse, and will blow as normal.
</details>
<details>
<summary>The Part I Chose</summary>
The part I chose is a 300A Bussmann Forklift Fuse. Since there is an option with my motor to provide 300 amps for 30 seconds, I had to choose a fuse with such a rating. This is the main fuse protecting the drive circuit. However, I also needed to integrate a smaller fuse to protect the control circuit. For this I chose a small 100A fuse. this would prevent the control circuit from burning out, thus preventing me from turning the kart on and off.
</details>

</details>

<details>
<summary>Pre-Charge Resistor</summary>

<details>
<summary>What is a Pre-Charge Resistor?</summary>
All controllers have built in capacitors. When a circuit is powered on, these capacitors will attempt to draw the maximum available currents in order to charge, thus causing damage to the controller. To prevent this, a pre-charge resistor must be used as a sort of valve. When a resistor and capacitor are wired together, they create an RC circuit. When charging, the capacitor will now follow an exponential charging curve dictated by the expression V<sub>c</sub> = V(1-e<sup>-t/τ</sup>). Where V<sub>c</sub> is the charge voltage, V is the supplied voltage, t is the charge time, and τ is the time constant calculated by resistance times capacitance. So by adding an appropriately sized resistor to the drive circuit, the capacitors will now take around five time constants to charge to the steady state system voltage of 99.33%. This steady rate of charge prevents any damage to the circuit, whether that be the controller or contactor.
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

<details>
<summary>Diode</summary>

<details>
<summary>What is a Diode?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

<details>
<summary>Fuse Holder</summary>

<details>
<summary>What is a Fuse Holder?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

<details>
<summary>Throttle</summary>

<details>
<summary>What is a Pot Box Throttle?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

<details>
<summary>Wiring</summary>

<details>
<summary>What is Wiring?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

<details>
<summary>Switch</summary>

<details>
<summary>What is a Switch?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

</details>


<details>
<summary><b>Mechanical Parts</b></summary>

<details>
<summary>Frame</summary>

<details>
<summary>What is a Go-Kart Frame?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

<details>
<summary>Steering Assembly</summary>

<details>
<summary>What is a Steering Assembly?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

<details>
<summary>Gear Assembly</summary>

<details>
<summary>What is a Gear Assembly?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

<details>
<summary>Brakes</summary>

<details>
<summary>What are Brakes?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

<details>
<summary>Pedals</summary>

<details>
<summary>What are Pedals?</summary>
</details>
<details>
<summary>The Part I Chose</summary>
</details>

</details>

</details>



