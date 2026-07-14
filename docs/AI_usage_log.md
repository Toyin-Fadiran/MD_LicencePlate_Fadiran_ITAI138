# AI Usage Log
**Project:** Automated License Plate Recognition (ALPR) System

---

## Entry 1: Overcoming OCR Limitations with Pre-Processing
* **Date and tool used:** July 08, 2026 - Gemini
* **What you asked, or the problem you had:** I was exploring risk mitigations for the CV pipeline project. I initially assumed that because EasyOCR uses a deep learning architecture, it would automatically handle the low-resolution and degraded bounding box crops outputted by YOLOv11.
* **What the AI suggested:** The AI clarified that while EasyOCR is robust for "text in the wild," it cannot invent missing pixel data from a 40x15 pixel crop. It suggested writing an OpenCV pre-processing script utilizing grayscale conversion, cubic upscaling, bilateral filtering, and adaptive thresholding to clean the YOLO crops before passing them to the OCR engine.
* **What you learned:** I learned the exact mechanical distinction between what modern deep learning OCR handles natively (like curved text) versus where traditional image matrix manipulations are still absolutely required (pixel density and contrast correction).
* **How you applied it in your project:** I added this OpenCV pre-processing step as the primary mitigation strategy for my highest-probability risk in the README, and incorporated OpenCV into the technical pipeline for the Make It Yours phase.
