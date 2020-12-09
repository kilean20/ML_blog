# Perturbative Correction Using ML 

this is part of the contents from a [slide](MLdecoherence1.pdf) which is presented in IOTA (Accelerator in Fermi Lab) collaboration meeting.

### Data Model and Goal

We assume the data to be time series of complex valued scalar. To be more specific, it is simulated measurement data of beam centroid from Beam Position Monitor (BPM). The details can be found from [here](Decoherence.md) or the [slide](MLdecoherence1.pdf). The data depends on the bare frequency *w<sub>0</sub>* and the frequency detuning parameter *w<sub>1</sub>* that we want to measure (find) and other hidden parameters including initial offset, beam emittance, optics parameter, and etc that we assume that we are not interested in discovering. 
