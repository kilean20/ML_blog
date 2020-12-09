# Perturbative Correction Using ML ( applied on nonlinear decoherence data of beam centroid )
this is part of the contents in [Here](MLdecoherence1.pdf) which a slide presented in IOTA (Accelerator in Fermi Lab) collaboration meeting.

## Data Model 

Assume the following time series data model:

<p align="center">
  <img src="deco_data_model.png" width="480"/>
</p>

where the bracket <> represent the ensemble average over particles, <img src="z_t.png" width="100"/> is the complex canoncial variable at time *t*, <img src="action.png" width="70"/> is the action, and <img src="A.png" width="20"/> is the transformation operator from physical coordinate to normal coordinate. The decoherence data is generated with 7 free parameters: initial offsets <img src="x0.png" width="20"/>, <img src="p0.png" width="20"/>, initial emittance <img src="epsilon.png" width="20"/>, optics parameters <img src="beta.png" width="20"/>, <img src="alpha.png" width="20"/>, bare frequency <img src="omega.png" width="20"/>, and nonlinear detuning parameter <img src="detuning.png" width="20"/>.


## Leading order theory

Consider normal coordinate normalized by emittance such that:
<p align="center">
  <img src="deco_data_model.png" width="480"/>
</p>
With an initial offset in normal coordinate <img src="xn0.png" width="20"/>, the frequency domain of the normaized centroid,
<p align="center">
  <img src="DFT.png" width="480"/>
</p>
becomes
<p align="center">
  <img src="LeadingOrderTheory.png" width="480"/>
</p>
in the **limit of** <img src="offset_limit.png" width="100"/> (i.e. **large initial offset compared to the initial emittance**).

