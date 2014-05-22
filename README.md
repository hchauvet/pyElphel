pyElphel
========

Control Elphel camera [353](http://www3.elphel.com/model_353_cameras>) from python using RTSP protocol and from imgsrv access for full resolution images.

### Requirement


* [Python OpenCv](http://docs.opencv.org/trunk/doc/py_tutorials/py_setup/py_table_of_contents_setup/py_table_of_contents_setup.html#py-table-of-content-setup)

### Installation

#### From python setup tools 

Download the ZIP archive https://github.com/hchauvet/pyElphel/archive/master.zip

Unzip and in the directory *pyElphel-master* run the following command as a root user

```bash
python setup.py install
```

#### From python pip repository

Just enter the following command as root user
```bash
sudo python pip install pyElphel
```

link to the pypi repository
https://pypi.python.org/pypi?:action=display&name=pyElphel

### Examples


Video at full resolution (2592x1936) is impossible using RTSP. For this resolution use *grab_image_slow()*, which relies on imgsrv access through http.

You can also check examples files in test folder for more detailed examples [*./pyElphel/test*](https://github.com/hchauvet/pyElphel/tree/master/pyElphel/test)

#### Set parameters

```python
from pyElphel import Elphel

cam = Elphel()

cam.params['WOI_WIDTH'] = 1280
cam.params['WOI_HEIGHT'] = 720
cam.params['COLOR'] = 1
cam.params['EXPOS'] = 10000

cam.set_params()
```   
    
#### Live display

```python
from pyElphel import Elphel

with Elphel() as cam:
    cam.display()
    
```    
    
#### Get single image
```python
from pyElphel import Elphel

with Elphel() as cam:
    cam.init_live()

    img = cam.grab_image()

```

#### Get single image at full resolution
```python
from pyElphel import Elphel

cam = Elphel()

img = cam.grab_image_slow()
```   
    

