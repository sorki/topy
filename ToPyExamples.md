# MBB Beam (with grey-scale filtering (GSF)) #

This is the "Hello, World!" of ToPy...

### Input file (TPD file) ###
```
[ToPy Problem Definition File v2007]

# Author: William Hunter
# The 'classic' 60x20 2d mbb beam, as per Ole Sigmund's 99 line code, but with
# grey-scale filtering.

PROB_TYPE  : comp
PROB_NAME  : beam_2d_reci_gsf
ETA        : 0.5  # reciprocal approx.
DOF_PN     : 2
VOL_FRAC   : 0.5
FILT_RAD   : 1.5
ELEM_K     : Q4
NUM_ELEM_X : 60
NUM_ELEM_Y : 20
NUM_ELEM_Z : 0
FXTR_NODE_X: 1|21
FXTR_NODE_Y: 1281
LOAD_NODE_Y: 1
LOAD_VALU_Y: -1

NUM_ITER   : 100

# Grey-scale filter (GSF)
P_FAC      : 1
P_HOLD     : 25  # num of iters to hold p constant from start
P_INCR     : 0.2  # increment by this amount
P_CON      : 1  # increment every 'P_CON' iters
P_MAX      : 3  # max value of 'P_CON'

Q_FAC      : 1
Q_HOLD     : 25  # num of iters to hold q constant from start
Q_INCR     : 0.05  # increment by this amount
Q_CON      : 1  # increment every 'Q_CON' iters
Q_MAX      : 5  # max value of 'Q_CON'
```
### Result ###
After 100 iterations you should see the following:

![http://topy.googlecode.com/files/beam_2d_reci_gsf_100.png](http://topy.googlecode.com/files/beam_2d_reci_gsf_100.png)

---

# 3D cantilever (with grey-scale filtering (GSF)) #
![http://topy.googlecode.com/files/cantilvr_3d.png](http://topy.googlecode.com/files/cantilvr_3d.png)

A 3D problem; rectangular prism with load at end as shown above.

### Input file (TPD file) ###
```
[ToPy Problem Definition File v2007]

# Author: William Hunter

PROB_TYPE:   comp
PROB_NAME:   cantilvr_3d_etaopt_gsf
ETA:         0.4
DOF_PN:      3
VOL_FRAC:    0.15
FILT_RAD:    1.5
ELEM_K:      H8
NUM_ELEM_X:  28
NUM_ELEM_Y:  37
NUM_ELEM_Z:  111
FXTR_NODE_X: 1
FXTR_NODE_Y: 1|1102
FXTR_NODE_Z: 1|1102
LOAD_NODE_Y: 122892
LOAD_VALU_Y: -1

NUM_ITER   : 50

# Grey-scale filter (GSF)
P_FAC      : 1
P_HOLD     : 15  # num of iters to hold p constant from start
P_INCR     : 0.2  # increment by this amount
P_CON      : 1  # increment every 'P_CON' iters
P_MAX      : 3  # max value of 'P_CON'

Q_FAC      : 1
Q_HOLD     : 15  # num of iters to hold q constant from start
Q_INCR     : 0.05  # increment by this amount
Q_CON      : 1  # increment every 'Q_CON' iters
Q_MAX      : 5  # max value of 'Q_CON'
```


### Result ###
After 5 iterations...

![http://topy.googlecode.com/files/cantilvr_3d_etaopt_gsf_005.png](http://topy.googlecode.com/files/cantilvr_3d_etaopt_gsf_005.png)

After 50 iterations...

![http://topy.googlecode.com/files/cantilvr_3d_etaopt_gsf_050.png](http://topy.googlecode.com/files/cantilvr_3d_etaopt_gsf_050.png)

**Animation**

![http://topy.googlecode.com/files/cantilvr_3d.gif](http://topy.googlecode.com/files/cantilvr_3d.gif)



---


# 3D trestle (with grey-scale filtering (GSF)) #
![http://topy.googlecode.com/files/trestle_3d.png](http://topy.googlecode.com/files/trestle_3d.png)

A 3D problem; block with load at top in centre of surface as shown above.

### Input file (TPD file) ###
```
[ToPy Problem Definition File v2007]

# Author: William Hunter
# 3d cube domain, held at 4 corners all on the same face of cube, pressure load
# applied to outer face of centre element on opposite side. All corners are
# held rigidly in place, which means (intuitively) that braces are not needed
# between the corners to maximise stiffness.

PROB_TYPE  : comp
PROB_NAME  : trestle_3d_etaopt_gsf
ETA        : 0.4  # 'optimal' choice for eta
DOF_PN     : 3
VOL_FRAC   : 0.15
FILT_RAD   : 1.8
ELEM_K     : H8
NUM_ELEM_X : 51
NUM_ELEM_Y : 51
NUM_ELEM_Z : 51
FXTR_NODE_X: 1; 52; 2653; 2704
FXTR_NODE_Y: 1; 52; 2653; 2704
FXTR_NODE_Z: 1; 52; 2653; 2704
LOAD_NODE_Z: 139230; 139231; 139282; 139283
LOAD_VALU_Z: -1; -1; -1; -1

NUM_ITER   : 50

# Grey-scale filter (GSF)
P_FAC      : 1
P_HOLD     : 15  # num of iters to hold p constant from start
P_INCR     : 0.2  # increment by this amount
P_CON      : 1  # increment every 'P_CON' iters
P_MAX      : 3  # max value of 'P_CON'

Q_FAC      : 1
Q_HOLD     : 15  # num of iters to hold q constant from start
Q_INCR     : 0.05  # increment by this amount
Q_CON      : 1  # increment every 'Q_CON' iters
Q_MAX      : 5  # max value of 'Q_CON'
```

### Result ###
After 5 iterations...

![http://topy.googlecode.com/files/trestle_3d_etaopt_gsf_005.png](http://topy.googlecode.com/files/trestle_3d_etaopt_gsf_005.png)

After 50 iterations...

![http://topy.googlecode.com/files/trestle_3d_etaopt_gsf_050.png](http://topy.googlecode.com/files/trestle_3d_etaopt_gsf_050.png)


**Animation**

![http://topy.googlecode.com/files/trestle_3d.gif](http://topy.googlecode.com/files/trestle_3d.gif)


---

See my thesis for more...