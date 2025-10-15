# Per-Unit System

The per-unit system is a powerful tool for simplifying power system calculations. Instead of dealing with large numbers and various voltage and power levels, the per-unit system normalizes all quantities to a common base, making calculations much easier to manage and interpret. It significantly reduces the chances of errors and provides a clearer picture of the system's behavior. This approach transforms actual values (like volts, amps, ohms) into dimensionless ratios, relative to chosen base values. This normalization simplifies complex calculations, especially in systems with multiple voltage levels due to transformers.

**Why Use the Per-Unit System?**

*   **Simplification:** Reduces the magnitude of numbers, making calculations easier.
*   **Transformer Elimination:** Transformers' turns ratios are effectively eliminated from calculations (ideal transformers), simplifying network analysis.
*   **Equipment Comparison:** Allows easy comparison of equipment parameters across different voltage and power levels.
*   **Error Reduction:** Reduces the likelihood of errors in calculations due to consistent units and smaller magnitudes.
*   **Standardization:** Facilitates the use of standardized impedance values for equipment.

**Basic Concepts**

The per-unit value of any quantity is defined as:

```
Per-Unit Value = (Actual Value) / (Base Value)
```

The base values are chosen arbitrarily, but certain relationships must be maintained. The most common choice is to select base values for apparent power (S<sub>base</sub>) and voltage (V<sub>base</sub>). From these, the base values for current (I<sub>base</sub>) and impedance (Z<sub>base</sub>) can be derived.

**Base Value Selection**

1.  **Apparent Power (S<sub>base</sub>):**  A convenient value for the entire system is chosen, typically in MVA (Mega Volt-Amperes). This value remains constant throughout the system, regardless of voltage levels.
2.  **Voltage (V<sub>base</sub>):** The base voltage is typically selected based on the nominal voltage of a specific section of the power system.  When dealing with transformers, the voltage base changes across the transformer based on the transformer's turns ratio.  It's crucial to select the correct base voltage for each voltage level in the system.
3.  **Current (I<sub>base</sub>):** Derived from S<sub>base</sub> and V<sub>base</sub> using the following formula:

    ```
    I_base = S_base / (sqrt(3) * V_base)  (for three-phase systems)
    I_base = S_base / V_base              (for single-phase systems)
    ```
4.  **Impedance (Z<sub>base</sub>):** Derived from V<sub>base</sub> and I<sub>base</sub> using Ohm's Law:

    ```
    Z_base = V_base / I_base = V_base^2 / S_base
    ```

**Example: Calculating Base Values**

Let's consider a 13.8 kV/138 kV transformer rated at 10 MVA. We choose a base apparent power of 10 MVA for the entire system.

*   **Low-Voltage Side (13.8 kV):**
    *   S<sub>base</sub> = 10 MVA
    *   V<sub>base</sub> = 13.8 kV
    *   I<sub>base</sub> = 10 MVA / (sqrt(3) * 13.8 kV) = 418.37 A
    *   Z<sub>base</sub> = (13.8 kV)^2 / 10 MVA = 19.044 ohms

*   **High-Voltage Side (138 kV):**
    *   S<sub>base</sub> = 10 MVA
    *   V<sub>base</sub> = 138 kV
    *   I<sub>base</sub> = 10 MVA / (sqrt(3) * 138 kV) = 41.84 A
    *   Z<sub>base</sub> = (138 kV)^2 / 10 MVA = 1904.4 ohms

Notice how the base impedance differs significantly between the low-voltage and high-voltage sides.

**Converting Actual Values to Per-Unit**

Once the base values are determined, you can convert any actual value to its per-unit equivalent.

**Example: Converting Impedance to Per-Unit**

Suppose a transmission line has an impedance of 10 + j50 ohms, and the base impedance for that section of the system is 100 ohms.

