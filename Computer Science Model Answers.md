# Computer Science Model Answers

## System Software

* **Explain what DLLs are:**
  * Dynamic Link Library
  * Subroutines that programmers can use in their programs
  * 
* **Identify the key management tasks carried out by the operating system:**
  * User-system interface
    * Command line interface
    * Graphical user interface (GUI)
  * Program-hardware interface
    * Ensures that hardware does what the software wants it to do
  * Resource management
    * Scheduling of processes
    * Resolution of conflicts when two processes require the same resource
  * Memory management
    * Ensures no programs use memory locations already in use
    * Decides which processes should be in main memory
  * Device management
    * Installing of driver software
    * Control of usage by processes
  * File management
    * File naming conventions
    * Directory (folder) structures
    * Access control mechanisms
  * Security management
    * Provision for recovery when data is lost
    * Prevention of intrusion
    * Ensuring data privacy
  * Error detection and recovery
* **Compiler:** 
  * The software reads the source code and reports all errors. 
  * The software produces and executable file. 
  * The software translates a high-level language program into machine code for the processor to execute.
  * **Detailed steps:**
    * Compiler program and source code file are made available but no data is needed
    * Compiler program begins execution
    * First line of source code is read
    * Line is analysed
    * If no error is found, this is recorded
    * If no error is found, the line of source code is converted into intermediate code
    * The next line of source code is read and Steps 4-7 are repeated
    * When the whole of the source code has been dealt with:
      * If no error is found, the complete intermediate code is converted to object code
      * If any errors are found, a list of these is output and no object code is produced
* **Assembler:** 
  * The software translates low-level statements into machine code for the processor to execute.
* **Interpreter:** 
  * The software reads each statement and checks it before running it. 
  * The software halts when it encounters a syntax error. 
  * The software translates a high-level language program into machine code for the processor to execute.
  * **Detailed steps:**
    * The interpreter program, the source code file and the data to be used by the source code program are all made available
    * The interpreter begins execution
    * The first line of source code is read
    * The line is analysed
    * If an error is found, this is reported and the interpreter program halts execution
    * If  no error is found, the line of source code is converted to an intermediate code
    * The interpreter program uses this intermediate code to execute the required action
    * The next line of source code is read and Steps 4-8 are repeated
* **Describe the processes of a two pass assembler:**
  * First Pass
    * Removal of comments
    * Creation of symbol table containing the binary codes for symbolic names and labels
    * Creation of a literal table if the programmer has used constants in the program
    * Expansion of macros
    * Identification of system calls and subroutines used
  * Second pass
    * Generates object code
      * Replaces symbolic addresses with absolute addresses
* **Describe the pros and cons of Interpreters/Compilers:**
  * Interpreters
    * +
      * Errors can be identified as they occur and corrected immediately without having to wait for the whole of the source code to be read and analysed
    * -
      * During a particular execution of the program, parts of the code which contain syntax errors may not be accessed so if errors are still present they are not discovered until later.
      * Source code has to be sent to the user
      * Source and interpreter have to be available each time that the program is run
  * Compilers
    * +
      * Executable can be distributed to users so the users have no access to the source code
      * Only the object has to be available each time that an error free program is run
      * Object code will provide faster execution than is possible for an interpreted program
    * -
      * Less secure as object code could contain  a virus
* **WTF is Java:**
  * Each type of computer had to have a Java Virtual Machine created
  * When a program is written in Java, it is compiled to Java Byte Code
  * When the program is run, this code is interpreted by the Java Virtual Machine. The Java Byte Code can be transferred to any computer that has a Java Virtual Machine installed

## Processor Fundamentals

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

* **Describe how sampling is used to record sound clips:**
  * The height/amplitude of the sound wave is determined at set time intervals to get an approximation of the sound wave.
  * This is encoded as a sequence of binary numbers.
  * Increasing the sampling rate will improve the accuracy of the recording.
* **Define Sampling Rate**:
  * Number of samples taken per unit time - number of times the amplitude is measured per unit time.
  * Increasing the sampling rate will increase the accuracy/precision of the digitized sound - result in smaller quantization errors.
* **Define the structure of a Vector Graphic file:**
  * Drawing list
    * Contains a command for each object included in the image
    * Each command has a list of attributes that define the properties of the object, such as:
      * the position of a circle's center/radius
      * thickness of line
      * color of a line
* **Define Pixel:**
  * Smallest picture element which can be drawn.
  * Defined by two properties - its position in the bitmap matrix and its colour
* **Define Screen Resolution:**
  * The number of pixels which can be viewed horizontally and vertically on the screen
  * A typical screen resolution is 1920 by 1080 pixels
