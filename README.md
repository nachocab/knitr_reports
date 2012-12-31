# knitr_reports

knitr_reports is a collection of files that make it easier to generate reports with [knitr][]. You can see what they look like [here][live_sample_report] and [here][live_basic_usage]

I like to work with Rmarkdown files because they have less cruft than other formats. My workflow involves converting .Rmd files to .md files, and then converting those to HTML files with embedded images. Using embedded images means that when I email a report, I don't have to also attach individual images.

I use a [custom snippet][new_report_snippet] to start every report with the following:

```md
    ---

    ```{r global_setup, echo=FALSE, cache=FALSE, warning=FALSE}

        opts_chunk$set(cache=FALSE, cache.path='cache/my_report/', fig.path='figure/my_report/', autodep=TRUE, fig.cap="", fig.width=7, fig.height=7, echo=FALSE, warning=FALSE, message=FALSE)
        dep_auto()

    ```

    # My Report
```

The `---` allows me to separate the table of contents from the rest of the report.

In global_setup chunk I set opts_chunk for all following chunks
    * defaults: no cache, fig dim,
    * directory structure
    * dep_auto

You can move the `rmd_sublime_snippets` folder to the Sublime Text Packages folder, but to use the `Rmd.sublime-build` file, you will have to update the path to `update_report_index` to your own path:

```
    "cmd": ["YOUR_PATH/knitr_reports/bin/update_report_index", "$file", "$file_base_name"],
```

## Create report
To create a new report use the `nr+tab` snippet, name the subfolder name you will give to your project (for example, `my_report`) and start writing. When you're ready to see the final output, compile your Rmd file using `Tools | Build` or press `Cmd+B`. You should see the progress of your compilation in the console `Tools | Build Results | Show build results` (I have it mapped to F11).

## View report
If there were no errors, it will generate the compiled `md` file, the converted `html` file, it will update the `index.html` file, and optionally, it will create the `figure` and `cache` folders. You can open the `index.html` file in Chrome or Firefox and see the list of reports in your current folder listed by descending modification date.

Each report will use `stylesheets/report.css` (feel free to customize it) and will include a table of contents at the top.

## Contributions
I would love to get some help, just send me a message.

## TO DO

* make renaming reports easier.

[knitr]: http://yihui.name/knitr/        "knitr"
[live_sample_report]: http://htmlpreview.github.com/?https://github.com/nachocab/knitr_reports/blob/master/example_reports/sample_report.html
[live_basic_usage]: http://htmlpreview.github.com/?https://github.com/nachocab/knitr_reports/blob/master/example_reports/basic_usage.html
[new_report_snippet]: https://github.com/nachocab/knitr_reports/blob/master/Rmd/new_report.sublime-snippet


