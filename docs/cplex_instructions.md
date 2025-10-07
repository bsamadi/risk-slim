# Downloading & Installing CPLEX

CPLEX is a cross-platform optimization solver with a Python API. It is free for students and faculty members at accredited institutions through the IBM Academic Initiative.

## Download CPLEX

### For Academic Users (Students and Faculty)

1. **Register for IBM Academic Initiative**
   - Visit the [IBM Academic Initiative](https://www.ibm.com/academic/home) website
   - Create an account using your academic email address (.edu domain)
   - Verify your academic status

2. **Download CPLEX Optimization Studio**
   - After registration, log in to your IBM Academic Initiative account
   - Navigate to the Software section
   - Search for "CPLEX Optimization Studio" or "IBM ILOG CPLEX"
   - Download the latest version compatible with your operating system (Windows, macOS, or Linux)
   - Note: CPLEX 12.6 or higher is required for risk-slim

### For Commercial Users

Commercial users can purchase CPLEX from the [IBM CPLEX Optimizer](https://www.ibm.com/products/ilog-cplex-optimization-studio) product page.

## Installation Steps

### 1. Install CPLEX Optimization Studio

Run the installer you downloaded and follow the installation wizard:

- **Windows**: Run the `.exe` installer
- **macOS**: Open the `.bin` installer (you may need to make it executable: `chmod +x cplex_studio*.bin`)
- **Linux**: Run the `.bin` installer as an executable

Default installation locations:
- **Windows**: `C:\Program Files\IBM\ILOG\CPLEX_Studio<version>`
- **macOS/Linux**: `/opt/ibm/ILOG/CPLEX_Studio<version>` or `~/Applications/IBM/ILOG/CPLEX_Studio<version>`

### 2. Setup the CPLEX Python API

After installing CPLEX Optimization Studio, you need to install the Python API:

#### Find the Python Setup Directory

Navigate to your CPLEX installation directory and locate the Python setup script:
```
<CPLEX_Studio_dir>/cplex/python/<python_version>/<platform>
```

For example:
- **Windows**: `C:\Program Files\IBM\ILOG\CPLEX_Studio221\cplex\python\3.10\x64_win64`
- **macOS**: `/Applications/CPLEX_Studio221/cplex/python/3.10/x86-64_osx`
- **Linux**: `/opt/ibm/ILOG/CPLEX_Studio221/cplex/python/3.10/x86-64_linux`

#### Install the Python Package

Open a terminal/command prompt and run:

```bash
cd <CPLEX_Studio_dir>/cplex/python/<python_version>/<platform>
python setup.py install
```

Or install using pip:
```bash
pip install <CPLEX_Studio_dir>/cplex/python/<python_version>/<platform>
```

#### Verify Installation

Test that CPLEX is properly installed by running Python and trying to import the module:

```python
import cplex
print(cplex.__version__)
```

If successful, you should see the CPLEX version number printed without any errors.

## Troubleshooting

### Common Issues

1. **ImportError: No module named 'cplex'**
   - Ensure you ran the setup.py installation from the correct Python version directory
   - Make sure you're using the same Python environment where you installed CPLEX

2. **License Error**
   - Academic users: Verify your IBM Academic Initiative registration is active
   - Check that the CPLEX license file is in the correct location
   - Academic licenses are typically included with the installation

3. **Platform/Architecture Mismatch**
   - Ensure you download the correct version for your operating system
   - Match your Python architecture (32-bit vs 64-bit) with the CPLEX installation

### Getting Help

- **CPLEX Documentation**: [IBM CPLEX Documentation](https://www.ibm.com/docs/en/icos)
- **Python API Setup Guide**: [CPLEX Python API Setup](https://www.ibm.com/docs/en/icos/latest?topic=cplex-setting-up-python-api)
- **IBM Support**: [IBM CPLEX Support](https://www.ibm.com/mysupport/)
- **Community Forums**: Search for CPLEX-related questions on Stack Overflow or IBM Developer forums

## Alternative: Using Conda

If you're using Anaconda or Miniconda, you can also install CPLEX via conda (requires IBM Academic Initiative credentials):

```bash
conda install -c ibmdecisionoptimization cplex
```

## Version Compatibility

risk-slim requires:
- Python 3.5 or higher
- CPLEX 12.6 or higher (latest version recommended) 
