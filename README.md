# knitr_reports

knitr_reports is a collection of files that make it easier to generate reports with [knitr][]. You can see what they look like [here][live_sample_report] and [here][live_basic_usage]

You can move the `rmd_sublime_snippets` folder to the Sublime Text Packages folder, but to use the `Rmd.sublime-build` file, you will have to update the path to `update_report_index` to your own path:

```
    "cmd": ["YOUR_PATH/knitr_reports/bin/update_report_index", "$file", "$file_base_name"],
```

## Create report
To create a new report use the `nr+tab` snippet, name the subfolder name you will give to your project (for example, `my_report`) and start writing. When you're ready to see the final output, compile your Rmd file using `Tools | Build` or press `Cmd+B`. You should see the progress of your compilation in the console `Tools | Build Results | Show build results` (I have it mapped to F11).

## View report
If there were no errors, it will generate the compiled `md` file, the converted `html` file, it will update the `index.html` file, and optionally, it will create the `figure` and `cache` folders. You can open the `index.html` file in Chrome or Firefox and see the list of reports in your current folder listed by descending modification date.

Each report will use `stylesheets/report.css` and will include a table of contents at the top.

[knitr]: http://yihui.name/knitr/        "knitr"
[live_sample_report]: http://htmlpreview.github.com/?https://github.com/nachocab/knitr_reports/blob/master/example_reports/sample_report.html
[live_basic_usage]: http://htmlpreview.github.com/?https://github.com/nachocab/knitr_reports/blob/master/example_reports/basic_usage.html



