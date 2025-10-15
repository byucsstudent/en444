# Per-Unit System

The per-unit system is a method used in power system analysis to simplify calculations by normalizing voltage, current, impedance, and power with respect to a chosen base value. This normalization eliminates the need to refer impedances to a common voltage level, which greatly simplifies calculations, especially in systems with multiple voltage transformations (e.g., transformers). It provides a consistent and easily comparable way to represent electrical quantities, regardless of the voltage or power level. It reduces the chance of errors and makes it easier to compare different power system components. Quantities are expressed as a fraction (or percentage) of a chosen base value.

## Base Values

The foundation of the per-unit system lies in selecting appropriate base values.  Two base values are independently chosen, and the other base values are derived from these.  Typically, the base apparent power ($S_{base}$) and base voltage ($V_{base}$) are chosen.  Once these are selected, the base current ($I_{base}$) and base impedance ($Z_{base}$) can be calculated as follows:

$I_{base} = \frac{S_{base}}{V_{base}}$

$Z_{base} = \frac{V_{base}^2}{S_{base}}$

It's crucial to understand that the choice of base values is *arbitrary*, but consistency is key.  Once base values are selected, they must be used throughout the entire calculation for that particular system.

**Example:**

Let's say we have a power system with a base apparent power of 100 MVA and a base voltage of 13.8 kV.  Then:

$I_{base} = \frac{100 \times 10^6 \text{ VA}}{13.8 \times 10^3 \text{ V}} = 7246.38 \text{ A}$

$Z_{base} = \frac{(13.8 \times 10^3 \text{ V})^2}{100 \times 10^6 \text{ VA}} = 1.9044 \ \Omega$

## Per-Unit Conversion

Once the base values are known, any actual value can be converted to a per-unit value using the following general formula:

$Quantity_{pu} = \frac{Quantity_{actual}}{Quantity_{base}}$

For example, if a line has an impedance of 0.9522 $\Omega$ and our base impedance is 1.9044 $\Omega$ (as calculated above), then the per-unit impedance is:

$Z_{pu} = \frac{0.9522 \ \Omega}{1.9044 \ \Omega} = 0.5 \ pu$

Similarly, any voltage, current, or power can be converted to per-unit values using their respective base values.

## Advantages of the Per-Unit System

The per-unit system offers several significant advantages:

*   **Simplified Calculations:** Eliminates the need to refer impedances across transformers, simplifying network analysis.
*   **Consistent Representation:** Provides a consistent way to represent electrical quantities, regardless of the voltage or power level.
*   **Reduced Errors:** Reduces the chance of errors in calculations.
*   **Easy Comparison:** Makes it easier to compare different power system components.  Typical impedance values for generators, transformers, and lines often fall within a relatively narrow range when expressed in per-unit.
*   **Manufacturers Data:** Equipment impedances are often specified in per-unit.
*   **Transformer Turns Ratio Eliminated:** When using per-unit values calculated on appropriate bases, transformers can often be ignored in calculations (except for phase shift effects in three-phase systems).

## Changing Base Values

Sometimes, it becomes necessary to change the base values used in a per-unit system. This is particularly common when analyzing systems with multiple voltage levels where different sections of the system may have different base voltages. The following formula allows you to convert a per-unit value from one base to another:

$Z_{pu,new} = Z_{pu,old} \times \frac{V_{base,old}^2}{V_{base,new}^2} \times \frac{S_{base,new}}{S_{base,old}}$

Similarly, for impedance:

$I_{pu,new} = I_{pu,old} \times \frac{V_{base,old}}{V_{base,new}} \times \frac{S_{base,new}}{S_{base,old}}$

**Example:**

Suppose a transformer has a per-unit impedance of 0.1 pu on a base of 10 MVA and 13.8 kV. What is its per-unit impedance on a base of 20 MVA and 34.5 kV?

$Z_{pu,new} = 0.1 \text{ pu} \times \frac{(13.8 \text{ kV})^2}{(34.5 \text{ kV})^2} \times \frac{20 \text{ MVA}}{10 \text{ MVA}} = 0.032 \text{ pu}$

## Three-Phase Systems

The per-unit system can be readily applied to three-phase systems. When dealing with three-phase systems, the base apparent power ($S_{base}$) is typically the three-phase apparent power, and the base voltage ($V_{base}$) is the line-to-line voltage. The base impedance is calculated using the line-to-line base voltage. For single-phase equivalent circuits, the per-phase values are used.

## Common Challenges and Solutions

*   **Incorrect Base Value Selection:** The most common error is using inconsistent base values. Ensure that the base values are clearly defined and consistently used throughout the entire system.  Always double-check your base values!
*   **Confusion with Single-Phase vs. Three-Phase:** Be careful to distinguish between single-phase and three-phase base values. For three-phase systems, use the three-phase apparent power and line-to-line voltage as base values.
*   **Changing Base Values:** When changing base values, carefully apply the conversion formula to ensure accurate results.  Pay close attention to which values are "old" and which are "new."
*   **Forgetting to Convert Back:** Remember to convert your per-unit results back to actual values at the end of the calculation to obtain meaningful results.

## Practical Applications

The per-unit system is widely used in power system analysis for various applications, including:

*   **Load Flow Studies:** Determining the voltage and current distribution in a power system under various operating conditions.
*   **Fault Analysis:** Calculating fault currents during short circuits, which is essential for protective device coordination.
*   **Stability Analysis:** Assessing the stability of a power system under transient conditions.
*   **Protection Coordination:** Coordinating the operation of protective relays and circuit breakers to isolate faults effectively.

## Summary

The per-unit system is a powerful tool for simplifying power system calculations. By normalizing electrical quantities with respect to chosen base values, it eliminates the need to refer impedances across transformers, reduces the chance of errors, and provides a consistent way to represent and compare different power system components. Understanding the principles of base value selection, per-unit conversion, and base value changes is crucial for effectively applying the per-unit system in power system analysis. Remember to always double-check your base values and convert back to actual values at the end of your calculations!

## Further Exploration

For a deeper understanding, consider exploring the following resources:

*   Stevenson, William D., Jr. *Elements of Power System Analysis*. McGraw-Hill.
*   Glover, J. Duncan, Mulukutla S. Sarma, and Thomas J. Overbye. *Power System Analysis and Design*. Cengage Learning.

Consider these points for further thought:

*   How does the per-unit system simplify calculations in systems with multiple voltage levels?
*   What are the advantages and disadvantages of using the per-unit system?
*   How does the choice of base values affect the per-unit values of different components?