This is now a bit more than a stub, keep watching this space...




# Introduction #

The most difficult part of using ToPy is probably setting up a problem. While it is not too difficult to create a smallish 2D problem, things can get a bit frustrating for setting up large 2D problems (> 10000 elements) and especially 3D problems. The main reason for this 'struggle' is that ToPy doesn't have a GUI to help with setting up the problem, i.e., it doesn't have a graphical preprocessor, so you have to keep track of element numbers and node numbers in your head (if you have the cerebral capacity to do that) or use a piece of paper (for mortals like myself).

In this example I'll show how to create a TPD file by translating a problem into a TPD file. Once you have the TPD file, you're basically done.


# Define a topology optimisation problem #

Below is the problem (it took me about 20 minutes to draw on some graphing paper). As you can see it consists of a domain of 29 elements in the x-direction and 19 in the y-direction. There are also some loads acting on the domain (the green arrows) at seven nodes on the boundary of the domain. Finally, the domain is restrained at three nodes (black triangles) to prevent rigid body motion (ToPy will warn if it finds a rigid body motion). Both the loads and restraints can be inside the boundary of the domain, they don't have to be on the boundary.

So now the question is: **what is the best use of this 2D domain (area) to obtain an optimally stiff structure?**

Of course the stiffest structure is simply the one in which the whole domain is used, i.e., all 19\*29 = 551 elements
(and if the effects of global acceleration, such as gravity, is ignored). But that is a trivial solution, and besides, we specifically don't want to use the whole domain, we just want to use a fraction of it. And that's exactly the point of topology optimisation (for minimum compliance or maximum stiffness, in this case).

![http://topy.googlecode.com/files/ToPy2DTut_Problem.jpg](http://topy.googlecode.com/files/ToPy2DTut_Problem.jpg)


# Create the TPD file #

This is where we create the TPD file by parsing the information in the problem above into a file that can in turn be parsed by ToPy. Open your favourite text editor...

We start with the easy bits first (see ToPyKeywords for reference):
```
[ToPy Problem Definition File v2007]

PROB_NAME: ToPy_2D_Tut
PROB_TYPE: COMP # minimum compliance (or maximum stiffness)
NUM_ELEM_X: 29 # number of elements in the x-direction
NUM_ELEM_Y: 19 # number of elements in the y-direction
NUM_ELEM_Z : 0 # it is a 2D problem...
```

Now we apply the constraints:
```
FXTR_NODE_X: 13; 583; 360 # separate the node numbers with ;
FXTR_NODE_Y: 360
```

The loads:
```
LOAD_NODE_Y: 181; 201; 221; 361; 381; 401; 587 # node numbers loaded in y-direction
LOAD_VALU_Y: 10; 10; 10; 3; 3; 3; 5 # load values at the nodes numbered above 
```

The rest of the keywords define the optimisation parameters:
```
NUM_ITER   : 80 # run 80 iterations
ETA        : 0.35  # reciprocal approximation
DOF_PN     : 2 # degrees of freedom per node is 2 since we can have translation in x and y
VOL_FRAC   : 0.2 # the fraction of the domain to use
FILT_RAD   : 2 # size of the filter radius
ELEM_K     : Q4 # type of 2D element to use

# Grey-scale filter (GSF)
P_FAC      : 1 # penalty factor
P_HOLD     : 25 # num of iterations to hold p constant from start
P_INCR     : 0.2 # increment by this amount
P_CON      : 1  # increment every iteration
P_MAX      : 3  # max value of 'P_CON'

Q_FAC      : 1 # extra penalty factor
Q_HOLD     : 25 # num of iterations to hold q constant from start
Q_INCR     : 0.05 # increment by this amount
Q_CON      : 1  # increment every iteration
Q_MAX      : 5  # max value of 'Q_CON'
```


# Solve the problem #

Once you've installed ToPy, save the the above `code` blocks to a file, you can name it anything you want, but it must have the `TPD` file extension. Or you can just download the file from [Downloads](http://code.google.com/p/topy/downloads/list) (`ToPy_2D_Tut_Prob.tpd`).

In a terminal (console):

`python optimise.py ToPy_2D_Tut_Prob.tpd`

You can find the `optimise.py` file in the scripts directory of the source download.


## Result ##

The image from the last (80th) iteration.
![http://topy.googlecode.com/files/ToPy_2D_Tut_080.png](http://topy.googlecode.com/files/ToPy_2D_Tut_080.png)


## Discussion ##
TBC...