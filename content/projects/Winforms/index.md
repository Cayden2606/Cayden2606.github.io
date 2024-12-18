---
title: Winforms Application
summary: An aesthetically pleasing and feature rich Windows Application.
date: 2023-10-27

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: **Me**'

authors:
  - admin

tags:
  - Application
  - Ui Design
---

{{< toc mobile_only=true is_open=true >}}

<a href="https://github.com/Cayden2606/Winforms-Calculator" style="display: flex; align-items: center;" target="_blank">
  <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" style="width: 30px; margin-right: 10px;">
  GitHub Repository for Winforms Calculator
</a>

<a href="https://github.com/Cayden2606/Winforms-Doodle-App" style="display: flex; align-items: center;" target="_blank">
  <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" style="width: 30px; margin-right: 10px;">
  GitHub Repository for Winforms Doodle
</a>


## Overview

This project utilizes WinForms in .NET Framework 4.8 to create visually appealing and functional applications. Below are two featured applications:

## Doodle Paint Enhancement

### Overview
Doodle Paint is a feature-rich painting and graphics application built using WinForms and .NET Framework 4.8. This project enhances the existing application with a range of new functionalities, focusing on drawing, text handling, color customization, and user interaction.

### Features

#### A. Drawing and Graphics
- **Custom Brushes**: Includes Charcoal and Watercolor brushes.
- **Brush Size Control**: Adjustable via a trackbar and text box, with input validation to prevent crashes from invalid sizes.
- **Independent Brush Sizes**: Each brush type retains its own size settings.
- **Shape Tools**: Create shapes like lines, circles, and rectangles with adjustable width and size.
- **Emoji Tools**: Add emojis like Happy and Sad with customizable sizes.

#### B. Text Handling
- **Font and Size Selection**: Combo boxes to choose fonts and sizes.
- **Custom Text on Canvas**: Add styled text with options like Bold, Italic, Underline, and Strikethrough.
- **Full Font Access**: Utilize all fonts available on the computer.
- **Input Validation**: Prevent crashes from invalid size or font selections.
- **Text Color Selection**: Choose from predefined colors or use a color dialog for customization.

#### C. Color and Fill
- **Color Picker Tool**: Select colors with ease.
- **Fill Tool**: Implemented using a flood fill algorithm.
- **Custom Colors**: Choose colors via a color dialog or predefined palettes.

#### D. Filters and Effects
- **Image Filters**: Apply effects like Grayscale, Luminosity, and custom transformations.

#### E. UI Components
- **Dynamic Labels**: Display canvas size and cursor position in real-time.
- **Tool Tips**: Hovering over clickable elements provides helpful tooltips.

#### F. Event Handling
- **Keyboard Shortcuts**: Increase efficiency with shortcuts for various actions.

#### G. Miscellaneous
- **Button Sounds**: Add auditory feedback for button clicks.

### Installation
1. Clone this repository:
   ```
   git clone https://github.com/your-username/doodle-paint-enhancement.git
   ```
2. Open the project in Visual Studio.
3. Build the solution using the Release configuration.
4. Run the application by executing the compiled `.exe` file located in the `bin/Release` folder.

### Usage
Explore the intuitive interface to create stunning artwork! Access advanced tools and features to enhance your creative workflow.

## Calculator Enhancement

### Overview
This project enhances the functionality of a calculator application built using WinForms and .NET Framework 4.8. The enhancements include a refined user interface, audio features, improved interaction, and added functionality for both standard and scientific calculations.

### Features

#### A. User Interface
- **Compact Design**: Streamlined layout with well-placed buttons.
- **Hamburger Menu**: Access additional options via a collapsible panel.
- **Mode Switching**: Toggle between Standard and Scientific interfaces.
- **Color Scheme**: Carefully selected colours for better usability.

#### B. Audio Enhancement
- **Button Sounds**: Provides auditory feedback for button clicks (both on-screen and keyboard).
- **Result Announcement**: Announces the calculation result audibly.
- **Independent Controls**: Enable or disable speech and button sounds independently via the panel.

#### C. Interaction Enhancement
- **Copy Button**: Fully functional copy button.
- **Status Indicators**: Display the status of:
  - Degree/Radian (Deg/Rad)
  - Standard/Scientific Mode (STD/SCI)
  - Button and Speaker sounds (mute/unmute)

#### D. Functional Buttons
- **Standard and Scientific Calculations**: Includes basic and advanced functions.
- **Shift Button**: Unlocks secondary functions.
- **Degree/Radian Toggle**: Switch between angle measurement modes.
- **ANS Button**: Retrieve the result of the previous calculation.
- **Dynamic Panel**: Adjusts button layout for Standard/Scientific modes.
- **Keyboard Input**: Accepts input from the physical keyboard.