* **Give examples of image file headers:**
  * File type
  * File size
  * Location/offset of image data within the file
  * Dimensions of the image in pixels
  * Color depth (bits per pixel)
  * Type of compression used, if any
* **Explain and justify the use of the different types of compression:**
  * **Lossy:**
    * Makes a decision about what parts of the image are important and then discard certain information.
    * For certain types of files - audio/video for example, human won't notice that parts of the original data have been discarded.
    * The reduction in file size is greater than using lossless.
    * This is useful for transmitting data over a network - a smaller file will take less time to transmit (be specific to the question)
    * The file may not need to be of high precision/accuracy.
    * Sometimes naming a type of file that uses this compression (mp3) will gain a  mark.
    * Lossy may result in a loss of detail.
  * **Lossless:**
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
* **Explain how a parity check can be used to detect a possible error in a transmitted byte:**
  * Type of parity (odd/even) is agreed by both devices concerned with the communication
  * Transmitting device counts the number of 1 bits in the byte
  * One bit is reserved for parity bit
  * This parity bit is set to 1 or 0 in order to make the number of 1s in the byte an odd or even number dependent on what type of parity is used
  * Receiving device on receipt of byte counts number of 1s
  * If the number is not odd/even (the parity agreed upon), an error has occurred.
* **Explain how the computer uses the parity byte to perform a check on the received data bytes:**
  * The parity bit is worked out for each column
  * The computer checks the parity of each bit position in the parity byte
  * If incorrect parity, then an error occurred
  * Position of the incorrect bit can be determined, using the bytes as a 2D grid:
    * Consider each row in sequence
    * Identify any row with incorrect parity
    * Repeat the process for each column in sequence
    * Identify where a row and column with incorrect parity intersect

## Ethics and Ownership

* **Types of software:**
  * **Opensource:**
    * Source code comes with the software
    * The software can be modified by the user
    * Software is free
  * **Freeware:**
    * Software is free
    * Source code not distributed
  * **Shareware:**
    * Software is provided free on a trial basis
  * **Commercial:**
    * Software is purchased before it can be used
    * A fee is paid for each individual copy of the software - or, a company might have the option of buying a site license which allows a defined number of copies to be running at any one time.
    * Special rates may be available for educational use.
    * Earlier/limited versions may be offered for free or at reduced price.
* **ACM/IEEEE Code of Ethics:**
  * **PUBLIC** - Software engineers shall act consistently with the public interest
  * **CLIENT AND EMPLOYER** - Software engineers shall act in a manner that is in the best interests of their client and employer consistent with the public interest
  * **PRODUCT** - Software engineers shall ensure that their products and related modifications meet the highest professional standards possible
  * **JUDGEMENT** - Software engineers shall maintain integrity and independence in their professional judgment
  * **MANAGEMENT** - Software engineering manages and leaders shall subscribe to and promote an ethical approach to the management of software development and maintenance
  * **PROFESSION** - Software engineers shall advance the integrity and reputation of the profession consistent with the public interest
  * **COLLEAGUES** - Software engineers shall be fair to and supportive of their colleagues
  * **SELF** - Software engineers shall participate in lifelong learning regarding the practice of their profession and shall promote an ethical approach to the practice of the profession.

## Networks

* **IP:**
  * **General:**
    * Internet Protocol
    * 32-bit format
    * Four numbers from 0 to 255 separated by dots
    * Give example - 10.0.0.1
  * **Public:**
    * Can be reached across the Internet
    * Less secure than private address
    * Provided by ISP
    * Unique to the Internet
  * **Private:**
    * Can only be reached enterally/through the Lan - cannot be reached across the internet.
    * Network Address Translation is necessary for a private IP to access the Internet directly.
    * More secure tan a public address
    * Assigned by the router.
    * Unique within their network by can be duplicated within other discrete networks.
    * Can be:
      * 10.0.0.1 to 10.255.255.254
      * 172.16.0.1 to 172.31.255.254
      * 192.168.0.1 to 192.168.255.254
    * IP addresses from the private address space are never assigned as public.
* **DNS**
  * Domain Name Server
  * URL - refence address to a resource on the Internet
  * URL passed to nearest Domain Name Server by browser
  * DNS stores a database/list of URLs and IP addresses
  * DNS looks for URL in its database
  * Finds the matching IP and returns it to its originator
  * Or, if it can't find it, it forwards to another Domain Name Server at a higher level
  * Original DNS server adds the returned IP address to its cache
  * Original DNS server returns the IP address to the browser
