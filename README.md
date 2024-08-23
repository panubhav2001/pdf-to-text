# Voter Information Extraction Solution

## Introduction

This project focuses on extracting structured voter information from text data derived from PDF files. The main goal is to capture details such as the voter's name, relative's name, relation type, and house number. This document outlines the process followed, challenges faced, and the solutions implemented.

## Process Overview

### 1. Initial Analysis

- **Data Examination**: The text data extracted from the PDF exhibited significant format variations. This variability made it challenging to create consistent extraction patterns.
- **Key Elements**: The primary data points to extract are:
  - Names
  - Relation types (e.g., "Father," "Husband")
  - House numbers

### 2. Developing Initial Regex Patterns

- **Patterns Created**:
  - **Names**: Extracting text following keywords such as "Name" or "Husband's Name."
  - **Relations**: Identifying specific relation types like "Father" or "Husband."
  - **House Numbers**: Capturing numeric sequences often labeled as "House No."

### 3. Challenges and Solutions

- **Libraries Not Able to Read PDF**:
  - **Challenge**: Traditional libraries could not extract text from the given PDF.
  - **Solution**: Used the `pdf2image` library to convert PDFs to images, followed by `pytesseract` to extract text from these images.

- **Inconsistent Formats**:
  - **Challenge**: Variations in name and relation formats, with some names preceded by titles or additional descriptors.
  - **Solution**: Refined regex patterns to handle these variations using optional groups and alternatives.

- **Missing Data**:
  - **Challenge**: Some house numbers and relations were not captured due to varied formats.
  - **Solution**: Adjusted patterns to be more inclusive, accommodating different ways house numbers and relation labels were presented.

### 4. Refining Regex Patterns

- **Names**: Modified patterns to better capture names, including cases where names were not directly after keywords.
- **Relations**: Focused patterns to extract only "Father" and "Husband," excluding unrelated terms.
- **House Numbers**: Improved patterns to reliably capture numeric sequences and handle various formatting issues.

### 5. Testing and Validation

- **Testing**: Refined regex patterns were tested with a variety of text samples to check for accuracy and consistency.
- **Validation**: Verified that each pattern correctly extracted and formatted the required data.

### 6. Final Implementation

- **Integration**: Final regex patterns were integrated into the extraction process, ensuring data was organized into separate columns for each information type: voter's name, relative's name, relation type, and house number.
- **Cleaning and Validation**: Implemented additional steps to clean and validate the extracted data.

## Conclusion

The development of this voter information extraction solution involved addressing diverse text formats, refining regex patterns, and conducting thorough testing to ensure accuracy. While the final output showed room for improvement, this project has significantly enhanced skills in text processing and pattern matching, valuable for data extraction and analysis tasks.

## Dependencies

- `pdf2image`
- `pytesseract`
- `re` (Regex library)
- `pandas`



For further details on implementation, refer to the project's source code and documentation.

