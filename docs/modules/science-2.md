# The Scientific Toolkit

## Agenda
- [ ] Collaborative paper discussion 
- [ ] A toolbox for science
- [ ] Hack-time: First lines of code in typsts
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

VS Code is a free code editor that helps you write and organize your project files in one place. Beyond coding, you can use it to manage documents, run scripts, and integrate extensions for Python, Git, Typst, and more, essentially making it your all-in-one research workspace.


### Collaborating on **:fontawesome-brands-github: GitHub**

Git provides version control to track changes to your files, while GitHub hosts your projects online, making it easy to share, collaborate, and back up your work. Using Git and GitHub ensures reproducibility, maintains a history of your work, and simplifies collaboration with anyone around the globe.

### Writing with **:fontawesome-solid-quote-left: Typst**

Typst is a lightweight, open-source tool for creating clean, formatted documents. Think of it as a text editor made for Scientific papers, notes, or reports which include figures, citations, or even math. Combined with Git, your research becomes reproducible, versionable, and easy to manage.


# Hack-Time: Setup + Your First Lines of Code 

## First Typst document
- Create a document named `paper.typ` with the following contents:
```
= Some Random Text

This document was produced with Typst.
We computed the average penguin body mass by species. See the figure below.
#image("find_some_figure.png", width: 80%)
```
- Compile (export as pdf).

You should get a PDF file (eg. `paper.pdf`).

- Can you also find a way to export your typst file (eg. `paper.typ`)?

---

## For next time

**:fontawesome-solid-pen-nib: Writers**

- Setup a shared typst project and share the link on the Chat.
- The typst document contains an introduction paragraph that introduces a puzzle/gap. 
    1. It leverages some of the academic articles we have found until now. 
    2. It introduces the **research question** and at least **3 hypotheses** (coordiante with :fontawesome-solid-laptop-code: Hackers). 
    3. It is formatted using typst.
- The documents contains a reference section with all the references found until now.
    - :fontawesome-solid-rocket: Above and beyond: Create a `references.bib` file in the typst project with current references. Adjust citations using typst academic citing syntax.

**:fontawesome-solid-laptop-code: Hackers**

- Acquire latest data & codebooks for the following datasets
    - [ESS](https://www.europeansocialsurvey.org/) & [CSES](https://cses.org/) datasets
- Identify questions (keep track of their id) in each of the codebooks that could be used to explore at least 3 of the 9 identified hypothesis.
    - :fontawesome-solid-rocket: Above and beyond: Identify questions (keep track of their id) to explore all of the identified hypothesis with links with existing papers.

- Instructor: Setup Github Repository with a `README.md` file

**:fontawesome-solid-house-laptop: Recommended Practice**

- [:fontawesome-solid-quote-left: typst bibliography](https://typst.app/docs/reference/model/bibliography/)
