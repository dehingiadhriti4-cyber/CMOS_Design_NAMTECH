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
    - As a result, the channel charge gradually drops from source to drain, and the effective overdrive at any time x becomes (Vgs − V(x) − Vt).
    - Q(i) = -Cox([Vgs − V(x)] − Vt)
- **Channel Length (L)**:- The channel length is the physical distance between Source and Drain defined during fabrication. It is physical gate length.

- **Effective Channel Lenght(Lₑff)**:- The actual conducting channel length after fabrication effects.
   - Leff=L−2ΔL
 <img width="556" height="339" alt="image" src="https://github.com/user-attachments/assets/a807161d-83c9-4a93-93b5-04842c678a51" />

 ## Lecture 2: Drift current theory

 <img width="555" height="525" alt="image" src="https://github.com/user-attachments/assets/a67c0814-2aac-402a-8b50-2cc47af1cdbd" />

 - In the channel (yellow region below), the induced inversion charge at any point x depends on the local gate overdrive voltage.
 - The effective gate voltage at location x is VGS − V(x) because the channel potential changes throughout its length.
 - The local overdrive voltage at location x is proportional to the inversion charge per unit area.

<img width="408" height="401" alt="image" src="https://github.com/user-attachments/assets/a7a3efa3-c829-48b2-8e8b-261ae1d2eeb8" />

 - From device physice point of view, we have two types of current
    - **Drift current** :- The current caused by the movement of charge carriers due to an applied electric field.
    - **Diffusion current** :- The current caused by the movement of charge carriers from high concentration region to low concentration region.

<img width="1195" height="682" alt="image" src="https://github.com/user-attachments/assets/1aa26eeb-9297-4cce-9aa3-790d6be20e15" />

 
 - Drift current(Id)= (Velocity of charge carriers x available charge)
   
## Lecture 3: Drain current model for linear region of operation

<img width="409" height="130" alt="image" src="https://github.com/user-attachments/assets/c3d2484d-0d39-43b1-9cef-0918e26b562a" />

- Substituting and integrating dx over channel length L with give the V-I relation of NMOS transistor
<img width="431" height="133" alt="image" src="https://github.com/user-attachments/assets/d5846991-ade0-4523-852d-ef80f495d029" />

- Integrate over length L on LHS and over drain-source voltage Vds on RHS we get the below
<img width="404" height="49" alt="image" src="https://github.com/user-attachments/assets/0eff1261-45d3-4941-84cb-47854bbda7aa" />

- μn, ​Cox, ​L/W are technology parameters

<img width="402" height="71" alt="image" src="https://github.com/user-attachments/assets/63b20a70-3484-4f4e-880d-4d6759f6b6e6" />

- Considering kn= unCox, where kn is the process transconductance, which determines how effectively the device converts gate voltage into drain current.
<img width="399" height="76" alt="image" src="https://github.com/user-attachments/assets/d29a8631-725d-4cd7-a866-3b4b20aee7ff" />

- The drain current is still a quadratic  function of Vds, after further simplification, we obtain
<img width="443" height="262" alt="image" src="https://github.com/user-attachments/assets/25f62945-2904-48a3-a1ee-9be2c197783d" />

- Therefore all values of Vds ≤ (Vgs − Vt), the MOSFET operates in the resistive (linear) region.
- In this region the channel is  uniform from source to drain and the MOSFET behaves like a **voltage-controlled resistor**.

## Lecture 4: SPICE conclusion to resistive operation

- To analyse the impact of Vgs and Vds on the drain current(Id), we consider different values of both voltages.
- For a given VGS, the device remains in the linear (triode) region as long as Vds < (Vgs − Vt).
  <img width="496" height="134" alt="image" src="https://github.com/user-attachments/assets/2c6f1f07-e7d1-40de-856e-893a4b5e10e8" />

- To calculate ID for different values of VGS, at every value of VGS, sweep VDS from 0 till (VGS − Vt).
- In this region, drain current(Id) follows the linear-region equation, and SPICE simulations can be used to obtain and verify the Id–Vds characteristics for each Vgs.
  
## Lecture 5: SPICE conclusion to resistive operation

<img width="1233" height="584" alt="image" src="https://github.com/user-attachments/assets/54f571ed-d057-4b84-b368-376b32fd9124" />

- when (VGS − VDS) > Vt, the effective gate voltage at the drain end remains higher than the threshold voltage even. This indicates that even at the drain side, inversion is maintained.
- A continuous conducting path connects source and drain because inversion occurs across the channel from source (x = 0) to drain (x = L).
- Under these circumstances, the device functions in the linear (triode) region, and for small values of VDS, the drain current rises roughly linearly with VDS.

<img width="1209" height="582" alt="image" src="https://github.com/user-attachments/assets/74a6de03-35c7-44f6-ae18-b5e76b76937f" />

- When Vgs-Vds = Vt, the effective gate voltage at the drain end becomes equal to the threshold voltage. At this point, inversion just begins at the drain side, so the channel thickness reduces to zero there and the channel starts to pinch off (disappear) near the drain. This is called **pinch-off**.
- In the pinch-off region, the channel disappears near the drain, but current does not stop. Electrons are swept into the drain by a strong electric field, and the MOSFET enters saturation. The drain current becomes almost constant and is mainly controlled by Vgs.

<img width="1236" height="588" alt="image" src="https://github.com/user-attachments/assets/a73a35ad-d268-4116-b5f2-bc4dd89f6fce" />

- When Vds exceeds Vgs-Vth, the MOSFET enters the saturation region. At this point, the drain end no longer satisfies the inversion condition, and pinch-off occurs near the drain.
- No channel present at the drain side, as the result of that the area near the drain channel got disappeared, some channel present in the source area, this is referred as saturation region and cannot do anything further.
- As Vds increases further beyond Vgs-Vth, the pinch-off point moves slightly toward the source.

## Lecture 6: Drain current model for saturation region of operation

- When Vgs-Vds ≤ Vt, the channel disappears at the drain side
- In the saturation region, the channel voltage is approximately fixed at Vgs-Vt, unlike in the linear region where it changes along the channel as V(x).
- Ideally, the drain current becomes independent of Vds and is primarily determined by Vgs-Vt, provided channel length modulation is ignored.
<img width="399" height="227" alt="image" src="https://github.com/user-attachments/assets/fb104807-7c02-42c9-8b13-8aedcb7091f5" />
- Replace Vds by Vgs-Vt
<img width="435" height="207" alt="image" src="https://github.com/user-attachments/assets/da32c0c3-7a05-4bba-adde-e4e1c76b09c9" />


- Drain Current (Id) is no more linear function of Vt, if we keep Vgs at constant value and increase Vds as such extent Id act as a constant current 
<img width="268" height="90" alt="image" src="https://github.com/user-attachments/assets/0f4b78f4-c262-41ce-b8b3-219c054ad95f" />

- Drain current(Id) looks to be a perfect current source because it is the function of all the constants.
- But somewhere it's not true, effective channel length is reduced, is moduleted by applied Vds.
- Drain current is increase a bit when Vds increases, depletion resion at the drain increases( minor linear function of Vds)
<img width="726" height="131" alt="image" src="https://github.com/user-attachments/assets/9378f5ea-39d8-4c97-ace1-ca3a38f9b1ca" />

- Drain current is slightly increase when Vds is increases






  ​

  


 
   


   
   
       



     
  



  
  


    

    


  










