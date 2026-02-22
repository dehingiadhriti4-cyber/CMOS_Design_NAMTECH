<img width="1920" height="892" alt="image" src="https://github.com/user-attachments/assets/f8b11e93-e877-4d58-9934-2821218c047e" /># CMOS_DESIGN


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

  **Threshold Voltage (Vt)**
- Threshold voltage is the minimum gate-to-source voltage required to create a conducting channel in an NMOS transistor. It determines when the device turns ON and controls current flow, switching speed, and power consumption.
  
  **Threshold Voltage Modelling**
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

# Introduction to SPICE

## L1 Basic SPICE setup
- SPICE is a simulation software that contains predefined device models. To generate output waveforms, the user must provide the appropriate input parameters or a properly defined netlist, which the simulation engine then processes to produce the desired results.
- The waveforms are eventually used to calculate the 





  ​

  


 
   
## L3 Define Technology parameters

<img width="519" height="505" alt="image" src="https://github.com/user-attachments/assets/d0252724-ea7d-4cb6-ac25-01bf50a416a3" />

- Now we will look for model of this particular NMOS
- All the model parameters are comes as a package. We give attribute and call model name (it has to correctly match with the netlist) also name given by the foundary
- Inside the brackets, technology paramteters will exist.
  
 <img width="473" height="200" alt="image" src="https://github.com/user-attachments/assets/fd9a8581-00b9-464b-a00e-7de7a37fcb7d" />

- We give description on NMOS and PMOS and the final step is to provide the gate voltage
- We have to give a name of the model```( .lib cmos_model)```

<img width="527" height="319" alt="image" src="https://github.com/user-attachments/assets/5b055c8a-12f9-4b55-b258-47ecf02bf2b1" />

- we just plug in this packaged file in ```.mod``` file and call this file in top level SPICE netlist.
  
<img width="576" height="163" alt="image" src="https://github.com/user-attachments/assets/c684e8d3-4a42-4620-8fac-a7c7224333e2" />
<img width="662" height="577" alt="image" src="https://github.com/user-attachments/assets/b9f35a88-6f5a-4df8-9a16-e88f9cabb4cf" />

- This is the complete SPICE tag and give a name ```NETLIST Description``` on the top and below is ```.include```
- We have to add the simulation command(provide the voltage, sweep the Vgs and Vds for SPICE simulations)

## Lecture-4 First SPICE simulation

- Open Vertual Box
- Type ```cd`` in comand prompt
- ```git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop.git```
- ```cd sky130CircuitDesignWorkshop/design/```
- ```ls```(get list of files)
- ```cd sky130_fd_pr/
- ```ls``` (Contains cells, models and tech files)
- ```cd cells/```
- ```ls```(contains nfet_01 and pfet_01 weight,)
-```nfet_01v8/```

 <img width="1920" height="892" alt="Screenshot from 2026-02-19 12-45-30" src="https://github.com/user-attachments/assets/e659b0a2-b2fa-43bf-97e5-0d6ea19eb534" />

- ```ls```(contains all the libraries)
- Inside nfet we will see spice libraries at different corners, we will select one such typical corner
- We use ```sky130_fd_pr__nfet_01v8__tt.pm3.spice```

