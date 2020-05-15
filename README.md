# seppi
Serializable Pandas pipelines

## Example

```python
import pandas as pd
from seppi import PandasPipeline

df = pd.DataFrame(dict(
    x=[1, 2, 3, 4, 5],
    y=[6, 2, 4, 3, 6],
    g=["a", "a", "b", "a", "b"]
))

steps = [("groupby", dict(by="g")), ("mean", dict())]
pipeline = PandasPipeline(steps)

output = pipeline.transform(df)
#           x         y
# g
# a  2.333333  3.666667
# b  4.000000  5.000000
```
