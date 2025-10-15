# Per-Unit System

The per-unit system is a method of normalizing electrical quantities—voltage, current, power, and impedance—to a common base. This simplification significantly streamlines power system analysis, especially in large, interconnected grids, by reducing the number of calculations and making it easier to identify potential problems. Using per-unit values allows engineers to quickly understand the relative magnitude of different quantities within the system, regardless of the actual voltage and power levels. It eliminates the need to refer impedances to one side of a transformer.

## Basic Concepts

The core idea behind the per-unit system is to express all electrical quantities as a fraction (or percentage) of a chosen base value. The base values are usually chosen such that they are convenient for the particular system being analyzed. Once the base values are selected, the per-unit value of any quantity is calculated as:

```
Per-Unit Value = (Actual Value) / (Base Value)
```

Typically, two base quantities are chosen independently: a base voltage (V<sub>base</sub>) and a base power (S<sub>base</sub>). Once these two are selected, the other base quantities, such as base current (I<sub>base</sub>) and base impedance (Z<sub>base</sub>), are derived from them:

*   **Base Current (I<sub>base</sub>):** I<sub>base</sub> = S<sub>base</sub> / V<sub>base</sub> (for single-phase systems) or I<sub>base</sub> = S<sub>base</sub> / (√3 * V<sub>base</sub>) (for three-phase systems)
*   **Base Impedance (Z<sub>base</sub>):** Z<sub>base</sub> = V<sub>base</sub> / I<sub>base</sub> = V<sub>base</sub><sup>2</sup> / S<sub>base</sub>

It's important to note that S<sub>base</sub> is a three-phase value in three-phase systems.

## Advantages of Using Per-Unit System

The per-unit system offers several advantages in power system analysis:

*   **Simplified Calculations:** Calculations are simplified because the per-unit impedance of transformers is often the same regardless of which side of the transformer it is calculated from.
*   **Easy Comparison:** Per-unit values allow for easy comparison of different components within a system, even if they operate at different voltage levels.
*   **Error Detection:** Unusual per-unit values can quickly highlight potential problems or errors in the system. For example, a very high per-unit current might indicate a fault.
*   **Manufacturer Data:** Equipment impedances are often provided in per-unit values by manufacturers, simplifying system modeling.
*   **System Invariance:** The per-unit impedance of a transformer is the same whether viewed from the high-voltage or low-voltage side. This eliminates the need to refer impedances across transformers.

## Example: Single-Phase System

Consider a single-phase transformer rated at 10 kVA, 2400/240 V, with a series impedance of 10 + j20 ohms referred to the high-voltage (2400 V) side.

1.  **Choose Base Values:** Let's choose S<sub>base</sub> = 10 kVA and V<sub>base</sub> = 2400 V (on the high-voltage side).

2.  **Calculate Base Impedance:** Z<sub>base</sub> = V<sub>base</sub><sup>2</sup> / S<sub>base</sub> = (2400<sup>2</sup>) / 10000 = 576 ohms

3.  **Calculate Per-Unit Impedance:** Z<sub>pu</sub> = (Actual Impedance) / (Base Impedance) = (10 + j20) / 576 = 0.0174 + j0.0347 pu

Now, consider the low-voltage side. If we choose V<sub>base</sub> = 240 V, then the base impedance is Z<sub>base</sub> = (240<sup>2</sup>) / 10000 = 5.76 ohms. The actual impedance referred to the low-voltage side is (10 + j20) * (240/2400)<sup>2</sup> = 0.1 + j0.2 ohms. The per-unit impedance is Z<sub>pu</sub> = (0.1 + j0.2) / 5.76 = 0.0174 + j0.0347 pu. The per-unit impedance is the same on both sides of the transformer.

## Example: Three-Phase System

