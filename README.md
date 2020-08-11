# nycr_meetup_talk

## That Feeling of Workflowing 20200810

  * [Video](https://www.youtube.com/watch?v=jU1Zv21GvT4)
  * [Slides](https://docs.google.com/presentation/d/18tEfBymtD50g3gTM2s2hfdRaoJTXRSohRSJxHb-FgU4/edit?usp=sharing)
  
## Demo Stuff

* [Original Stat 545 makfile example](https://stat545.com/automating-pipeline.html#the-final-makefile)
* [Live coded drake graph](https://github.com/MilesMcBain/nycr_meetup_talk_code)
* [{drake}](https://github.com/ropensci/drake)
* [{dflow}](https://github.com/milesmcbain/dflow)
* [{fnmate}](https://github.com.milesmcbain/fnmate)

### Keybindings

#### rstudio_bindings.json

in `~/.R/rstudio/keybindings/rstudio_bindings.json`:

```
{
    "activateTerminal": "Ctrl+3",
    "insertAssignmentOperator": "Ctrl+'",
    "insertPipeOperator": "Ctrl+Shift+'",
    "goToDefinition": "Ctrl+Shift+J"
}

```

#### addins.json

in `~/.R/rstudio/keybindings/addins.json`:

```
{
    "fnmate::rs_fnmate": "Ctrl+Shift+F",
    "drake::rs_addin_r_make": "Ctrl+M",
    "drake::rs_addin_loadd": "Ctrl+L",
    "shrtcts::shortcut_01": "Ctrl+P",
    "shrtcts::shortcut_02": "Ctrl+Shift+O",
    "shrtcts::shortcut_03": "Ctrl+T"
}
```

#### shrcts.yaml

using [{shrtcts}](https://github.com/gadenbuie/shrtcts).

in `~/shrtcts.yml`:

```
- Name: Source ./packages.R
  Binding: |
    cat(glue::glue('> source(\"./packages.R\")\n\n'))
    source("./packages.R")
  Interactive: true
- Name: Output symbol at cursor
  Binding: |
    target <- mmmisc::rs_get_symbol_at_cursor(rstudioapi::getActiveDocumentContext())
    cat(glue::glue("> {target}\n\n"))
    eval(as.symbol(target))
  Interactive: true
- Name: Thead at symbol at cursor
  Binding: |
    target <- mmmisc::rs_get_symbol_at_cursor(rstudioapi::getActiveDocumentContext())
    eval(parse(text = glue::glue("t(head({target}))")))
  Interactive: true

```

### QA Stuff:

* [{drake} manual](https://books.ropensci.org/drake/)
* [Will Landau's rOpenSci community call](https://ropensci.org/commcalls/2019-09-24/)
* {drake} for new R users? I didn't give a good answer to this in the talk. Like I mention in ['The {drake} post'](https://milesmcbain.xyz/the-drake-post/):

> Building comfort with writing functions by forcing yourself to do it more often would be a great stepping stone to a workflow like this.

Anyone know any good resources for learning how to make R functions?

