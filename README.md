# Swiping Response Format – Qualtrics Integration Guide

This repository contains the code for implementing the **Swiping response format** into a Qualtrics project. For the Swiping format containing videos, visit the [video swiping repository](https://github.com/adamstr99/swipevid).

The code is available as supplementary material to the study:

**Strojil & Cígler (n.d.)**


**Disclaimer:** The code is a prototype, made available for replicability in line with the principles of **open science** and for adaptation by interested researchers/developers. Full optimization is not guaranteed.

---

## Instructions

### 1. Preview (`index`)
- The `index` file is a working prototype with all necessary code merged (HTML, CSS, JS).  
- It works outside Qualtrics for preview and testing purposes, or for integration to websites and other survey engines.

### 2. Integration into Qualtrics
1. Paste the content of `look&feel_JS` into the **Look and Feel → Header** of your Qualtrics project.  
2. Paste the content of `look&feel_CSS` into the **Look and Feel → Custom CSS** of your Qualtrics project.  
3. Create a **question block** in the Qualtrics survey builder.  
4. Create an **empty question**.  
   - Paste the content of `questionCSS` into the HTML editor of the empty question.  
   - Paste the content of `questionJS` into the question’s JavaScript.

### 3. Customizing the Question JavaScript (`questionJS`)
- Each swipe is saved as `swipedir` embedded data.  
- In **Survey Flow**, at the beginning, create embedded data fields to save the responses: e.g., `swipedir1`, then `swipedir2`, then `swipedir3`…  
- Each question must use a different `swipedir` variable.  
  - In the provided JS, find:  
    ```javascript
    Qualtrics.SurveyEngine.setEmbeddedData("swipedir1", swipedir);
    ```
  - Change `"swipedir1"` to match one of your embedded data fields, e.g., `swipedir1`, or `swipedir2`, or `swipedir3`…

### 4. Customizing the Question Card Content (`questionCSS`)
- To change the statement, edit:  
  ```html
  <div class="text-container">On the whole, I am satisfied with myself.</div>
  ```
- To change the agree/disagree/skip stamp text, insert your stamp description, e.g., Agree -> Yes:  
  ```html
  <div class="stamp agree">Agree</div>
  <div class="stamp disagree">Disagree</div>
  <div class="skip">Skip</div>
  ```
- The footer uses **Google Fonts Icons**: [https://fonts.google.com/icons](https://fonts.google.com/icons)

---

## License & Acknowledgment

MIT License  
Copyright (c) 2025 Adam Strojil

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

Acknowledgment:  
The JavaScript used here was adapted from the code for the swiping carousel by: [Simone P.M.](https://github.com/simonepm)  
MIT License  
Copyright (c) 2019 Simone P.M. github.com/simonepm
