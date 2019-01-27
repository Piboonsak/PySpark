## Pyspark Course
**ref : https://datawookie.netlify.com/blog/2017/06/setting-up-jupyter-with-python-3-on-ubuntu/**
check python version

python
quit()
python3
quit()

### Install jupyter
`sudo apt install -y python3 python3-pip ipython3`
  
`pip3 install jupyter`

```
piboonsak@piboonsak-asus:~$ pip3 install jupyter
Collecting jupyter
  Downloading https://files.pythonhosted.org/packages/83/df/0f5dd132200728a86190397e1ea87cd76244e42d39ec5e88efd25b2abd7e/jupyter-1.0.0-py2.py3-none-any.whl
Collecting nbconvert (from jupyter)
  Downloading https://files.pythonhosted.org/packages/b5/bb/94c493051d60e5b9c0f7f9a368b324201818c1b1c4cae85d1e49a41846c7/nbconvert-5.4.0-py2.py3-none-any.whl (405kB)
    100% |████████████████████████████████| 409kB 1.7MB/s 
Collecting qtconsole (from jupyter)
  Downloading https://files.pythonhosted.org/packages/e0/7a/8aefbc0ed078dec7951ac9a06dcd1869243ecd7bcbce26fa47bf5e469a8f/qtconsole-4.4.3-py2.py3-none-any.whl (113kB)
    100% |████████████████████████████████| 122kB 2.7MB/s 
Collecting ipywidgets (from jupyter)
  Downloading https://files.pythonhosted.org/packages/30/9a/a008c7b1183fac9e52066d80a379b3c64eab535bd9d86cdc29a0b766fd82/ipywidgets-7.4.2-py2.py3-none-any.whl (111kB)
    100% |████████████████████████████████| 112kB 2.6MB/s 
Collecting jupyter-console (from jupyter)
```
### export execute path
export PATH=$PATH:~/.local/bin/

**It’s a good idea to add that to one of your startup scripts, probably .bashrc.**


### Execution Time
At this stage you should be ready to roll.

`jupyter notebook`

```
piboonsak@piboonsak-asus:~/.local/bin$ jupyter notebook
[I 01:01:37.874 NotebookApp] Writing notebook server cookie secret to /run/user/1000/jupyter/notebook_cookie_secret
[I 01:01:38.158 NotebookApp] Serving notebooks from local directory: /home/piboonsak/.local/bin
[I 01:01:38.158 NotebookApp] The Jupyter Notebook is running at:
[I 01:01:38.158 NotebookApp] http://localhost:8888/?token=96486650701a3efbaa6dc02adcb87d0d6fadfa2367cb7863
[I 01:01:38.158 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 01:01:38.176 NotebookApp] 
    
    To access the notebook, open this file in a browser:
        file:///run/user/1000/jupyter/nbserver-23740-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/?token=96486650701a3efbaa6dc02adcb87d0d6fadfa2367cb7863
ATTENTION: default value of option force_s3tc_enable overridden by environment.
Created new window in existing browser session.

```
### copy token frist time.
put url for first login

**http://localhost:8888/?token=96486650701a3efbaa6dc02adcb87d0d6fadfa2367cb7863**
Check and Stop it!

## Install JDK
apt-get updaste
apt-get install default-jre

check java by
java -version

## Install scala

`sudo apt-get install scala`

<b>Check version</b>
```
piboonsak@piboonsak-asus:~$ scala -version
Scala code runner version 2.11.8 -- Copyright 2002-2016, LAMP/EPFL
```


`pip3 install py4j`

```
piboonsak@piboonsak-asus:~$ pip3 install py4j
Collecting py4j
  Downloading https://files.pythonhosted.org/packages/04/de/2d314a921ef4c20b283e1de94e0780273678caac901564df06b948e4ba9b/py4j-0.10.8.1-py2.py3-none-any.whl (196kB)
    100% |████████████████████████████████| 204kB 2.1MB/s 
Installing collected packages: py4j
Successfully installed py4j-0.10.8.1
```

## Install apache spark

download at it website
**ref : https://spark.apache.org/downloads.html**

move file in home path and extract them

## then export paramitter

