# forwardspres format

This is a Quarto Revealjs presentation format that is consistent with the [Forwards](https://forwards.github.io) brand.

It offers the following:

- A Forwards hex on the title slide
  - Note that this is a variation of the usual hex. That one has a gradient border, but since that blends into the title slide background, here we use a hex with a solid pink border instead.
- A theme consistent with colours in the Forwards logo (the [viridis magma palette](https://cran.r-project.org/web/packages/viridis/vignettes/intro-to-viridis.html)), including an inverse class
- The [Atkinson Hyperlegible](https://www.brailleinstitute.org/freefont/) font family. Atkinson Hyperligible Next for body text and headings and the Atkinson Hyperlegible Mono for code
- Custom colours for quarto callouts
- A custom syntax highlighting theme consistent with the theme colours
- Additional convenience classes for sizing and aligning

It is an adaptation of [warwickpres](https://Warwick-Stats-Resources/warwickpres) (both developed by [Ella Kaye](https://github.com/EllaKaye))

## Installing forwardspres

```bash
quarto use template forwards/forwardspres
```

This will install the extension and create an example `.qmd` file that you can use as a starting place for your presentation. This also serves as documentation.

## Workflow for using this extension in [positron](https://positron.posit.co)

This is my preferred workflow for using the template and forwardspres extension:

1. In positron, open a new folder, which is where the template and extension will go
2. In the terminal, run

```bash
quarto use template forwards/forwardspres
```

3. When prompted, type 'Y' to trust the authors of the template
4. When prompted, type 'N' to **not** create a subdirectory
5. When prompted, type 'Y' to install the forwardspres extension

## Workflow for using this extension in RStudio

I have found it a bit fiddly to get this working with RStudio projects.
The following workflow works well for me. There may be a other/better ways.

When you want to start a new project with the template:

1. Close the current project (if one is open).
2. In the RStudio terminal, navigate to the parent directory in which you want to save the project
3. Run the following:

``` bash
quarto use template forwards/forwardspres
```

4. When prompted, type 'Y' to trust the authors of the template
5. When prompted, type 'Y' to create a subdirectory, then enter the directory name
5. When prompted, type 'Y' to install the forwardspres extension
5. In RStudio Files pane (or other file navigator), go to the directory just created
6. The directory should contain `"forwardspres.Rproj"`. Click on that to launch the project.
    - If you have lots of directories from the same extension, may want to rename the .Rproj file to something unique, e.g. to share the directory name (to make file search easier)

## Workflow for using with git/GitHub/gh-pages

This works in both RStudio and positron, and uses the [usethis](https://usethis.r-lib.org) R package.

Before using this workflow for the first time, check that you have git set up to use 'main' as the default branch.

1. Run `usethis::git_sitrep()` and check that the default initial branch name is 'main'
2. If it not 'main', change the configuration by running `usethis::use_git_config(init.defaultBranch = "main")`

For each new presentation:

1. In the RStudio console, run `usethis::use_git()` and follow through the prompts
2. After restarting as prompted, run `usethis::use_github()`
3. You may want to add a README.md at this point
4. Work in the `.qmd` file created in the directory, which will share a name with the directory
5. Commit, push, etc as often as you wish!
6. When the presentation is ready to publish, run `quarto publish gh-pages` in RStudio terminal. 
    - This creates a `gh-pages` branch, and the website https://USER.github.io/REPO (where USER is your GitHub username and REPO is the name of the repository).
7. Keep working in `main` branch. When ready to publish again, run `quarto publish gh-pages`. This brings `gh-pages` branch in sync with `main`. Repeat as often as need be. You could also use a GitHub Action to update the published version on each push, as per this [quarto documentation](https://quarto.org/docs/publishing/github-pages.html#github-action).

I have documented an R -> positron/RStudio -> git/GitHub workflow because that's what I use. 
Quarto also works well in other IDEs, especially VSCode, and with other programming languages, 
so of course feel free to adapt this workflow for your use case.

In positron, you can also use the built-in 'Source Control' pane to set up git and GitHub (rather than the usethis R package).

## Example

Here is the source code for a minimal sample document: [template.qmd](template.qmd)

And here it is online: <https://forwards.github.io/forwardspres>

These files together demonstrate what the forwardspres extension offers and how to use it.

