# Per-Unit System

The per-unit system is a method used to simplify power system calculations by normalizing voltage, current, power, and impedance values to a common base. This normalization process eliminates the need to refer impedances through transformers, greatly reducing the complexity of calculations, especially in systems with multiple voltage levels. By expressing all quantities as a fraction of a chosen base value, the per-unit system provides a more intuitive and consistent representation of system behavior.

Why use the per-unit system? It simplifies calculations, especially when dealing with transformers. Transformers change voltage and current levels, making direct comparisons of impedance on different sides difficult. The per-unit system eliminates this problem by expressing all impedances relative to a common base, allowing for easier analysis of power system performance and fault conditions. It also helps in identifying abnormal conditions by providing a standardized reference.

## Base Values

The foundation of the per-unit system lies in selecting appropriate base values. Two base values are chosen, typically base voltage ($V_{base}$) and base apparent power ($S_{base}$). From these, the base current ($I_{base}$) and base impedance ($Z_{base}$) can be derived.

The relationships are as follows:

*   $I_{base} = \frac{S_{base}}{V_{base}}$
*   $Z_{base} = \frac{V_{base}^2}{S_{base}}$

It's crucial to select consistent base values across different voltage levels within the system. Commonly, a single $S_{base}$ is chosen for the entire system, simplifying calculations significantly. The $V_{base}$ is then chosen to match the nominal voltage level at each location.

**Example:**

Consider a 13.8 kV / 480 V transformer rated at 500 kVA. Let's choose a base apparent power of $S_{base} = 500 \text{ kVA}$.

*   On the high-voltage side: $V_{base, HV} = 13.8 \text{ kV}$
*   On the low-voltage side: $V_{base, LV} = 480 \text{ V}$

Now we can calculate the base currents and impedances:

*   $I_{base, HV} = \frac{S_{base}}{V_{base, HV}} = \frac{500,000 \text{ VA}}{13,800 \text{ V}} \approx 36.23 \text{ A}$
*   $I_{base, LV} = \frac{S_{base}}{V_{base, LV}} = \frac{500,000 \text{ VA}}{480 \text{ V}} \approx 1041.67 \text{ A}$
*   $Z_{base, HV} = \frac{V_{base, HV}^2}{S_{base}} = \frac{(13,800 \text{ V})^2}{500,000 \text{ VA}} \approx 381.12 \ \Omega$
*   $Z_{base, LV} = \frac{V_{base, LV}^2}{S_{base}} = \frac{(480 \text{ V})^2}{500,000 \text{ VA}} \approx 0.4608 \ \Omega$

## Per-Unit Conversion

Once the base values are established, any actual value can be converted to a per-unit value using the following formula:

$Value_{pu} = \frac{Value_{actual}}{Value_{base}}$

For example, if the actual voltage at a certain point in the system is 13.5 kV and the base voltage at that point is 13.8 kV, then the per-unit voltage is:

$V_{pu} = \frac{13,500 \text{ V}}{13,800 \text{ V}} \approx 0.978 \text{ pu}$

Similarly, impedances, currents, and power can be converted to per-unit values.

## Transformer Impedance

One of the most significant advantages of the per-unit system is its handling of transformer impedances. When referred to the same base, the per-unit impedance of a transformer is the same regardless of which side of the transformer it is calculated from. This greatly simplifies network calculations.

If a transformer has an impedance of $Z_{pu}$ on a base of $S_{base1}$ and $V_{base1}$, and we want to find the per-unit impedance $Z_{pu,new}$ on a new base of $S_{base2}$ and $V_{base2}$, the following formula can be used:

$Z_{pu,new} = Z_{pu} \cdot \frac{S_{base1}}{S_{base2}} \cdot \left(\frac{V_{base2}}{V_{base1}}\right)^2$

**Example:**

A transformer is rated 10 MVA, 13.8 kV / 2.4 kV and has a per-unit impedance of 0.08 pu on its own base. If we choose a system base of 20 MVA and 13.8 kV at the high-voltage side, what is the per-unit impedance of the transformer referred to the new base?