```
*floder spark-2.4.0-bin-hadoop2.7 that you are extracted*

piboonsak@piboonsak-asus:~$ export SPARK_HOME='home/piboonsak/spark-2.4.0-bin-hadoop2.7'
piboonsak@piboonsak-asus:~$ echo $SPARK_HOME 
home/piboonsak/spark-2.4.0-bin-hadoop2.7

piboonsak@piboonsak-asus:~$ export PATH=$SPARK_HOME:$PATH
piboonsak@piboonsak-asus:~$ echo $PATH
home/piboonsak/spark-2.4.0-bin-hadoop2.7:home/piboonsak/spark-2.4.0-bin-hadoop2.7/:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/piboonsak/.local/bin/

piboonsak@piboonsak-asus:~$ export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH
piboonsak@piboonsak-asus:~$ echo $PYTHONPATH
home/piboonsak/spark-2.4.0-bin-hadoop2.7/python:home/piboonsak/spark-2.4.0-bin-hadoop2.7//python:

piboonsak@piboonsak-asus:~$ export PYSPARK_DRIVER_PYTHON="jupyter"
piboonsak@piboonsak-asus:~$ echo $PYSPARK_DRIVER_PYTHON
jupyter

piboonsak@piboonsak-asus:~$ export PYSPARK_DRIVER_PYTHON_OPTS="notebook"
piboonsak@piboonsak-asus:~$ echo $PYSPARK_DRIVER_PYTHON_OPTS
notebook

piboonsak@piboonsak-asus:~$ export PYSPARK_PYTHON=python3
piboonsak@piboonsak-asus:~$ echo $PYSPARK_PYTHON
python3

```

## Set permission

```
piboonsak@piboonsak-asus:~$ sudo chmod 777 spark-2.4.0-bin-hadoop2.7
[sudo] password for piboonsak: 
piboonsak@piboonsak-asus:~$ cd spark-2.4.0-bin-hadoop2.7/
piboonsak@piboonsak-asus:~/spark-2.4.0-bin-hadoop2.7$ ls
bin  conf  data  examples  jars  kubernetes  LICENSE  licenses  NOTICE  python  R  README.md  RELEASE  sbin  yarn
piboonsak@piboonsak-asus:~/spark-2.4.0-bin-hadoop2.7$ cd
piboonsak@piboonsak-asus:~$ sudo chmod 777 spark-2.4.0-bin-hadoop2.7/python/
piboonsak@piboonsak-asus:~$ cd spark-2.4.0-bin-hadoop2.7/python/
piboonsak@piboonsak-asus:~/spark-2.4.0-bin-hadoop2.7/python$ ls
dist  lib          pylintrc  pyspark.egg-info  run-tests     run-tests-with-coverage  setup.py       test_support
docs  MANIFEST.in  pyspark   README.md         run-tests.py  setup.cfg                test_coverage
piboonsak@piboonsak-asus:~/spark-2.4.0-bin-hadoop2.7/python$ python3
Python 3.6.3 (default, Oct  3 2017, 21:45:48) 
[GCC 7.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 

```
## Import pyspark

```
piboonsak@piboonsak-asus:~/spark-2.4.0-bin-hadoop2.7/python$ python3
Python 3.6.3 (default, Oct  3 2017, 21:45:48) 
[GCC 7.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

```
>>> import pyspark
>>> quit()

```
## Set permission pyspark and test run `jupyter notebook`
```
piboonsak@piboonsak-asus:~/spark-2.4.0-bin-hadoop2.7/python$ sudo chmod 777 pyspark
[sudo] password for piboonsak: 
piboonsak@piboonsak-asus:~/spark-2.4.0-bin-hadoop2.7/python$ jupyter notebook

```

# Config pyspark can use in every where

```

piboonsak@piboonsak-asus:~$ pip3 install findspark
Collecting findspark
  Downloading https://files.pythonhosted.org/packages/b1/c8/e6e1f6a303ae5122dc28d131b5a67c5eb87cbf8f7ac5b9f87764ea1b1e1e/findspark-1.3.0-py2.py3-none-any.whl
Installing collected packages: findspark
Successfully installed findspark-1.3.0

piboonsak@piboonsak-asus:~$ cd spark-2.4.0-bin-hadoop2.7/
piboonsak@piboonsak-asus:~/spark-2.4.0-bin-hadoop2.7$ pwd
/home/piboonsak/spark-2.4.0-bin-hadoop2.7
piboonsak@piboonsak-asus:~/spark-2.4.0-bin-hadoop2.7$ cd
piboonsak@piboonsak-asus:~$ python3
Python 3.6.3 (default, Oct  3 2017, 21:45:48) 
[GCC 7.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import pyspark
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'pyspark'
>>> import findspark
>>> findspark.init('/home/piboonsak/spark-2.4.0-bin-hadoop2.7')
>>> import pyspark

```
## import pyspark on jupyter note book

```
piboonsak@piboonsak-asus:~$ jupyter notebook
[I 17:19:40.861 NotebookApp] The port 8888 is already in use, trying another port.
[I 17:19:40.861 NotebookApp] The port 8889 is already in use, trying another port.
[I 17:19:40.867 NotebookApp] Serving notebooks from local directory: /home/piboonsak
[I 17:19:40.867 NotebookApp] The Jupyter Notebook is running at:
[I 17:19:40.867 NotebookApp] http://localhost:8890/?token=6d9fe54130ae9fc7290a3d6010ceb26ea6552d61b63af041
[I 17:19:40.867 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).

```
<image src='python/pic/001_notebook_findspark.png'>


