<img width="1920" height="892" alt="Screenshot from 2026-02-19 13-17-34" src="https://github.com/user-attachments/assets/a1a5e68f-9f3d-459d-ade1-9dc5c90cae5b" />

 - We will see all the model paramteres required for the process.
 - We use ```sky130_
 - <img width="1920" height="892" alt="Screenshot from 2026-02-19 13-17-34" src="https://github.com/user-attachments/assets/930ca602-610c-4c8d-adf1-950d3863852b" />
  <img width="1920" height="892" alt="Screenshot from 2026-02-19 14-31-50" src="https://github.com/user-attachments/assets/aefd998c-707b-4c1f-8f25-cd72948ac0a7" />

 - We have different W and L values which pre-described. For simulation we need to take any one value which is present inside the library.
 <img width="1920" height="892" alt="Screenshot from 2026-02-19 14-34-11" src="https://github.com/user-attachments/assets/9505ac92-40a0-402b-985b-b92978160a33" />
<img width="1254" height="175" alt="Screenshot from 2026-02-19 14-35-33" src="https://github.com/user-attachments/assets/ccca539f-4b0c-4c2d-a659-01f1c093a0fd" />

 - Now go inside models --> lib.spice file. We will see library files which are present for nfet and pfet. The corner files are present, include Typical, slow-fast and fast-fast corner files
<img width="1459" height="175" alt="image" src="https://github.com/user-attachments/assets/7ab57c72-c1a7-41b7-bd48-e51551e5f8b7" />

<img width="1920" height="892" alt="Screenshot from 2026-02-19 14-39-23" src="https://github.com/user-attachments/assets/3c74b2d6-3812-4b65-a3b3-5d61c48657f0" />

<img width="1920" height="892" alt="image" src="https://github.com/user-attachments/assets/22be82cf-e225-4d7c-be4e-7b62204dd0bd" />

<img width="1920" height="892" alt="Screenshot from 2026-02-19 14-49-30" src="https://github.com/user-attachments/assets/4af7034e-b77b-44fa-a8c0-76b367cbb501" />

<img width="308" height="155" alt="image" src="https://github.com/user-attachments/assets/221a3a0d-e586-45e4-920e-3380a637e8f4" />

## L5 SPICE lab with Sky130 models

- dddd



# NgspiceSky130-Day2-Velocity saturation and basics of CMOS inverter VTC
## SPICE simulation for lower nodes and velocity saturation effect
### L1 SPICE simulation for lower nodes

<img width="659" height="518" alt="image" src="https://github.com/user-attachments/assets/52ca2440-442f-46fd-b92d-f875f85d2e71" />

- In the graph(Id vs Vds for different Vgs)
   - x-axis is Vds(Drain-to-Source Voltage)
   - Y-axis is Id(Drain Current)
- When Vgs=0, zero drain current so the device is not turn on hence no channel.
- At Vgs=1V, it just cross the threshold voltage so bare minimum channel is available for drain current flow so small amount of drain current at Vgs=0.5v
  
 <img width="1167" height="663" alt="image" src="https://github.com/user-attachments/assets/1a44c54a-40e4-4211-90d6-7fc599a25f86" />


- In the above graph, the region to the left of the curve defined by Vds=Vgs-Vt corresponds to the **linear region**, where the drain current increases approximately linearly with Vds.
- The region to the right represents the **saturation region**, where the current shows only a slight increase due to effects such as velocity saturation. The lower portion of the graph indicates the cutoff region, where the device is essentially turned off.
- This behavior is characteristic of a MOSFET with a relatively long channel length.
- When W/L ratio is constant, drain current will same at any node.
- Now we are taking different W and L, but the ration of W/L is same as previous, so the Id should not change. But this is not the case practically.
- Below is the spice deck, where only the values of W and L is changed, rest everything remains same.
    ```*** MODEL Description ***
       *** NETLIST Description ***
       M1 vdd n1 0 0 nmos W=0.375u L=0.25u
       R1 in n1 55
       Vdd vdd 0 2.5
       Vin in 0 2.5
       *** SIMULATION Command ***
       .op
       .dc Vdd 0 2.5 0.1 Vin 0 2.5 0.5
       *** .include mosis_1um_model.mod
       .LIB "tsmc_025um_model.mod" CMOS_MODELS
       .end
    
<img width="785" height="307" alt="image" src="https://github.com/user-attachments/assets/45b897de-0d34-4796-a85d-131912ee17bc" />

- Below is the setplot of the code
<img width="769" height="609" alt="image" src="https://github.com/user-attachments/assets/de12d5e4-b925-4497-b4a0-64a6a66e0d6e" />


- In the previous case the current value for saturation region is different
- The difference between two adjacent curve appeared to be constant

  ### L2 Drain current vs gate voltage for long and short channel device
<img width="1248" height="538" alt="image" src="https://github.com/user-attachments/assets/a6ece7e4-b229-4eb5-888e-cdcee4f04586" />

