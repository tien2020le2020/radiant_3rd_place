# Tree-based Crop Classification Models using Image Feature Extraction

Third place solution by the team `re-union` in the final round to classify crop types in agricultural fields across Northern India using multispectral observations from Sentinel-2 satellite. 

## ML Model Documentation

Please review the model architecture, license, applicable spatial and temporal extents
and other details in the [model documentation](/full_solution/README.md).

## System Requirements

* Git client
* [Docker](https://www.docker.com/) with
    [Compose](https://docs.docker.com/compose/) v1.28 or newer.

## Hardware Requirements

|Inferencing|Training|
|-----------|--------|
|12 GB RAM | 30 GB RAM|

## Get Started With Inferencing

1. Clone this Git repository, you need to use git lfs to get all the big files.

2. Prepare your input data in the data folder

3. Build the docker image

    ```bash
    cd docker-service
    docker build -t skamot/model_radiant:4 -f Dockerfile .
    ```

4. Run Model to generate the predictions

    ```bash
    # change paths to your actual input and output folders
    export INPUT_DATA="/opt/radiant/docker-solution/data/input"
    export OUTPUT_DATA="/opt/radiant/docker-solution/data/output"
    export MODELS_DIR="/opt/radiant/docker-solution/models"
    export WORKSPACE_DIR="/opt/radiant/docker-solution/workspace"

    docker-compose up model_radiant_3
    ```

4. Wait for the `docker compose` to finish running, then inspect the
`OUTPUT_DATA` folder for results.
