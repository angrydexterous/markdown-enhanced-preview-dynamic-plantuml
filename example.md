```python {cmd="python" hide continue run_on_save matplotlib=true}
from os import path
import io
import plantuml as puml
import matplotlib.pyplot as plt
from PIL import Image

x = 9
name = "william"

render = f"""
@startgantt
[Prototype design] lasts 20 days
then [{name}] lasts {x} days
@endgantt
"""

pml = puml.PlantUML("http://www.plantuml.com/plantuml/img/")
content = pml.processes(render)
img = Image.open(io.BytesIO(content))
imgplot = plt.imshow(img)
plt.show()
```

