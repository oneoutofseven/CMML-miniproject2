\section*{CMML-miniproject2}

\subsection*{Overview}

This project systematically evaluates the performance of \textbf{scDblFinder} for doublet detection in single-cell RNA-seq data, and benchmarks it against \textbf{DoubletFinder} and \textbf{Scrublet} across multiple datasets, including both simulated and real data.

\subsection*{Project Structure}
\begin{itemize}
  \item \texttt{/analysis/} -- Main analysis scripts for doublet detection on PBMC dataset.
  \item \texttt{/benchmark/} -- Benchmarking scripts and pre-computed results.
  \item \texttt{misc.R} -- Utility functions.
  \item \texttt{/dataset/} -- Input datasets (e.g., \texttt{pbmc.rds}, \texttt{GSM2560248\_noAmbiguous.processed.CD.rds}).
\end{itemize}

\subsection*{Environment and Dependencies}

Please install the following R packages:
\begin{itemize}
  \item Seurat (\textbf{v4.4.0} recommended)
  \item scDblFinder
  \item SingleCellExperiment, scran, scater, splatter
  \item PRROC, igraph, cowplot, plotly
\end{itemize}

\textbf{Important:} To ensure compatibility, Seurat v4 is required. If you already have Seurat v5 or other versions installed, reinstall v4 as follows:
\begin{verbatim}
remove.packages(c("Seurat", "SeuratObject"))
install.packages('Seurat', repos = c('https://satijalab.r-universe.dev'))
packageVersion("Seurat")
\end{verbatim}

\subsection*{How to Use}

\textbf{Recommended:}
\begin{itemize}
  \item Clone the repository using Git (due to Git LFS large files):
\begin{verbatim}
git clone https://github.com/oneoutofseven/CMML-miniproject2.git
\end{verbatim}
\end{itemize}

\textbf{Alternative:}
\begin{itemize}
  \item If manually downloading from GitHub, please also download necessary datasets from the \textbf{Release} page:
  \begin{itemize}
    \item Place \texttt{pbmc.rds} into \texttt{analysis/dataset/}.
    \item Place \texttt{cline-ch.rds} into \texttt{benchmark/datasets/}.
  \end{itemize}
\end{itemize}

\subsection*{Execution Steps}

\begin{enumerate}
  \item Open and run \texttt{analysis/scDblFinder.Rmd} to reproduce doublet detection analysis and simulation evaluation.
  \item (Optional) Run \texttt{benchmark/benchmark.Rmd} to recompute benchmarking results (takes $\sim$2 hours).
  \item Alternatively, directly run \texttt{benchmark/benchmark\_figure.Rmd} to plot figures using pre-computed \texttt{benchmark.results.rds}.
\end{enumerate}

\subsection*{Quick Summary}

\begin{tabular}{|l|l|l|}
\hline
\textbf{File} & \textbf{Function} & \textbf{Run?} \\
\hline
\texttt{scDblFinder.Rmd} & PBMC dataset analysis & Required \\
\texttt{benchmark.Rmd} & Full benchmark recomputation & Optional (slow) \\
\texttt{benchmark\_figure.Rmd} & Plot benchmark figures & Recommended \\
\hline
\end{tabular}

\subsection*{References}

\begin{itemize}
\item Germain, P.L., Lun, A.T.L., Meixide, C.G., Macnair, W., and Robinson, M.D. (2022).\\
\textit{Doublet identification in single-cell sequencing data using scDblFinder}. F1000Research, 10, 979. \href{https://doi.org/10.12688/f1000research.55869.1}{DOI:10.12688/f1000research.55869.1}
\end{itemize}

