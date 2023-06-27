1. Create env: conda create -n env_name python=3.10
2. Delete env: conda deactiate, conda remove --name env_name --all
3. Update python env: 
  conda env langchain2 update to python=3.10
  conda install python=3.10
4. Set environment variable in Jupyter notebook - %env HNSWLIB_NO_NATIVE=1 