*   Z<sub>actual</sub> = 10 + j50 ohms
*   Z<sub>base</sub> = 100 ohms
*   Z<sub>pu</sub> = (10 + j50) / 100 = 0.1 + j0.5 pu

**Changing Base Values**

Sometimes, you may need to change the base values used in a calculation.  For instance, you might have impedance data provided on one base, but your system calculations require a different base.  The following formula allows you to convert per-unit impedance from one base to another:

```
Z_pu_new = Z_pu_old * (V_base_old / V_base_new)^2 * (S_base_new / S_base_old)
```

**Example: Changing Base Values**

A generator has a reactance of 0.2 pu on a base of 13.8 kV and 50 MVA.  What is the per-unit reactance on a base of 13.2 kV and 75 MVA?

*   Z<sub>pu_old</sub> = 0.2 pu
*   V<sub>base_old</sub> = 13.8 kV
*   S<sub>base_old</sub> = 50 MVA
*   V<sub>base_new</sub> = 13.2 kV
*   S<sub>base_new</sub> = 75 MVA

```
Z_pu_new = 0.2 * (13.8 / 13.2)^2 * (75 / 50) = 0.329 pu
```

**Applying Per-Unit to Power System Components**

*   **Generators:** Generator parameters (reactance, voltage) are typically given in per-unit.
*   **Transformers:**  A key advantage of the per-unit system is that the transformer's turns ratio is implicitly accounted for. When the base voltages are chosen according to the transformer's voltage ratio, the per-unit impedance of the transformer is the same whether referred to the high-voltage or low-voltage side. This simplifies circuit analysis because the ideal transformer can be removed from the equivalent circuit.
*   **Transmission Lines:** Line impedance is converted to per-unit using the appropriate base values.
*   **Loads:** Loads can be represented as constant impedances, constant currents, or constant power, and their values are converted to per-unit.

**Common Challenges and Solutions**

*   **Incorrect Base Value Selection:** This is a common source of errors.  Double-check that the base values are consistent throughout the system and that voltage bases are correctly adjusted across transformers. *Solution:* Carefully track base values for each zone of the power system.  Use a single-line diagram to visually represent the system and note base values at each location.
*   **Forgetting to Convert Back to Actual Values:** After performing calculations in per-unit, remember to convert the results back to actual values for practical interpretation. *Solution:*  Clearly label all per-unit values and include a reminder to convert back to actual values at the end of the calculation.
*   **Mixing Single-Phase and Three-Phase Base Values:** Ensure consistency. If using three-phase base values, all calculations must be done on a three-phase basis. *Solution:*  Explicitly state whether you are using single-phase or three-phase base values.  When converting between the two, use the appropriate conversion factors (e.g., sqrt(3) for voltage and current).
*   **Dealing with Three-Winding Transformers:** Three-winding transformers require careful consideration of base values and equivalent impedances. *Solution:* Use the wye-equivalent circuit representation of the three-winding transformer and ensure that the base values are consistent across all three windings.

**Engagement and Further Exploration**

To solidify your understanding, consider these steps:

*   **Work Through Examples:** Practice converting actual values to per-unit and vice versa. Solve power flow problems using the per-unit system.
*   **Simulate a Simple Power System:** Use power system simulation software (e.g., PowerWorld, ETAP, PSS/E) to model a small power system and perform calculations in per-unit.
*   **Review IEEE Standards:** Consult IEEE standards related to per-unit systems for more in-depth information and best practices.
*   **Reflect:** How does using per-unit simplify calculations in systems with multiple voltage levels?  What are the potential pitfalls of using per-unit and how can they be avoided?

**Summary**

The per-unit system is a valuable tool for simplifying power system analysis. By normalizing quantities to a common base, it reduces calculation complexity, minimizes errors, and facilitates equipment comparison. Understanding the principles of base value selection, conversion to per-unit, and base changing is crucial for effective application of this technique. While challenges exist, careful attention to detail and consistent application of the principles will lead to accurate and efficient power system calculations.