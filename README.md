# The AI Scientist Reproduced

## Important files in this repository
##### **aiScientist.def** - Singularity container definition to build a container. It is based on the official (experimental) docker image
##### **data/AI-Scientist/** - This directory is mounted into the container and is a clone of the [official repository](https://github.com/SakanaAI/AI-Scientist).
##### **data/AI-Scientist/templates/sgd/** - This directory contains the necessary files for a custom template. Refer to the ["Making Your Own Template" section of the original README](https://github.com/SakanaAI/AI-Scientist/blob/c19f0f8ac575fd2426f56af526adc7a80341a761/README.md#making-your-own-template).
##### **buildContainer.sh** - Builds the singularity container using the sylabs cloud builder. We use the cloud builder because of permission restriction on our cluster.
##### **launch_scientist.slurm** - Slurm jobscript to queue a job that starts the ai scientist inside the singularity container.
##### **runShell.sh** - Runs an interactive shell inside the singularity container. Since all the files that ai scientist uses are in the *data/* directory this probably only has to be used rarely.
##### **.env** (ignored by git) - A .env file can be placed in the root directory. It is loaded by singularity to e.g. define API keys for the ai scientist.
Example:
```Shell
OPENAI_API_KEY="<your api key>"
```