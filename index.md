**This is the project website for CS 766 Computer Vision in the University of Wisconsin-Madison**
## Documents
[Proposal](https://github.com/arrow789/CS766_Project/files/8614111/CS766.Project.Proposal.pdf)

[MidTerm Report](https://github.com/arrow789/CS766_Project/files/8614186/MidTerm.Report.pdf)

[Final Presentation](https://github.com/arrow789/CS766_Project/files/8614190/Presentation.pdf)

## Introduction
Emotion recognition has attracted major attention in numerous fields because of its relevant applications in the contemporary world. Marketing, psychology, surveillance, and entertainment are some examples. 

It is possible to recognize emotion in several ways, such as facial expression, body language or speaking tones. Facial Expression Recognition (FER) is an important visual recognition technology to detect emotions given input to the intelligent system. There are many applications in multiple domains as below.

•Human–Computer Interaction
•Virtual Reality 
•Augmented Reality 
•Advanced Driver Assistance Systems 
•Education
•Entertainment

## Goals
This project focuses on the state-of-art FER methods and reimplements FER algorithms (including Conventional and Deep Learning-based approaches). Two groups will be tested and compared on several datasets(In-the-Lab/ In-the-Wild). Defects of current methods and future works will be pointed out.

## Why FER is important?
FER in the human-computer interactive system is one of the challenging research topics in the field of artificial intelligence which has drawn plenty of attention in recent years. However, it is difficult to achieve natural and harmonious emotional interaction with traditional interaction methods such as keyboard, mouse, screen, and pattern, which is far from meeting the requirements for artificial intelligence. 
Human expression is the most important carrier of inspirational perception and the most direct and obvious way of expressing emotions. And Facial expression is arguably the most natural, powerful, and immediate signal to communicate emotional states and intentions. Thus, FER has important theoretical significance for improving the emotional interaction ability of computers.

## State-of-Art
There are many approaches in different areas to achieve FER. 

For example, we can use RF signals to measure heart beats and get the emotions. We can use the Thermals measurement to get blood flow on face to get the emotions.

| ![The Procedure of RF Signals Detecting Emotion](https://user-images.githubusercontent.com/46728665/166586964-b8583cf9-b2da-42a8-a776-172e10028b03.png)
|:--:| 
| *The Procedure of RF Signals Detecting Emotion* |

| ![image](https://user-images.githubusercontent.com/46728665/166587223-af64c7bc-e513-4e95-9a6b-fa33e4f00588.png)
|:--:| 
| *RF Signal Classification* |

In the computer vision areas, work [1] applies the HOG to encode these facial components as features. A linear SVM is then trained to perform the facial expression classification. Paper [2] proposes es-LBP (expression-specific LBP) which could better capture the local information of faces on important fiducial points. However, it has the disadvantage of being sensitive to noise. Due to an increase in the ready availability of computational power and increasingly large training databases to work with, the machine learning technique of neural networks has seen a resurgence in popularity. Work [3] presents a new deep neural network architecture for FER which increased classification accuracy on both subject independent and cross-database evaluation scenarios. The addition of  Inception layers increases the depth and width of the network while keeping the computational budget constant. Paper [4] instead of using the whole face region, three kinds of active regions are applied to classify facial expression through a decision-level fusion strategy. Work [5] proposes a deep convolutional fusion network, which addresses the FER task through discriminative spatial features learning and temporal dependencies accumulating.

| ![image](https://user-images.githubusercontent.com/46728665/166588429-30fa8c99-8f81-4ae0-b7b4-797b3e55c21f.png)
|:--:| 
| *Deep Convolutional Fusion Network* |











## Welcome to GitHub
 Pages

You can use the [editor on GitHub](https://github.com/arrow789/CS766_Project/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/arrow789/CS766_Project/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