#### E. Additional Features
- **Unary Operators**: Added functions for inverse trigonometry, rounding, and x^y.
- **Constants**: Includes Pi (π) and Euler’s number (e).
- **Dynamic Layout**: Seamless transitions between Standard and Scientific modes.
- **Boot-Up Sound Effect**: Plays a sound during application startup.
- **Error-Free Editing**: Allows character deletion without breaking equation evaluation.

### Installation
1. Clone this repository:
   ```
   git clone https://github.com/your-username/calculator-enhancement.git
   ```
2. Open the project in Visual Studio.
3. Build the solution using the Release configuration.
4. Run the application by executing the compiled `.exe` file located in the `bin/Release` folder.

### Usage
Enjoy a feature-packed calculator for all your mathematical needs. Switch between Standard and Scientific modes with ease, customize the sound settings, and use the enhanced interaction features for a smooth user experience.



<div style="font-family: Arial, sans-serif; margin: 20px;">

<h2 style="color: #2c3e50; border-bottom: 2px solid #ecf0f1;">Overview</h2>
<p>This project utilizes <strong>WinForms</strong> in .NET Framework 4.8 to create visually appealing and functional applications. Below are two featured applications:</p>

<div style="padding: 15px; border: 1px solid #bdc3c7; margin-bottom: 20px; border-radius: 8px;">
<h2 style="color: #3498db;">Doodle Paint Enhancement</h2>

<h3 style="color: #2c3e50;">Overview</h3>
<p>Doodle Paint is a feature-rich painting and graphics application built using WinForms and .NET Framework 4.8. This project enhances the existing application with a range of new functionalities, focusing on drawing, text handling, color customization, and user interaction.</p>

<h3 style="color: #2c3e50;">Features</h3>

<h4 style="color: #1abc9c;">A. Drawing and Graphics</h4>
<ul>
  <li><strong>Custom Brushes:</strong> Includes Charcoal and Watercolor brushes.</li>
  <li><strong>Brush Size Control:</strong> Adjustable via a trackbar and text box, with input validation to prevent crashes from invalid sizes.</li>
  <li><strong>Independent Brush Sizes:</strong> Each brush type retains its own size settings.</li>
  <li><strong>Shape Tools:</strong> Create shapes like lines, circles, and rectangles with adjustable width and size.</li>
  <li><strong>Emoji Tools:</strong> Add emojis like Happy and Sad with customizable sizes.</li>
</ul>

<h4 style="color: #1abc9c;">B. Text Handling</h4>
<ul>
  <li><strong>Font and Size Selection:</strong> Combo boxes to choose fonts and sizes.</li>
  <li><strong>Custom Text on Canvas:</strong> Add styled text with options like Bold, Italic, Underline, and Strikethrough.</li>
  <li><strong>Full Font Access:</strong> Utilize all fonts available on the computer.</li>
  <li><strong>Input Validation:</strong> Prevent crashes from invalid size or font selections.</li>
  <li><strong>Text Color Selection:</strong> Choose from predefined colors or use a color dialog for customization.</li>
</ul>

<h4 style="color: #1abc9c;">C. Color and Fill</h4>
<ul>
  <li><strong>Color Picker Tool:</strong> Select colors with ease.</li>
  <li><strong>Fill Tool:</strong> Implemented using a flood fill algorithm.</li>
  <li><strong>Custom Colors:</strong> Choose colors via a color dialog or predefined palettes.</li>
</ul>

<h4 style="color: #1abc9c;">D. Filters and Effects</h4>
<ul>
  <li><strong>Image Filters:</strong> Apply effects like Grayscale, Luminosity, and custom transformations.</li>
</ul>

<h4 style="color: #1abc9c;">E. UI Components</h4>
<ul>
  <li><strong>Dynamic Labels:</strong> Display canvas size and cursor position in real-time.</li>
  <li><strong>Tool Tips:</strong> Hovering over clickable elements provides helpful tooltips.</li>
</ul>

<h4 style="color: #1abc9c;">F. Event Handling</h4>
<ul>
  <li><strong>Keyboard Shortcuts:</strong> Increase efficiency with shortcuts for various actions.</li>
</ul>

<h4 style="color: #1abc9c;">G. Miscellaneous</h4>
<ul>
  <li><strong>Button Sounds:</strong> Add auditory feedback for button clicks.</li>
</ul>

