# Blog-CAS-task
Behavioral task software program codes created and used for running a conditional action sequencing (CAS) task

Copyright [2022] [Daigo Takeuchi]

Licensed under the Apache License, Version 2.0 (the “License”);
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an “AS IS” BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

### Description of the Behavior Logging System (Blog) ###

1.System Requirements:
The softwares were tested and used on a standard desktop PC with an operating system of 64bit Windows 7.   
The versions of the softwares are:
- LabVIEW 2015 Version 15.0.1 (32-bit)
- LabVIEW FPGA Module (2016)
- NI RIO Device Drivers (NI USB-6343)
- Microsoft Visual Studio 2013
We used a National Instruments DIO interface board (NI USB-6343) for detecting animals' entries into the lever and side ports as well as controlling the timing of tone stimulus delivery or the LED. 
 
2 The structure of the software codes: 
- The main function of the C++ task control program is declared in "Blog ver4.1.cpp". 
- This C++ task program controls the timing of tone stimulus delivery, the timing of turning the LED light on and off, writes the timestamps of animals' entry into the left IR port, the right IR port or the center lever in the hard disk of the computer. 
- This C++ program calls FPGA Interface C APIs with which it controls the National Instruments FPGA DIO board (NI USB-6343).
- The bit file for the NI FPGA module (which is called in the C++ program through the FPGA Interface C API) was created in a custom-written VI program ("discrimination(FPGA).vi") in the LabVIEW software (LabVIEW 2015 Version 15.0.1 (32-bit)). 
- Sound files (.wav) called in the main task program (i.e., Blog ver4.1.cpp) were creared with an m-script ("make_sound_file.m") in Matlab (R2013b).

3. Additinal notes for installation and use of the software and the code:
- Please see NI USB-6343.txt for details of the pinout of the NI intreface DIO board (NI USB-6343).
- Please see property setting.txt for adequately running the Blog task program.
- When modifying the LabVIEW program, please update the newly created NiFpga_discriminationFPGA.lvbitx file stored in the Project folder in Visual Studio (i.e., Blog ver4.1).