A three-phase power system has a 100 MVA, 13.8 kV generator connected to a transformer rated 100 MVA, 13.8 kV Δ / 115 kV Y with a per-unit leakage reactance of 0.08 pu. Choose S<sub>base</sub> = 100 MVA and V<sub>base</sub> = 13.8 kV on the generator side and V<sub>base</sub> = 115 kV on the high-voltage side of the transformer.

The per-unit reactance of the transformer is already given as 0.08 pu. This value remains the same regardless of whether we are referring to the generator side or the high-voltage side, as long as we maintain a consistent base MVA throughout the system.

## Changing Base Values

Sometimes, you need to convert per-unit values from one base to another. The following formula is used:

```
Z_pu_new = Z_pu_old * (V_base_old / V_base_new)^2 * (S_base_new / S_base_old)
```

Where:

*   Z<sub>pu_new</sub> is the per-unit impedance on the new base
*   Z<sub>pu_old</sub> is the per-unit impedance on the old base
*   V<sub>base_old</sub> is the old base voltage
*   V<sub>base_new</sub> is the new base voltage
*   S<sub>base_old</sub> is the old base power
*   S<sub>base_new</sub> is the new base power

**Example:** A transformer has a per-unit impedance of 0.05 pu on a base of 10 MVA and 13.8 kV. What is the per-unit impedance on a base of 20 MVA and 6.9 kV?

Using the formula:

Z<sub>pu_new</sub> = 0.05 * (13.8 / 6.9)<sup>2</sup> * (20 / 10) = 0.05 * 4 * 2 = 0.4 pu

## Common Challenges and Solutions

*   **Incorrect Base Value Selection:** Choosing inappropriate base values can complicate calculations. Solution: Select base values that are close to the actual operating values or the ratings of major equipment.
*   **Confusion with Single-Phase vs. Three-Phase:** Ensure you are using the correct formulas for base current and impedance, depending on whether you are analyzing a single-phase or three-phase system. Always specify whether S<sub>base</sub> is a single-phase or three-phase value.
*   **Changing Base Values Incorrectly:** Using the wrong formula or making errors in the conversion process can lead to incorrect results. Solution: Double-check the formula and ensure the units are consistent.
*   **Forgetting to Convert Back to Actual Values:** After performing calculations in per-unit, remember to convert the results back to actual values for practical interpretation. Solution: Keep track of your base values and use them to convert back to actual values.

## Practical Applications

The per-unit system is widely used in power system studies, including:

*   **Load Flow Analysis:** Determining the voltage and current distribution in a power system under various operating conditions.
*   **Short-Circuit Analysis:** Calculating fault currents to design protective devices and ensure system stability.
*   **Transient Stability Analysis:** Studying the dynamic behavior of a power system following a disturbance, such as a fault or a sudden load change.
*   **Harmonic Analysis:** Analyzing the presence of harmonic currents and voltages in the system.

## Further Learning

For deeper understanding, consider exploring these resources:

*   **Books:**
    *   "Power System Analysis and Design" by J. Duncan Glover, Mulukutla S. Sarma, and Thomas J. Overbye
    *   "Electrical Power Systems: Analysis, Design, and Operation" by A. K. Al-Othman, J. J. Grainger, and William D. Stevenson, Jr.

*   **Online Resources:**
    *   IEEE Power & Energy Society (PES) website: [https://www.ieee-pes.org/](https://www.ieee-pes.org/)
    *   MIT OpenCourseWare offers courses on power system analysis.

## Summary

The per-unit system is a powerful tool for simplifying power system calculations. By normalizing electrical quantities to a common base, it facilitates easier comparison of different components, reduces the complexity of calculations, and helps in identifying potential problems. Understanding the basic concepts, advantages, and limitations of the per-unit system is essential for any power system engineer. Remember to choose appropriate base values, pay attention to single-phase versus three-phase considerations, and always convert back to actual values for practical interpretation. Now, consider how you might apply the per-unit system to analyze a simple power distribution network. What base values would you choose, and why?