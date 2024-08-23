# Semiconductor and Performance Metrics

## Cost per Die
\[ \text{Cost per Die} = \frac{\text{Cost per Wafer}}{\text{Dies per Wafer} \times \text{Yield}} \]

### Dies per Wafer
\[ \text{Dies per Wafer} = \frac{\text{Wafer Area}}{\text{Die Area}} \]

### Yield
\[ \text{Yield} = \frac{1}{\left(1 + \left(\frac{\text{Defects per Area} \times \text{Die Area}}{2}\right)^2\right)} \]

## Performance Metrics
- **Performance**: \( \text{Performance} = \frac{1}{\text{Execution Time}} \)
- **Units**: Programs per second

### Comparing Performance
- **Speedup**: 
  \[ \text{Speedup} = \frac{\text{Performance}_A}{\text{Performance}_B} = \frac{\text{Execution Time}(B)}{\text{Execution Time}(A)} \]

## Iron Law of Computer Performance
- **Execution Time**: 
  \[ \text{Execution Time} = \frac{\# \text{ of Instructions} \times (\# \text{ of Clock Cycles per Instruction})}{\text{Clock Rate}} \]
- **Performance**: 
  \[ \text{Performance} = \text{Clock Rate} \times \frac{1}{\# \text{ of Instructions} \times \text{Cycles per Instruction}} \]

## Miscellaneous Notes

### Yield Equation
The yield equation is "empirically derived," meaning it comes from observations and studies.

### Performance Measurements
- Computations per second
- Floating Point Operations per Second (FLOPS)
- Clock Frequency (e.g., gigahertz)

### Why Hasn't the Clock Rate Improved Much?
- **Power Consumption**: Increasing the clock rate significantly raises power consumption.
  - **Power**: 
    \[ \text{Power} = \text{Dynamic Power} + \text{Static Power} \]
  - **Static Power**: Refers to leakage current, the power flowing through transistors even when they are not actively switching.
  - **Energy**: 
    \[ \text{Energy} = \frac{1}{2} C V^2 \]
  - **Power**: 
    \[ \text{Power} = \frac{1}{2} C V^2 f \]
    - Where \( C \) is the capacitance, \( V \) is the voltage, and \( f \) is the frequency.

