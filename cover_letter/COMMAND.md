# Commands 
Bash commands to create documents via `pandoc`.

## Command to create `Creating a sense of urgency`

To create `Creating_a_sense_of_urgency.tex` from `Creating_a_sense_of_urgency.md`. 
```bash
pandoc -t latex Creating_a_sense_of_urgency.md -o Creating_a_sense_of_urgency.tex

```

To create `Creating_a_sense_of_urgency.pdf` from `Creating_a_sense_of_urgency.tex` using `pandoc`. 
```bash
pandoc Creating_a_sense_of_urgency.tex -V geometry:margin=1in -V fontsize:12pt -o Creating_a_sense_of_urgency.pdf
```
