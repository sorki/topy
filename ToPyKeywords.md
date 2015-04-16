# Introduction #

This page explains what each ToPy keyword stands for as used in a TDP (ToPy Problem Definition) file. You should also look at the `template.tpd` file, in Downloads, which gives more information.

# Keywords #
| **KEYWORD** | **Description** |
|:------------|:----------------|
| PROB\_NAME | Problem name |
| PROB\_TYPE | Problem type |
| NUM\_ELEM\_X | Number of elements in the X-direction |
| NUM\_ELEM\_Y | Number of elements in the Y-direction |
| NUM\_ELEM\_Z | Number of elements in the Z-direction |
| VOL\_FRAC  | Volume fraction |
| FILT\_RAD  | Filter radius |
| NUM\_ITER | Number of iterations to run |
| CHG\_STOP | Change stop value; controls the number of iterations |
| P\_FAC | Start value of penalty factor (p) |
| P\_INCR | Increment value of the penalty factor |
| P\_CON | Number of iterations to keep the penalty factor constant after each increment |
| P\_MAX | Max value that the penalty factor is allowed to reach |
| Q\_FAC | Start value of extra penalty factor (q) for grey-scale filtering (GSF) |
| Q\_INCR | Analoguous to P\_INCR |
| Q\_CON | Analoguous to P\_CON |
| Q\_MAX | Analoguous to P\_MAX |
| ETA | Damping factor |
| APPROX | Type of approximation, reciprocal, exponential or diagonal quadratic |
| ELEM\_K | Type of finite element to use; really specifies the element stiffness matrix to use |
| FXTR\_NODE\_X | Node number(s) at which you want to fix the translation in the X direction |
| FXTR\_NODE\_Y | Node number(s) at which you want to fix the translation in the Y direction |
| FXTR\_NODE\_Z | Node number(s) at which you want to fix the translation in the Y direction |
| LOAD\_NODE\_X | Node number(s) at which you require load(s) in the X direction |
| LOAD\_NODE\_Y | Node number(s) at which you require load(s) in the Y direction |
| LOAD\_NODE\_Z | Node number(s) at which you require load(s) in the Z direction |
| LOAD\_VALU\_X | Load value(s) in the X direction |
| LOAD\_VALU\_Y | Load value(s) in the Y direction |
| LOAD\_VALU\_Z | Load value(s) in the Z direction |
| PASV\_ELEM | Element number(s) at which you require passive (void) elements |
| ACTV\_ELEM | Element number(s) at which you require active (solid) elements |

## Mechanism synthesis ##
| LOAD\_NODE\_X\_OUT | Node number(s) at which you require the output in the X direction |
|:-------------------|:------------------------------------------------------------------|
| LOAD\_VALU\_X\_OUT | Value of output at specified OUT node in X direction |
| LOAD\_NODE\_Y\_OUT | Node number(s) at which you require the output in the Y direction |
| LOAD\_VALU\_Y\_OUT | Value of output at specified OUT node in Y direction |
| LOAD\_NODE\_Z\_OUT | Node number(s) at which you require the output in the Z direction |
| LOAD\_VALU\_Z\_OUT | Value of output at specified OUT node in Z direction |