#  Generative model ( vs. discriminative model )

- Data assumed to be generated from unknown latent variables
- “Modeling” is understood in almost every science as unveiling this generating process by hypothesizing theories and testing these theories through observations.
    - The resulting models are usually highly intuitive and interpretable
    - Tend to make stronger assumptions on the data than purely discriminative counterparts, often leading to higher asymptotic bias when wrong.
    
- If one is solely interested in learning to discriminate, and one is in a regime with a sufficiently large amount of data, then purely discriminative models typically will lead to fewer errors in discriminative tasks
    - However, one may have few labeled examples and many more unlabeled examples. In this case, the generative model can greatly improve prediction