
---

# Pixel Heart Project with NumPy and Linear Algebra

## Project Description

The Pixel Heart Project is an innovative and engaging program that demonstrates the power of NumPy and linear algebra in Python to manipulate and transform a pixelated heart image. This project uses mathematical operations to create, invert, rotate, and solve for image transformations, showcasing the versatility of Python's scientific libraries.

## Features

- **Image Creation and Display:** Generates a pixelated heart image using NumPy arrays and displays it using Matplotlib.
- **Color Inversion:** Demonstrates the use of NumPy array operations to invert the colors of the heart image.
- **Image Rotation:** Uses NumPy's transpose function to rotate the heart image.
- **Random Image Generation:** Creates a random 7x7 image using NumPy’s random integer generation.
- **Linear Algebra Solutions:** Applies NumPy's linear algebra functions to solve for image transformations.
- **Interactive Visualization:** Includes a helper function to display images with Matplotlib.

## Setup Instructions

### Prerequisites

- Python 3.x
- NumPy
- Matplotlib
- Codecademylib3 (if using Codecademy’s learning environment)

### Installation

1. **Clone the Repository:**
    ```sh
    git clone https://github.com/your-username/pixel-heart-numpy.git
    cd pixel-heart-numpy
    ```

2. **Create a Virtual Environment:**
    ```sh
    python -m venv env
    source env/bin/activate   # On Windows, use `env\Scripts\activate`
    ```

3. **Install the Required Libraries:**
    ```sh
    pip install numpy matplotlib
    ```

## Usage

1. **Run the Script:**
    ```sh
    python pixel_heart.py
    ```

2. **Observe the Outputs:**
    The script will display several images: the original heart image, the inverted heart image, the rotated heart image, a random image, and the solved heart image.

## Code Overview

Here's a brief overview of the main components of the script:

```python
import numpy as np
import matplotlib.pyplot as plt
import codecademylib3

# Define the pixel heart image
heart_img = np.array([[255,0,0,255,0,0,255],
                      [0,255/2,255/2,0,255/2,255/2,0],
                      [0,255/2,255/2,255/2,255/2,255/2,0],
                      [0,255/2,255/2,255/2,255/2,255/2,0],
                      [255,0,255/2,255/2,255/2,0,255],
                      [255,255,0,255/2,0,255,255],
                      [255,255,255,0,255,255,255]])

# Helper function to show images
def show_image(image, name_identifier):
    plt.imshow(image, cmap="gray")
    plt.title(name_identifier)
    plt.show()

# Display the original heart image
show_image(heart_img, "Heart Image")

# Invert the heart image colors
inverted_heart_img = 255 - heart_img
show_image(inverted_heart_img, "Inverted Heart")

# Rotate the heart image
rotated_heart_img = heart_img.T
show_image(rotated_heart_img, 'Rotated Heart Image')

# Generate a random image
random_img = np.random.randint(0,255, (7,7))
show_image(random_img, 'Random Image')

# Solve for the heart image using linear algebra
x = np.linalg.solve(random_img, heart_img)
show_image(x, "x")
solved_heart_img = random_img @ x
show_image(solved_heart_img, 'Solved Heart Image')
```

## Future Enhancements

- Expanding the project to include more complex transformations and image filters.
- Implementing interactive features such as real-time adjustments of image parameters.
- Exploring 3D visualizations and animations using additional libraries like `mpl_toolkits.mplot3d`.

## Contributions

Contributions are welcome! Please open an issue or submit a pull request with your ideas or improvements.
