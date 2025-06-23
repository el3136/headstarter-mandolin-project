### Task: Automate the Prior Authorization (PA) Form Filling Workflow

# Notable exmaple files:
- **Automate_Insurance_Claims_Week2_Abdulla_example1.mkv**
- **Week2_Automate_Insurance_Claims.ipynb**

# PAFill - Medical Form Automation

🏥 **Automate Prior Authorization Forms with AI-Powered Medical Information Extraction**

PAFill is a Streamlit-based application that uses Google's Gemini AI to automatically extract patient information from medical referral packages and fill out Prior Authorization (PA) forms, significantly reducing manual data entry time for healthcare professionals.

## ✨ Features

- **Intelligent Medical Information Extraction**: Automatically extracts patient demographics, medical history, diagnoses, medications, and clinical data from referral packages
- **Smart Form Field Mapping**: Uses AI to understand form context and map extracted information to appropriate fields
- **Multi-Step Processing Pipeline**: Breaks down the complex task into manageable steps with progress tracking
- **Interactive Review Interface**: Allows healthcare professionals to review and validate mappings before final form completion
- **High Accuracy Field Filling**: Supports text fields, checkboxes, and other form elements with confidence-based validation
- **Batch Processing**: Efficiently handles large forms with many fields through optimized batch processing

## 🚀 Quick Start

### Prerequisites

- Python 3.8+
- Google Gemini API key
- Streamlit

### Installation

1. **Clone or download the application files**
   ```bash
   # Save the app.py file from the provided code
   # Or download from your source
   ```

2. **Install required dependencies**
   ```bash
   pip install streamlit google-generativeai pymupdf
   ```

3. **Set up your Gemini API key**
   ```bash
   # Option 1: Environment variable
   export GEMINI_API_KEY="your_api_key_here"
   
   # Option 2: Enter directly in the app interface
   ```

4. **Run the application**
   ```bash
   streamlit run app.py
   ```

### For Google Colab

If running in Google Colab, use the provided cell structure:

```python
# Install dependencies
!pip install streamlit google-generativeai pymupdf

# Set up your API key
import os
os.environ['GEMINI_API_KEY'] = 'your_api_key_here'

# Run the app
!streamlit run app.py --server.port 8501 &
```

## 📋 Usage

### Step 1: Upload Documents
- **PA Form**: Upload the Prior Authorization form PDF that needs to be filled
- **Referral Package**: Upload the complete medical referral package containing patient information

### Step 2: Configure Settings
- **API Key**: Enter your Google Gemini API key if not set as environment variable
- **Review Mode**: Enable to review mappings before form filling (recommended)
- **Confidence Threshold**: Adjust the confidence level for automatic field filling

### Step 3: Process Forms
1. Click "🚀 Process and Fill Forms"
2. The application will:
   - Extract patient information from referral package
   - Analyze PA form fields and context
   - Map patient data to form fields
   - Validate mappings with confidence scoring
   - Fill the PDF form automatically

### Step 4: Review and Download
- Review high, medium, and low confidence mappings
- Download the completed PA form
- Process additional forms as needed

## 🔧 Technical Architecture

### Core Components

- **Information Extraction Engine**: Uses Gemini 2.0 Flash model to extract structured patient data from medical documents
- **Form Analysis Module**: Analyzes PDF form fields and understands their medical context
- **Intelligent Mapping System**: Maps extracted patient information to appropriate form fields using medical knowledge
- **PDF Form Filler**: Programmatically fills PDF forms with extracted and mapped data
- **Validation Framework**: Provides confidence scoring and validation for all mappings

### AI Models Used

- **Gemini 2.0 Flash**: Primary model for medical information extraction and form field mapping
- **Context-Aware Processing**: Specialized prompts for understanding medical terminology and PA form requirements

### Supported Form Elements

- Text fields (names, addresses, dates, medical information)
- Checkboxes (yes/no questions, previous treatments, contraindications)
- Dropdown menus and selection fields
- Complex medical fields (diagnoses, medications, lab results)

## 📊 Medical Information Categories

PAFill extracts and processes the following types of medical information:

### Patient Demographics
- Full name, date of birth, contact information
- Insurance details and member IDs
- Address and emergency contacts

### Medical Information
- Primary and secondary diagnoses with ICD codes
- Current medications and dosages
- Known allergies and adverse reactions
- Height, weight, and vital signs

