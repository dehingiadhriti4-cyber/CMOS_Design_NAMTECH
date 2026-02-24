<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/67100ee6-6f37-46d5-8e3e-754d1a9dfbd5" /><img width="1920" height="892" alt="image" src="https://github.com/user-attachments/assets/f8b11e93-e877-4d58-9934-2821218c047e" /># CMOS_DESIGN


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

## CMOS voltage transfer characteristics (VTC)
### L1 MOSFET as a switch
- We will now look at the device parameters from the switch point of view.
 <img width="819" height="471" alt="image" src="https://github.com/user-attachments/assets/b8336827-6b0d-4439-8a04-a195ffb90528" />

- It's just a MOS transistor, it is work when |Vgs| is greater than Vt
    -  In case of N-MOS it is +ve Vgs
    -  In case of P-MOS it is -ve Vgs
- Whenever |Vgs|>Vt, the device turns ON,  it acts as closed switch
- Let's try to bias the devices properly. We will take one PMOS and one NMOS transistor, connect them together, and form a CMOS configuration.
  
- CMOS stands for Complementary MOSFET. It is called “complementary” because it uses both NMOS and PMOS transistors, which operate in opposite (complementary) manners—when one transistor turns ON, the other turns OFF. 
- We have PMOS at the top and NMOS at the bottom, the source of NMOS is connected to the GND(Vss) and the source of PMOS is connected to the Vdd, both the gates are tie together and connected to Vin, both the drains are tie together to get the output potential Vout, also we have a load Cl
 <img width="1143" height="690" alt="image" src="https://github.com/user-attachments/assets/64e6990f-3ce5-400f-ac35-efd54729dd5b" />

- The calculation of Vgs will differ by the value of potential that we apply
    -  In the case of NMOS, if Vin=0V then Vgs is 0V, NMOS is OFF
    -  In the case of PMOS, if Vin=0V then Vgs is negative Vdd, PMOS is ON
    
- When Vgs>Vt, NMOS can be replaced by a resistor and we have output load as well when Vin=Vdd

### L2 Introduction to standard MOS voltage current parameters
- We are trying to get the equivalent circuit of CMOS when Vin is 'high' and 'low', so that we can get the Voltage Transfer Characteristics (VTC) and therefore calculate the delay of the cell(the cell here is inverter).
  
  <img width="1172" height="700" alt="image" src="https://github.com/user-attachments/assets/a18fd590-26b0-4da3-8337-144f67b73c4a" />

- We take different condition when Vin is 'low' or 0V
    -  For PMOS Vgs will be -5V, it turn ON the PMOS, it can be modeled as resistor
    -  For NMOS Vgs will be 0V, NMOS is OFF
- Now, we need to analyze and understand how the currents behave in the circuit under different input conditions
   <img width="1183" height="645" alt="image" src="https://github.com/user-attachments/assets/80fd94ed-2920-443c-a68e-d143471d7e42" />


    -  when Vin=Vdd, there is a direct path exists between Vout and Vss, resulting in Vout=0( if the capacitance is completely charged, all the charges will discharged through the resistor Rn)
    -   when Vin=0V, there is a direct current flow from Vdd to the capacitance, resulting in Vout=Vdd(charging this caapacitor under this condition) 

- Let us give the naming convention of the CMOS
   <img width="1183" height="630" alt="image" src="https://github.com/user-attachments/assets/35b3ecdb-24d9-40e5-b1e2-2183b045f87c" />
    -  Idsp = -Idsn, both are opposite in direction to each other.

### L3 PMOS/NMOS drain current vs drain voltage
- We try to get some equations and tune them to get voltage-current characteristics, voltage transfer characteristics is purely a function of voltage
  <img width="441" height="687" alt="image" src="https://github.com/user-attachments/assets/8e6732f8-7f43-495d-96a8-95f83f95607b" />
- When we plot the Id VS Vds for both the NMOS and PMOS devices, the characteristic curves look like the ones shown here.
  <img width="825" height="442" alt="image" src="https://github.com/user-attachments/assets/7be81114-098e-4bb6-b64a-d7ff97f83c3b" />
