# Text2Scene: Generating Compositional Scenes from Textual Descriptions
## Albert Nasybullin (a.nasibullin@innopolis.university), Marina Lisnichenko (m.lisnichenko@innopolis.university)
### Project idea: to rebuild text into image
### Dataset: Abstract Scene Dataset v1.1
### Timeline with each member individual task:
- 1st week: literature review and code investigation
- 2nd week: object detection
- 3rd week: object moving
- 4th week: image to text
- 5th week: presentation
### References: 
[Original paper](http://openaccess.thecvf.com/content\_CVPR\_2019/papers/Tan\_Text2Scene\_Generating\_Compositional\_Scenes\_From\_Textual\_Descriptions\_CVPR\_2019\_paper.pdf), [their previous paper](http://openaccess.thecvf.com/content_iccv_2013/papers/Zitnick_Learning_the_Visual_2013_ICCV_paper.pdf)
### What do we want:
As far as some code was found in the GitHub, firstly we want to test it and find out either it is workable or not. If there is no problem, we can suggest to do the following work: on synthesized image find objects, image of which separately are saved in the dataset (just pattern recognition).

Then there is an idea to move some objects. For example, when sentence is "Mike throws a ball to Jenny" ball is moving from Mike to Jenny. 

In the end it could be done text-to-image work. For example, when ball appears in the Jenny's hands the output sentence is "Now Jenny holds ball"

But to do all of this work we firstly have to be sure, that primary scripts from Git are workable.


### Part2: Cartoonizing filter:
In the beginning, we wanted to create GAN, which will generate comics-like images from the images we get from the text2image part. Regretfully, we failed on this part. Mostly because of computation complexity and my personal (Albert's) lack of expertise in Generative Adversarial Network. Also, we realized a GAN approach is overcomplicated for our goals. So, we decided to create a filter based on classical Computer Vision methods.

We could've to use a pre-trained model for cartoonizing, but it doesn't sound like fun. Isn't it? So, we have spent most of our time trying to make the GAN works but failed. I will be happy to try it one more time during the summer holidays.

### How cartoonizing filter works?
Papers and articles we found useful in this work:
- [Learning the K in K-Means](https://www.researchgate.net/publication/2869155_Learning_the_K_in_K-Means),
- [Converting Color Real Image to Cartoon Image Using NonParametric Mean-Shift Technique](https://www.iasj.net/iasj?func=fulltext&aId=65525),
- [Introduction to Image Segmentation with K-Means clustering](https://towardsdatascience.com/introduction-to-image-segmentation-with-k-means-clustering-83fd0a9e2fc3),
- [Color Quantization with OpenCV using K-Means Clustering](https://www.pyimagesearch.com/2014/07/07/color-quantization-opencv-using-k-means-clustering/),
- [Learn How To Do K-Means Clustering On An Image](https://laconicml.com/k-means-clustering/),
- [OpenCV with Python By Example](https://learning.oreilly.com/library/view/opencv-with-python/9781785283932/);

Step by step:
- to create histogram for given image,
- to find centroid,
- to update centroids as long as they won't stop changing,
- to choose minimum group size, alpha value to get the best value of k,
- to calculate values of H, S and V,
- to extract contours,
- to fill contours with calculated H, S, V; 

### Given results of cartoonizng filter:
Regretfully, we didn't get enough attention to a fact, that Abstract Scene Dataset is very abstract itself. So, there is no real sense in cartoonizing abstract images. But our filter works pretty good for another type of image. For our image this filter gives us a way more shape contours. You can see several examples here:

![1a](https://github.com/levshaazz/CV_Project/blob/master/cartoonizer_examples/1a.png)
Format: ![Iron Man and Warmachine before cartoonizing](url)

![1b](https://github.com/levshaazz/CV_Project/blob/master/cartoonizer_examples/1b.png)
Format: ![Iron Man and Warmachine after cartoonizing](url)

Another examples:

![1c](https://github.com/levshaazz/CV_Project/blob/master/cartoonizer_examples/1c.png)
Format: ![Iron Man and Warmachine](url)

![2c](https://github.com/levshaazz/CV_Project/blob/master/cartoonizer_examples/2c.png)
Format: ![Just a city corner](url)

![3c](https://github.com/levshaazz/CV_Project/blob/master/cartoonizer_examples/3c.png)
Format: ![Falcon Heavy's rocket boosters landing](url)


