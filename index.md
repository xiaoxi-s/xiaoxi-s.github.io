# Overview

Illumination prediction is a crutial component for augmented reality (AR) and mixed reality (MR) to produce expected virtual objects and scenes. 

 - importance, application
 - complexity

# State of Art
 

# Our Approach

 - Deep learning based
 - Simplified parametric estimation

## Environment Specification

 - GPUs:  
 - Libraries
  - 

## Network Architecture

The feature extracter is (dense121)[https://arxiv.org/abs/1608.06993]. The classification layer is replaced with two linear layers with Relu activation between them. The output consists of three light sources.

## Data and Preprocess

 - Dataset
 - Labeling process

## Training

### Parameter Setting

 - Optimizer:
 - Learning rate: 
 - Batch size: 
 - 

### Network reference

 - Time for training with fine tune: 
 - Time for training without fine tune: 
 - network (reference)[https://github.com/xiaoxi-s/Illumination-Prediction/blob/main/checkpoint/model_epoch_20_res_360x240]


# Result

## Accuracy

## Rendering Examples

### Ground Truth

### Predicted Result

# Discussion

## Accuracy Measure

## Feature Extracter

# Material

## Project Proposal

## Mid-term Report

# Reference



# Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/xiaoxi-s/xiaoxi-s.github.io/edit/main/index.md) to maintain and preview the content for your website in Markdown files.

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

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/xiaoxi-s/xiaoxi-s.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
