# The Scientific Toolkit

## Agenda
- [ ] Collaborative paper discussion 
- [ ] A toolbox for science: LLMs, Typst, VS Code, Git/GitHub, 
- [ ] Hack-time: setup + first lines of code 
- [ ] For next time 


## Learning Objectives
1. **Learn to apply the scientific method** to design, analyze, and interpret research transparently.
2. **Use a modern research toolbox** for reproducible and collaborative work.
3. **Develop practical coding and documentation skills** to produce and manage reproducible outputs.


<!-- - Next week -->
<!-- - Python -->
<!-- - Run your first Python script and produce a simple plot -->

---

## The Scientific Method

![](../images/coffee.jpg){: style="height:175px" align=right}

1. Goal is inference: We seek to learn about the world from data.
2. Procedures are public: Methods and materials should be transparent and reproducible.
3. Conclusions are uncertain: We quantify uncertainty and avoid overclaiming.
4. The content is the method: The contribution lies in clear, defensible procedures.

### [Is a literature review a contribution?](https://www.cambridge.org/core/services/aop-cambridge-core/content/view/00B62000B6760AB78E1BD27E32A94C9F/S1049096506060264a.pdf/doing-a-literature-review.pdf?casa_token=szUhrJK1G30AAAAA:yj5nqRIULvP0oFEmACEq9AkAIZPdF8YBt9xWDetabQJwdKzVTZQ3yZvbGszZMNoesDnYgFtim2AA)


---

# Your Researcher Toolbox

!!! warning 

    **Getting started is the hardest part!** Setting up your tools is tedious, but once everything is in place, your research workflow will continuously improve, and will can elevate your work to new highs. Invest the effort now, and your future self will thank you!

## :fontawesome-solid-wand-magic-sparkles: A quick word about ChatGPT and other LLMs 

### What are they? What is the intuition behind it? 

ChatGPT is a Large Language Model (LLM) designed to generate human-like text based on the input it receives. It is part of the GPT (Generative Pre-trained Transformer) family of models and relying on deep learning algorithms to generate coherent and contextually relevant responses in a conversational format.

- [The intuition behind word embeddings](https://www.cs.cmu.edu/~dst/WordEmbeddingDemo/)
- [The intuition behind LLM's](https://ig.ft.com/generative-ai/)

![](https://upload.wikimedia.org/wikipedia/commons/a/a3/Gradient_descent.gif)

### Using LLMs as a learning tool
1. **Ask Open-Ended Questions**: Instead of seeking direct answers, pose open-ended questions that encourage exploration of concepts. For example, ask, *"What factors influence voter behavior in elections?" to gain a deeper understanding of political behavior.*

2. **Request Explanations and Summaries**: Use ChatGPT to explain complex topics in simpler terms or to summarize articles and books. For instance, you might ask, "Can you summarize the main theories of public opinion formation?" to clarify your understanding of how public opinion is shaped.

3. **Engage in Discussion**: Treat your interaction as a conversation. Ask follow-up questions, such as, "How do social media platforms impact public opinion during elections?" This encourages critical thinking and helps you explore the nuances of political behavior.

4. **Seek Practical Examples**: When learning new concepts, ask for real-world applications or examples. You could inquire, "Can you provide examples of how political campaigns have successfully influenced public opinion?" This contextualizes your knowledge and makes it more relatable.

5. **Reflect and Review**: After receiving information, take time to reflect on what you've learned. For example, summarize the key factors that affect public opinion in your own words, or discuss with ChatGPT how these factors might apply to current political events to solidify your understanding.


## Other Tools: What They Are & Why They Matter

### Hacking with **:fontawesome-solid-laptop-code: VS Code**

VS Code is a free, user-friendly code editor that helps you write and organize your project files in one place. Beyond coding, you can use it to manage documents, run scripts, and integrate extensions for Python, Git, Typst, and more, essentially making it your all-in-one research workspace.

### Collaborating on **:fontawesome-brands-github: GitHub**

Git provides version control to track changes to your files, while GitHub hosts your projects online, making it easy to share, collaborate, and back up your work. Using Git and GitHub ensures reproducibility, maintains a history of your work, and simplifies collaboration with anyone around the globe.

### Writing with **:fontawesome-solid-quote-left: Typst**

Typst is a lightweight, open-source tool for creating clean, formatted documents. Think of it as a text editor made for Scientific papers, notes, or reports which include figures, citations, or even math. Combined with Git, your research becomes reproducible, versionable, and easy to manage.


# Hack-Time: Setup + Your First Lines of Code 

## Package Manager Setup:  
- This will make installing software much easier!
    - **Windows**: [Chocolatey](https://chocolatey.org/install)  
    - **Mac**: [Homebrew](https://brew.sh/)  
    - **Linux**: You already have a package manager (e.g., `apt`, `dnf`, `pacman`).  
- Can you install :fontawesome-brands-python: Python ?

## First Typst document
- Create a document named `paper.typ` with the following contents:
```
= Week 2: First Results

This document was produced with Typst.
We computed the average penguin body mass by species. See the figure below.
#image("find_some_figure.png", width: 80%)
```
- Compile (export as pdf).

You should get paper.pdf.

## Put your paper on GitHub
- In GitHub 
  - Create a new public or private repository.
  - Upload the pdf.
  - Add a commit changes: “My first commit, horray!”
  - Push your changes to GitHub.

---

## For next time

**:fontawesome-solid-pen-nib: Writers:**

- Research Question with regards to France (One at least. Your goal is to find a gap, or a puzzle in the literature)
- 3 hypothesis that you can link to one or more scientific papers.

**:fontawesome-solid-laptop-code: Hackers:**

- Identify existing and conventional datasets that could be used to measure AP in France? 
    - Include scientific reference if it is an existing data set used in another paper.
- Suggest other data less conventional datatypes to measure AP in France.
- can you think of feasible primary data collection approaches? (less than 1 month of work)

**:fontawesome-solid-house-laptop: Recommended Practice**

- [Iyengar, Shanto, Gaurav Sood, and Yphtach Lelkes. "Affect, not ideology: A social identity perspective on polarization." *Public opinion quarterly* 76, no. 3 (2012): 405-431.](https://academic.oup.com/poq/article-abstract/76/3/405/1894274)

**:fontawesome-solid-house-laptop: Recommended Practice**

- [:fontawesome-solid-quote-left: typst](https://typst.app/docs/tutorial/)