- Let us now compare the results obtained from the two simulations we performed to analyze the differences in device behavior.
- The technology nodes of the two graphs are different
- **Observation 1**:-
     - In 1st graph(1.2u), the drain current at each and every gate voltage at Vds=2.5v there is a quadratic dependance (the drain current quadratically increases with increase in gate voltage)
       <img width="650" height="518" alt="image" src="https://github.com/user-attachments/assets/a022f365-ad9f-41dc-839f-cb169c125442" />

     - For short channel device 2nd graph(0.25u), initially the lower value of gate voltage still have a quadratic dependence, as gate voltage will increases the drain current will increasing linearly due to velocity saturation.
  
- Now we will plot graph of Id vs Vgs and sweeping Vds or keeping Vds constant = 2.5V.
        ```*** MODEL Description ***
       *** NETLIST Description ***
       M1 vdd n1 0 0 nmos W=0.375u L=0.25u
       R1 in n1 55
       Vdd vdd 0 2.5
       Vin in 0 2.5
       *** .include mosis_1um_model.mod ***
       .LIB "tsmc_025um_model.mod" CMOS_MODELS
       *** SIMULATION Commands ***
       .op
       .dc Vin 0 2.5 0.1 Vdd 0 2.5 2.5
       .end
- In the syntex whatever in the left hand side that will be tunned every value of right hand side
<img width="756" height="298" alt="image" src="https://github.com/user-attachments/assets/47ebb653-c354-42d2-8b3f-0c981fbe0d26" />
<img width="719" height="559" alt="image" src="https://github.com/user-attachments/assets/6936b584-0426-420f-9f59-8449d7d5d1a6" />

- For example, in this case, for each value of Vdd, the input voltage Vin is swept across a specified range.The resulting plot exhibits a quadratic characteristic, which is observed specifically when Vds=2.5V.
   
- Let us see the same effect for short channel device. For L=0.25 micron.
        ```*** MODEL Description ***
       *** NETLIST Description ***
       M1 vdd n1 0 0 nmos W=0.375u L=0.25u
       R1 in n1 55
       Vdd vdd 0 2.5
       Vin in 0 2.5
       *** .include mosis_1um_model.mod ***
       .LIB "tsmc_025um_model.mod" CMOS_MODELS
       *** SIMULATION Commands ***
       .op
       .dc Vin 0 2.5 0.1 Vdd 0 2.5 2.5
       .end
   

### L3 Velocity saturation at lower and higher electric fields  
<img width="1266" height="600" alt="image" src="https://github.com/user-attachments/assets/bd83447d-3ab6-4a23-a290-73f6cd938181" />

- For short-channel devices, the drain current tends to exhibit a more linear dependence on Vgs as it increases. This behavior arises due to the velocity saturation effect, which limits the carrier velocity at high electric fields and reduces the quadratic nature of the current–voltage relationship.
- For lower node, we have four region of operations:- **Cut-off**,**Linear**,**Saturation** and **velocity saturation**
  <img width="458" height="199" alt="image" src="https://github.com/user-attachments/assets/9bc6f4a1-d247-439f-87c2-b84dae169c32" />

- **velocity saturation** is for lower value of electric field the velocity tends to be linear function of electric field but after cut-off point velocity saturated(velocity becomes constat due to scattering effect)
    -   Velocity Vn(x)=mobilty.electric field
    -   <img width="398" height="81" alt="image" src="https://github.com/user-attachments/assets/c51155a3-4ce0-4f97-8a2d-079a7d9579e3" />
    -   <img width="418" height="129" alt="image" src="https://github.com/user-attachments/assets/03a75a09-c334-4827-b688-ec39725c55c9" />
    -    <img width="170" height="37" alt="image" src="https://github.com/user-attachments/assets/be194df7-0735-4f03-a2ef-568b85cad2ec" />
    - Re derive the drain current equation in the presence of electric field
      <img width="1153" height="353" alt="image" src="https://github.com/user-attachments/assets/93cc39de-205f-47f9-b4b2-3e1f10a580a5" />
    - It becomes to complex to handle so we try to simplify the equation
       <img width="886" height="396" alt="image" src="https://github.com/user-attachments/assets/37f0511f-0e75-4c1a-a5b1-a2d561cae2e3" />

