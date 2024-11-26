Some materials usedin battery thechnology
- Copper as electron collector anode)
- Graphite
- Separator, prevent the lithium ions to travel around inside the battery, only the electrons will flow through the load
- metal oxide
- Aluminum (cathode)

# battery shapes and technologies
- Cylindrical as cans
- Prismatic
- Pouch

Primary batteries invented in the past but only in 1990 the first rechargeable battery, by SONY, then Pansonic in Japan improved the battery technology, as energy density and overall weight, it was important for planes but also for the cost of the battery, industries had to pay for the building materials of the batteries.


The most expensive part of a battery is the metal cathode, on the energy density increase, industries had to consider safety and stability parameters as limit.

Reaction of a LiFePO battery:
$$
Li_{y}FePO_{4} \to FePO_{4} + yLi^+ + e^-
$$
where $y$ is the ...
On the other side the lithium recombines with carbon:
$$
6C +xLi^+ + e^- \to Li_{x}C_{6}
$$
The terminal voltage is measured across the whole battery.

In the past Lithium metal battery where used but they can't be recharged, they are used principally in medical applications where the battery life last as long as the patient, without the needs of a recharge.


## How to know when a battery fills up
The $V_{{max}}$ is a battery specification that indicates when the battery is full, in that case the SoC (State of Charge) is translated in a voltage measurement.
When a battery is full no more lithium ions can stack at the cathode.

Different battery chemicals have different voltage-capacity graphs, most of them are quite flat for a range of charge andthen they dumps down quickly, this is a problem for the detectability and measurement of a battery SoC.

Specifically the LiFePO4 is very flat, for this reason the graph is called *neck and shoulder*.

State of charge integrator:
$$
\dot{z} = -\frac{I}{3600\cdot C}
$$
where $C$ is the capacity of the battery, $I$ the current flow, $3600$ the conversion term for the $Ah$ (Ampere-hour) unit.

Most of the batteries can be modeled with a polynomial function.
Studying the battery voltage dynamics respect to a current pulse is possible to model the internal resistance and capacitance of the battery, in order to estimate its state oh health.
Observing a Nyquist plot is possible to estimate a Pristine or a degraded battery.

The **C rate** is a current in Amp that will (dis)charge in 1 hour.

# SoC estimation
Basic linear model:
$$
\begin{aligned}
\dot{z} &= -\frac{I}{\hat{C}} - L(V + n - \hat{V})\\
\hat{V} &= V_{0} + \alpha \hat{z} - I\hat{R}
\end{aligned}
$$
and the estimation error:
$$
\begin{aligned}
\dot{e}_{z} &= -L\alpha e_{z} + Ln + \text{modelling error}\\
\dot{e}_{z} &= -L\alpha e_{z} + Ln - \frac{\Delta C}{C \hat{C}}I + L\Delta R \cdot I
\end{aligned}
$$
$\alpha$ is the natural gain of the battery.
$\Delta$ indicates the errors.

$$
\alpha  =  \frac{\partial V_{OCV}}{\partial \dots}
$$
# Battery degradation
Degradation is usally related to battery usage (in Ah) or even with simply storage. Too high or too low temperatures also degradates battery life.
Batteries in EV usually have an AC system to keep them cool.

THe capacity decrease is usually called "knees" and the resistance incres is usually referred as "elbows".

The capacity degradation usually comes from the anode, it manifest after a 75% of battery discharge, a battery capacity degradation is difficult to estimate when the battery is charged.

Carbon structure suffer for a mechanical degradation with charge/discharge cycles, Lithium atoms have to pass inside the carbon structure to accumulate and discharge, this movement can actually crack the carbon structure of the anode.
Copper too can oxide and aluminum will corrode.
Every degradation battery model consider the SEI degradation.

Lithium ions are consumed during charges, this will reduce the capacity, it happens also in the first charge, during manifacturing, almost 10% of lithium is consumed for rust during the first charge.
The degradation accelerates aat higher teperature, that's why hotspots in battery should be monitored.
Also standby degrades battery in time.

Lithium deposition on the Anode will form growing dendride formations, that will reduce the potential gap between the electrodes, creating a positive feedback phenomena, where more lithium continues to accumulate on those spot, resulting in small shorts in the battery cell.

During manufacturing all the litium is put on the cathode side, during the first charge a part of lithium is trapped in the SEI, so less lithium is available and less SEI is available to the battery.
Lithium degradation is still less than Lead acid battery degradation.

In order to reuse a battery as second user, the history of the battery SOH is important in order to estrapolate the battery remaining life, using only the SOH at a certain point is not sufficient to decide whenever to buy or not an used battery.
Changing use case of the battery also incide on the remaining battery life, for example a back-up power battery will have a longer remaining life than a bus/car daily usage battery.

Two category of phenomena model the degradation of a battery:
- Intra-cycles regards fast phenomena, occurring during charge and discharge of batteries, related to lithium particles movements inside the SEI
- Inter-cycles regards slow phenomena, regardings aging of the battery, particle cracking, Li-plating etc...

Having a digital twin of the battery iss useful for a lifetime simulation, it's useful for degradation estimation, permitting to simulate numerous simulations of multiple charge/discharge cycles, using ML models to it etc..

# V2G applications (Vehicle to Grid)
Most of EV are kept parked and less driven than ICE vehicles, this could be useful for a V2G application where vehicles acts as a battery for the electrical grid, during night time, leveling the grid load curve.

Some researches states that the V2G application will degrade faster the battery, some others states that the V2G could reduce the battery degradation, leveling the load on the battery during its lifespan.

Some cells are cycling aging dominant, others are calendar aging dominant, so the latter are best to use for V2G applications, giving a better life gain in Ah versus the capacity drop.

### Battery inhomogeneity
Cooling systems are important to balance the cell to cell temperature difference.
Not all the batteries have a balancing system, this is often done by the charger, this is done for reducing the weight of the battery. Balancing the cells is important in order to preserve the battery capacity.