<h3 style="color: #2c3e50;">Installation</h3>
<ol>
  <li>Clone this repository:
    <pre style="background: #ecf0f1; padding: 10px; border-radius: 5px;">git clone https://github.com/your-username/doodle-paint-enhancement.git</pre>
  </li>
  <li>Open the project in Visual Studio.</li>
  <li>Build the solution using the Release configuration.</li>
  <li>Run the application by executing the compiled <code>.exe</code> file located in the <code>bin/Release</code> folder.</li>
</ol>

<h3 style="color: #2c3e50;">Usage</h3>
<p>Explore the intuitive interface to create stunning artwork! Access advanced tools and features to enhance your creative workflow.</p>
</div>

<div style="padding: 15px; border: 1px solid #bdc3c7; margin-bottom: 20px; border-radius: 8px;">
<h2 style="color: #3498db;">Calculator Enhancement</h2>

<h3 style="color: #2c3e50;">Overview</h3>
<p>This project enhances the functionality of a calculator application built using WinForms and .NET Framework 4.8. The enhancements include a refined user interface, audio features, improved interaction, and added functionality for both standard and scientific calculations.</p>

<h3 style="color: #2c3e50;">Features</h3>

<h4 style="color: #1abc9c;">A. User Interface</h4>
<ul>
  <li><strong>Compact Design:</strong> Streamlined layout with well-placed buttons.</li>
  <li><strong>Hamburger Menu:</strong> Access additional options via a collapsible panel.</li>
  <li><strong>Mode Switching:</strong> Toggle between Standard and Scientific interfaces.</li>
  <li><strong>Color Scheme:</strong> Carefully selected colours for better usability.</li>
</ul>

<h4 style="color: #1abc9c;">B. Audio Enhancement</h4>
<ul>
  <li><strong>Button Sounds:</strong> Provides auditory feedback for button clicks (both on-screen and keyboard).</li>
  <li><strong>Result Announcement:</strong> Announces the calculation result audibly.</li>
  <li><strong>Independent Controls:</strong> Enable or disable speech and button sounds independently via the panel.</li>
</ul>

<h4 style="color: #1abc9c;">C. Interaction Enhancement</h4>
<ul>
  <li><strong>Copy Button:</strong> Fully functional copy button.</li>
  <li><strong>Status Indicators:</strong> Display the status of:</li>
  <ul>
    <li>Degree/Radian (Deg/Rad)</li>
    <li>Standard/Scientific Mode (STD/SCI)</li>
    <li>Button and Speaker sounds (mute/unmute)</li>
  </ul>
</ul>

<h4 style="color: #1abc9c;">D. Functional Buttons</h4>
<ul>
  <li><strong>Standard and Scientific Calculations:</strong> Includes basic and advanced functions.</li>
  <li><strong>Shift Button:</strong> Unlocks secondary functions.</li>
  <li><strong>Degree/Radian Toggle:</strong> Switch between angle measurement modes.</li>
  <li><strong>ANS Button:</strong> Retrieve the result of the previous calculation.</li>
  <li><strong>Dynamic Panel:</strong> Adjusts button layout for Standard/Scientific modes.</li>
  <li><strong>Keyboard Input:</strong> Accepts input from the physical keyboard.</li>
</ul>

<h4 style="color: #1abc9c;">E. Additional Features</h4>
<ul>
  <li><strong>Unary Operators:</strong> Added functions for inverse trigonometry, rounding, and x^y.</li>
  <li><strong>Constants:</strong> Includes Pi (π) and Euler’s number (e).</li>
  <li><strong>Dynamic Layout:</strong> Seamless transitions between Standard and Scientific modes.</li>
  <li><strong>Boot-Up Sound Effect:</strong> Plays a sound during application startup.</li>
  <li><strong>Error-Free Editing:</strong> Allows character deletion without breaking equation evaluation.</li>
</ul>

<h3 style="color: #2c3e50;">Installation</h3>
<ol>
  <li>Clone this repository:
    <pre style="background: #ecf0f1; padding: 10px; border-radius: 5px;">git clone https://github.com/your-username/calculator-enhancement.git</pre>
  </li>
  <li>Open the project in Visual Studio.</li>
  <li>Build the solution using the Release configuration.</li>
  <li>Run the application by executing the compiled <code>.exe</code> file located in the <code>bin/Release</code> folder.</li>
</ol>

<h3 style="color: #2c3e50;">Usage</h3>
<p>Enjoy a feature-packed calculator for all your mathematical needs. Switch between Standard and Scientific modes with ease, customize the sound settings, and use the enhanced interaction features for a smooth user experience.</p>
</div>

</div>
