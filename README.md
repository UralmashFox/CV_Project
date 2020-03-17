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

Final step is to generate from the output image a comic-book style picture. We propose to creater another GAN for this task.

In the end it could be done text-to-image work. For example, when ball appears in the Jenny's hands the output sentence is "Now Jenny holds ball".

But to do all of this work we firstly have to be sure, that primary scripts from Git are workable.
