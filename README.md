# CSTR-Desktop
![CTSR Logo](./assets/Image_README.png)

This project was developed as part of the
**Practical Programming in Chemistry (CHE-200)** course at EPFL.

**CSTR** is a flexible and modular simulator for a continuous flow stirred tank reactor. It models
a chemical reactions, including recycle streams, reversible and irreversible steps, and
temperature effects.

The tool helps analyze dynamic behavior and optimize key process variables to **maximize the selectivity** 
towards a desired product.

---
### 👥 Team

This project was developed by three bachelor students in Chemistry and Chemical Engineering at EPFL, as part of the CHE-200 course.

- **Yann Woeffray**           [![GitHub](https://img.shields.io/badge/GitHub-yann--woeffray-black?logo=github)](https://github.com/yann-woeffray)

- **Delio Vozza**             [![GitHub](https://img.shields.io/badge/GitHub-DelioVozza-black?logo=github)](https://github.com/DelioVozza)

- **Andrea Bonnefous**        [![GitHub](https://img.shields.io/badge/GitHub-Andrea--Bonnefous-black?logo=github)](https://github.com/Andrea-Bonnefous)

---
### ✨ Features

🔁 **Recycle loop integration**  
Simulates a continuous stirred-tank reactor (CSTR) with a recycle stream.

🧪 **Steady-state calculations**  
Computes concentrations for key species (e.g. CO, CH₃OH, CH₃COOH).

🔄 **Feed and recycle contributions**  
Handles both fresh feed and recycle inputs.

🧮 **Reactor performance metrics**  
Calculates:
- ⏱️ Residence time  
- 💧 Exit flow rate  
- ⚛️ Reaction rates  
- 📉 Reactant conversions

🌡️ **Adjustable temperature**  
Specify operating temperature.

📊 **Result summary**  
Outputs a clean textual summary with all key parameters.

📈 **Graphical visualization**  
Displays a flowchart that represents the process

---
### 🧠 What is a CSTR?

A Continuous Stirred Tank Reactor (CSTR) is a fundamental type of reactor used in chemical engineering. In a CSTR, reactants are continuously introduced into a well-mixed tank, and products are simultaneously withdrawn. The constant stirring ensures that the composition and temperature are uniform throughout the reactor. This configuration allows the system to operate at steady-state and makes it particularly suitable for continuous large-scale processes.

CSTRs offer several practical advantages. Their design is relatively simple and easy to scale up, making them cost-effective for industrial production. They allow precise control over key variables such as temperature, pressure, and residence time. In addition, because the reactor is continuously fed and emptied, it is ideal for automated, uninterrupted production lines. The constant mixing also helps avoid the formation of hot spots or concentration gradients, which is especially important for sensitive reactions.

CSTRs are widely used in industrial applications. For example, in the **production of polyethylene** (plastic), CSTRs are employed to maintain a controlled polymerization environment and ensure uniform product quality. The steady-state operation and good heat transfer properties make them suitable for exothermic reactions like this. Another example is **wastewater treatment**, where CSTRs are used in biological reactors to maintain optimal conditions for microbial degradation of pollutants. The continuous flow and mixing ensure that the bacteria are evenly distributed and active throughout the reactor, maximizing the treatment efficiency.

---
## ⚙️ How does it work?

The CTSR Simulator follows a modular pipeline composed of the following steps:

1. **🧪 Reaction Input**
   - The user specifies one chemical reactions from the database provided.
   - The program allows automatic retrieval of kinetic and thermodynamic parameters (e.g. Activation energy, rate constants).

2. **⚙️ Parameter Configuration**
   - Users define operating parameters such as:
     - Reactor volume
     - Flow rate
     - Temperature

3. **🧮 Simulation Execution**
   - The model solves mass balance equations at steady state.
   - It calculates:
     - Species concentrations
     - Reaction rates
     - Residence time
     - Conversion levels


4. **Web Interface**
   - A streamlit interface is created representing displaying a scheme of a flowchart representing the reaction
   - The results of the simulations are displayed

---
## 🗂️ Project Structure
```bash
## 📦 Project Structure

CTSR/
├── assets/                           # Images and diagrams for documentation
│   └── Image_README.png
├── notebooks/                        # Jupyter notebooks for development and demos
│   └── CSTR_simulation.ipynb         # Main interactive notebook to explore key functions
├── src/
│   └── projet_chem200/
│       ├── cstr_simulator/
│       │   ├── pycache/
│       │   └── functions.py          # Core simulator logic: CSTRSimulator, methods, kinetics
│       └── cstr_streamlit/
│           ├── .DS_Store
│           └── final_streamlit_cstr4.py  # Streamlit frontend for the simulator
├── tests/                            # Unit tests for core components
│   ├── test_fonctions.py
│   └── test_simulation.py
├── LICENSE.txt
├── README.md                         # Project documentation
└── environment.yml                   # Conda environment file with all dependencies
```
---
### 🛠️ Installation & Requirements

This project uses a Conda environment to manage dependencies.  
All required packages are listed in the file `environment.yml`.

#### 📄 Requirements

Main packages included:
Python 3.10
- `numpy`, `scipy` — numerical computations and optimization
- `matplotlib` — plotting
- `pandas` — data management
- `streamlit` — web interface
- `tkinter` — desktop interface (Tk GUI)
- `json` — data storage (Python standard)
- `jupyterlab` — for notebook usage

✅ Getting Started with a Clean Environment

To ensure smooth setup and compatibility, we recommend creating a dedicated Conda environment for the project.

🧪 Create the environment
```bash
# Clone the repository (if not already done)
git clone https://github.com/Andrea-Bonnefous/CTSR-Desktop.git
cd CTSR-Desktop

# Create and activate the environment from the YAML file
conda env create -f environment.yml
conda activate cstr_env
```
🚀 Run the project
```bash
# ▶️ Run the main simulation script (if implemented)
python main.py

# 🌐 Launch the web interface (Streamlit version)
streamlit run src/projet_chem200/cstr_streamlit/final_streamlit_cstr4.py

# 🧪 Open the main interactive notebook
jupyter lab notebooks/CSTR_simulation.ipynb
```
## ✅ Test Coverage Summary

| File                                             | Stmts | Miss | Cover |
|--------------------------------------------------|-------|------|--------|
| `tests/functions.py`                             | 368   | 65   | 82%    |
| `tests/test_calculate_conversion.py`             | 16    | 1    | 94%    |
| `tests/test_calculate_elemental_balance.py`      | 16    | 1    | 94%    |
| `tests/test_calculate_reaction_rates.py`         | 14    | 1    | 93%    |
| `tests/test_calculate_yield.py`                  | 14    | 1    | 93%    |
| `tests/test_create_visualization.py`             | 15    | 1    | 93%    |
| `tests/test_database.py`                         | 9     | 1    | 89%    |
| `tests/test_mass_balance_adjustment.py`          | 13    | 1    | 92%    |
| `tests/test_optimize_temperature.py`             | 13    | 1    | 92%    |
| `tests/test_print_results.py`                    | 19    | 1    | 95%    |
| `tests/test_reaction_rate.py`                    | 17    | 2    | 88%    |
| `tests/test_run_simulation.py`                   | 16    | 1    | 94%    |
| `tests/test_set_parameters.py`                   | 22    | 1    | 95%    |
| `tests/test_solve_steady_state.py`               | 14    | 1    | 93%    |
| **TOTAL**                                        | 566   | 79   | **86%**|
