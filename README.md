# Erratic Rectilinear Analysis Code

This Python script performs motion analysis based on user-provided input functions for position, velocity, and acceleration. The program uses symbolic computation with SymPy and numerical evaluation with NumPy to generate plots of motion graphs. Below is the explanation of the code, how it works, and instructions for using it.

## Theory

The program is based on the fundamental principles of kinematics:

1. **Position, Velocity, and Acceleration Relations**:
   - Velocity \(v(t)\) is the first derivative of position \(s(t)\) with respect to time.
   - Acceleration \(a(t)\) is the first derivative of velocity \(v(t)\) or the second derivative of position \(s(t)\).

   \[
   v(t) = \frac{d}{dt}s(t), \quad a(t) = \frac{d}{dt}v(t)
   \]

2. **Velocity-Displacement and Acceleration-Displacement Relations**:
   - Velocity and acceleration can be expressed as functions of displacement \(s\):

   \[
   a(s) = v(s) \cdot \frac{dv}{ds}
   \]

3. **Numerical Computation and Visualization**:
   - User-defined functions for position, velocity, or acceleration are parsed symbolically and evaluated over specific intervals.
   - The results are plotted to visualize the motion over time or displacement.

---

## How to Use

### 1. Run the Program
Ensure you have Python installed with the following libraries:
- SymPy
- NumPy
- Matplotlib

Install any missing dependencies using:
```bash
pip install sympy numpy matplotlib
```
Run the script in any Python environment.

### 2. Select the Mode
When prompted, select the type of input function you want to provide:
- `position`: Input position as a function of time \(s(t)\).
- `acceleration`: Input acceleration as a function of time \(a(t)\).
- `vs-as`: Analyze motion based on velocity-displacement \(v(s)\) or acceleration-displacement \(a(s)\) relations.
- `velocity`: Input velocity as a function of time \(v(t)\).

### 3. Follow Prompts for Each Mode

#### **Position Mode**
1. Enter the number of time intervals.
2. For each interval:
   - Provide the position function \(s(t)\) (e.g., `3*t**2 + 2*t + 1`).
   - Input the start and end times for the interval.
3. The program calculates velocity and acceleration from the position function and plots the results.

#### **Acceleration Mode**
1. Enter the number of acceleration phases.
2. Provide initial velocity and position.
3. For each phase:
   - Enter the acceleration function \(a(t)\) (e.g., `10`, or `3*t`).
   - Specify the duration for the phase or solve for it if unknown.
4. The program computes velocity and position functions and plots the motion.

#### **Velocity-Displacement and Acceleration-Displacement Mode (vs-as)**
1. Specify the number of intervals.
2. For each interval:
   - Choose between `v-s` or `a-s` scenario.
   - Enter the respective function (e.g., `2*s + 1` for \(v(s)\) or `3*s + 2` for \(a(s)\)).
   - Provide start and end displacement values.
3. The program derives related functions, calculates time, and plots velocity-displacement or acceleration-displacement graphs.

#### **Velocity Mode**
1. Enter the number of time intervals.
2. For each interval:
   - Input the velocity function \(v(t)\) (e.g., `3*t**2 + 2*t + 1`).
   - Provide the start and end times, and initial position.
3. The program computes position and acceleration functions and visualizes them.

---

## Outputs
- **Position-Time Graph**: Visual representation of position \(s(t)\).
- **Velocity-Time Graph**: Derived from the position or provided by the user.
- **Acceleration-Time Graph**: Calculated as the derivative of velocity.
- **Velocity-Displacement and Acceleration-Displacement Graphs**: For `vs-as` mode.

---

## Example Usage

### Example 1: Position Mode
```plaintext
Do you want to input a position function, acceleration scenario, v-s/a-s scenario, or velocity function v(t)? (position/acceleration/vs-as/velocity): position
Enter the number of time intervals: 1
Enter the position function s(t) for interval 1 (e.g., 3*t**2 + 2*t + 1): 3*t**2 + 2*t + 1
Enter the start time for interval 1: 0
Enter the end time for interval 1: 5
```
**Output**: Plots for position, velocity, and acceleration vs. time.

### Example 2: Acceleration Mode
```plaintext
Do you want to input a position function, acceleration scenario, v-s/a-s scenario, or velocity function v(t)? (position/acceleration/vs-as/velocity): acceleration
Enter the number of acceleration phases: 1
Enter the initial velocity: 0
Enter the initial position: 0
Enter the acceleration for phase 1: 9.81
Enter the duration for phase 1 (in seconds or 't' if unknown): 10
```
**Output**: Plots for position, velocity, and acceleration vs. time.

---

