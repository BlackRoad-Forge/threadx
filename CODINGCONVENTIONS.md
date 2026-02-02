# Eclipse ThreadX Coding Conventions
_Version: 2026.01-DRAFT_

All ThreadX software conforms to a strict set of coding conventions. 

## 1. C coding conventions
Versions of ThreadX 6.0 and greater follow the MISRA-C:2004 and MISRA C:2012 coding conventions. 

### 1.1. ThreadX File Names
All ThreadX C file names take the form `tx_x.c` where `x` represents the component name (e.g., `tx_thread_create.c` contains the function `_tx_thread_create`). Component specification file names take the form `tx_x.h` (e.g., `tx_thread.h`). These naming conventions distinguish ThreadX files from all other application source files.

### 1.2. ThreadX Name Space
All ThreadX functions and global data have a leading `_tx` in their name. This keeps ThreadX global symbols separate from the application symbols and in one contiguous area of the load map created by the linker.

### 1.3. ThreadX Constant Names
All ThreadX constants have the form `TX_NAME` or `TX_C_NAME` and are comprised of capital letters, numerals, and underscores. System constants defined in `tx_api.h` or `tx_port.h` take the form `TX_NAME` (e.g., `TX_SUCCESS`). Component constants defined in component specification files take the form `TX_x_NAME` where `x` represents the capitalized entire component name (e.g., `TX_INITIALIZE_IN_PROGRESS`).

### 1.4. ThreadX Struct and Typedef Names
ThreadX C structure and typedef names are similar to component-specific constant names. System-wide typedefs have the form `TX_X_NAME`, where `x` is the capitalized component name (e.g., `TX_QUEUE`). Component-specific typedefs are contained in `tx_api.h`. Primitive data types like `UINT`, `ULONG`, and `VOID` do not require the leading `TX` modifier and are defined in `tx_port.h`.

#### 1.4.1 ThreadX Member Names
Structure member names are all lower case and take the form `tx_x_name` where `x` is the entire component name (e.g., `tx_thread_id` in the `TX_THREAD` structure).

### 1.5. ThreadX Global Data Names
Each component has a small amount of global C data elements. These elements are lower-case and have the form `_tx_x_name` (e.g., `_tx_thread_current_ptr`).

### 1.6. ThreadX Local Data Names
Readability is the primary requirement for local data elements defined inside ThreadX C functions. Frequently used elements are typically assigned the register modifier if supported by the target compiler.

### 1.7. ThreadX Function Names
All component function names have the form `_tx_x_name` in lower-case, where `x` represents the entire component name (e.g., `_tx_thread_create`).

### 1.8. Source Code Indentation
The standard indentation increment is four spaces. Tab characters are avoided to make the source code less sensitive to text editors.

### 1.9. Comments
Each C statement in the ThreadX source code generally has a meaningful comment. Each source file contains a standardised header as described below.


## 2. Assembly coding conventions

### 2.1. TBD


## 3.0. File headers
ThreadX file headers are made of two distinct sections.

The first section states the copyright owners of the code found in the file, and states the applicable license. The MIT license applies to the vast majority of the files making up ThreadX. It is mandatory to include the applicable SPDX license identifier.

The second section describes the ThreadX component the files belongs to.

Below is a sample file header.

```
/***************************************************************************
 * Copyright (c) 2024 Microsoft Corporation 
 * Copyright (c) 2026 Eclipse ThreadX Contributors
 * 
 * This program and the accompanying materials are made available under the
 * terms of the MIT License which is available at
 * https://opensource.org/licenses/MIT.
 * 
 * SPDX-License-Identifier: MIT
 **************************************************************************/


/**************************************************************************/
/**************************************************************************/
/**                                                                       */
/** ThreadX Component                                                     */
/**                                                                       */
/**   Block Pool                                                          */
/**                                                                       */
/**************************************************************************/
/**************************************************************************/
```