### Clinical History
- Disease severity and progression
- Previous treatment attempts and outcomes
- Reasons for treatment discontinuation
- Laboratory test results and clinical assessments

### Provider Information
- Prescribing physician details and credentials
- NPI numbers and practice information
- Administration location and contact details

### Treatment Requests
- Requested medications and dosages
- Route of administration and frequency
- Medical necessity justification

## 🛡️ Privacy and Security

- **No Data Storage**: Patient information is processed in memory only and not stored permanently
- **Secure API Communication**: All data transmission uses secure HTTPS connections
- **Session-Based Processing**: Information is cleared when the session ends
- **HIPAA Considerations**: Users are responsible for ensuring compliance with their organization's HIPAA requirements

## ⚙️ Configuration Options

### API Configuration
```python
# Environment variable (recommended)
GEMINI_API_KEY = "your_api_key_here"

# Model selection
MODEL_CTX = "gemini-2.0-flash"  # Context extraction model
MODEL_MAP = "gemini-2.0-flash"  # Field mapping model
```

### Processing Parameters
- **Batch Size**: Number of fields processed simultaneously (default: 30)
- **Confidence Threshold**: Minimum confidence for automatic field filling (default: 0.7)
- **Review Mode**: Enable manual review before form completion (default: enabled)

## 🔍 Troubleshooting

### Common Issues

**API Key Errors**
- Ensure your Gemini API key is valid and has sufficient quota
- Check that the API key is correctly set in environment variables or the interface

**PDF Processing Errors**
- Verify that uploaded PDFs are not password-protected
- Ensure forms contain fillable fields (not scanned images)

**Memory Issues with Large Files**
- Break down large referral packages into smaller documents
- Reduce batch size in configuration if experiencing timeouts

**Extraction Accuracy Issues**
- Ensure referral packages contain clear, structured information
- Review and adjust confidence thresholds as needed

### Error Logging
The application provides detailed error logging and stack traces for debugging. Check the Streamlit interface for specific error messages and suggested solutions.

## 📈 Performance Optimization

### For Large Forms
- Enable batch processing for forms with 50+ fields
- Use optimized field grouping by page for faster processing
- Consider processing during off-peak hours for better API response times

### For High Volume Usage
- Implement API key rotation if processing many forms
- Monitor API usage and quotas
- Consider caching common form templates for repeated use

## 🤝 Contributing

This application is designed for healthcare professionals and developers working in medical informatics. Contributions should focus on:

- Improving medical information extraction accuracy
- Supporting additional form types and formats
- Enhancing security and HIPAA compliance features
- Adding new AI models and processing capabilities

## 📝 License and Disclaimer

**Important Medical Disclaimer**: This application is designed to assist healthcare professionals with form completion but should not replace human review and validation. All automatically filled forms should be reviewed by qualified healthcare professionals before submission. Users are responsible for ensuring accuracy and compliance with medical and regulatory requirements.

**Usage Responsibility**: Users must ensure compliance with HIPAA, GDPR, and other relevant privacy regulations when processing patient information.

## 🆘 Support

For technical support or questions:
- Review the troubleshooting section above
- Check Streamlit and Gemini API documentation
- Contact your system administrator for enterprise deployments

---

**PAFill - Streamlining healthcare administration through intelligent automation** 🏥✨

---

### **Purpose of this assignment**

This task is designed to assess the candidate's skills, creativity, and problem-solving abilities in a practical setting. Specifically, we are looking for:

1. The ability to quickly learn and adapt to domain knowledge (in this case, healthcare) from a new vertical.
2. Existing skills and knowledge in building multimodal ML pipelines.
3. The capacity to think outside of the box, discovering novel solutions when existing methods fall short.
4. The ability to effectively leverage existing resources, tools, and libraries to resolve challenges.
5. Strong fundamental coding skills, including clean, readable, and maintainable code.
6. Thoughtful handling of ambiguous or incomplete requirements, demonstrating sound judgment in decision-making.

### Background:

**Prior Authorization (PA)** is a process where healthcare providers must obtain approval from a health insurance plan before delivering a specific service (e.g., a drug infusion) to a patient. This process requires assembling evidence to demonstrate that the patient meets specific criteria, such as:

- **Severity of illness**
- **Ineffectiveness of alternative treatments**