- On the left, we see how NMOS drain current increases with drain voltage for different gate voltages. At low VDS it behaves like a resistor, and at high VDS it enters saturation where current becomes constant. On the right, PMOS shows similar behavior but with negative voltages and current direction reversed. 

### L4 Step1- Convert PMOS gate-source-voltage to Vin

- We have analyzed several internal node voltages inside the CMOS circuit. However, from a user’s perspective, these internal voltages are not directly visible. The user can only observe the external input voltage 𝑉in and the output voltage 𝑉out.
- Now we will se the steps to obtain voltage transfer characteristics for static CMOS inverter(Let's assume that it is a long channel device with Vdd=2V)

  <img width="397" height="261" alt="image" src="https://github.com/user-attachments/assets/3ae2c5b1-7c26-4ccc-8f8b-37adf8a584c4" />

	- We know that for the PMOS transistor,
      -  Vgsp=Vin−Vdd From this relation, we can rewrite it as:
      -  Vin=Vgsp+Vdd (our objective is to express all internal voltages in terms of the external variables Vin and Vout)
 - Next, we attempt to plot the PMOS characteristics in terms of Idsn(to compare NMOS and PMOS currents on the same axis). In this plot, the corresponding Vin values are obtained from the calculated Vgsp values using the relation above, as shown in the table.
	
	<img width="810" height="382" alt="image" src="https://github.com/user-attachments/assets/0f3c0f3b-2da3-428c-8515-d90677c04d31" />
​
### L5 Step2 & Step3 – Convert PMOS and NMOS drain-source-voltage to vout
- Now we have to convert the Vdsp into the function of output voltage​, we know Vdsp = Vout-Vdd
- Let us convert Vdsp into Vout. So to get Vout there is a shift of Vdd towards left hand side.
  
  <img width="1274" height="389" alt="image" src="https://github.com/user-attachments/assets/31839a96-39be-4953-b080-16cc0e04a23b" />

- If Vdsp is -2V we add a +2V to it to get Vout, so Vout=0V,  we will see a finite current(the output capacitor is completely discharged, we need to charge it so this is the charging current of it)
- Whenever Vdsp=0V, Vout=2V so the current is zero and the output capacitor is completely charged (this is true only when PMOS is combination with NMOS to form a CMOS inverter, not as PMOS as independent device)
- When Vdsp=1V, Vout=+1V, it means it is half charged and it need some amount of current to get charge.
- When we convert the graph as a function of Vin and Vout and Idsn, we called is as the load curve for PMOS transistor

 <img width="461" height="392" alt="image" src="https://github.com/user-attachments/assets/af33fbc4-8312-4f0c-b609-17b167128a49" />

- Now we will try to get the "load curve" for NMOS transistor from this equations.
  <img width="241" height="88" alt="image" src="https://github.com/user-attachments/assets/7497c15e-fd07-4120-947a-db663dbfc96b" />
- It is actually simple as Vgsn = Vin and Vdsn = Vout, directly we can get the graphs.

<img width="400" height="299" alt="image" src="https://github.com/user-attachments/assets/dc350e43-a8d9-49c9-915b-d7018e00650c" />

- It is just a matter of replacing the names.
  <img width="858" height="378" alt="image" src="https://github.com/user-attachments/assets/a43307db-11af-47ae-b1f3-f0a013f106b3" />

### L6 Step4 – Merge PMOS – NMOS load curves and plot VTC

- Now we will combine the two characteristic curves and use them to obtain the Voltage Transfer Characteristics (VTC) of the CMOS inverter.
- We will superimpose the load curve of NMOS on the load curve of POMS because Vin and Vout common to PMOS and NMOS so graphically if we want to derive the VTC of CMOS it has to be the intersection point between the PMOS and NMOS load curve.
   <img width="547" height="361" alt="image" src="https://github.com/user-attachments/assets/a994f23d-2ce8-40d4-8448-48b1d492feb3" />
- So the range of Vin and Vout is 0V-2V.

<img width="1267" height="699" alt="image" src="https://github.com/user-attachments/assets/b0ded0b1-71a1-422d-9524-32a2625f262c" />


| **Vin (V)** | **Vout (V)** | **NMOS Region** | **PMOS Region** |
| ----------- | ------------ | --------------- | --------------- |
| 0 V         | 2 V          | Cut-Off         | Linear          |
| 0.5 V       | 1.5–2 V      | Saturation      | Linear          |
| 1 V         | 0.5–1.5 V    | Saturation      | Saturation      |
| 1.5 V       | 0–0.5 V      | Linear          | Saturation      |
| 2 V         | 0 V          | Linear          | Cut-Off         |


# NgspiceSky130-Day3-CMOS switching threshold and dynamic simulations

## Voltage transfer characteristics-SPICE simulations
### Lecture 1:-SPICE deck creation for CMOS inverter
- 1) For this, we first need to create a SPICE deck, which contains the connectivity information of the circuit in the form of a netlist. This netlist defines the devices, their parameters, and how they are interconnected in the CMOS inverter configuration.
   <img width="415" height="429" alt="image" src="https://github.com/user-attachments/assets/db819675-42c5-4a02-ad4e-5ad874917431" />
