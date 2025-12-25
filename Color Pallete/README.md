# Color Pallete

A service that extracts the dominant color palette from an uploaded image.

## Functional Requirements (FR):

-   **FR01 (Upload)**: Users upload an image file.
-   **FR02 (Extraction)**: The system analyzes the image pixels and identifies the N most dominant colors.
-   **FR03 (Output)**: Return the palette as a list of Hex codes (e.g., ["#FF0000", "#00FF00", ...]) and their relative percentage/prominence.
-   **FR04 (Formats)**: Support standard image formats (JPG, PNG).

## Non-Functional Requirements (NFR):

-   **NFR01 (Algorithm)**: Implement a color quantization algorithm (like K-Means Clustering or Median Cut) manually or use a library that exposes these low-level controls.
-   **NFR02 (Performance)**: Large images should be resized/sampled before processing to avoid OOM errors and slow response times.
-   **NFR03 (Caching)**: If the same image (hash) is uploaded, return the cached result.
