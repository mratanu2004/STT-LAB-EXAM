Step 1: Document Setup
latex
Copy code
\documentclass{article}
\usepackage{graphicx}
\usepackage{caption}
\usepackage{subcaption}
\usepackage{multirow}
Explanation:
\documentclass{article} sets the document type to an article.
\usepackage{graphicx} allows you to include images (though not used directly in this table).
\usepackage{caption} and \usepackage{subcaption} are for formatting captions for tables or images.
\usepackage{multirow} is essential here since it allows you to merge cells vertically in the table.
Step 2: Begin the Document
latex
Copy code
\begin{document}
Explanation:
This marks the start of the actual content of your LaTeX document. All the content that follows, including the table, will be rendered in the output.
Step 3: Start the Table Environment
latex
Copy code
\begin{table}[h!]
    \centering
Explanation:
\begin{table}[h!] starts the table environment. The [h!] option forces the table to appear at the current position in the document.
\centering centers the table on the page.
Step 4: Define Table Structure
latex
Copy code
\begin{tabular}{|c|c|c|c|c|c|}
Explanation:
The \begin{tabular} environment is used to create the table.
The part |c|c|c|c|c|c| defines 6 columns, where:
Each c means center-aligned content.
Each | inserts a vertical line between the columns, giving the table borders.
Step 5: Create Header with Merged Rows
latex
Copy code
\multirow{2}{*}{\textbf{S.No}} & \multirow{2}{*}{\textbf{USN}} & \multirow{2}{*}{\textbf{StudentName}} & \multicolumn{3}{c|}{\textbf{Marks}} \\ \cline{4-6}
Explanation:
\multirow{2}{*} is used to merge the cells for S.No, USN, and StudentName across two rows (because they span two rows in the final table).
\multicolumn{3}{c|}{Marks} merges three columns to create one header "Marks" across the subjects.
\cline{4-6} creates a horizontal line across columns 4, 5, and 6 (subject marks) to separate the "Marks" header from the individual subjects.
Step 6: Create Subject-Specific Headers
latex
Copy code
& & & \textbf{Subject1} & \textbf{Subject2} & \textbf{Subject3} \\ \hline
Explanation:
This creates headers for each subject (Subject1, Subject2, Subject3).
The & & & is used to skip the first three columns because these cells have already been merged in the previous step.
\hline creates a horizontal line separating the header from the data rows.
Step 7: Insert Data Rows
latex
Copy code
1 & 4XX22XX001 & Name1 & 89 & 60 & 90 \\ \hline
2 & 4XX22XX002 & Name2 & 78 & 45 & 98 \\ \hline
3 & 4XX22XX003 & Name3 & 67 & 55 & 59 \\ \hline
Explanation:
These are the actual data rows for the students.
Each entry is separated by &, and each row ends with \\.
For each row, you have:
S.No (e.g., 1, 2, 3)
USN (e.g., 4XX22XX001)
StudentName (e.g., Name1)
Marks for Subject1, Subject2, Subject3 (e.g., 89, 60, 90)
\hline draws a horizontal line after each row.
Step 8: Close the Table and Document
latex
Copy code
\end{tabular}
    \label{tab:marks}
\end{table}
\end{document}
Explanation:
\end{tabular} closes the table structure.
\label{tab:marks} adds a label to the table, allowing you to reference it elsewhere in the document if needed.
\end{table} ends the table environment.
\end{document} marks the end of the LaTeX document.