- 2) The next task is to define the component values,  keeping W/L for both NMOS and PMOS same( i.e. same size of POMS and NMOS)
   <img width="399" height="437" alt="image" src="https://github.com/user-attachments/assets/dd5145f8-f492-493c-b085-9269ac1c6800" />

- 3) Next we will assume the Vin and Vout values, both are 2.5V and the output load is 10fF
   <img width="527" height="414" alt="image" src="https://github.com/user-attachments/assets/c0ff7919-62c9-407f-a469-7f179a877b46" />
- 4) Next step is to identify the Nodes (Node is the point where two components meet)
   <img width="683" height="524" alt="image" src="https://github.com/user-attachments/assets/938d61a1-0d82-4a1b-ae6f-a3a9f903e229" />
- 5) Name the nodes (example-2.5V input lies between Vin and 0, similarly Vdd lies between vdd and 0)
   <img width="528" height="453" alt="image" src="https://github.com/user-attachments/assets/533f3181-c16c-43f9-99d1-17807f16efdf" />
- 6) Now we write the SPICE deck
     ```*** MODEL Descriptions ***
        *** NETLIST Description ***
        M1 out in vdd vdd pmos W=0.375u L=0.25u(Drain-Gate-Substrate-Source)
        M2 out in 0 0 nmos W=0.375u L=0.25u```
     
   <img width="1190" height="542" alt="image" src="https://github.com/user-attachments/assets/a59c7418-dba3-44f7-a52e-9f024c544041" />
 
### Lecture 2:-SPICE simulation for CMOS inverter

   <img width="1186" height="562" alt="image" src="https://github.com/user-attachments/assets/a9958fcb-a612-41aa-8492-0a8dc62fb7da" />
   <img width="1180" height="565" alt="image" src="https://github.com/user-attachments/assets/f17d0f06-2a77-4ef3-a184-8156b90da83a" />
   <img width="1182" height="560" alt="image" src="https://github.com/user-attachments/assets/94b56878-3884-4f69-8589-cc0fd0ac2646" />

- 7) Next we have to give simulation command, Here we will be sweeping the gate input voltage from 0 to 2.5V with steps of 0.05. The reason we are doing this to calculate the VTC, the voltage at the output while sweeping the input voltage.
- 8) The final step is to describe the model file, all the technological parameters is describe in the model file.
   <img width="1176" height="558" alt="image" src="https://github.com/user-attachments/assets/138c83f7-5433-4710-9eb5-c093888f4ccf" />
- Now we will do the SPICE simulation for Wn=Wp=0.375u, Ln=Lp=0.25u, Wn/ln=Wp/Lp=1.5. Below is the VTC we get for the above netlist.
   <img width="754" height="618" alt="image" src="https://github.com/user-attachments/assets/75d94d09-0b9e-400d-87a6-8792840c54e6" />
