# Textual Swipe Scale – Qualtrics Integration Guide

This repository contains the code for implementing the **Textual Swiping response format** into a Qualtrics project.

The code is available as supplementary material to the research article:

**Strojil & Cígler (n.d.)**


***Disclaimer:** The code is a prototype, made available for replicability purposes in line with the principles of **open science** and for adaptation by interested researchers/developers. Full optimization is not guaranteed.*

---

<p align="center">
  <img src="https://github.com/adamstr99/swipescale/blob/8aec32c233a5d0e622f6a5bcd72fd205f0766306/Swipe.png" alt="Swipe" style= width:600px;">
</p>

---

## Instructions

### 0. Dependencies and description

#### Progress bar
- The Qualtrics progress bar was customized not to obstruct the screen.
- Make sure to **ENABLE** the progress bar in the **Look and Feel** of your Qualtrics project
- It is disabled by default in the `look&feel.CSS`, change the *height: 0px* to another value to enable the progress bar.
  ```css
  .Skin #ProgressBarFillContainer, .Skin .ProgressBarFill, .Skin .ProgressBarFillContainer { 
  height: 0px !important;
  }
  ```

### 1. Preview (`index.html`)
- The `index.html` file is a working prototype with all necessary code merged (HTML, CSS, JS).  
- It works outside Qualtrics for preview and testing purposes, or for integration to websites and other survey engines.

### 2. Integration into Qualtrics
1. Paste the content of `look&feel.JS` into the **Look and Feel → Header** of your Qualtrics project.  
2. Paste the content of `look&feel.CSS` into the **Look and Feel → Custom CSS** of your Qualtrics project.  
3. Create a **question block** in the Qualtrics survey builder.  
4. Create an **empty question**.  
   - Paste the content of `question.CSS` into the HTML editor of the empty question.  
   - Paste the content of `question.JS` into the question’s JavaScript.

### 3. Customizing the Question JavaScript (`question.JS`)
- Each swipe is saved as `swipedir` embedded data.  
- In **Survey Flow**, at the beginning, create embedded data fields to save the responses (e.g., `swipedir1`, then `swipedir2`, then `swipedir3`…).  
- Each question must use a different `swipedir` variable.  
  - In the provided JS, find:  
    ```javascript
    Qualtrics.SurveyEngine.setEmbeddedData("swipedir1", swipedir);
    ```
  - Change `"swipedir1"` to match one of your embedded data fields (e.g., `swipedir1`, or `swipedir2`, or `swipedir3`…).

### 4. Customizing the Question Card Content (`question.CSS`)
- To change the statement, edit:  
  ```html
  <div class="text-container">On the whole, I am satisfied with myself.</div>
  ```
- To change the agree/disagree/skip stamp text, insert your stamp description (e.g., "Agree" -> "Yes"):  
  ```html
  <div class="stamp agree">Agree</div>
  <div class="stamp disagree">Disagree</div>
  <div class="skip">Skip</div>
  ```
- The footer uses **Google Fonts Icons**: [https://fonts.google.com/icons](https://fonts.google.com/icons). Feel free to change the icons by replacing the name of the icon with a different one (e.g., "thumb_up" -> "check"):
  ```html
  <span class="material-icons">navigate_before</span>
  <span class="material-icons thumb-down">thumb_down</span></div>
  
  <span class="material-icons arrow-up">keyboard_double_arrow_up</span>
  
  <span class="material-icons thumb-up">thumb_up</span>
  <span class="material-icons">navigate_next</span></div>
  ```
  
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
