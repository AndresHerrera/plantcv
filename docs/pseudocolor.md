## Pseudocolor any Grayscale Image

This function pseudocolors any grayscale image to custom colormap. An optional mask can leave background out in the
pseudocolored image. Additionally, optional maximum and minimum values can be specified.

**plantcv.pseudocolor**(*gray_img, mask=None, cmap=None, min_value=0, max_value=255, path="."*)

**returns** pseudocolored image

- **Parameters:**
    - gray_img  - Grayscale image data
    - mask      - Binary mask made from selected contours
    - cmap      - Custom colormap, see [here](https://matplotlib.org/tutorials/colors/colormaps.html) for tips on how to choose a colormap in Matplotlib.
    - min_value - Minimum value (optional) for range of interest
    - max_value - Maximum value (optional) for range of interest
    - path      - Path giving location the image will get saved
- **Context:**
    - Used to pseudocolor any grayscale image to custom colormap
- **Example use:**
    - [Interactive Documentation](https://mybinder.org/v2/gh/danforthcenter/plantcv-binder.git/master?filepath=notebooks%2FpsII_tutorial.ipynb)

**Original grayscale image**

![Screenshot](img/documentation_images/pseudocolor/original_grayscale.jpg)

**Mask**

![Screenshot](img/documentation_images/pseudocolor/mask.jpg)


```python

from plantcv import plantcv as pcv

pcv.params.debug='plot'

# Pseudocolor an image with 'viridis' colormad
pseudo_img = pcv.pseudocolor(gray_img=img, mask=None, cmap='viridis', min_value=0, max_value=255, path='.')

# Pseudocolor the same image but include the mask and limit the range of values
pseudo_img_masked = pcv.pseudocolor(gray_img=img, mask=mask, cmap='viridis', min_value=30, max_value=200, path='.')

# Save the masked and pseudocolored image
pcv.print_image(pseudo_img_masked, 'nir_tv_z300_L1_pseudocolored.png')
```


**Pseudocolored Image**

![Screenshot](img/documentation_images/pseudocolor/pseudo_nomask.jpg)


**Pseudocolored and Masked Image**

![Screenshot](img/documentation_images/pseudocolor/pseudo_img.jpg)