- Next we will get the VTC for Wn= 0.375u, Wp= 0.9375u, Ln,p=0.25u; Wn/Ln=1.5, Wp/Lp=2.5 (PMOS width is 2.5 times more than NMOS)
   <img width="753" height="606" alt="image" src="https://github.com/user-attachments/assets/5bf03145-65c9-40fa-ba41-87ab0771cae2" />
- If we closely look this waveform and previous waveform, we notice that it is slightly shifted toward the left(in previous waveform it is exactly in the middle). This shift occurs because the NMOS transistor is stronger than the PMOS transistor in that configuration.
  
### Lecture 3:-Labs Sky130 SPICE simulation for CMOS
- Now we will get the VTC characteristics
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/14545e14-17de-494b-8934-0eece06034eb" />
- We are using both a PFET and an NFET to implement the CMOS inverter. The W/L ratio of the PMOS is chosen to be 2.33 times larger than that of the NMOS, so that their drive strengths are properly balanced. Now, we will perform a DC sweep of Vin from 0 V to 1.8 V, with a step size of 0.01 V, and observe the corresponding variation in Vout. From this, we can plot the Voltage Transfer Characteristics (VTC) of the CMOS inverter.
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/6bbdab1f-88f6-48df-abc4-9ea7bf8538c5" />
- To get the plot type ```ngspice``` and ```plot out vs in```.
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/d90735c5-090d-4e65-87eb-f1f255f26771" />
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/48c012ce-1c2c-4d30-9fa2-fa56daa0ee37" />
- Now we need to plot switching threshold from the graph, it is the point when Vin=Vout.To zoom in the curve; press righ mouse button + hold it.
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/c9656a91-c772-4d29-9ed4-ec1d80ada6b7" />
  So switching threshold for W/L=2.3 is around 0.876V
   <img width="280" height="30" alt="image" src="https://github.com/user-attachments/assets/070ab57e-33ce-4770-b29e-2f8ef5f49b6b" />

- We will se the transient analysis, for that we will go inside the tansient SPICE file for day3
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/b76d281f-e91c-47a1-9fe9-0ea55f42a281" />
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/4a431c39-bd2f-449a-ad21-ded7f850f912" />
- We can observe that this simulation is performed at the typical process corner, and the W/L ratios remain the same as before.Now, instead of a DC sweep, we are applying a transient pulse input that switches from 0 V to 1 V, with no time delay. The rise time and fall time are both 0.1 ns. The pulse width is 2 ns, and the total time period is 4 ns. Let us run the transient simulation to analyze the dynamic response of the CMOS inverter.
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/949158f8-b03f-4354-9b3a-b65cc24f46d7" />
 

- To calculate rise delay and fall delay we have to consider the 50% of Vdd, i.e. at 0.9V.
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/3dfa2a43-f6d5-43b1-8c9d-1cf1f737ae6c" />
  <img width="341" height="76" alt="image" src="https://github.com/user-attachments/assets/24b21a61-fada-4e55-a5ee-4858270ec34d" />
     - Rise delay = 2.482ns-2.15ns = 0.333ns
- For calculation of fall delay fall delay
  <img width="1920" height="891" alt="image" src="https://github.com/user-attachments/assets/cd67b09e-6d2e-4384-bf52-9753d00b8d25" />
  <img width="292" height="109" alt="image" src="https://github.com/user-attachments/assets/f855c68d-49c6-4d7b-bfcc-afabf8386f60" />
      - Fall Delay = 4.334ns-4.050ns = 0.285ns
  
## Static behaviour evaluation-CMOS inverter robustness-Switching Threshold

### Lecture 1:-Switching Threshold, Vm
- Now we will compare the two CMOS inverters that have different W/L ratios for the PMOS and NMOS transistors(one is Wn/Ln=Wp/Lp=1.5 and another one is Wn/Ln=1.5,Wp/Lp=3.75). We observe that in both cases, the overall shape of the Voltage Transfer Characteristics (VTC) remains the same. However, the switching threshold voltage shifts depending on the relative strength of the transistors.
  <img width="1148" height="545" alt="image" src="https://github.com/user-attachments/assets/50091d6b-fda6-46cc-b623-51e68e607a6f" />

