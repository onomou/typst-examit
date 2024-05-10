# examit

An exam template based on the MIT LaTeX [exam](https://ctan.org/pkg/exam)

## Features

- Grading table
- Grading boxes
- Different first page or title block
- Configure even/odd headers/footers
- Read questions from file/question bank
- Question types
  - Standard answerline
  - Multiple choice (including true-false)
  - Writing box
  - Blank rectangular and polar graphs

## Usage

`main.typ`
```typst
#import "@preview/examit:0.1.0": *
#import "questions.typ": questions

#show: examit.with(
  margin: (
    left: 18mm,
    top: 17mm,
    // bottom: 12mm
    // right: 25mm
  ),
  cols: 2,
  gutter: 18mm,

  title: [Class Name\ Chapter X Test],
  date: "1990-01-01",
  questions: questions,
  // showdrawbox: false,
  dropboxes: true,
  // instructions: [#v(1mm)],
  // before: v(1in),
)
```

`questions.typ`
```typst
#let questions = (
  ("header": [Multiple Choice]),
  (
    "question": [What attributes #underline("must") a *vector* have?],
    "answer": "",
    "points": 2,
    "spacing": -1.4em,
    "choices": (
      [position],
      [magnitude],
      [direction],
      [x- and y-coordinates],
      // [height],
      [width],
    ),
  ),
  ("question": [$bold(sin^(-1))$ returns an angle in which quadrants?],
    "choices": ([I],[II],[III],[IV],),
    "spacing": -3.3em,
    "points": 2,
  ),
  (
    "question": [A *scalar* is a vector with a magnitude of *1*.],
    "tf": true,
    "points": 2,
  ),
  ( "break": true ),
  ("header": [Graphing]),
  (
    "question": [
      Simplify and graph the complex number\ $5(cos 15 degree + i sin 15 degree) dot 10(cos 5 degree + i sin 5 degree)$.
    ],
    "points": 3,
    "spacing": -1.5cm,
    "graph": "rect",
    "answerline": true,
  ),
  ("subheader": [A child is pulling a wagon with a force of 15 lb at an angle of 35° to the ground.
  Gravity is pulling down on the wagon with a force of 12 lb.]),
  (
    "question": [
      What is the resulting force vector?
    ],
    "points": 4,
    "spacing": 1cm,
  ),
  (
    "question": [
      Write this polar equation in rectangular form: $r = frac(5 ,cos theta + sin theta )$
    ],
    "points": 4,
    "bonus": true,
    "spacing": 1cm,
  ),
)
```

## To Do

- [ ] Parts or sub-questions

