# Photogrammetry
Photogrammetry for extraction of object coordinates from featureless terrain


## Photogrammetry
```
This is the science or the process of obtaining reliable information (location, coordinates, perspectives, shape, size, etc.) about objects,

environments or situations through recording, measuring and interpreting photographics images.

```

**_Input ----> Photograph_**

**_Output ----> Measurement, Model, Map, Drawing_**

# Overview of the Project

## Feature Extraction

```
a) Takes in an image from a camera
    - Camera focal length, height the photo is taken from and other parameters are to be known.
b) Converts into grayscale for processing
c) Applies thresholding algorithm through histogram processing to find the optimal level of threshold for clarity
d) Applies edge detection techniques to find the object contours and draw a bounding box around it
e) Takes in the center of the box as the object pixel position

```

## Mapping

```
a) Takes in an image from a camera with known focal lenght and height with a reference object in focus.
b) The reference object has known dimensions
c) A focal-length rule is applied to find the projection of object on lens
d) The projection size is mapped to pixels
e) This is translated to the camera placed at different heights and thus the distance per pixel values at required heights are calculated

```

## Pixels to meters

```
a) The feature (location of object desired) is extracted
b) The scaling factor per pixel is known
c) The difference from either the photo center or the camera to the object is calculated in terms of pixels
d) Then the pixels are multiplied with the scale to get the distance in meters

```

## Perspective forshortening

```
a) The stretch in length due to the camera viewing angle is to be considered
b) https://www.scantips.com/lights/subjectdistance.html -> a relation provided in this website helps us calculate the multiplier required
```

## Final result

```
Distance = {(Difference in pixels) * (Length per pixel) * (Perspective Multiplier)}
```
