# Data Exploration I

## Collaborative paper discussion


![Mental Model for Reviewers](https://images.squarespace-cdn.com/content/v1/55f73529e4b0e5bde7f43a66/1529065898666-ZTYIPZ3Y5PSV0DUZRU90/like+wish+wonder.png){width=66%}
/// caption
Mental Model for Reviewers.
///


## The Data Science Pipeline & Hacker's Demo
![Data Science](https://mickaeltemporao.github.io/data-analysis/images/ds-pipeline.svg)


## Hack-time
!!! tip inline end
    To load and use a notebook in VS Code follow the steps 3 to 5 in [📘 Notebooks in VS Code](../resources/notebook-vscode.md)
### Working with Data

- The coding quest continues. Open the notebook of the day in VS Code:

    - [:fontawesome-solid-folder: **Notebook Repository**](https://github.com/mickaeltemporao/materials/tree/main/notebooks)

        - [:fontawesome-solid-file-code: **Subsetting DataFrames** (student's notebok)](https://github.com/mickaeltemporao/materials/tree/main/paper-spsc-2026/notebooks/subset_dataframes.ipynb)


## For next time

Everyone, remember:

- you can ask me for help on WhatsApp.

- you can and should all work on each of these tasks together.

- don't wait until you're the hackers to practise code, nor until you're the writers to get involved in writing, nor until you're the reviewers to give feedback. You should all be involved at every stage.

Writing a scientific paper is not easy. It takes a lot of self-discipline and good communication to make it work. You have been making lots of progress and I'm confident you'll manage it!


### **:fontawesome-solid-pen-nib: Writers**

- Integrate your `main.typ` file with the [starter-journal-article](https://typst.app/universe/package/starter-journal-article/).
    - I've integrated some initial code into the `main.typ` file already. You need to update the template.
    - Don't do this alone or only among the writers. Keep the others involved and explain to the reviewers and hackers how they can use a template.
- Add a title and a short abstract (fewer than 250 words) using the template placeholder.
    - In the abstract you need to answer 5 questions:
        - What are you doing?
        - Why does it matter?
        - What have others been doing on the topic?
        - What are you doing that's better?
        - What do you expect to find?
- Fix all missing Typst syntax citations using the `@authorYEARkeyword`.
    - In the `main.typ`, especially in the first four paragraphs, we seem to have shifted to manually written citations. This sounds a lot like ChatGPT. Make sure to use the correct Typst syntax.
    - We should use Typst formatting all the time!
    - Also remove any sentences like `= Summary Group 1` or anything of the sort.

**Deliverable:**

- Updated `main.typ` and compiled PDF shared in the General Chat with the group.
- A **5-minute overall presentation** walking through the current version of the paper in the `main.typ` file.
    - Don't talk about the structure (this is for the reviewers) or what you did in a specific part. We want to discuss the paper itself. What is it about? What are the current problems? How are we going to fix them?

**Going the extra mile (Optional):**

A figure has been integrated into the `main.typ`, but if you include a figure in a scientific paper, you should refer to it in the text and explain what it shows.

- Make sure to use the `#figure` function (see the first example [here](https://typst.app/docs/reference/model/figure/)).
- Add a figure caption.
- Make a reference to that figure (again see (see the first example [here](https://typst.app/docs/reference/model/figure/)).


### **:fontawesome-solid-laptop-code: Hackers**

- Create a notebook to explore relevant variables.
- Produce an `.ipynb` file that generates descriptive statistics for the quantities of interest (QOIs).
    - You will mostly use `df['some_variable'].value_counts()`.
    - Start with some of the variables listed by this week's hackers notebook:
    ```python
    variables = ["cntry", "prtdgcl", "clsprty", "lrscale", "prtclffr"]
    ```
    - Integrate other relevant SES variables (e.g. age, sex, education, etc.).
        - You can/should also take inspiration from previously published scientific papers.
- You should build your notebook starting from last week's notebook:
    - [Notebook - Subsetting DataFrames](https://github.com/mickaeltemporao/itds/tree/main/materials/subset_dataframes.ipynb)

**Going the extra mile (Optional):**

Can you create a simple figure of the distribution of ideology using the `pandas` plotting function?

- See [pandas.DataFrame.plot](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.plot.html).
- Tip: you will have to install matplotlib `!pip install matplotlib`

### **:fontawesome-solid-magnifying-glass: Reviewers**

**5-Minute Brief**

- Use the “I like, I wish, I wonder” model to give constructive feedback.
- Identify the **top 3 current risks** in the paper.
- Always refer to the `main.typ` file.

**Going the extra mile (Optional):**

- Assist the Writers and Hackers with integrating any feedback received during class!