- Whe we look into the waveforms, the shapes of the waveform are same irrespective of voltage level in which they are switching, this tells us the CMOS inverter is a very robust device. There are certain parameters which define the robustness of the CMOS.
    -  1)**Switching threshold**:- It is the point at which the device switches, it is a point when Vin=Vout. Vm in both the cases by drawing a 45 degree line.
So, in first case Vm comes out to be somewhere around 0.9V and in second case Vm=1.2V.
       <img width="1124" height="603" alt="image" src="https://github.com/user-attachments/assets/dc0b5143-cff7-4abf-a2a8-52901fb303a9" />
	   <img width="1133" height="449" alt="image" src="https://github.com/user-attachments/assets/9b8eecb2-632d-4427-968f-5924cae09fe5" />


      -  This is the area where PMOS and NMOS both are in saturation region(both are kind of turn ON). Current flows from both the transistor, it is actually a dangerous situation(There is a high possibility of leakage, which increases the chance of current flowing directly from the power supply to ground).

       <img width="996" height="446" alt="image" src="https://github.com/user-attachments/assets/9263731d-5222-4a78-87da-08c674af5f14" />

### Lecture 2:-Analytical expression of Vm as a function of (W/L)p and (W/L)n
- There are two parts of solving the equation
    - 1)Try to evaluate the value of Vm for given W/L PMOS and NMOS
    - 2)Define the value of Vm then find the value of W/L PMOS and NMOS
- 1) We will now calculate the value of Vm w.r.t the NMOS and PMOS width and length.
     <img width="774" height="287" alt="image" src="https://github.com/user-attachments/assets/68a6871a-ad2e-4b0c-8c42-d938f4b866f3" />
     <img width="510" height="209" alt="image" src="https://github.com/user-attachments/assets/18ddfa14-baf3-4663-94ab-5ac89dbb2707" />
- Put the epression of ```Idsn``` and ```Idsp``` in the equation ```Idsn+Idsp=0```
      <img width="797" height="227" alt="image" src="https://github.com/user-attachments/assets/c26af15a-6703-42bf-b6bc-794d4089cf75" />
     - kn and kp are transconductance parameters.
          - kn=(Wn/Ln)Kn'
          - kp=(Wp/Lp)Kp'
             - Where:
                 - W = Width of transistor
                 - L = Length of transistor 
                 - K= Process transconductance parameter, dpends on device size and mobility
                      - Kn'=μn.Cox
                      - Kp'=μp.Cox
	                      ​
### Lecture 3:-Analytical expression of (W/L)n and (W/L)p as a function of Vm

- 2)We will now calculate the value of W/L for PMOS and NMOS when Vm is given.
   - Now, we need to approach the problem in a reverse manner. Instead of choosing the W/L ratios first and then observing the switching threshold, we will start by fixing the desired switching threshold.Since the power supply voltage is Vdd=2.5V, we want the switching threshold Vm to be exactly half of Vdd. Therefore,
      - Vm=Vdd/2=2.5/2=1.25V
   - Our goal is to determine the appropriate W/L ratios of the PMOS and NMOS transistors such that the inverter switches precisely at 1.25V.
   - We will start from the current equation itself i.e. Idsn = -Idsp
     <img width="437" height="89" alt="image" src="https://github.com/user-attachments/assets/fedbbb9c-27c9-416b-ac7b-e49cabf759a3" />
	   - Expanding Kp and Kn (Gain factor)
         <img width="510" height="86" alt="image" src="https://github.com/user-attachments/assets/643b325a-d496-4348-bb66-19af17070cfc" />
	     <img width="481" height="94" alt="image" src="https://github.com/user-attachments/assets/09d5689d-1921-433d-93e7-6fb5b7889688" />
	   - Now here on the RHS all of them are constant except Vm, If we know Vm then we can get the W/L ratios.
       - So now this will allow us to find out for what value of W/L ratio of PMOS will be N times greater than NMOS, we can decide the value od N based on the size of the transistor(Vm value).
 - Now we will analyze the behaviour of CMOS for below difference in W/L ratios of PMOS and NMOS and see where does the switching threshold lies.
   <img width="325" height="256" alt="image" src="https://github.com/user-attachments/assets/7cd5d605-b870-4c9b-b93b-2d91070696a2" />
