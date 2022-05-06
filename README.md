# 台大工學院碩士論文模板（NTU Master Thesis Template Revision）
> Reference from: [Hsin's GitHub Repo / NTU-Thesis-LaTeX-Template](https://github.com/Hsins/NTU-Thesis-LaTeX-Template)
- Get Updated Template from 
  - [Overleaf]()
  - [GitHub](https://github.com/yihanYozikua/ntu_master_thesis_template_latex)

## How to Use
1. Download from GitHub (via *Download button* or *command*)
2. 

## 需要修改的參數
### 語言設定
- 修改 `main.tex` #9 `language` 參數

### 封面
- 修改 `ntusetup.tex` 的內容

### 致謝
- 請寫上你想感謝的人事物動物

### 摘要/Abstract
- 關鍵字：修改 `ntusetup.tex` 的 `keywords` 和 `keywords*` 參數

### 目錄/圖目錄/表目錄
- 理論上沒東西要改，會自己生成

### 符號列表
- 在 `denotation.tex` 中新增以下
  ```tex
  \item[符號]{
    符號解釋...
  }
  ```

### 正文：第一章 ～ 第五章
- 分別在 `contents/chapter01.tex`~`contents/chapter05.tex`
- 以下列方式分層
  ```tex
  \section{Image Preprocessing}
  1.1
  \subsection{Dilation}
  1.1.1
  \subsubsection{Dilation with Deep Learning Based Methods}
  1.1.1.1
  ```
#### 插入表格
- 只要在內文的任何地方生成表格，就會自動按照順序被加入到表目錄中，不用自己新增
- 表格新增方法
  ```tex
  % 其中一種表格生成方式 begin
  \begin{tabular}{|c|c|}
  \hline
  a & b \\\hline
  c & d \\\hline
  e & f \\\hline
  \hline
  \end{tabular}
  % 其中一種表格生成方式 end

  % 表格標題 begin
  \captionsetup{type=table}
  \captionof{table}{表格名稱}\label{tbl:自訂表格編號名稱}
  % 表格標題 end
  ```
- 表格新增方法舉例
  ```tex
  % 其中一種表格生成方式 begin
  \begin{tabular}{|c|c|}
  \hline
  a & b \\\hline
  c & d \\\hline
  e & f \\\hline
  \hline
  \end{tabular}
  % 其中一種表格生成方式 end

  % 表格標題 begin
  \captionsetup{type=table}
  \captionof{table}{test table 2}\label{tbl:test_table_2}
  % 表格標題 end
  ```
- 表格引述方法
  ```tex
  \ref{tbl:剛剛自訂的表格編號名稱}
  ```
#### 插入圖片
- 加入圖片
  ```tex
  \begingroup
  \centering
  \begin{graphicx}
  \includegraphics{figures/seal.pdf}
  \end{graphicx}
  \captionsetup{type=figure}
  \captionof{figure}{test figure 1}\label{fig:test_fig_1}
  \endgroup
  ```
- 引述圖片
  ```tex
  \ref{fig:剛剛訂定的圖片編號名稱}
  ```
#### Citation
- 先去 `back/references.bib` 新增citation（內容應該通常可以直接在paper網站上面複製）
  - bibtex 格式的 citation 可以從 [Google Scholar](https://scholar.google.com.tw/)/引用/BibTex 找到
  ```bib
  @article{isensee2021nnu,
    title={nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation},
    author={Isensee, Fabian and Jaeger, Paul F and Kohl, Simon AA and Petersen, Jens and Maier-Hein, Klaus H},
    journal={Nature methods},
    volume={18},
    number={2},
    pages={203--211},
    year={2021},
    publisher={Nature Publishing Group}
  }
  ```
- 再到要引述的地方輸入以下
  ```te區
  \cite{isensee2021nnu}
  ```
### 附錄
- 修改 `back/appendix*.tex`

## 檔案說明
```bash
├── back
│   ├── appendix-*.tex              // 附錄
│   ├── references.bib              // 參考文獻
│   └── ...
├── contents
│   ├── chapter-*.tex               // 論文內容
│   └── ...
├── figures
│   └── ...
├── fonts
│   ├── chinese
│   │   ├── BiauKai.ttf             // 標楷體
│   │   └── ...
│   └── english
│       ├── Times New Roman-*.ttf   // Times New Roman 字體
│       └── ...
├── front
│   ├── abstract.tex                // 摘要
│   ├── acknowledgement.tex         // 致謝
│   └── denotation.tex              // 符號列表
├── main.tex                        // 主文件
├── ntusetup.tex                    // 模板設定
├── ntuthesis.cls                   // 模板文件
└── ...
```