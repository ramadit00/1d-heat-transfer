# 2D Transient Heat Transfer Simulator

A web-based numerical simulator for solving 2D transient heat conduction problems using the Finite Difference Method (FDM).

## 🔥 Features

- **Real-time Animation**: Watch temperature distribution evolve over time
- **Interactive Parameters**: Customize domain size, boundary conditions, material properties, and simulation time
- **Numerical Stability**: Automatic time step calculation ensuring stability (Fourier number criterion)
- **Responsive Visualization**: Smooth animated heatmap with color-coded temperature distribution
- **GIF Export**: Save simulation results as animated GIF files
- **All SI Units**: Length (m), Temperature (°C), Thermal conductivity (W/m·K), Time (s)

## 📐 Mathematical Background

### Governing Equation

The 2D heat diffusion equation:

```
∂T/∂t = α(∂²T/∂x² + ∂²T/∂y²)
```

where:
- **T** = Temperature (K)
- **t** = Time (s)
- **α** = Thermal diffusivity (m²/s) = k/(ρ·c_p)
- **k** = Thermal conductivity (W/m·K)
- **ρ** = Density (kg/m³)
- **c_p** = Specific heat capacity (J/kg·K)

### Numerical Method

**Explicit Finite Difference Scheme:**

```
T(i,j)^(n+1) = T(i,j)^n + Fo_x[T(i+1,j)^n - 2T(i,j)^n + T(i-1,j)^n]
                        + Fo_y[T(i,j+1)^n - 2T(i,j)^n + T(i,j-1)^n]
```

where:
- **Fo_x** = α·Δt/Δx² (Fourier number in x-direction)
- **Fo_y** = α·Δt/Δy² (Fourier number in y-direction)

**Stability Criterion:**
```
Fo_x + Fo_y ≤ 0.5
```

The simulator automatically calculates the appropriate time step (Δt) to satisfy this stability condition.

## 🚀 Usage

### Running the Simulator

Simply open `index.html` in a modern web browser. No installation or server required!

### Input Parameters

1. **Geometry**:
   - Length (x-direction) [m]
   - Width (y-direction) [m]

2. **Boundary Conditions** [°C]:
   - Top boundary temperature
   - Bottom boundary temperature
   - Left boundary temperature
   - Right boundary temperature

3. **Material Properties**:
   - Thermal Conductivity [W/m·K]
   - Density [kg/m³]
   - Specific Heat [J/kg·K]

4. **Simulation Settings**:
   - Simulation Time [s]
   - Grid Points in x-direction (10-200)
   - Grid Points in y-direction (10-200)

### Example Cases

#### Case 1: Steel Plate
- Material: Steel
- Thermal conductivity: 50 W/m·K
- Density: 7800 kg/m³
- Specific heat: 500 J/kg·K
- Boundary: Hot top (100 °C), Cold bottom (0 °C), Moderate sides (27 °C)

#### Case 2: Aluminum Plate
- Material: Aluminum
- Thermal conductivity: 205 W/m·K
- Density: 2700 kg/m³
- Specific heat: 900 J/kg·K

#### Case 3: Copper Plate
- Material: Copper
- Thermal conductivity: 400 W/m·K
- Density: 8960 kg/m³
- Specific heat: 385 J/kg·K

## 🎨 Visualization

The simulator displays:
- **Animated heatmap**: Color-coded temperature distribution (blue=cold, red=hot)
- **Real-time status**: Current simulation time, progress, time step, and Fourier numbers
- **Interactive controls**: Start/Stop simulation, Export to GIF

### Exporting Results

After running a simulation, click the "Save as GIF" button to export the animation as an animated GIF file. The GIF will contain up to 100 frames captured throughout the simulation, making it easy to share or present your results.

## 🔬 Technical Details

- **Method**: Explicit Finite Difference Method (FDM)
- **Scheme**: Central difference in space, forward difference in time
- **Boundary Conditions**: Dirichlet (fixed temperature)
- **Initial Condition**: Linear interpolation from boundaries
- **Visualization**: Plotly.js heatmap

## 📊 Performance

- Grid resolution affects accuracy and computation time
- Recommended: 50x50 grid points for balance
- Higher resolution (100x100+) gives better accuracy but slower animation
- Automatic time step ensures stability

## 🌐 Browser Compatibility

Works on all modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari

## 📝 License

MIT License

## 👨‍💻 Author

Created using numerical methods for heat transfer simulation.
