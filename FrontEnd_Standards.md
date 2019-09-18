General Code Styles for all Frontend Projects
===

**Table of Contents**
- [General Code Styles for all Frontend Projects](#general-code-styles-for-all-frontend-projects)
  - [File Structure](#file-structure)
    - [Lines](#lines)
    - [Files](#files)
    - [Variable, Function, Class, Constant and Module naming](#variable-function-class-constant-and-module-naming)
  - [Linter files](#linter-files)

## File Structure

### Lines

Lines **must**:
 - Use `spaces` instead of tabs
 - Use `4 spaces` for indentation
 - Use `LF` for the End of Line character
 - **Not** contain any trailing `whitespace`

### Files

Files **must**
 - Use `UTF-8` file encoding
 - Have a `new line` at the End of File
 - Have the same name as the module they are defining, using lowercase letters and dashes between words
   - TestService
     - test-service.{js|ts}
     - test-service.html
     - test-service.{Spec.js|spec.ts} 

### Variable, Function, Class, Constant and Module naming

 - Variables **must** use camelcase
 - Functions **must** use camelcase
 - Constants **must** use titlecase
 - Classes **must** use titlecase
   - `constructor` functions are **not allowed** to return any value. [Reason](https://www.jstips.co/en/javascript/return-values-with-the-new-operator/)
 - Modules **must** use titlecase
