# Python Seam Carving

This repository contains a Python implementation of Seam Carving, an algorithm for content-aware image resizing. The script utilizes Numpy, Kornia, PyTorch, torchvision, and PIL to dynamically adjust the size of images while preserving their key features.

## Introduction

Seam Carving is a technique that enables resizing images without distorting important content. Unlike traditional resizing methods, which uniformly scale down or crop images, Seam Carving removes seams containing pixels that are less important, thus preserving the integrity of the main features in the image.

## Screenshot

- https://github.com/vashavi-20/Seam-Carving/main_image.jpg
- https://github.com/vashavi-20/Seam-Carving/seam_carved_1200x1151.jpg
- https://github.com/vashavi-20/Seam-Carving/seam_carved_1728x720.jpg

## Installation

To use this script, you need to install the required Python libraries. You can install them using pip:

```bash
pip install numpy kornia torch torchvision pillow
```

## Requirements

- Python
- Numpy
- Kornia
- PyTorch
- torchvision
- PIL (Python Imaging Library)

## Usage

The `MySeamCarving` function in the script takes an image and target dimensions (width and height) as input and returns the resized image using Seam Carving algorithm.

Example usage:

```python
from PIL import Image
img = Image.open("path_to_your_image.jpg")
target_width, target_height = 800, 600
resized_img = MySeamCarving(img, target_width, target_height)
resized_img.show()
```


## How It Works

- Energy Calculation: The algorithm starts by computing an energy map of the image, identifying pixels that form less important parts of the image.
- Seam Identification: It then identifies seams (vertical or horizontal lines of pixels) that have the lowest energy and are therefore less important.
- Seam Removal: The identified seams are removed from the image, effectively reducing its size while preserving the most important content.
- Repeating the Process: Steps 1-3 are repeated until the image is resized to the desired dimensions.