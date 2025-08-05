1. The system is incapable of learning incrementally. After being trained on a dataset, it does not learn after being deployed.
2. This is also called **offline learning**

## Cons
1. For a fast changing environment, like stock prices, the model becomes outdated quickly.
   This is called model rot or data drift. The model needs to be retrained on a new dataset from scratch.
2. It takes lots of hardware resource.