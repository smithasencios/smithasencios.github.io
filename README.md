## Strategy Pattern

### Introduction
Strategy pattern can be categorized as behavioral design pattern and it is simple and powerful. It can be considered in a kind of scenario where your object would perform a common action and that too selecting from various options available.

### UML class diagram
![Image](http://www.dofactory.com/images/diagrams/net/strategy.gif)

### How it works?
Let’s understand the widely accepted definition of strategy pattern which you can find from various resources on net. “**Strategy pattern defines a family of algorithms, encapsulates each one of them and makes them interchangeable.**” Confused with the definition? let’s try to break it in three parts:-

1) **Family of Algorithms-** The definition says that the pattern defines the family of algorithms- it means we have functionality (in these algorithms) which will do the same common thing for our object, but in different ways.

2) **Encapsulate each one of them-** The pattern would force you to place your algorithms in different classes (encapsulate them). Doing so would help us in selecting the appropriate algorithm for our object.

3) **Make them interchangeable-** The beauty with strategy pattern is we can select at run time which algorithm we should apply to our object and can replace them with one another

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

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/smithasencios/smithasencios.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
