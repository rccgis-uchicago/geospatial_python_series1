# RCC - UChicago, 2025

## `Introduction to Satellite and Climate Data with Python`

### Instructors

- **Hamid Dashti** — hdashti@uchicago.edu  
- **Parmanand Sinha** — pnsinha@uchicago.edu

---

## Setup Instructions

This workshop is designed to run on the RCC cluster (Midway3), but you are welcome to run the code locally if you prefer. Below are the steps to get set up on the cluster.

### 1. Connect to Midway3
```bash
ssh cnetid@midway3.rcc.uchicago.edu
```

### 2. Create and Navigate to a Workshop Directory
```bash
mkdir workshop
cd workshop
```

### 3. Clone the Workshop Repository
```bash
git clone https://github.com/rccgis-uchicago/geospatial_python_series1.git
cd intro_geospatial
```

### 4. Copy Workshop Data
```bash
cp /project/rcc/workshops/hamid/spring2025/data/* .
```

### 5. Start an Interactive Session with Slurm
```bash
sinteractive --nodes=1 --ntasks-per-node=2 --account=rcc-staff
```

### 6. Load Python Module
```bash
module load python
```

### 7. Check Available Conda Environments
```bash
conda env list
```

If you see the `geospatial` environment listed, activate it:
```bash
source activate geospatial
```

### 8. Register the Environment with Jupyter
```bash
ipython kernel install --name geospatial --user
```

### 9. Get Host IP Address
```bash
HOST_IP=`/sbin/ip route get 8.8.8.8 | awk '{print $7;exit}'`
echo $HOST_IP
```

### 10. Start Jupyter Lab
```bash
jupyter-lab --no-browser --ip=$HOST_IP --port=15021
```

---

You’re now ready to start working with satellite and climate data on the cluster!