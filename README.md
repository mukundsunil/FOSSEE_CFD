# CFD Analysis of Flow Meters and Pipe Fittings
### FOSSEE Semester Internship | IIT Bombay. More information regarding this can be found here: https://cfd.fossee.in/lab-migration/lab-migration-run/19

## 📌 Project Overview
This project was completed during a semester-long internship at **IIT Bombay** under the **FOSSEE** program. The work involves the numerical simulation and turbulence modeling of incompressible flows through various engineering components using CFD. The primary goal was to study flow features and determine performance parameters such as the **Coefficient of Discharge ($C_d$)** and **Minor Loss Factors ($K$)**.

---

## 🛠 Technical Implementation
* **Algorithms:** The **SIMPLE algorithm** was used to simulate steady-state incompressible flow for all cases.
* **Turbulence Models:** * **$k$-$\epsilon$ model:** Used for the Orifice Meter and Sudden Expansion/Contraction studies.
    * **$k$-$\omega$ SST model:** Utilized for the Pipe Bend analysis.
* **Meshing:** Geometry and meshes were created using `blockMeshDict` for pipe flows and ANSYS Design Modeler/Meshing for bend cases.

### Turbulence Boundary Conditions
Inlet properties were calculated using the following engineering relations :
* **Reynolds Number ($Re$):** $Re = \frac{v \cdot d}{\nu}$
* **Intensity ($I$):** $I = 0.16 \cdot Re^{-1/8}$ 
* **Kinetic Energy ($k$):** $k = 1.5 \cdot (u \cdot I)^2$
* **Dissipation Rate ($\epsilon$):** $\epsilon = \frac{C_{\mu} \cdot k^{1.5}}{l}$ 

---

## Key Case Studies & Results

### 1. Orifice Meter
Analysis of turbulent flow through an orifice meter to determine $C_d$.

* **Geometry:** Entrance diameter ($D_1$) of 16mm and orifice diameter ($D_2$) of 8mm.
* **Findings:** $C_d$ was calculated using pressure predicted between the upstream and the **Vena Contracta**, where wall pressure is at its minimum.
* **Validation:** Numerical results showed error margins as low as **0.37%** compared to experimental data.

### 2. Sudden Expansion & Contraction
Investigation of minor loss factors ($K$) and flow separation.

* **Setup:** Larger diameter $D_1 = 14.3$ mm and smaller diameter $D_2 = 9.22$ mm.
* **Results:** Successfully quantified head loss ($h_{min}$) and validated $K$ factors against theoretical and experimental data.

### 3. Smooth vs. Sharp Pipe Bends
A comparative study of loss factors for 90° bends.

* **Smooth Bend:** Utilized a radius of 14.3 mm. Minor loss factors ($K$) were found to be generally lower, with experimental values around **0.31 to 0.46**.
* **Sharp Bend:** Exhibited significantly higher loss factors ($K$), with values reaching up to **0.67** in experimental comparisons.

---

## Repository Structure
* `/Orifice_Meter`: OpenFOAM dictionaries and boundary conditions.
* `/Expansion_Contraction`: Case files and mesh dictionaries for area change simulations.
* `/Pipe_Bends`: Meshing and setup for smooth and sharp elbow comparisons.
* `/Docs`: Final internship report and reference data.

## 🎓 References
* [1] IIT Bombay Thermofluids Lab Manual.
* [2] McCabe, Smith, & Harriott, *Unit Operations of Chemical Engineering*.
* [3] White, F.M., *Viscous Fluid Flow*.
* [4] Shah et al. (2012), Analysis of flow through an orifice meter: CFD simulation.
