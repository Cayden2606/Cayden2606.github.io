---
title: Winforms Application
summary: An aesthetically pleasing and feature-rich Windows Application.
date: 2024-07-04

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

## Winforms Doodle Paint 

### Overview
Doodle Paint is a feature-rich painting and graphics application built using WinForms and .NET Framework 4.8. This project enhances the existing application with a range of new functionalities, focusing on drawing, text handling, color customization, and user interaction.

![Doodle](https://github.com/Cayden2606/Winforms-Doodle-App/raw/main/Paint.png)

### Features

#### 1. Drawing and Graphics
- **Custom Brushes**: Includes Charcoal and Watercolor brushes.
- **Brush Size Control**: Adjustable via a trackbar and text box, with input validation to prevent crashes from invalid sizes.
- **Independent Brush Sizes**: Each brush type retains its own size settings.
- **Shape Tools**: Create shapes like lines, circles, and rectangles with adjustable width and size.
- **Emoji Tools**: Add emojis like Happy and Sad with customizable sizes.

#### 2. Text Handling
- **Font and Size Selection**: Combo boxes to choose fonts and sizes.
- **Custom Text on Canvas**: Add styled text with options like Bold, Italic, Underline, and Strikethrough.
- **Full Font Access**: Utilize all fonts available on the computer.
- **Input Validation**: Prevent crashes from invalid size or font selections.
- **Text Color Selection**: Choose from predefined colors or use a color dialog for customization.

#### 3. Color and Fill
- **Color Picker Tool**: Select colors with ease.
- **Fill Tool**: Implemented using a flood fill algorithm.
- **Custom Colors**: Choose colors via a color dialog or predefined palettes.

#### 4. Filters and Effects
- **Image Filters**: Apply effects like Grayscale, Luminosity, and custom transformations.

#### 5. UI Components
- **Dynamic Labels**: Display canvas size and cursor position in real-time.
- **Tool Tips**: Hovering over clickable elements provides helpful tooltips.

#### 6. Event Handling
- **Keyboard Shortcuts**: Increase efficiency with shortcuts for various actions.

#### 7. Miscellaneous
- **Button Sounds**: Add auditory feedback for button clicks.

### Installation
1. Clone this repository:
   ```
   git clone https://github.com/Cayden2606/Winforms-Doodle-App.git
   ```
2. Open the project in Visual Studio.
3. Build the solution using the Release configuration.
4. Run the application by executing the compiled `.exe` file located in the `bin/Release` folder.

### Usage
Explore the intuitive interface to create stunning artwork! Access advanced tools and features to enhance your creative workflow.

## Winform Calculator 

### Overview
This project enhances the functionality of a calculator application built using WinForms and .NET Framework 4.8. The enhancements include a refined user interface, audio features, improved interaction, and added functionality for both standard and scientific calculations.

![Calculator](https://github.com/Cayden2606/Winforms-Calculator/raw/master/Calculator.png)

### Features

#### 1. User Interface
- **Compact Design**: Streamlined layout with well-placed buttons.
- **Hamburger Menu**: Access additional options via a collapsible panel.
- **Mode Switching**: Toggle between Standard and Scientific interfaces.
- **Color Scheme**: Carefully selected colours for better usability.

#### 2. Audio Enhancement
- **Button Sounds**: Provides auditory feedback for button clicks (both on-screen and keyboard).
- **Result Announcement**: Announces the calculation result audibly.
- **Independent Controls**: Enable or disable speech and button sounds independently via the panel.

#### 3. Interaction Enhancement
- **Copy Button**: Fully functional copy button.
- **Status Indicators**: Display the status of:
  - Degree/Radian (Deg/Rad)
  - Standard/Scientific Mode (STD/SCI)
  - Button and Speaker sounds (mute/unmute)

#### 4. Functional Buttons
- **Standard and Scientific Calculations**: Includes basic and advanced functions.
- **Shift Button**: Unlocks secondary functions.
- **Degree/Radian Toggle**: Switch between angle measurement modes.
- **ANS Button**: Retrieve the result of the previous calculation.
- **Dynamic Panel**: Adjusts button layout for Standard/Scientific modes.
- **Keyboard Input**: Accepts input from the physical keyboard.

#### 5. Additional Features
- **Unary Operators**: Added functions for inverse trigonometry, rounding, and x^y.
- **Constants**: Includes Pi (π) and Euler’s number (e).
- **Dynamic Layout**: Seamless transitions between Standard and Scientific modes.
- **Boot-Up Sound Effect**: Plays a sound during application startup.
- **Error-Free Editing**: Allows character deletion without breaking equation evaluation.

### Installation
1. Clone this repository:
   ```
   git clone https://github.com/Cayden2606/Winforms-Calculator.git
   ```
2. Open the project in Visual Studio.
3. Build the solution using the Release configuration.
4. Run the application by executing the compiled `.exe` file located in the `bin/Release` folder.

### Usage
Enjoy a feature-packed calculator for all your mathematical needs. Switch between Standard and Scientific modes with ease, customize the sound settings, and use the enhanced interaction features for a smooth user experience.



