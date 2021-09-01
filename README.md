# latex-build-pdf-cicd
CI/CD to build Latex pdf and create a release in GitHub. The workflow triggers on push to the repository. Integrates with Overleaf.

## Why this pipeline?

The CI/CD pipeline integrates with Overleaf's GitHub commit. The automatic building and hosting of the file under static URL help sharing the latest version with peers or academic advisors. This automation cuts the cycle of manual download from Overleaf and uploading to the hosting service.

## How to use

1. Edit root LaTeX file and working directory in `compile.yml` (currently `main.tex` and `LaTeX`).
2. Edit correspond file and folder names in the `Rename pdf` step (currently `run: mv LaTeX/main.pdf LaTeX/Thesis.pdf`).
3. Move `compile.yml` to the `.github/workflows/` folder in your repository.
4. Push LaTeX files to the repository.
5. Upon a successful build, the compiled pdf is released under the `latest` tag.

## Including graphics

Appending graphics need to be referred to concerning the root folder. For example, including file `VirtualizationTypes.pdf` in path `LateX/images/VirtualizationTypes.pdf` should be referred as follows:

    \begin{figure}[ht]
      \begin{center}
        \includegraphics[width=13.5cm]{images/VirtualizationTypes.pdf}
        \caption{Physical server and two types of virtualization}
        \label{fig:VirtualizationTypes}
      \end{center}
    \end{figure}

## Resources

For more resources about the usage, check my [Thesis repository](https://github.com/markkuleppala/Thesis).