### Lecture 4:-Static and dynamic simulation of CMOS inverter
- 1) For (W/L)n = (W/L)p = 1.5
     <img width="749" height="605" alt="image" src="https://github.com/user-attachments/assets/2f17b5ca-2d57-42b6-9990-88b15ccd9713" />
      - We can also calculate the "Rise Delay" and "Fall Delay" by using the transient analysis.
      <img width="219" height="158" alt="image" src="https://github.com/user-attachments/assets/81ed0696-1226-461c-b805-2244f3fcfe14" />
      <img width="746" height="609" alt="image" src="https://github.com/user-attachments/assets/ecee09c7-2846-41ef-a3eb-5700fa126453" />

	  - Rise delay = 1.162ns-1.014ns = 0.148ns
      - Fall delay = 2.076ns-2.004ns = 0.071ns
     <img width="1168" height="511" alt="image" src="https://github.com/user-attachments/assets/f70574e5-9107-4d31-84d0-ef904837420b" />
	  - Switching threshold is 0.99V.
- Similarly we do the same thing for all the set of combination and plot table specifying the value of the switching voltage.

### Lecture 5:-Static and Dynamic simulation of CMOS inverter with increased PMOS width
-  2) For (W/L)p = 2(W/L)n
      <img width="755" height="602" alt="image" src="https://github.com/user-attachments/assets/8f662877-63df-40be-b5ac-e22fb3eef273" />
	  - The curve has shifted toward the right side because the PMOS transistor is stronger than the NMOS transistor in this configuration. Since the PMOS has a larger W/L ratio, it provides higher drive strength.
      - Rise delay = 1.094ns-1.014ns = 0.08ns
      - Fall delay = 2.081ns-2.004ns = 0.076ns
      <img width="1169" height="498" alt="image" src="https://github.com/user-attachments/assets/54eb88e4-8ccf-42e5-9114-11eae1484fce" />
	  - We can see that the Vm is now increased as the PMOS has become more stronger and it needs more current to charge the output load capacitor.
- 3) For (W/L)p = 3(W/L)n
      <img width="1172" height="486" alt="image" src="https://github.com/user-attachments/assets/802808d7-8073-4e2c-af1f-5473daa7557e" />
	  - Switching threshold lies exactly at the centre or somewhere near the centre.
- 4) For (W/L)p = 4(W/L)n
      <img width="1169" height="492" alt="image" src="https://github.com/user-attachments/assets/a0650293-51de-44da-a148-1b599fc10f6d" />
	  - Switching threshold moves towards the right, it is about 1.35V.
- 5) For (W/L)p = 5(W/L)n
      <img width="1173" height="493" alt="image" src="https://github.com/user-attachments/assets/5f0bc8cf-3a9c-4775-80cd-7701e977edd1" />
	  - The rise delay has significantly reduced
- Rise delay decreases with increase in PMOS width, this shows the time required to charge the output capacitor decreases significantly this is because we have a bigger area.

### Lecture 6:-Applications of CMOS inverter in clock network and STA
- We try to tabulate everything what we got:-
    <img width="702" height="250" alt="image" src="https://github.com/user-attachments/assets/ed6eb011-b9b9-4077-8fd8-20144669a9f0" />
- From this experiment, we can draw the following conclusions:-
   - 1) If we vary the PMOS size w.r.t NMOS by some few numbers, the variation of the switching threshold is very small range. It is due to the robustness of CMOS inverter.
   - 2) When (W/L)p = 2(W/L)n, in this case the rise delay approximately equal to the fall delay, By performing simulation, we can determine the appropriate sizing ratio between PMOS and NMOS such that the rise delay and fall delay become equal. When the rising and falling propagation delays are equal, the CMOS inverter exhibits symmetrical switching behavior. This symmetry indicates that both pull-up and pull-down networks have balanced drive strengths.

