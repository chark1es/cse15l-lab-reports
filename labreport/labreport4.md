# Lab Report 4 - Charles Nguyen

## Commands:

### Logging into ieng6:

```
ssh cse15lfa23cz@ieng6.ucsd.edu
```

### Cloning my forked Lab7 github repo:

```
git clone https://github.com/chark1es/lab7.git
```

![](screenshots/labreport4/before_vim.png)

### Using Vim to edit the file:

```
cd lab7
vim ListExamples.java
```

![](screenshots/labreport4/using_vim.png)

### Within Vim

I used these commands to get onto the line with the error

```bash
<G>
<UP>
<UP>
<UP>
<UP>
<UP>
<UP>
```

I used these commands to get to the typo labeled `index1`

```bash
<Right Arrow>
<Right Arrow>
<Right Arrow>
<Right Arrow>
<Right Arrow>
<Right Arrow>
<Right Arrow>
<Right Arrow>
<Right Arrow>
<Right Arrow>
<Right Arrow>
```

I used these commands to replace the `1` in `index1` to `2`.

```
<r>
<2>
```

![](screenshots/labreport4/fixing_error.png)

I used these commands to save the file

```
<ESC>
<:wq>
```

### Test Passed

![](screenshots/labreport4/passed_tests.png)
