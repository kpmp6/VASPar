# VAS*P<ins>ar</ins>*
* [**VASP**](https://www.vasp.at/) *<ins>Par</ins>allelization* tool - This tool determines the number of occupied electronic states and, using the default settings for the [NBANDS](https://www.vasp.at/wiki/index.php/NBANDS) parameter, estimates the required number of unoccupied (empty) bands based on information extracted from the [POSCAR](https://www.vasp.at/wiki/index.php/POSCAR) and [POTCAR](https://vasp.at/wiki/POTCAR) files. It then proposes optimal processor core (two bands per core) and node configurations, and correspondingly updates the [JOB submission script](https://slurm.schedmd.com/sbatch.html) as well as the [INCAR](https://www.vasp.at/wiki/INCAR).
* It can recommend suitable values for [KPAR](https://vasp.at/wiki/KPAR) and [NCORE](https://vasp.at/wiki/NCORE) using structural and k-point information obtained from the [KPOINTS](https://vasp.at/wiki/KPOINTS) and [POSCAR](https://www.vasp.at/wiki/index.php/POSCAR) files, respectively.

## Installation
VAS*P<ins>ar</ins>* is a standalone binary that requires no additional packages. On Linux, it can be installed by specifying the binary path.
* Installation steps
  Download the [VAS*P<ins>ar</ins>*-1.0.zip](VASPar-1.0.zip) file or
  > git clone https://github.com/kpmp6/VASPar.git
  Unzip the [VAS*P<ins>ar</ins>*-1.0.zip](VASPar-1.0.zip) file
  > unzip VASPar-1.0.zip
  >
  Enter password > vaspar
  > cd VASPar-1.0
  >
  > chmod +x install
  >
  > ./install
  >
  > source ~/.bashrc