- This is a typical characteristic of Clock Inverter/buffer where we want the rise delay and fall delay to be equal.
  <img width="1229" height="688" alt="image" src="https://github.com/user-attachments/assets/f7446eb4-8b60-4c3e-8a4a-bcdb692e3323" />
- Other types of cells can be used according to the data path requirement.
  <img width="1241" height="676" alt="image" src="https://github.com/user-attachments/assets/f3021af0-2725-4266-8590-733322cfa342" />

- SLACK should be either +ve or 0, data arrival time<data required time
- In a situation when data required time<data arrival time, increase the delay of data arrival time by plug in the right inverter.The theta(θ), combinational delay is much higher, in that case we must use a cell which got lower delay.

# NgspiceSky130-Day4-CMOS Noise Margin robustness evaluation
## Static behaviour evaluation-CMOS inverter robustness-Noise Margin
### Lecture 1:-Introduction to noise margin
- The next step in evaluating the robustness of the CMOS inverter is to determine its noise margin. Every digital device has a certain noise margin, which defines its tolerance to unwanted disturbances.
- Noise margin is primarily related to issues such as crosstalk noise and transient glitches. It indicates how much noise can be superimposed on the input signal without causing an incorrect logic transition at the output.
- By varying the CMOS inverter switching threshold, how does the noise margin varies.
  <img width="535" height="498" alt="image" src="https://github.com/user-attachments/assets/327db8db-ea94-43e5-9a33-c8e96fc25ced" />

- For example if we consider an ideal Inverter, for inputs 0/1 it gives output as 1/0. The slope of switch is infinite.
- At Vdd/2 switch happening (sudden shift of output voltage from logic '1' to logic '0'),slope defines the change in the output voltage w.r.t input voltage.The slope of switch is ideally infinite.
- However, in practical circuits, this is not possible. Due to the presence of parasitic resistances and capacitances, the inverter exhibits delay during switching.
- The slope is finite slope, it has some value, putput will be a gradual move.
  <img width="360" height="335" alt="image" src="https://github.com/user-attachments/assets/73c16c08-bd0b-4303-931b-4efdd1f10e49" />

- Now, we observe the following behavior from the VTC curve:
  -  1) Whenever the input voltage is between 0 and VIL(Input Low Voltage), the output remains at VOH(Output High Voltage).
  -  2) Similarly, whenever the input voltage is between VIH(Input High Voltage) and Vdd, the output remains at VOL(Output Low Voltage).
-  This defines the valid logic regions of operation for the CMOS inverter and helps in determining the noise margins.

### Lecture 2:-Noise Margin voltage paramters

- Now we will comside the more practical scenario and take the non-idealities of a CMOS inverter, the VTC curve deviates from the ideal case. Due to finite gain, parasitic resistances, and capacitances, the output levels are not perfectly equal to 0 and Vdd.
- In this case:
    - When 0<Vin<VIL, the output remains in the high region, but
        - VOH<Vout<Vdd
    - When VIH<Vin<Vdd, the output remains in the low region, but
        -  0<Vout<VOL
    - Also, the logic levels satisfy the following practical conditions:
        -  VOL<VOH<Vdd
           -  because VOH must be recognized as a valid logic high by the next inverter stage.
        -  0<VOL<VIL
           -   because VOL must be safely interpreted as a logic low by the next stage.
   <img width="352" height="340" alt="image" src="https://github.com/user-attachments/assets/625c0a1d-e12a-4348-89f2-66400b4330e9" />

- These relationships ensure proper cascading of CMOS inverters and define the noise margin of the circuit.
- The slope is close to -1,as for increase in input, output is reducing.
  
### Lecture 3:-margin equation and summary

- Now we will calculate the noise margin equation, for that we will plot the voltages on the same scale.
  <img width="683" height="510" alt="image" src="https://github.com/user-attachments/assets/09e512be-294b-478a-b38c-384826066abb" />

