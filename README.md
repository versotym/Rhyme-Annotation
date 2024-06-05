# Rhyme-Annotation
Data for talk "Gold Standard Annotations for Rhyme Detection" (DH2024).

These JSONs contain random samples from poetry corpora in 5 languages (Czech, German, English, French, and Russian) and a manual annotation of rhymes provided by two different annotators for each language.

Structure of each file is as follows:

```
[
  {   # poem
    "text": [   # text of the poem
      [str:1st_line_of_the_poem, int:stanza_id],
      [str:2nd line of the poem, int:stanza id],
      ...
    ],
    "annot1": [   # annotation of the poem by annotator 1
      list:rhyme_group_1, # zero-based indices of lines that rhyme together 
      list:rhyme_group_2,
      ...
    ],
    "annot2": [   # annotation of the poem by annotator 2
      list:rhyme_group_1, # zero-based indices of lines that rhyme together 
      list:rhyme_group_2,
      ...
    ]  },
  ...

]

```

Thus. e.g. a sonnet:
```
Night, welcome art thou to my mind destrest
Darke, heavy, sad, yett nott more sad then I
Never could'st thou find fitter company
For thine owne humor then I thus oprest.

If thou beest dark, my wrongs still unredrest
Saw never light, nor smalest bliss can spy;
If heavy, joy from mee too fast doth hy
And care outgoes my hope of quiett rest,

Then now in friendship joine with haples mee,
Who ame as sad, and dark as thou canst bee
Hating all pleasure, or delight of lyfe;

Silence, and griefe, with thee I best doe love
And from you three, I know I can nott move,
Then lett us live companions without strife.
```

(should both annotator agree upon that rhymes go as ABBA ABBA CCD EED) would be encoded as:

```

  {   
    "text": [   
      ["Night, welcome art thou to my mind destrest", 0],
      ["Darke, heavy, sad, yett nott more sad then I", 0],
      ["Never could'st thou find fitter company", 0],
      ["For thine owne humor then I thus oprest.", 0],
      ["If thou beest dark, my wrongs still unredrest", 1],
      ["Saw never light, nor smalest bliss can spy;", 1],
      ["If heavy, joy from mee too fast doth hy", 1],
      ["And care outgoes my hope of quiett rest,", 1],
      ["Then now in friendship joine with haples mee,", 2],
      ["Who ame as sad, and dark as thou canst bee", 2],
      ["Hating all pleasure, or delight of lyfe;", 2],
      ["Silence, and griefe, with thee I best doe love", 3],
      ["And from you three, I know I can nott move,", 3],
      ["Then lett us live companions without strife.", 3]
    ],
    "annot1": [  
      [0, 3, 4, 7],
      [1, 2, 5, 6],
      [8, 9],
      [10, 13],
      [11, 12]
    ],
    "annot2": [   
      [0, 3, 4, 7],
      [1, 2, 5, 6],
      [8, 9],
      [10, 13],
      [11, 12]   
    ]
  }
 
```
