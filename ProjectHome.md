# What is ToPy? #

ToPy is a program (written in Python) to solve one of three types of topology optimisation problems. You type a simple text input file (TPD file) and define one of the following three problems:
  1. minimum compliance,
  1. heat conduction or
  1. mechanism design (synthesis).

ToPy solves the problem to obtain a 2D (or 3D, depending on the input file) solid-void (black and white) solution. The result is
  1. an optimally stiff structure for minimum compliance problems,
  1. an optimal distribution of two materials for heat conduction problems and
  1. an optimal distribution of material for efficient mobility.

The 2D results are PNG files and the 3D results are VTK files.

Some examples are shown here: ToPyExamples

There is a tutorial to solve a 2D compliance problem here [ToPy2DTutorial](https://code.google.com/p/topy/wiki/ToPy2DTutorial).

## Limitations ##
  * ToPy only works with regular square/cubic meshes
  * No GUI for defining problems
  * No CAD interface (although you can save the 3D files as STL files via Paraview)
  * ...

## Background ##
The development was done on Linux (32-bit), but ToPy works on Windows (32 and 64-bit¹) and OS X (Lion 10.7.4 64-bit)¹ too.

ToPy was part of my Master's (see [Downloads](http://code.google.com/p/topy/downloads/list)) and I've decided to make it available here in the hope that somebody might find it useful.

¹ <sub>Thanks to Nikos Kaminakis for letting me know.</sub>