- In the above scale:-
   - 1)Noise Margin High(NMH) - value between VIH and VOH.
       -  It says that any voltage level whether it is in input or output side will be detected as logic'1'
   - 2)Noise Margin Low(NML) - value between VIL and VOL.
       -  It says that any voltage level whether it is in input or output side will be detected as logic'0'
- If the induced noise remains within these allowable ranges, it will not affect the circuit operation. This is because the signal will still be correctly interpreted as  logic ‘1’ or logic ‘0’.Such noise levels fall within the noise margin and, therefore, do not cause any logic error. This type of noise can be safely tolerated and effectively rejected by the CMOS inverter. Apart from this region the value is "Undefined" and the logic level can swing between 'high' and 'low'.
  <img width="666" height="354" alt="image" src="https://github.com/user-attachments/assets/abb16190-4fd1-455f-98e1-5cf6ff2c2200" />
  <img width="715" height="444" alt="image" src="https://github.com/user-attachments/assets/9055c109-4d9a-4d53-b501-a45db9184ee5" />

### Lecture 4:-Noise margin variation with respect to PMOS width

- We will evaluate the noise margin as a function of the PMOS width and analyze how it influences the inverter characteristics. By varying the PMOS sizing and observing the corresponding changes in the VTC and noise margins, we can demonstrate the robustness of the CMOS inverter.
- First step is to find out the point on the particular curve where the slope is -1 and we need to extend them towards x-y axis and find the Noise Margin High and Noise Margin Low.
   - 1)For (W/L)p = (W/L)n
     <img width="1185" height="527" alt="image" src="https://github.com/user-attachments/assets/cfef7365-c7d5-47ed-b57c-9122326d6a5d" />

        - NMH=0.3V
        - NML=0.3V
        - It's able gto sustain the noise which are lying on the spacific ranges.
    - 2)For (W/L)p = 2(W/L)n
      <img width="1162" height="534" alt="image" src="https://github.com/user-attachments/assets/a71cc0c3-bfe3-4e26-bb2c-7ddb675a0be8" />

        - Noise Margin High is increased by 0.05, NMH=0.35V
        - NML=0.3V
        - The larger the Noise margin, stronger is CMOS inverter and immune to Noises.
    - 3)For (W/L)p = 3(W/L)n
      <img width="1175" height="514" alt="image" src="https://github.com/user-attachments/assets/77244b67-c8d1-471d-aa1a-ddff0bde27cb" />

        - NMH=0.4V(increase more)
        - NML=0.3V
        - PMOS is resoinsible for holding logic '1' on the output capacitor and NMOS is responsible for holding logic '0' on the output capacitor
     - 4)For (W/L)p = 4(W/L)n
       <img width="1169" height="523" alt="image" src="https://github.com/user-attachments/assets/df1b1cc7-3f08-44f7-aa62-a973e3bea675" />
	    - NMH=0.42V
        - NML=0.27V
        - Dorp in the NML because NMOS becomes weaker as compared to the PMOS, the ability for the noise margin for NMOS to hold the logic '0' has deminished.
     - 5)For (W/L)p = 5(W/L)n
       <img width="1164" height="527" alt="image" src="https://github.com/user-attachments/assets/fd5fdd2f-6e71-4403-a2f3-47963047b1c9" />

        - NMH=0.42V
        - NML=0.27V
        - The noise margin high almost comes to static value,so even if we increase the widths further noise margin will be static.

- Now we will try to bring everything in tabular format:-
  <img width="700" height="249" alt="image" src="https://github.com/user-attachments/assets/3f16ec3d-0780-48dc-9ab0-eb611efb4522" />

- Also we come to know the ranges for **Digital desig** and **Analog design** in the CMOS inverter.
  <img width="683" height="537" alt="image" src="https://github.com/user-attachments/assets/899702e3-2311-44bb-b914-57606ddab243" />
   - This area is use for switching purpose.
  <img width="693" height="559" alt="image" src="https://github.com/user-attachments/assets/a8e868bf-6ee6-404d-8bc5-1a90a2fc56fd" />
   - This area is use for amplification purpose.

### Lecture 5:-Sky130 Noise margin labs
- 
