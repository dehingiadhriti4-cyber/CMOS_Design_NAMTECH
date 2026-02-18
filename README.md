# CMOS_DESIGN


# Introduction to Circuit Design and Spice Simulations

## Lecture 1:- Why do we need SPICE simulations?
- All the logic gates such as NAND, NOR, OR, AND etc are implemented at the transistor level using combinations of PMOS (p-channel MOSFET) and NMOS (n-channel MOSFET) devices arranged in specific configurations. They perform their required functionality of that particular respective gate. Example- Inverter.
<img width="495" height="378" alt="image" src="https://github.com/user-attachments/assets/93ef85d4-0137-4bb4-8929-32b889fe4741" />

This circuit is fed with some wavefrom to identify the output response, the characteristic curve of this circuit decide the delay and based on that delay we will get the W/L ratio of the particular transistor using SPICE simulation.
<img width="890" height="698" alt="image" src="https://github.com/user-attachments/assets/39991449-4568-4f5f-b87c-84bf0f80ccde" />

## WHy do we need SPICE?
-The physical design flow, clock tree synthesis, crosstalks, and timing are built on SPICE (Simulation Program with Integrated Circuit Emphasis),it allows designers to analyze, verify, and optimize a circuit’s performance using delay tables before physical fabrication.

-Assume that the given circuit has undergone Clock Tree Synthesis (CTS), where multiple clock buffers have been inserted throughout the design. These buffers are sized appropriately to drive varying capacitive loads at different output nodes, ensuring balanced clock distribution and controlled skew across the network.
<img width="1077" height="389" alt="image" src="https://github.com/user-attachments/assets/a8d2b6e3-a367-4466-bb4b-ab6639f3ec2f" />

- We receive a "Delay Table" with input slew and output load following the SPICE simulation. 
- Delay is defined as the intersection of the input slew and output load values. 
- There are delay tables displayed for both level 1 and level 2 buffers. This is calculated by circuit design and simulation.
<img width="1223" height="669" alt="image" src="https://github.com/user-attachments/assets/68c95e15-e176-41d7-9fcf-7fad4f53abed" />

The circuit design process employing SPICE simulations is the source of the delay tables seen above. Characterization of any CMOS logic is part of SPICE simulations.
- Due to lower drive and higher drive of 

## Lecture 2:- Introduction to basic element in circuit design-NMOS
-An NMOS transistor is a four-terminal device built on lightly doped p-type substrate, with two heavily doped n-type regions which are source and drain . The isolation region isolate the transistor from other transistor,There is a thin gate oxide layer of Silicon Dioxide separates gate from semiconductor and prevents direct current flow and above it metal or Polysilicon is deposited which is the gate terminal.
<img width="1094" height="472" alt="image" src="https://github.com/user-attachments/assets/8496d382-0ad1-4808-85e7-7c59f506080c" />

## Threshold Voltage (Vt)
Threshold voltage is the minimum gate-to-source voltage required to create a conducting channel in an NMOS transistor. It determines when the device turns ON and controls current flow, switching speed, and power consumption.
## Threshold Voltage Modelling
- Let Vgs=0
- Drain, Source and Body is connected to GND
- Substrate-Source(B-S) and Substrate-Drain(B-D) form p-n junction diodes
- Both junctions are OFF, no conduction path between source and drain hence Source-Drain resistance is High
  
<img width="1185" height="425" alt="image" src="https://github.com/user-attachments/assets/d0643f77-6f5f-4c70-be2a-90ab2f123416" />

**When small voltage is applied(Vgs<Vth)**

<img width="763" height="445" alt="image" src="https://github.com/user-attachments/assets/be0b6d73-a480-4b08-83c4-b003a61c4566" />

- Positive charges appears on gate surface
- An electric field is created from gate toward substrate
- It forms oxide capacitor, holes(majority carriers in P-substrate) are pushed away from substrate
- Fixed negative acceptors ions remain near to the surface
    
<img width="780" height="385" alt="image" src="https://github.com/user-attachments/assets/0ac8b1bf-641c-4408-a6e7-2469eb9e7b25" />

- Due to negative charges accumulation, a depletion layer forms under the gate where majority carriers are delpeted.

## Lecture 3:- Strong Inversion
**When we increase the gate voltage(Vgs=Vth)**

<img width="769" height="425" alt="image" src="https://github.com/user-attachments/assets/c479621c-5c1f-49c9-bc3c-0cfe98084bea" />

- Width of the depletion region increases
- More number of electrones accumalate at the surface
- Finally it reached at a point where the surface region of the substrate gets completely inverted to n-type material which is known as inversion layer.This is called **strong inversion** or **surface inversion**.

**When we increase the gate voltage further(Vgs>Vth)**

<img width="477" height="396" alt="image" src="https://github.com/user-attachments/assets/6575192f-8f2f-4c32-871f-1683ff147461" />