The process typically involves comparing two main documents:

1. **PA Form:**  
   A structured PDF form specific to a drug, containing fields for the required information needed for insurance approval.

2. **Supporting Documentation (Referral Package):**  
   A collection of scanned documents such as:
   - Insurance card
   - Medical history notes
   - Test results  
     These are combined into a single PDF, often sent via fax as high-resolution images.

After comparing the documents and confirming that all criteria are met, the PA request is submitted.

---

### Current Manual Workflow:

Currently, a human worker performs the following steps:

1. **Download the PA Form:**  
   Retrieve the specific drug's form from the insurance company's website.

2. **Review the Referral Package:**  
   Extract necessary information from the referral package to complete the PA form.

3. **Complete the PA Form:**  
   Fill in the required fields on the PA form using information from the referral package.

---

### Goal:

Develop a pipeline to automate this workflow.

- **Input:**  
  Pairs of PA forms and referral packages provided in the input data folder. Input data structure is as follow:

      📁 Input Data

          📁 Patient A

              📄 PA.pdf

              📄 referral_package.pdf

          📁 Patient B

              📄 PA.pdf

              📄 referral_package.pdf

          📁 Patient C

              ...

  The dataset includes approximately 10 referrals and 10 different types of forms for different drugs from different insurance companies. **The pipeline should be designed to generalize to any form and any drug, even those unseen during development.**

- **Output:**
  - For each patient, the primary output is a **filled PA form as a PDF document**. This PDF will be populated with information extracted and inferred from the provided referral package. Fields for which information could not be found will remain blank on the form.
  - Accompanying the filled PDF, a **separate report (e.g., a text or markdown file) must be generated for each patient, listing any required fields for which information was missing** from the referral package. This report will clearly indicate what information could not be populated.
  - The example image below illustrates the general appearance of a filled PA form. Your pipeline will generate the actual filled PDF document.
    ![Alt text](image/image1.png)

---

### Notes:

1. **Referral Package Complexity:**

   - These packages consist of multiple scanned documents combined into a single PDF.
   - Since these are high-resolution images, text cannot be directly extracted using standard PDF libraries (e.g., PyMuPDF). Optical Character Recognition (OCR) is required.

2. **PA Form Structure:**

   - Unlike referral packages, PA forms are well-structured PDFs with retrievable text blocks, making field identification more straightforward.

3. **PA Fields Format:**

   - Not every field in a PA form should be filled out. The form often contains mutually exclusive options and branching paths, particularly in checkbox sections. For example:

     1. If you check "New Patient", you shouldn't also check "Existing Patient"
     2. Selecting certain options may make other sections irrelevant or inapplicable
     3. Some sections are conditional and should only be completed based on previous answers

     The goal is to fill out only the appropriate fields based on the patient's specific situation and the logical flow of the form, not to complete every possible field.

4. **Form Types and Implementation Priority:**

   - PA forms come in two formats: interactive widget-based PDFs (containing AcroForm widgets) and non-widget-based PDFs.
   - The primary expectation is for the pipeline to work with widget-based PDFs that contain fillable form fields.
   - While the solution should be designed to handle any form type, successfully implementing support for non-widget-based PDFs will be considered a bonus achievement.
   - The solution should prioritize robust handling of interactive widget-based forms first, then extend capabilities to non-widget formats if possible.

### Delivery Requirement:

1. **Submission Format:**

   - The automated pipeline, along with all supporting materials, must be submitted as a new branch named `automation-pa-filling-[your name]` in the GitHub repository. Do **not** push changes directly to the `main` branch.

2. **Required Deliverables:**
   - **Source Code:**
     - Implement the complete pipeline for automating the PA form-filling workflow. Code should be modular, readable, and include appropriate comments.
   - **Documentation:**
     - Replace the current `README.md` file with your own documentation that includes:
       - Step-by-step installation instructions
       - Your thought process on how you implement
       - Any assumptions or limitations of the implementation
     - Additional documentation in the `docs/` folder if necessary, such as architectural diagrams, workflows, or examples of the expected outputs.
   - **Output Examples:**
     - Include examples of the **filled PA form PDFs** and their **corresponding missing information reports** for the sample input data. These examples will demonstrate the expected pipeline behavior and output format. It is recommended to store these example files in a dedicated directory (e.g., `output_examples/`).
