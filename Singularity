BootStrap: docker
From: continuumio/anaconda3

%runscript

     echo "Starting notebook..."
     echo "Open browser to localhost:8888"
     exec /opt/conda/bin/jupyter notebook --notebook-dir=/opt/notebooks --ip='*' --port=8888 --no-browser --allow-root

%post

     # Install jupyter notebook
     /opt/conda/bin/conda install jupyter -y --quiet 
     mkdir /opt/notebooks
     apt-get autoremove -y
     apt-get clean
