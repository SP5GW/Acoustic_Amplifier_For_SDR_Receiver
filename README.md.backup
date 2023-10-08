                                                                                                      
**<p style="text-align: center;">Acoustic Amplifier for SDR Receiver</p>**
<p style="text-align: center;">Rev. B, August 2023, Andrzej SP5GW</p>
<p align="center">
<img src="./img/amp_front.jpg" width="300" height="200"/>
<img src="./img/amp_internal_view_1.jpg" width="300" height="200"/>
</p>
**Key Requirements**

The main requirements for this amplifier are the following:

* It shall be possible to connect it to the output of sound card of the PC or Raspberry Pi.The output volume of the sound card shall be set to approximately 80% of maximum value.
* The amplifier shall be monophonic, but it shall accept stereo input signal.
* It shall be possible to control, both volume and tone using same knobs for headphone and speaker channels.
* It shall be possible to control tone of voice starting from about 2.5kHz (the assumption is that SSB emission is limited in bandwidth to about 3kHz).
* Amplifier bandwith shall be not less then 100Hz - 10kHz.
* It shall be possible to use USB socket of the PC as power source, but option to connect other power supply shall exist (9-12V DC input).
* It shall be possible to switch between headphones and speaker with toggle switch, which also acts as on/off switch.
* Use of headphones or speaker shall be indicated by LED.
* All audio sockets shall be 3.5mm mini jack type.
* USB port shall be micro USB type.

**Architecture**

Amplifiers design is based on:

* AVT 1744 (10W Power Amplifier  based on TDA2003),
* AVT 794 (Power Amplifier with LM386)

Toggle switch SW1 selects, which one of two power amplifiers is powered on at given moment making it possible to select between speaker and headphone operations.

CB BV-550 8ohm 5W spkeaker  from Blow is used together with Sony MDR-V150 standard computer headphone speakers. Spkear and headphone makes are not critical.

The following componets outside AVT kits were also added:

* Automatic power source selector based on Shotkey diodes D2 and D3 (source supplying higher voltage is selected).
* EMC filter based on L1 and C8, C9 and C10
* Stereo to mono signal mixer based on resistors R1 and R2
* Volume and Tone control including signal divider based on  RV1, RV2, C1, R3 and R4
* Bi-color LED is used in actual design instead of LED D1 and D4

Attempt was made to skip dedicated amplifier in headphone channel, but then it was not possible to find well working passive volume/tone control, which would control both speaker and headphones. This was a reason for adding AVT 794 to the design.

Input voltage divider (R3 and R4) is designed to lower the maximum volume of the device to comfortable level and at the same time make speaker and headphone channel volume levels comparable for the same setting of volume knob RV1. In practice this means that headphone channel acts as power attenuator (approx. 40% attenuation) (see Fig. 1) while speaker channel amplifies input signal from PC's sound card by approx. 2.6 times (see Fig. 2).

When USB is used as a DC power source then in order to avoid distortions of output signal (see Fig. 3) the level of input signal provided by the sound card shall be reduced to the amplitude not exceeding 680mV. 

To avoid EMC interference shielded or twisted cables where used to interconnect all the modules. Positioning of the PCB boards have been also optimized with EMC in mind.

Especially EMC prone components such as tone control RV2 were grounded (chassis). Interconnect cable between RVmax and RVslider on AVT 794 was twisted with ground wire for the same purpose.    

**Characteristics Measurements**

**Simulations**

* Simulation results of EMC filter
LTSpice simulation of EMC filter has been conducted to mainly find out minimum value of inductor used. Results are depicted below:
<p align="center">
	<img src="./ltspice/EMCFilterSimulationCircuit.png" width="600" height="300"/>
	<img src="./ltspice/EMCFilterSimulationResult.png" width="600" height="800"/>
</p>

* Simulation result of Tone control circuit
Simulation of tone control circuit suggests that better results (less attenuation of frequencies above 1kHz in potentiometer position when tone control shall have minimum impact) can be achieved when using 1Meg potentiometer. This is potential future improvement.
<p align="center">

	<img src="./ltspice/ToneControlSimulationCircuit.png" width="600" height="300"/>
	<img src="./ltspice/ToneControlSimulationResult.png" width="600" height="800"/>
</p>


**References**