### L4 Velocity saturation drain current model
 <img width="900" height="514" alt="image" src="https://github.com/user-attachments/assets/8edfd449-d368-4554-a1e3-2ad5376d6eb7" />

-   Let us take Vgs-Vt=Vgt because we will be taking Vgs as large values. Current equation we will be using as shown above, For lower values of Vds the channel length modulation parameter λ can be ignored. 
- There is another important technology parameter called 𝑉dsat. It represents the drain-to-source voltage at which the device just begins to enter the velocity saturation region.
   <img width="349" height="74" alt="image" src="https://github.com/user-attachments/assets/35a7e0b8-c419-4713-b7f9-5a7a830254ce" />
   <img width="572" height="249" alt="image" src="https://github.com/user-attachments/assets/dd75dfa8-e23a-40e2-bb59-65a95c346889" />

   - When Vgs-Vt is minimum, Vds is at maximum voltage
     
   <img width="563" height="333" alt="image" src="https://github.com/user-attachments/assets/e662acfd-bf77-4f32-9dfb-17f509749c2c" />

   - When Vds is minimum, device enters into resistive or linear region of operation
     
   <img width="886" height="447" alt="image" src="https://github.com/user-attachments/assets/b9530f4c-d841-42cc-be0b-1123ebd9b00a" />

   - When Vdsat is minimum, this is applicable only for short channel devices
   - In the above equation, it seems when W is constant and L is lowered then Id should increase, But it is not so practically.

- **Observation 2**:-
  
  <img width="1317" height="662" alt="image" src="https://github.com/user-attachments/assets/657ecfa9-e79c-4f02-90c5-7142ec75d70f" />

- For smaller technology nodes, the saturation current is lower instead of higher. This happens because velocity saturation occurs earlier in short-channel devices. As a result, the device reaches saturation sooner, and the maximum (peak) drain current becomes significantly smaller compared to larger technology nodes.
     
### L5 Labs Sky130 Id-Vgs

<img width="1920" height="891" alt="Screenshot from 2026-02-22 21-02-52" src="https://github.com/user-attachments/assets/7eee0388-827f-4ac9-800f-d7d5c83dcb14" />
<img width="1920" height="891" alt="Screenshot from 2026-02-22 21-09-40" src="https://github.com/user-attachments/assets/f30e2dc8-439b-439b-aac6-2dd6d39079f2" />
<img width="1920" height="891" alt="Screenshot from 2026-02-22 21-19-31" src="https://github.com/user-attachments/assets/0564abed-5cc9-40b8-99c4-4ec663fa9f4b" />
<img width="1920" height="891" alt="Screenshot from 2026-02-22 21-20-04" src="https://github.com/user-attachments/assets/00fd61c0-b34f-4c65-a091-c4927f09ae29" />
<img width="1920" height="891" alt="Screenshot from 2026-02-22 21-20-56" src="https://github.com/user-attachments/assets/28445160-0191-475f-bc06-1786c7ab4154" />







<img width="284" height="58" alt="image" src="https://github.com/user-attachments/assets/5f5939bb-1cf1-4f2a-b52a-db906055e40a" />


- Similarly we observe Id vs Vgs graph
  
  <img width="1920" height="891" alt="Screenshot from 2026-02-22 23-07-55" src="https://github.com/user-attachments/assets/999e8493-c145-4de6-95a5-0a8fd2474da3" />

- Keeping Vds constant which is 1.8V
<img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/08f14279-15b6-4298-ab09-a5412211a95a" 
 - It is showing linear behaviour

- Calculate threshold voltage for Id vs Vgs graph
- In the graph current starts increasing rapidly with a small change of Vgs value. To plot threshold voltage we have to take the tengent of the slope and extended on the x-axis

  
  


    

    


  










