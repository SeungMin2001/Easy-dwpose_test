# Easy-dwpose_test
### > This project is based on [easy_swpose](https://github.com/carpedm20/easy_dwpose?tab=readme-ov-file).
#### pip (Jupyter)
```py
!pip install easy-dwpose
```
#### Quickstart
```py
import torch
from PIL import Image

from easy_dwpose import DWposeDetector

# You can use a different GPU, e.g. "cuda:1"
device = "cuda:0" if torch.cuda.is_available() else "cpu"
detector = DWposeDetector(device=device)
input_image = Image.open("assets/pose.png").convert("RGB")

skeleton = detector(input_image, output_type="pil", include_hands=True, include_face=True)
skeleton.save("skeleton.png")
```
