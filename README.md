# trinity

This repository contains the code for the paper “Trinity: A Scalable and Forward-Secure DSSE for Spatio-Temporal Range Query” (including SHVE and QF related implementations), and is intended for reproducing and evaluating the experimental results in the paper.

**Copyright 2023-2025, BDS-SDU. MIT License**

---

## Hardware Information ✅
- Typical test platform: Intel Xeon or equivalent x86_64 processor
- Memory: >= 32 GB recommended
- Storage: source code and data together < 20 GB (depends on dataset size)

> Note: Some experiments may require more memory or disk space depending on dataset size and whether multi-threading or large-scale tests are enabled.

---

## Dependencies & Build Steps 🔧
- Operating System: Ubuntu 22.04/24.04 recommended (other Linux distributions should be similar)
- Dependencies (example installation via apt):
  - build-essential, cmake, libssl-dev, libgmp-dev, libntl-dev
  - additional tools: pkg-config, git

Example install commands:

```bash
sudo apt update
sudo apt install -y build-essential cmake libssl-dev libgmp-dev libntl-dev pkg-config git
```

If some libraries (e.g., GMP/NTL) need to be built from source, examples:

GMP:
```bash
# in the GMP source directory
./configure CXXFLAGS=-fPIC
make -j$(nproc)
sudo make install
sudo ldconfig
```

NTL:
```bash
# in the NTL source directory (NTL/src)
./configure CXXFLAGS=-fPIC
make -j$(nproc)
sudo make install
sudo ldconfig
```

---

## Configuration & Running ▶️
1. Clone the repository and create a build directory:
```bash
git clone <repo-url>
cd trinity
mkdir build && cd build
cmake ..
make -j$(nproc)
```

2. Executables and examples:
- The main implementation and example programs are under `shve-qf/`; see the README files in subdirectories (if present) for details.

3. Run an example:
```bash
# assuming the generated executable is trinity_example
./trinity_example --help
```

---

## License & Contributing ✍️
This project is licensed under the MIT License (see the `LICENSE` file).

---

## Contact & Citation
If you use this repository in academic or engineering work, please cite the paper and/or contact the maintainers at BDS-SDU.

---