$Z_{pu,new} = 0.08 \text{ pu} \cdot \frac{10 \text{ MVA}}{20 \text{ MVA}} \cdot \left(\frac{13.8 \text{ kV}}{13.8 \text{ kV}}\right)^2 = 0.04 \text{ pu}$

## Advantages of the Per-Unit System

*   **Simplified Calculations:** Eliminates the need to refer impedances through transformers.
*   **Consistent Representation:** Provides a standardized reference for system parameters.
*   **Easy Comparison:** Allows for easy comparison of equipment ratings and performance.
*   **Error Detection:** Helps in identifying abnormal conditions and potential errors in calculations.
*   **Industry Standard:** Widely used in power system analysis software and industry practices.

## Common Challenges and Solutions

*   **Incorrect Base Value Selection:** Choosing inconsistent or incorrect base values can lead to significant errors. Ensure that base values are properly selected and consistent across different voltage levels. Double-check your calculations!
*   **Confusion with Actual Values:** It's easy to confuse per-unit values with actual values. Always label your values clearly and remember to convert back to actual values when needed for practical applications.
*   **Changing Base Values:** When changing base values, use the appropriate conversion formula to update all per-unit quantities. It's a common source of error to forget to update all relevant values.

## Example System Calculation

Consider a simple power system consisting of a generator, a transformer, and a load.

*   Generator: 100 MVA, 13.8 kV, $X = 0.15 \text{ pu}$
*   Transformer: 100 MVA, 13.8 kV / 138 kV, $X = 0.10 \text{ pu}$
*   Load: 80 MVA, 132 kV, 0.8 power factor lagging

Let's choose a system base of 100 MVA and 13.8 kV at the generator.  Therefore, the base voltage at the load is 138 kV.

1.  **Generator Impedance:**  The generator impedance is already given in per-unit on the base of 100 MVA and 13.8 kV, so $X_{gen,pu} = 0.15 \text{ pu}$.

2.  **Transformer Impedance:** The transformer impedance is also given in per-unit on the base of 100 MVA and 13.8 kV / 138 kV, so $X_{trans,pu} = 0.10 \text{ pu}$.

3.  **Load Impedance:**  First, calculate the load impedance in ohms.  The load apparent power is 80 MVA at 132 kV.
    $S_{load} = 80 \text{ MVA} = 80 \angle \cos^{-1}(0.8) = 64 + j48 \text{ MVA}$
    $Z_{load} = \frac{V^2}{S^*} = \frac{(132 \text{ kV})^2}{(64 - j48) \text{ MVA}} = \frac{132^2}{80 \times 10^6 \angle -\cos^{-1}(0.8)} \text{ V}^2/\text{VA} = 217.8 + j163.35 \ \Omega$

    Now, calculate the base impedance at the load:
    $Z_{base,load} = \frac{V_{base,load}^2}{S_{base}} = \frac{(138 \text{ kV})^2}{100 \text{ MVA}} = 190.44 \ \Omega$

    Finally, calculate the per-unit load impedance:
    $Z_{load,pu} = \frac{Z_{load}}{Z_{base,load}} = \frac{217.8 + j163.35}{190.44} \approx 1.144 + j0.858 \text{ pu}$

With all impedances in per-unit, you can now perform various power system studies, such as load flow analysis or fault calculations, much more easily.

## Summary

The per-unit system is a powerful tool for simplifying power system calculations. By normalizing voltage, current, power, and impedance values to a common base, it eliminates the need to refer impedances through transformers and provides a more intuitive representation of system behavior. Understanding base value selection, per-unit conversion, and the advantages of the system are crucial for effective power system analysis. Remember to double-check your base values and conversions to avoid common errors. Embrace the per-unit system, and you'll find power system calculations becoming significantly more manageable!

## Further Exploration

For a deeper dive into the per-unit system and its applications, consider exploring these resources:

*   **Textbooks:** "Power System Analysis and Design" by J. Duncan Glover, Mulukutla S. Sarma, and Thomas J. Overbye.
*   **IEEE Standards:** Consult relevant IEEE standards for power system analysis.
*   **Online Tutorials:** Search for online tutorials and videos on the per-unit system for visual and interactive learning.