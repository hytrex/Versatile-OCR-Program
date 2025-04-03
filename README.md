# OCR System Optimized for Machine Learning: Figures, Diagrams, Tables, Math & Multilingual Text

## Overview

This OCR system is specifically designed to extract structured data from complex educational materials—such as exam papers—in a format optimized for machine learning (ML) training.
It supports multilingual text, mathematical formulas, tables, diagrams, and charts, making it ideal for creating high-quality training datasets.

## Key Features

– Optimized for ML Training: Extracted elements such as diagrams, tables, and figures are semantically annotated with contextual explanations.
This includes automatic generation of natural language descriptions for visual content (e.g., “This figure shows the process of mitosis in four stages”) to enhance downstream model training.

– Multilingual Support: Works with Japanese, Korean, and English, and can be easily customized for additional languages.

– Structured Output: Generates AI-ready outputs in JSON or Markdown, including human-readable descriptions of mathematical expressions, table summaries, and figure captions.

– High Accuracy: Achieves over 90–95% accuracy on real-world academic datasets such as EJU Biology and UTokyo Math.

– Complex Layout Support: Accurately processes exam-style PDFs with dense scientific content, formula-heavy paragraphs, and rich visual elements.

– Built With: DocLayout-YOLO, Google Vision API, Gemini Pro Vision, MathPix OCR, OpenAI API, OpenCV, and more.

# Sample Outputs

Below are actual examples of outputs generated by this system using real-world materials (2017 EJU Biology & 2014 University of Tokyo Math), including English-translated semantic context and extracted data.

**Math Input**
![Math Original](/sample_images/Math_Original.jpeg)
**Output**
![Math Converted](/sample_images/Math_Converted.jpeg)

**English-translated outputs**

Question 1. Consider the rectangular prism OABC–DEFG with a square base of side length 1. Points P, Q, R are on the segments AE, BF, and CG, respectively, and four points O, P, Q, and R lie on the same plane. Let S be the area of quadrilateral OPQR. Also, let ∠AOP be α and ∠COR be β. (2) If α + β = 1 and S = S, find the value of tan α + tan β. Also, if α ≤ β, find the value of tan α. 

[Image Start] 

Image description:
This image shows the rectangular prism OAB–CDEFGQ. Each vertex is labeled with alphabets. The angle α is marked on face OAB. The plane ORPQ intersects the prism and is highlighted. Line RC lies on face ODCG, and line PB lies on face ABFQ. 

Educational value:
This image enhances spatial reasoning by visualizing 3D geometry and cross-sections. It helps learners understand concepts such as plane geometry, solid shapes, spatial visualization, and angles. 

Related topics:
Solid geometry, cross-sections, prism faces, triangle, spatial reasoning

Exam relevance:
This type of question appears in entrance exams like:
1. Calculate the area of ORPQ using angle α
2. Find the lengths of OR, RP, PQ, QO
3. Determine the angle between ORPQ and the prism's face
4. Locate points P, Q, R in coordinate space
5. Calculate volume/area of the prism parts
6. Predict shapes based on constraints
7. Sketch the shape of the prism

[Image End]

**Biology Input**
![Biology Original](/sample_images/Biology_Original.jpeg)
**Output**
![Biology Converted](/sample_images/Biology_Converted.jpeg)

**English-translated outputs**

Question 39. The photo shows the mitotic cell division process (somatic cell division) of an onion root tip. Cells A–D are in different stages of division. Match the stages (prophase, metaphase, anaphase, telophase) to each cell and select the correct combination from options ①–⑧.

[Image Start]

Image description:
This image shows the process of plant cell division observed under a microscope. Various cells are in different mitotic phases, including chromosomes aligned at the center (metaphase), separating to poles (anaphase), or forming daughter nuclei (telophase). 

A – appears to be in anaphase  
B – possibly telophase  
C – prophase or prometaphase  
D – metaphase

Educational value:
This helps students visually understand the process of mitosis, reinforcing knowledge of cell division phases and their characteristics. It connects to biology concepts like DNA replication, cancer biology, and genetics.

Related topics:
Mitosis, Cell cycle, Prophase, Metaphase, Anaphase, Telophase, DNA replication

Exam relevance:
This image is used in questions such as:
1. Match A, B, C, D to appropriate mitotic phases
2. Describe characteristics of each phase
3. Explain the significance of mitosis
4. Discuss how errors in mitosis lead to genetic diseases

[Image End]

[Table Start]
| 前期 | 中期 | 後期 |
|------|------|------|
| A    | C    | D    |
| A    | D    | B    |
| B    | C    | C    |
| B    | D    | C    |
| C    | A    | D    |
| C    | D    | A    |
| D    | A    | B    |
| D    | C    | A    |

Summary:
Each option (①–⑧) corresponds to a specific mapping of A, B, C, D to prophase, metaphase, and anaphase.

Educational value:
Understanding time-based transition in mitosis and data organization in tables. Enhances data interpretation, pattern recognition, and analysis skills.

Related topics:
Data analysis, table interpretation, biological data classification

[Table End]


## Usage Workflow
1.	Step 1 – Initial OCR Extraction
Run ocr_stage1.py to extract raw elements (text, tables, figures, etc.) from input PDFs.
This step performs layout detection and stores intermediate results (e.g., coordinates, cropped images, raw content).
	
2.	Step 2 – Semantic Interpretation & Final Output
Run ocr_stage2.py to process the intermediate data and convert it into structured, human-readable output.
This includes generating natural-language explanations, summaries, and organizing content into AI-ready formats (JSON/Markdown).



## Technical Implementation

– Table Processing OptimizationTable regions are detected using DocLayout-YOLO

– Google Vision OCR is used for table processing instead of MathPix for better accuracy with Japanese text

– Table structures are preserved in structured JSON format (maintaining row/column structure)

– Y-coordinate information is maintained to ensure contextual continuity

– Original layout information is preserved alongside structured data for ML training

– Image and Special Region ProcessingImage regions are processed using Google Vision API's image analysis features (imageProperties, labelDetection, textDetection)

– Image descriptions are generated using Google Cloud Vision API

– Graphs/charts are processed using Google Cloud Vision API's document analysis features with data point extraction

– Special region processing results are stored in structured JSON format for ML training

– Original coordinate information and region type metadata are added to maintain contextual continuity

## Purpose and Contact

This OCR system is an open project, and I’d love to see others improve or build upon it. Continuous updates and community-driven enhancements are the goal.

If you’re interested in custom AI tools or would like to collaborate on an AI-related project, feel free to reach out via email:

**Email**: [ses425500000@gmail.com](mailto:ses425500000@gmail.com)
⸻
_Note: The English translations in the examples were manually reformatted for clarity and consistency. Please treat them as reference only, as structure and layout may differ slightly from the original._
_Keywords: OCR, exam OCR, table recognition, diagram OCR, AI education tools, OpenAI, Gemini Pro Vision, multilingual OCR, DocLayout-YOLO, Machine Learning, educational ML dataset, research OCR, paper OCR, document AI
