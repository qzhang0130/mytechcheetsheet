/opt/slurm/sbin/slurmctld   # only need to open on head node
/opt/slurm/sbiin/slurmd     # need to open on each node

scontrol ping # check the status of primary and backup controllers
sinfo # see the information of the slurm cluster
sbatch <script.sh>  # submit job to slurm cluster
squeue   # check the job queue
scancel <job id>   # cancel job

# sample submission script
#!/bin/bash
#
#SBATCH --job-name=test_omp
#SBATCH --output=res_omp.txt
#
#SBATCH --ntasks=1
#SBATCH --cpus-per-task=4
#SBATCH --time=10:00
#SBATCH --mem-per-cpu=100

export OMP_NUM_THREADS=$SLURM_CPUS_PER_TASK
./hello.omp
