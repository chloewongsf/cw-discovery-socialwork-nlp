# cw-discovery-socialwork-nlp
Analyzing public comments on CMS's proposed nursing home staffing rule using NLP methods such as TF-IDF vectorization and cosine similarity.

---

## Overview
This project explores how various data science techniques can be used to analyze public comments submitted during the rulemaking process for the Centers for Medicare & Medicaid Services (CMS) proposed staffing rule for nursing homes. The work presented here represents **my individual contributions** to a larger team project. My personal objectives focused on identifying comments that adhered to a specific template provided by the National Association of Social Workers (NASW) and analyzing additional content added by commenters.

---

## Objectives
As part of the team, I focused on the following individual objectives:
1. **Identify Template Matches**:
   - Use TF-IDF vectorization and cosine similarity to detect comments that follow the NASW-provided template.
2. **Analyze Additional Content**:
   - Separate template-matching comments into exact matches and those with additional unique content such as personal anecdotes or professional insights.
3. **Provide Actionable Insights**:
   - Summarize public sentiment and key additions to the template for better policymaker understanding.

---

## Methods
### Data Preprocessing
- **Cleaning Comments**: Removed whitespace, punctuation, and converted all text to lowercase for consistency.
- **Handling Missing Data**: Filled missing comments with empty strings.
- **Normalization**: Tokenized text and removed non-ASCII characters.

### Analysis
1. **TF-IDF Vectorization**:
   - Transformed public comments and the NASW template into numerical representations.
2. **Cosine Similarity**:
   - Measured the similarity between each comment and the template.
   - Used thresholds (e.g., 0.8 for close matches and 0.6 for any potential misses) to classify comments.
3. **Comment Categorization**:
   - Categorized comments into:
     - **Exact Matches**: Comments identical to the template.
     - **Additional Content Matches**: Comments with added unique content, such as personal experiences or advocacy insights.

### Challenges and Solutions
- Early attempts using **FuzzyWuzzy** and **NLTK tokenization** struggled with variability in comment structure and lacked contextual nuance.
- TF-IDF with cosine similarity provided a scalable and accurate approach, allowing for both precision and flexibility in matching.

---

## Project Structure
### Data
The following files are located in the `data/` folder:
- **bin_data_from_jupyter.xlsx**:
  - **Sheet 1**: `All_Comments` - The complete dataset of public comments processed during the project.
  - **Sheet 2**: `Cleaned_Comments` - Public comments after preprocessing steps such as text normalization and punctuation removal.
  - **Sheet 2**: `Template_Matches_0.8_Threshold` - Comments that matched the NASW template with a cosine similarity score of 0.8 or higher.
  - **Sheet 2**: `Non_Template_Matches` - Comments that did not meet the 0.8 cosine similarity threshold for matching the NASW template.
  - **Sheet 2**: `Potential_Matches_0.6_Threshold` - Comments that matched the NASW template with a relaxed cosine similarity threshold of 0.6 to capture partial matches.
  - **Sheet 2**: `Exact_Matches` - Comments that perfectly matched the NASW template without any additional content.
  - **Sheet 2**: `Additional_Content_Matches` - Comments that followed the NASW template but included unique personal anecdotes, insights, or advocacy recommendations.
- If you'd like to preview the data, you can download the `.xlsx` file and view it locally using Excel or any spreadsheet software.

### Code
The `code/` folder contains:
- **analysis.ipynb**: A Jupyter Notebook detailing the full workflow, including data cleaning, TF-IDF vectorization, and cosine similarity analysis.

### Outputs
- **Structured Data Files**: 
  - Analyzed and categorized public comments saved in Excel sheets, with classifications such as exact matches, additional content, and cleaned comments.
  - Excel files organized into meaningful sheets for easy interpretation and further analysis.
- **Future Work**:
  - A detailed analysis of comments containing additional content, such as personal anecdotes and professional insights.
  - Identification of recurring themes in these unique contributions to better understand public sentiment and advocacy priorities.
  - Exploration of how this additional content may influence policy-making decisions, especially regarding nursing home staffing standards.
 
These structured files provide a comprehensive summary of the project outcomes, making it easy to replicate or build upon the analysis.

---

## How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/chloewongsf/cw-discovery-socialwork-nlp.git