* **Describe the difference between real-time and on-demand streaming**
  * **Real time:**
    * Life stream of event taking place
    * Event is captured live with a video camera connected to computer
    * Cannot be paused/rewound
  * **On demand:**
    * Streaming of event/program that has taken place in the past
    * Existing media are encoded to bit streaming format and uploaded to a server
    * Can be paused/rewound/fast forwarded
* **Explain the difference between the World Wide Web and the Internet**
  * WWW is a collection of interlinked, hyper text documents/webpages/multimedia resources accessed via the internet
  * Internet is the global connection of interconnected computer networks
  * Internet uses TCP/IP protocol/WWW uses http protocols to transmit data

## Databases

* **DBMS:**
  * Database Management System
* **How can a Database Admin use the DBMS software to ensure the security of student data:**
  * **Issue usernames and passwords**
    * This stops unauthorized access to the data
    * Making sure the passwords are strong and changed regularly
  * **Access rights/privileges**
    * Only relevant staff can read/edit certain parts of the data
    * Can be read/write/delete
    * Give example
  * **Create regular backups**
    * A copy of the data is available in case of loss/damage
    * Give example
  * **Encryption of data**
    * Means that even if there is unauthorized access to the data, it cannot be understood
    * Give example
  * **Definition of different views**
    * Composed of one or more tables
    * Controls the scope of the data accessible to authorized users
    * Give example
  * **Usage monitoring/logging activity**
    * Creates an audit/activity log
    * Records the use of the data in the database
    * Give example
* **Describe how a standard user might use a query processor for the DBMS:**
  * Set up search criteria to find/retrieve the data that matches the criteria
  * Give example
* **Describe how using a relational database has overcome the previous problems associated with a file-based approach:**
  * By storing data in separate linked tables data redundancy is reduced
  * Compatibility/data integrity issues are reduced as data only needs to be updated once
  * Unwanted or accidental deletion of linked data is prevented as the DBMS will flag an error
  * Program - Data dependence is overcome
  * Changes made to the structure of the data have little effect on existing programs
  * Ad-hoc /complex queries can be more easily made as the DBMS will have a query language/QBE form
  * Unproductive maintenance is eliminated as changes only need to be made once
  * Fields can be added or removed without any effect on existing programs (that do not use these fields)
  * Security/privacy of the data is improved as each application only has access to the fields it needs.
  * There is better control of data integrity as the DBMS uses its Data Dictionary to perform validation checks on data entered.

## Security

* **Describe the difference between security and integrity of data:**
  * Security
    * Keeping data safe
    * Preventing data loss
    * e.g. usernames/passwords/firewalls
  * Integrity
    * Making sure that data is correct/valid
    * Ensures that the data received is the same as the data sent/data copied is the same as original
    * e.g. parity checks/double entry
* **Describe security measures you can take to protect a computer network:**
  * **Installing a firewall and ensuring it is switched on**
    * Stops unauthorized access/hackers gaining access
  * **Use authentication methods such as passwords and usernames**
    * Passwords should be strong/biometrics
  * **Encrypt the data**
    * If data is accessed it will be meaningless unless you have the decryption key
  * **Set up access rights**
    * To stop users reading/editing data that they shouldn't
  * **Installing and running an up to dat anti-malware program**
    * To detect/remove/quarantine viruses/key-loggers etc.
  * **Make regular backups of the data**
    * To separate device or off site to enable recovery if necessary
  * **Employ measures for physical security**
    * Example of a measure for physical security

## Hardware

* **How does a laser jet printer work?**
  * The drum is given an electric charge
  * The drum starts to revolve step by step
  * At each step a laser beam is directed by the mirror and lens assembly to a sequence of positions across the width of the drum
  * At each position the laser is either switch off to leave the charge on the drum or switched on to discharge the position
  * This process repeats until a full page electrostatic image has been created
  * The drum is coated with a charged toner which only sticks to positions where the drum has been discharged
  * The drum rolls over a sheet of paper which is initially given an electric charge
  * The sheet of paper is discharged and then is passed through heated rollers to fuse the toner particles and seal the image on the paper surface
  * The drum is discharged before the process starts again for the next page
* **Explain the differences between SRAM and DRAM:**
  * **Dynamic RAM (DRAM)** 
    * Constructed from capacitors which leak electricity and need regular recharging to maintain the identity of the data stored.
    * Longer access time
    * Less expensive
    * Stored more bits per chip
    * Less power to operate
    * Used for main memory
  * **Static RAM (SRAM)**
    * Constructed from flip-flops which continue to store data indefinitely while the computer system is switched on.
    * Shorter access time
    * More expensive
    * More power to operate
    * Used for cache memory

