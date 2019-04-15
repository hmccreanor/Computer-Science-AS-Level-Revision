# Computer Science Model Answers

## System Software

### Definitions

* **Compiler:** 
  * The software reads the source code and reports all errors. 
  * The software produces and executable file. 
  * The software translates a high-level language program into machine code for the processor to execute.
* **Assembler:** The software translates low-level statements into machine code for the processor to execute.
* **Interpreter:** 
  * The software reads each statement and checks it before running it. 
  * The software halts when it encounters a syntax error. 
  * The software translates a high-level language program into machine code for the processor to execute.

## Processor Fundamentals

### Definitions

* **Describe how special purpose registers are used in the fetch-execute cycle:**
  * The Program Counter (PC) holds the address of the next instruction to be fetched.
  * The address in the Program Counter (PC) is copied to the Memory Address Register (MAR).
  * The Program Counter (PC) is incremented.
  * The instruction is copied to the Memory Data Register (MDR) from the address held in the Memory Address Register (MAR).
  * The instruction from the Memory Data Register (MDR) is copied to the Current Instruction Register (CIR).
* **Describe how the fetch-execute cycle handles an interrupt:**
  * At the end of the cycle for the current instruction, the processor checks if there is an interrupt.
  * If the interrupt flag is set: 
    * the register contents are saved
    * the address of the Interrupt Service Routine (ISR) is loaded to the Program Counter (PC)
    * when the ISR completes, the processor restores the register contents
  * The interrupt program continues its execution.

## Information Representation

### Definitions

* **Describe how sampling is used to record sound clips:**
  * The height/amplitude of the sound wave is determined at set time intervals to get an approximation of the sound wave.
  * This is encoded as a sequence of binary numbers.
  * Increasing the sampling rate will improve the accuracy of the recording.
* **Explain and justify the use of the different types of compression:**
  * Lossy
    * Makes a decision about what parts of the image are important and then discard certain information.
    * For certain types of files - audio/video for example, human won't notice that parts of the original data have been discarded.
    * The reduction in file size is greater than using lossless.
    * This is useful for transmitting data over a network - a smaller file will take less time to transmit (be specific to the question)
    * The file may not need to be of high precision/accuracy.
    * Sometimes naming a type of file that uses this compression (mp3) will gain a  mark.
    * Lossy may result in a loss of detail.
  * Lossless
    * A bitmap/other file type may contain the same sequence of pixels (i.e. a pattern) repeated many times.
    * A lossless technique is designed to lose none of the original detail - allows the original file to be re-created exactly.
    * One lossless technique is 'run-length encoding' - this stores the color and number of consecutive pixels of that color'. JPEG and GIF file formats use RLE (i.e. a lossless technique).
    * Lossless techniques are founded on some form of replacement.
    * Lossless is used when the file needs to be a high precision/accuracy.
    * None of the original data is lost - the decompressed file will be identical to the original.
    * Sometimes naming a type of file that uses this compression (flac) will gain a  mark.
* **Explain run-length encoding (RLE):**
  * Lossless method of compression.
  * Reduces the physical size of a string of adjacent, identical characters/pixels/bytes etc..
  * The repeating string (a run) is encoded into two values:
    * One value represents the number of identical characters in the run (the run count).
    * The other value is the code of the character/color code of pixel etc. in the run (the run value).
    * The run value and run count combination may be preceded by a control character.
  * Give a valid example.

## Ethics and Ownership

### Definitions

* **Types of software:**
  * Opensource
    * Source code comes with the software
    * The software can be modified by the user
  * Shareware
    * Software is provided free on a trial basis
  * Commerical
    * Software is purchased before it can be used