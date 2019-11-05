BootStrap: docker
From: continuumio/anaconda3

%runscript

     echo "Mounting shared drive..."
     /sbin/mount.cifs //server/share /opt/notebooks/share -o user=shareusername,password=sharepassword
     echo "Starting notebook..."
     echo "Open browser to localhost:8888"
     exec /opt/conda/bin/jupyter notebook --notebook-dir=/opt/notebooks --ip='*' --port=8888 --no-browser --allow-root

%post

     # Install jupyter notebook
     /opt/conda/bin/conda install jupyter -y --quiet 
     mkdir /opt/notebooks
     # Make a mountpoint that will be visible within jupyter
     mkdir /opt/notebooks/share
     # Install utils to allow connections to share
     apt-get install cifs-utils libtalloc2 libwbclient0 -y
     apt-get autoremove -y
     apt-get clean

