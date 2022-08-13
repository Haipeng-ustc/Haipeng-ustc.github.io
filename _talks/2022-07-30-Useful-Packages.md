---
title: Useful Packages
categories:
- Ideas
excerpt: |
  This post presents some useful packages for seismic waveform modeling, imaging, and inversion.
---

<!-- more -->

* TOC
{:toc}

## Seismic Waveform Modeling
- [FDFDMATRIX3D](https://www.geoazur.fr/WIND/bin/view/Main/Opencodes/WebHome#mjx-eqn%3AFDFDMATRIX3D): Solution of the 3D time-harmonic visco-acoustic VTI wave equation with the 27-point finite-difference stencil.
- [SEMLAB](https://github.com/jpampuero/semlab): Spectral Element Method for wave propagation and rupture dynamics in Matlab.
- [SEISMIC_CPML](https://github.com/geodynamics/seismic_cpml): a set of sixteen open-source Fortran90 programs to solve the two-dimensional or three-dimensional isotropic or anisotropic elastic, viscoelastic or poroelastic wave equation using a finite-difference method with Convolutional or Auxiliary Perfectly Matched Layer (C-PML or ADE-PML) conditions
- [SPECFEM2D](https://github.com/geodynamics/specfem2d): SPECFEM2D allows users to perform 2D and 2.5D (i.e., axisymmetric) simulations of acoustic, elastic, viscoelastic, and poroelastic seismic wave propagation. The package can also be used for full waveform imaging (FWI) or adjoint tomography.
- [SPECFEM3D_Cartesian](https://github.com/geodynamics/specfem3d): SPECFEM3D_Cartesian simulates acoustic (fluid), elastic (solid), coupled acoustic/elastic, poroelastic or seismic wave propagation in any type of conforming mesh of hexahedra (structured or not.)
- [SW4](https://github.com/geodynamics/sw4): SW4 (Seismic Waves, 4th order) implements substantial capabilities for 3-D seismic modeling, with a free surface condition on the top boundary, absorbing super-grid conditions on the far-field boundaries, and an arbitrary number of point force and/or point moment tensor source terms.
- [SALVUS](https://mondaic.com/): Salvus is a suite of software for performing full waveform modelling and inversion provided by Mondaic.
- [Devito](https://github.com/devitocodes/devito): Code generation framework for automated finite difference computation
- [FDwave3D](https://github.com/leileely/FDwave3D): A Matlab solver for the 3D anisotropic wave equation using the finite-difference (FD) method.



## Seismic Imaging & Inversion
- [FWI.jl](https://github.com/JuliaInv/FWI.jl): A Julia package for solving the Full Waveform Inversion on a regular rectangular mesh
- [PySIT](http://pysit.org/): PySIT is an open source toolbox for seismic inversion and seismic imaging developed by Russell J. Hewett and Laurent Demanet in the Imaging and Computing Group in the Department of Mathematics at MIT.
- [SAVA](https://github.com/daniel-koehn/SAVA): 3D seismic modelling, FWI and RTM code for wave propagation in isotropic (visco)-acoustic/elastic and anisotropic orthorhombic/triclinic elastic media.
- [SeisFlows](https://github.com/adjtomo/seisflows): An automated workflow tool for full waveform inversion and adjoint tomography.
- [SeisElastic2D](https://github.com/crewesleo/SeisElastic2D): An open-source package for multiparameter FWI in isotropic-, anisotropic- and visco-elastic media.
- [TOOLBOX_OPTIMIZATION](https://seiscope2.osug.fr/SEISCOPE-OPTIMIZATION-TOOLBOX): The SEISCOPE OPTIMIZATION TOOLBOX is a set of FORTRAN 90 optimization routines dedicated to the resolution of unconstrained and bound constrained nonlinear minimization problems.
- [JUDI.jl](https://github.com/slimgroup/JUDI.jl): JUDI is a framework for large-scale seismic modeling and inversion and is designed to enable rapid translations of algorithms to fast and efficient code that scales to industry-size 3D problems.
- [LASIF](https://github.com/dirkphilip/LASIF_2.0): An End-to-end Workflow for Adjoint Full Seismic Waveform Inversions, specifically designed for SALVUS.
- [IFOS2D](https://git.scc.kit.edu/GPIAG-Software/IFOS2D): IFOS2D (Inversion of Full  Observed Seismograms) is a 2-D elastic full waveform inversion code.  
- [RAJZEL](https://github.com/daniel-koehn/RAJZEL): 2D parallel first-arrival traveltime modelling and inversion code using an Eikonal solver and the adjoint state method.
- [TOY2DAC](https://seiscope2.osug.fr/TOY2DAC-273): a 2D Acoustic frequency-domain Full Waveform modeling and inversion code.

## Seismic Signal Processing
- [MathGeo2022](https://github.com/sevenysw/MathGeo2022): Seismic data denoising, regularization and so on.
- [BIRGIT](https://github.com/daniel-koehn/BIRGIT): Pre- and Postprocessing tools for full waveform inversion (FWI) field data applications written in Matlab, Python and shell scripts.
- [CurveLab](http://www.curvelet.org/): CurveLab is a toolbox implementing the Fast Discrete Curvelet Transform, both in Matlab and C++.
- [PyCurvelab](https://github.com/slimgroup/PyCurvelab): Python interface to Curvelab
- [SeismicPro](https://github.com/gazprom-neft/SeismicPro): a framework for accelerating processing of pre-stack seismic data with deep learning models.



## High Performance Computing
- [Slurm](https://github.com/accre/SLURM): SLURM example scripts.

## Utilities
- [GMT](https://gmt-china.org/)
- [Gmsh](https://gmsh.info/)
- [PyGmsh](https://github.com/meshpro/pygmsh): Gmsh for Python
- [SeismiGraphix](https://github.com/abelsurace/seismigraphix)
- [SegDSee](https://www.softpedia.com/get/Science-CAD/SegDSee.shtml)

## Learning Resources
- [Lecture Notes on Inverse Theory](https://swp_ethz.gitlab.io/public/lecture_notes_inverse_theory/index.html)
