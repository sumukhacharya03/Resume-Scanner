# 📄 Resume Scanner

> *Because manually checking if your resume matches a job description is so 2010...*

## What is this Project all about?

Resume Scanner is a Java application that analyzes your resume against job descriptions to see if you're a good match. It extracts skills from both documents, calculates match percentages, and generates a detailed report with recommendations. Now you can find out why you're getting ghosted by recruiters before you even apply! 

## Why I chose Java?

I chose Java for this project because:
1. **Cross-platform compatibility** - Works on Windows, Mac, Linux (recruiters use all kinds of systems!)
2. **Rich UI libraries** - Swing makes it easy to create a simple but functional interface
3. **PDF processing libraries** - Apache PDFBox handles the complex task of extracting text from PDFs
4. **Object-oriented design** - Perfect for modeling the different components of resume analysis
5. **Learning opportunity** - Great way to practice Java's design patterns in a real-world application

## Project Structure

| Class | Description |
|-------|-------------|
| `ResumeScannerApp` | Entry point of the application that launches the UI |
| `MainUI` | The graphical user interface for uploading resumes and displaying results |
| `MainController` | Orchestrates the resume scanning process and database operations |
| `ResumeParser` | Extracts text and information from PDF resumes using Apache PDFBox |
| `KeywordAnalyzer` | Identifies and matches keywords between resumes and job descriptions |
| `ReportGenerator` | Creates formatted reports based on the analysis results |
| `DBConnection` | Manages database connections for storing report data |
| `ResumeData` | Data model class that stores parsed resume information and match statistics |
| `Report` | Simple model class for storing report content and file location |

## Workflow

1. **Input**: User selects a resume PDF file and enters a username
2. **Processing**:
   - Resume is parsed using Apache PDFBox to extract text
   - Job description is loaded from a predefined file
   - Skills are extracted from both documents
   - Matching is performed for both required and preferred skills
   - A weighted score is calculated (75% required skills, 25% preferred skills)
   - Report is generated with detailed matching information
3. **Output**:
   - A formatted report is displayed in the application
   - Report is saved to disk for future reference
   - Basic information is stored in a database

## Report Generation Logic

The application generates a detailed report showing:
- Candidate details (name, email extracted from resume)
- Job description details (title, company, location)
- Required skills match percentage with lists of matched and missing skills
- Preferred skills match percentage with lists of matched and missing skills
- Weighted match score combining both required and preferred skills
- Final recommendation based on the weighted score:
  - ≥80%: STRONG MATCH - RECOMMENDED
  - ≥60%: GOOD MATCH - WORTH CONSIDERING
  - ≥40%: MODERATE MATCH - REVIEW FURTHER
  - <40%: LOW MATCH - NOT RECOMMENDED


## 🛠️ How to Run the Project

1. **Navigate to the project directory**:
   ```bash
   cd path/to/ResumeScanner
   ```
2. **Run the build script**:
   ```bash
   ./build.sh
   ```
   Make sure  build.sh has executable permissions. If not, run:
   ```bash
   chmod +x build.sh
   ```


## Future Work

-  **Improved name extraction**: Enhance the algorithm to better identify names in various resume formats
-  **Custom job descriptions**: Allow users to upload or paste job descriptions instead of using a predefined file
-  **More file formats**: Support for Word documents, plain text, and HTML resumes
-  **Detailed skill analysis**: Add visualization of skill matches with strength indicators
-  **ATS simulation**: Add features to simulate how ATS systems might score the resume
-  **Job recommendation**: Suggest which skills to add to improve match percentages
-  **Cloud storage**: Store reports online for access from multiple devices
-  **Browser extension**: Create a browser extension to analyze job postings on popular job sites
-  **API service**: Create a RESTful API to allow other applications to use the scanning functionality

## Acknowledgements

- Apache PDFBox for PDF parsing capabilities
- All the recruiters who never told me why I didn't get the job
