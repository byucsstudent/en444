# Per-Unit System

The per-unit system is a method used to simplify power system calculations by normalizing voltages, currents, impedances, and power with respect to a chosen base value. This normalization process eliminates the need to refer impedances through transformers, significantly simplifying calculations involving power systems with multiple voltage levels. It also provides a more intuitive understanding of system behavior, as values are typically expressed as percentages of their base values. This system is widely used in power system analysis, protection, and control.

Why use per-unit? Imagine trying to analyze a power grid with dozens of transformers, each stepping the voltage up or down. Without per-unit calculations, you'd constantly be converting impedances from one voltage level to another. This is tedious and prone to error. The per-unit system streamlines this process, making calculations much easier to manage.

### Basic Concepts

The per-unit value of any quantity is defined as the ratio of the actual value to a chosen base value. The base value is a reference value chosen for that particular quantity.  The per-unit value is dimensionless.

Mathematically, this is expressed as:

`Quantity (per-unit) = Actual Quantity / Base Quantity`

The key quantities involved in per-unit calculations are:

*   **Voltage (V):** Represents the electrical potential difference.
*   **Current (I):** Represents the flow of electrical charge.
*   **Impedance (Z):** Represents the opposition to the flow of alternating current.
*   **Power (S):** Represents the rate at which electrical energy is transferred (complex power).
*   **Apparent Power (S):** The magnitude of complex power, expressed in volt-amperes (VA).
*   **Active Power (P):** The real part of complex power, expressed in watts (W).
*   **Reactive Power (Q):** The imaginary part of complex power, expressed in volt-amperes reactive (VAR).

### Base Value Selection

The selection of base values is crucial for the per-unit system. Typically, two base values are chosen independently, and the remaining base values are derived from these two. Commonly, the base apparent power (S<sub>base</sub>) and base voltage (V<sub>base</sub>) are selected.

Once S<sub>base</sub> and V<sub>base</sub> are selected, the base current (I<sub>base</sub>) and base impedance (Z<sub>base</sub>) can be calculated as follows:

`I_base = S_base / V_base`

`Z_base = V_base / I_base = V_base^2 / S_base`

For three-phase systems, the base values are usually defined on a per-phase basis.  So, V<sub>base</sub> is the line-to-neutral voltage and S<sub>base</sub> is the three-phase apparent power. The base current and impedance are still calculated using the same formulas above.

**Example:**

Let's say we have a 13.8 kV/480 V, 500 kVA transformer.  We can choose a base apparent power of 500 kVA and a base voltage of 13.8 kV on the high-voltage side.  Then, on the low-voltage side, the base voltage is 480 V, and the base apparent power remains the same, 500 kVA.

### Changing Base Values

Often, it's necessary to change the base values used in a per-unit system, especially when dealing with interconnected systems with different voltage levels and base selections. The following formula is used to convert a per-unit impedance from one base to another:

`Z_pu (new) = Z_pu (old) * (V_base (old) / V_base (new))^2 * (S_base (new) / S_base (old))`

This formula is essential for ensuring that all components in a power system are represented on the same base, allowing for accurate calculations.

**Example:**

A transformer has a per-unit impedance of 0.05 pu on a 10 MVA, 13.8 kV base. What is the per-unit impedance on a 100 MVA, 138 kV base?

Using the formula:

`Z_pu (new) = 0.05 * (13.8 / 138)^2 * (100 / 10) = 0.005`

Therefore, the per-unit impedance on the new base is 0.005 pu.

### Advantages of the Per-Unit System

*   **Simplified Calculations:** Eliminates the need to refer impedances through transformers.
*   **Standardized Values:** Typical impedance values for similar equipment fall within a narrow range in per-unit, facilitating quick estimations and comparisons.
*   **Error Reduction:** Reduces the likelihood of errors in calculations due to the elimination of voltage level conversions.
*   **System Understanding:** Provides a more intuitive understanding of system behavior by expressing values as percentages of base values.
*   **Equipment Comparison:** Facilitates the comparison of equipment ratings and performance across different voltage and power levels.

### Common Challenges and Solutions

*   **Incorrect Base Value Selection:** Choosing inappropriate base values can lead to confusion and inaccurate results.  *Solution:* Carefully select base values that are representative of the system's operating conditions and equipment ratings.  Consistency is key.
*   **Forgetting to Convert Back to Actual Values:** After performing calculations in per-unit, it's crucial to convert the results back to actual values for practical applications. *Solution:* Always remember to multiply the per-unit value by the appropriate base value to obtain the actual value.
*   **Misunderstanding Three-Phase Systems:** Applying single-phase formulas directly to three-phase systems can lead to errors. *Solution:* Ensure that base values are defined on a per-phase basis for three-phase systems. Use line-to-neutral voltage for V<sub>base</sub>.
*   **Changing Bases Mid-Calculation:** Changing base values in the middle of a calculation introduces complexity and potential for errors. *Solution:* Stick to one set of base values for the entire calculation, or convert all values to a common base before proceeding.

### Practical Applications

The per-unit system is used extensively in various power system studies, including:

*   **Load Flow Analysis:** Determining the voltage and power flow throughout the system under various operating conditions.
*   **Short-Circuit Analysis:** Calculating fault currents during short-circuit conditions for protection coordination.
*   **Stability Analysis:** Assessing the system's ability to maintain synchronism after a disturbance.
*   **Protection Coordination:** Designing and coordinating protective devices to isolate faults and minimize system disruptions.
*   **Transformer Modeling:** Representing transformers in power system models for accurate simulation and analysis.

### Let's Practice

Consider a single-phase power system with the following components:

*   Generator: 10 MVA, 13.8 kV, Z = 0.1 pu
*   Transformer T1: 10 MVA, 13.8 kV / 138 kV, Z = 0.08 pu
*   Transmission Line: 100 miles, Z = 0.5 + j1.0 ohms/mile
*   Transformer T2: 10 MVA, 138 kV / 13.8 kV, Z = 0.08 pu
*   Load: 8 MVA, 0.8 power factor lagging, 13.8 kV

1.  Choose a common S<sub>base</sub> (e.g., 10 MVA).
2.  Determine the V<sub>base</sub> for each voltage level (13.8 kV and 138 kV).
3.  Calculate the base impedance for each voltage level.
4.  Convert the transmission line impedance to per-unit.
5.  Draw the per-unit impedance diagram of the system.

This exercise reinforces the concepts and provides a hands-on experience in applying the per-unit system.

### Summary

The per-unit system is a powerful tool for simplifying power system calculations. By normalizing values with respect to chosen base values, it eliminates the need to refer impedances through transformers, reduces the likelihood of errors, and provides a more intuitive understanding of system behavior. Understanding and applying the per-unit system is essential for any power system engineer. Remember to carefully select base values, convert impedances to a common base, and convert results back to actual values for practical applications.