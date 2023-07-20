
# Lip Syncing

This project aims to generate realistic lip-sync videos from a given input video and a separate audio source. It leverages the power of the Wav2Lip model, a deep learning model specifically designed for this task. The objective is to match the lip movements in the video with the phonetics of the audio to create a convincing lip-sync effect.


## Run Locally

Clone the project

```bash
  git clone https://github.com/Ihtreeek/Wav2lipAssignment
```

Go to the project directory

```bash
  cd project
```

Install dependencies

```bash
  pip install -r requirements.txt
```

Executing Model
```bash
python script.py
```

## Evaluation
To evaluate the performance of the model, we will use the SyncNet model, a lip-sync discrepancy model.


### Setup

1. Clone the SyncNet repository:

    ```bash
    git clone https://github.com/joonson/syncnet_python.git
    ```

2. Navigate to the SyncNet directory and install the required Python libraries. We recommend doing this in a separate virtual environment to avoid conflicts with other projects:

    ```bash
    cd syncnet_python
    pip install -r requirements.txt
    ```

3. Download the pretrained SyncNet models:

    ```bash
    sh download_model.sh
    ```



### Running the Evaluation Scripts

1. Copy the evaluation scripts from the Wav2Lip project to the SyncNet directory:

    ```bash
    cd Wav2Lip/evaluation/scores_LSE/
    cp *.py ../syncnet_python/
    cp *.sh ../syncnet_python/
    ```



2. Navigate back to the SyncNet directory:

    ```bash
    cd syncnet_python
    ```



5. For the ReSynced dataset or your own generated videos, run the following command:

    ```bash
    sh calculate_scores_real_videos.sh /path/to/video/data/root
    ```

The generated scores will be present in the all_scores.txt file generated in the `syncnet_python/` folder. These scores indicate the level of synchronization between the audio and the lip movements in the video. The lower the score, the better the lip-sync.





