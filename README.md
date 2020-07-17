# SlurmSub
Slurm job submission scripts with proper thread binding.
It works only for openmpi on machines where hyper-threading is turned off.
It reads the settings in the slurm allocation request section in `jobsub.slurm`.

For example, for 1 mpi rank per socket and 20 threads per mpi rank, use the following slurm request:
```bash
# configuration per socket
#SBATCH --ntasks-per-socket=1
#SBATCH --cpus-per-task=20
```
Then this script binds each thread to each core on each socket.
