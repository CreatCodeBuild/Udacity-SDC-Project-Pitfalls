# Udacity-SDC-Project-Pitfalls
A collection of pitfalls and tricky parts of SDC projects

I created this document to collect all tricky parts which I found while I was doing projects and which I discovered while I was mentoring other students.

Feel free to add more if you have any by submitting a pull request.

## Find Lane Lines

## Traffic Sign Classifier

## Behavioral Cloning

## Advanced Lane Finding
In the course video [Calibrating Your Camera](https://classroom.udacity.com/nanodegrees/nd013/parts/fbf77062-5703-404e-b60c-95b78b2f3f9e/modules/2b62a1c3-e151-4a0e-b6b6-e424fa46ceab/lessons/40ec78ee-fb7c-4b53-94a8-028c5c60b858/concepts/a30f45cb-c1c0-482c-8e78-a26604841ec0) and the example code in project repo under examples/, we see the following code  
```python
# prepare object points, like (0,0,0), (1,0,0), (2,0,0) ....,(6,5,0)
objp = np.zeros((6*9,3), np.float32)
objp[:,:2] = np.mgrid[0:9,0:6].T.reshape(-1,2)
```
mgrid returns a 3-d ndarray, which contains 2 matrices. These 2 matrices are just counting numbers from different dimention. One horizontally(dimension 0), another vertically(dimension 1).
```
>>> mgrid[0:3,0:4]
array([[[0, 0, 0, 0],
        [1, 1, 1, 1],
        [2, 2, 2, 2]],

       [[0, 1, 2, 3],
        [0, 1, 2, 3],
        [0, 1, 2, 3]]])
```
.T returns the transpose matrix of a ndarray. Please refer to:
  1. https://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.T.html
  2. https://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.transpose.html

.reshape reshapes the ndarray. (-1,2) just means "compute the lenght of this dimension by number of elements / 2"
