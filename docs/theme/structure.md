---
id: structure
title: Theme Structure
---

## Overview

Here are a few important tidbits:
- All themes have their files located in the /themes root or module folder.
- Each theme has its own sub-folder, in the main themes folder.
- Each theme is made of template files, image files, one or more LESS/CSS files, and sometimes even JavaScript files (.js).

## Create Own Theme Folder

> Note: Do not edit the default HumHub themes directly. All changes may overwritten on updates.

The best way to start is to copy the default theme folder `HumHub`.

Select a preferably unqiue theme name (e.g. MyCompanyName) for your new theme folder.

** Example: Copy theme folder (Linux)**

```
cd /path/to/HumHub
cp -rfa themes/HumHub themes/MyCompany
```

** Enable the theme **

Once you created an own theme folder, you need to enable it in the administration section of HumHub: 
`Administration -> Settings -> Appeareance` 


## Folder Structure Example

This overview shows a complete theme folder structure including own less and view files.

```mermaid
graph TD
    A[/themes/] --> B[/mytheme/]
    B --> C[/css/]
    B --> D[/less/]
    B --> E[/js/]
    B --> F[/font/]
    B --> G[/img/]
    B --> H[/views/]
    
    C --> C1[theme.css]
    C1[theme.css] --> C2[Your actual theme css file]
    
    D --> D1[build.less]
    D --> D2[variables.less]
    D --> D3[mixins.less]
    D --> D4[theme.less]
    D1 --> D1a[Used to build your theme.css]
    D2 --> D2a[Contains theme variables]
    D3 --> D3a[Used to define own mixins]
    D4 --> D4a[Contains your own theme definitions]
    
    E --> E1[Additional javascript files]
    F --> F1[Additional fonts]
    G --> G1[Images]
    
    H --> I[/moduleId/]
    H --> J[/widgets/]
    
    I --> I1[/controllerId/]
    I --> I2[/widgets/]
    
    I1 --> I1a[index.php]
    I1a --> I1b[Overwritten View File]
    
    I2 --> I2a[someWidget.php]
    I2a --> I2b[Overwritten widget view]
    
    J --> J1[Links to /protected/widget/views]
    
    B --> B1[My Theme Name]
    C --> C3[Your theme css files optional]
    D --> D5[Contains less files used to build your theme.css optional]
    E --> E2[optional]
    F --> F2[optional]
    G --> G2[optional]
    H --> H1[Overwritten Views]
    I --> I3[Id of Module module_core Id, module Id, or base controller id]
    I1 --> I1c[Id of Controller]
    I2 --> I2c[Links to /someModule/widgets/views/]
```
