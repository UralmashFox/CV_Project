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

# Update (05.04.2020)
What do we have till now:
- [x] literature review
- [x] Text2Scene algorithm (NOT from paper)
- [ ] Moving objects
- [x] Comic-book style picture
- [ ] Image-to-text work

## Problems
Unfortunately, we couldn't run git from source paper. It happened because of (1) too slow internet to download around 100 Gb of info and (2) there is no instruction about how to run the code.

Text-to-scene algorithm was done from scratch by Marina. There is no Neural Networks, but, was done attempt to save the idea of authors of paper (make a code from text -> from code take image -> place images in the background). Because of this unexpected task, following moving objects wasn't done yet.

However, by Albert was done GAN, making comic-book style of pictures. Till now, it needs some debugging process, but already we have some good results.

You can check our git: [https://github.com/UralmashFox/CV_Project](https://github.com/UralmashFox/CV_Project)
there is "CV_project.ipynb" file. All you need is to open it (for example in collab), in the last cell input the desired text:
![](https://i.imgur.com/vwNFxII.png)

For example, input

*It was sunny day. Happy Mike was sitting in the park and playing with ball. There was a snake and Jenny was worried, she was wearing silly hat*

will give you a following picture:

![](https://i.imgur.com/Cl1tTJq.png)

if you are going to change text, from second time run ONLY the last cell, not all the program.

Important issues:
1) try to build picture in following steps for each sentence: 
sky objects -> ground objects -> person + mood + hat + activity -> animals.
In case to not overlap small objects by big
2) follow syntax rules of English
3) you can input any amount of sentences with any amount of words
4) NOT input sentence with only hat or activity

Some examples:

*There is a bear*

![](https://i.imgur.com/IiVY1xI.png)

*The rocket was flying in the sky and Jenny was excited*

![](https://i.imgur.com/4o2hjQx.png)

*It was a storm. Despite of this, kids were in the park and playing soccer. Mike was sitting near sand. Jenny was a happy princes, she was kicking soccer*

![](https://i.imgur.com/ED3o9OU.png)

*On the table there is a drink and hotdog*

![](https://i.imgur.com/d4954yd.png)

The next step will be either finding out how to make the algorithm via networks or moving objects and making GIF file.

