<div align="center">

  <img src="assets/header.png" alt="logo" width="300" height="auto" />
  <h1>MAP - Charting Student Math Misunderstandings</h1>
  
  <p>
    [Kaggle Competition] Predict the affinity between misconceptions and student open-ended questions
  </p>

</div>

<br />

<!-- Badges -->

## Tools

![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white)

---

<br />

<!-- Table of Contents -->

# :notebook_with_decorative_cover: Table of Contents

- [About the Project](#star2-about-the-project)
- [Details on Data](#bookmark_tabs-details-on-data)
- [Contact](#handshake-contact)
- [Acknowledgements](#gem-acknowledgements)

<!-- About the Project -->

## :star2: About the Project

🎯**Goal**: Tag student's explanations as containing potential misconceptions

- Use NLP model that predicts students' potential math misconceptions based on student explanations
- Each question can have up to 3 `Category:Misconception` values per row (any predictions beyond the third are ignored), each prediction is space-delimited

Performs the following:

1. Determines whether the selected answer is correct. (True or False in Category; e.g., True_Correct)
2. Assesses whether the explanation contains a misconception. (Correct, Misconception, or Neither in Category; e.g., True_Correct)
3. Identifies the specific misconception present, if any

### Evaluation

Evaluation is done according to the Mean Average Precision @ 3 (MARP@3):

$$
MAP@3 = \frac{1}{U} \sum_{u=1}^U \sum_{k=1}^{min(n,3)} P(k) \times rel(k)
$$

Average of the top 3 recommendation categories. If the entry is matched, ignore the rest.

## :bookmark_tabs: Details on Data

Student's were asked multiple-choice Diagnostic Questions and provided an explanation to why the chose the answer. Explanations are the basis of this challenge.

_[train/test].csv_

- `QuestionId` - Unique question identifier
- `QuestionText` - The text of the question
- `MC_Answer` - The multiple-choice answer the student selected
- `StudentExplanation` - A student's explanation for choosing a specific multiple-choice answer
- `Category` - [train only] A classification of the relationship between a student's multiple-choice answer and their explanation (e.g., True_Misconception, which indicates a correct multiple-choice answer selection accompanied by an explanation that reveals a misconception)
- `Misconception` - [train only] The math misconception identified in the student's explanation for answers. Only applicable when Category contains a misconception, otherwise is 'NA'

## :handshake: Contact

Author: Martin Ho

Project Link: [Github](https://github.com/minimartzz/math-misunderstandings)

<!-- Acknowledgments -->

## :gem: Acknowledgements

- [Kaggle Competition Link](https://www.kaggle.com/competitions/map-charting-student-math-misunderstandings/overview)
