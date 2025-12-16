# VAS*P<ins>ar</ins>*
* [**VASP**](https://www.vasp.at/) *<ins>Par</ins>allelization* tool - This tool determines the number of occupied electronic states and, using the default settings for the [NBANDS](https://www.vasp.at/wiki/index.php/NBANDS) parameter, estimates the required number of unoccupied (empty) bands based on information extracted from the [POSCAR](https://www.vasp.at/wiki/index.php/POSCAR) and [POTCAR](https://vasp.at/wiki/POTCAR) files. It then proposes optimal processor core (two bands per core) and node configurations, and correspondingly updates the [JOB submission script](https://slurm.schedmd.com/sbatch.html) as well as the [INCAR](https://www.vasp.at/wiki/INCAR).
* It can recommend suitable values for [KPAR](https://vasp.at/wiki/KPAR) and [NCORE](https://vasp.at/wiki/NCORE) using structural and k-point information obtained from the [KPOINTS](https://vasp.at/wiki/KPOINTS) and [POSCAR](https://www.vasp.at/wiki/index.php/POSCAR) files, respectively.

## Installation
VAS*P<ins>ar</ins>* is a standalone binary that requires no additional packages. On Linux, it can be installed by specifying the binary path.
* Download the [VAS*P<ins>ar</ins>*-1.0.zip](VASPar-1.0.zip) file or
  ```
  git clone https://github.com/kpmp6/VASPar.git
  ```
  > 
  Unzip the [VAS*P<ins>ar</ins>*-1.0.zip](VASPar-1.0.zip) file
  >
  ```
   unzip VASPar-1.0.zip
  ```  
  Enter password > **vaspar**

  ``` 
  cd VASPar-1.0
  chmod +x install
  ./install
  source ~/.bashrc
  ```
## Documentation
* Run **vaspar** in the terminal from the working directory to use the tool.
  > INCAR, KPOINTS, POSCAR and POTCAR files must present in the working directory
  ```
  vaspar
  ```
  Enter the maximum number of cores per node available on the HPC system.
  It will display a list of core and node configurations. Select an option by entering the corresponding list number, then choose the specific configuration for the calculation.
  > The first list and the first Cores/Nodes configuration are optimal for most cases.
  
  It will automatically update the Slurm JOB script and INCAR.

* To set the KPAR and NCORE parallelization tags,
  ```
  vaspar --par
  ```
  It will show the recommended KPAR and NCORE values, and entering these values will automatically update the INCAR file.
* To assign *N* number of bands per core,
  > By default, it assigns 2 bands per core
  ```
  vaspar --bpc <N>
  ```
  > and proceed as usual
* To add extra unoccupied bands per ion,
  > By default, it sets 1 empty band per ion
  ```
  vaspar --n <n>
  ```
  > and proceed as usual
  
* Help
  ```
  vaspar -h
  ```
> [!NOTE]
> This tool is not compatible with OPENMP configurations

