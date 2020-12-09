# Nonlinear decoherence of beam centroid.

Given an inital offset, the beam centroid evolution can be modeled by

<p align="center">
  <img src="deco_data_model.png" width="200"/>
</p>

where the bracket <> represent the ensemble average over particles, *z<sub>t</sub> = x<sub>t</sub> - ip<sub>t</sub>* is the complex canoncial variable at time *t*, *I=zz<super>\*</super>/2* is the action, and *A* is the transformation operator from physical coordinate to normal coordinate. 

<!--- The decoherence data is generated with 7 free parameters: initial offsets *x<sub>0</sub>, p<sub>0</sub>*, <img src="p0.png" width="20"/>, initial emittance &epsilon;, optics parameters &alpha;, &beta;, bare frequency &omega;, and nonlinear detuning parameter &partial; <img src="detuning.png" width="20"/>. --->

# Limit of large initial offset

Consider normal coordinate normalized by emittance such that:

<p align="center">
  <img src="normal_coordi.png" width="420"/>
</p>

With an initial offset in normal coordinate *x<sub>n,0</sub>*, the frequency domain of the normalized centroid,

<p align="center">
  <img src="DFT.png" width="280"/>
</p>
becomes
<p align="center">
  <img src="LeadingOrderTheory.png" width="320"/>
</p>

in the **limit of** *x<sub>n,0</sub>>>1* (i.e. **large initial offset compared to the initial emittance**).
