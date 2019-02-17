# Emotion Recognition with semi-supervised GAN

The goal of this work was to assemble two models used to depict emotions on faces. These models are Action Units and Valence Arousal. <br/>
Action Units are facial muscle movements. The combination of these Action Units can be interpreted as an emotion. 
Valence Arousal is a 2D continuous scale where Valence represents how positive or negative a person is when feeling an emotion and Arousal represents how excited or calm the person is. <br/>
Now the possibility to run the code with the facemotion repository ! 

# Prerequisites 

- Python 2.7
- Virtual environment manager :
  - [virtualenv](https://virtualenv.pypa.io/en/latest/)
  - [virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/)
  
- [Git LFS](https://git-lfs.github.com) <br/>
Git LFS is necessary to download the images contained in the FaceMotion dataset

# Setup

1. Clone the project to your environment :
    ```
    git clone https://github.com/ValentinRicher/emotion-recognition-GAN.git
    ```

2. Create the virtual environment : 
  - with virtualenv
    ```
    virtualenv <venv-name>
    ```
  - or with virtualenvwrapper
    ```
    mkvirtualenv <venv-name>
    ```

3. Activate your virtual environment :
  - with virtualenv
    ```
    source <venv-name>/bin/activate
    ```
  - with virtualenvwrapper
    ```
    workon <venv-name>
    ```

4. Install the libraries :
  - if you use a GPU (recommended)
    ```
    pip install -R gpu-requirements.txt
    ```
  - if you use a CPU
    ```
    pip install -R requirements.txt
    ```

# Usage

- Download the FaceMotion dataset
    ```
    python download.py --model xx --img_size yy
    ```
    This will download the images from the FaceMotion dataset into a ./datasets/facemotion directory if not already done and create the h5py files with the good labels and image sizes.


- Train the models 
    ```
    python trainer.py --model xx --img_size yy
    ```
    
- Evaluate the models
    ```
    python evaler.py --checkpoint_path ckpt_p
    ```
    `ckpt_p` should be like : 



# To Do

- Add metrics for the real or fake images ✅
- Connect the GAN repo with the dataset repo to create automatic downloading ✅
- Re-organize the facemotion.py to the same level as other .py files ✅
- Use Google Cloud Platform ❌ -> impossible to use a GPU without paying
- Use Google Colab ❌ -> impossible to download the dataset quickly
- Config file to YAML ✅
- Add a file to get the info stored in events files created for TensorBoard ✅
- Do a notice to explain the project and how to use it
- Create an architecture for 64*64 images
- Create an architecture for 96*96 images
- Add an early stopping possibility


# Acknowledgments

Parts of the code from https://github.com/gitlimlab/SSGAN-Tensorflow
