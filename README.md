# EETLauncher - SapienForms

**EETLauncher** is a launcher for EET with minimal configuration options.

## Features

- Support for EEEx  
- Open the EET readme file  
- Open the EET forum  
- Open the EET website  
- Open the appropriate `baldur.lua` for EET  
- Ability to switch between EET GUIs  

## Technology Stack

- **PowerShell**  
- **Windows Forms**  
- **SAPIEN PowerShell Studio**  

## SAPIEN Notes

- **File Management:**  
  Each project file (`.pss`, `.ps1`, `.psf`) has a `Properties > Build Order` setting. Pay attention to this when creating new files.

- **Entry Point:**  
  The application starts from `Startup.pss`. Function implementations are located in the `Functions.ps1` file.

- **Shared Properties:**  
  The `Functions.ps1` file is set to `Shared=True`, making all defined variables, functions, and classes globally available—except within runspaces.

- **Job Tracker:**  
  SAPIEN provides a built-in "Background Process" template. Unfortunately, it can cause the GUI to lag when modifying control properties. Use runspaces instead.

## Key Remarks

- **PowerShell Familiarization:**  
  PowerShell differs significantly from C#. Understand its unique features, including variable scopes, function outputs, jobs, runspaces, and other quirks.

- **C# Assumptions:**  
  Avoid directly applying C# conventions to PowerShell—especially with the `return` keyword—as behavior differs and can lead to confusion.

- **Windows Forms Behavior:**  
  Windows Forms controls behave similarly to those in C#, but handling background tasks requires special considerations.

- **Window/Form Scope:**  
  Each new window/form introduces a new scope because they are implemented as functions. While they can be invoked easily, this can affect variable visibility.
