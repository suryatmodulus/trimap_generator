## Automatic Trimap Generator ##

<b>Description: </b> 
<ul>
<li/>Generate a grayscale trimap (foreground, background, and unknown regions) from an input of binary (mask) image.
<li/>Foreground has a pixel value of 255; background has a pixel value of 0; and unknown has a pixel value of 127.
<li/>In this example, the trimap is generated by extending a binary image of a previously segmented tumor. 
<li/>The binary image consists of two parts: foreground (white) which is the tumor and background (black) which is the surrounding region
<li/>Keep in mind that the unknown region is simply an approximation rather than an exact delineation. Therefore, matting process becomes a crucial key to extract foreground images with exact precision (<b>Deep Image Matting</b> anyone?)
</ul>
<br /><b>Input :</b> a binary image (from a segmented lesion)
<br /><b>Output:</b> a trimap with unknown region (gray) from tumor dilation
<hr />
<b>May 25, 2018: </b> <br/>

- [x] Update(s): create a function that converts a binary image to a trimap
- [x] To Do: documentation to accompany the code, a program that directly & recursively converts binary images to trimaps 
---
<b>December 30, 2018: </b> <br/>

- [x] Update(s): documentation, illustration, and tutorial
- [x] Built a recursive version of the module that can handle multiple input images

---
## Example ##
**PROCESS:** Dilating the binary image <br/>
```python
name    = "sample_image.png";
size    = 10;
number  = 1;
bin_img = cv2.imread(name, cv2.IMREAD_GRAYSCALE)
trimap_generate(bin_img, name, size, number)
```

<center>
|**INPUT:** A binary image | **OUTPUT:** Trimap with 10 pixels unknown region <br/> |
|:----------:|:----------:|
|![alt text](./images/sample_image.png)| ![alt text](./images/10px_sample_image.png_1.png) | 
</center>
