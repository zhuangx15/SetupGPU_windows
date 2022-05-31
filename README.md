# SetupGPU_windows
For my personal use, set up GPU on my windows machine

Overall following: https://www.youtube.com/watch?v=OEFKlRSd8Ic

Step1:  Download and Install NIVIDA Graphic driver at https://www.nvidia.com/download/index.aspx

Step2:  Install visual-studio-2022 [need to check] -->desktop development with C++
        check if vcvars64.bat exist under C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build\
        if so, success;

Step3:  Install CUDA Toolkit:
        NOTE THAT Python 3.9 + Tensorflow 2.9 ==> use CUDA 11.2!!!!!!! 
        Find the correct combination at https://www.tensorflow.org/install/source_windows [bottom part]

Step4:  Install CuDNN to folder C:\tools\cuda
        NOTE that CuDNN version should also match CUDA version
        For CUDA 11.2 --> cudnn-v8.2.4; find at https://developer.nvidia.com/rdp/cudnn-archive
        
Step5:  Setup PATH; environment variable
        C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\bin;
        
        C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\extras\CUPTI\lib64;
        C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\include;
        C:\tools\cuda\bin;
        C:\tools\cuda\include
        
Step6:  Install Anaconda 

Step7:  Create new environment for GPU computing with python 3.9; and setup kernel
        open anaconda prompt:
        conda create env --name tensorflow_GPU2 python=3.9
        conda activate tensorflow_GPU2
        NOW UNDER ENVIRONMENT tensorflow_GPU2
        conda install ipykernel
        python -m ipykernel install --user --name tensorflow_GPU2 --display-name "Python 3.9 (tensorflow)"
        
Step8:  install tensorflow and other needed library
        NOTE THAT: pip install tensorflow to get the most up-to-date tensorflow [in my case: 2.9]
  
Trouble shooting:
Jupyter debug mode: jupyter notebook --debug
error 193: the combination of all parties' version is not correct! Check step 3

Conda cheat sheet: https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf
        