- Large number of electrons are accumulated the surface
- The positive potential of the gate area attract the negative charge particle from the n+ source area like a magnet
- Channel width get increased and no change of the depletion layer width
- 
<img width="503" height="411" alt="image" src="https://github.com/user-attachments/assets/264ecd41-982b-4f01-80b1-318555beb6d5" />

- There will be a point at which a continuous n-channel formation from Source to Drain, posibility of current flow whose conductivity is modulated by Vgs
- Initially Vgs=0, the Source to Drain resistance is so high, there was absolutely zero current flow

  **Case 1(Vsb=0)**

<img width="494" height="469" alt="image" src="https://github.com/user-attachments/assets/5ada57f4-4f1d-49e4-a19c-6f680c0474dd" />

- When Gate to Source potential will be increase, a strong inversion is observed here
- Semiconductor surface inverts to n-type material at Vgs=Vto,Vsb=0(say)
- Threshold voltage equation:- Vth=Vto
    
**Case 2(Vsb=positive potential to the source and negative potential to the body)**

<img width="629" height="479" alt="image" src="https://github.com/user-attachments/assets/6a646079-757e-4efd-8cac-c41dc1c6c1a5" />

- Depletion region will be slightly high near 'S', there is more additional reverse bias between Source'S' and Body'B' to this p-n junction diode
- More holes (positive charges) are drawn deeper into the substrate and away from the surface as a result of the increased electric field between the source and the p-substrate.
 - Due to positive Vsb few charges from channel are pulled towards source 'S'
 - This indicates that more ionized acceptor ions, or negative fixed charge, are left behind close to the surface, more gate voltage is required to form inversion, causing the threshold voltage to increase. This phenomenon is called the **body effect**.
- When we increase Vgs more then finally at some potential Vgs=Vth+V1, additional potential V1 needed for the strong inversion of the surface due to Vsb=+ve
- Threshold voltage equation:-
<img width="622" height="248" alt="image" src="https://github.com/user-attachments/assets/f7293435-f519-4900-9a78-78579c32a64c" />

- Vto is the threshold voltage at Vsb=0

<img width="403" height="230" alt="image" src="https://github.com/user-attachments/assets/0b67a726-ba6c-4cca-bb1c-af95c3e185a8" />

- γ is the body effect coefficient, it shows how strongly Vth changes with Vsb.It depends on substrate doping and oxide capacitance.

<img width="486" height="137" alt="image" src="https://github.com/user-attachments/assets/a8770307-b5a4-46ad-a1fd-cb3081cf4a08" />

- φF is the Fermi potential of the substrate, represents energy difference between fermi level and intrinsic level
- NA is substrate doping concentration

- This all vales are fef into SPICE simulator, SPICE tool derive the threshold voltage, that threshold voltage represent the device NMOS
- This is about the behaviour of the NMOS below threshold.

# NMOS resistive region and saturation region of operation
## Lecture 1: Resistive region of operation with small drain-source voltage

<img width="637" height="422" alt="image" src="https://github.com/user-attachments/assets/cf132d5e-5424-4ebb-a027-92e421bdc52f" />

- When Vgs>Vth, it attract a large number of electrons to the surface
- Hence in the channel Induced charge(Qi) is directly proportional to (Vgs-Vt). This excess voltage, known as the overdrive voltage, creates additional mobile electrons in the channel, increasing the drain current.
- Let's analyze at Vgs=1v and small Vds (say 0.05V). Assume at(NMOS)=0.45V
<img width="658" height="402" alt="image" src="https://github.com/user-attachments/assets/eb30a6e8-07e0-4150-a07b-ccd953223c88" />

- Vgs=1v, it is good enough to create a short circuit channel between the source and drain.
- Vgs>Vt, the transistor will turn ON
- Because the source is grounded and the drain is at a positive voltage, a voltage gradient develops along the channel from source to drain.

<img width="768" height="485" alt="image" src="https://github.com/user-attachments/assets/f2c78b40-0e67-4122-9866-bc98840a2eca" />


- Plotting a graph with the y-axis denoting channel charge/strength and the x-axis showing the channel length (from 0 to L, taking into account that L ≈ Leff)
    - When VDS is not present, the gate overdrive voltage (VGS − Vt) is the same at all points along the channel.
    - The local channel potential changes from 0 at the source to VDS at the drain when VDS is applied, becoming V(x).
    - As a result, the channel charge gradually drops from source to drain, and the effective overdrive at any time x becomes (VGS − V(x) − Vt).
  
- **Channel Length (L)**:- The channel length is the physical distance between Source and Drain defined during fabrication. It is physical gate length.

- **Effective Channel Lenght(Lₑff)**:- The actual conducting channel length after fabrication effects.
   - Leff=L−2ΔL

     
  



  
  


    

    


  










