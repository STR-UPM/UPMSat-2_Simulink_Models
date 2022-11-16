# UPMSat-2 Simulink models

This repository contains the Simulink models used during the development and testing activities
from the UPMSat-2 Attitude Control System (ACS).

## General Structure:

* `Control_Algorithm`: Contains the `control.slx` Simulink model
   that corresponds to the implementation of the UPMSat-2 ACS controller.
   This model is transformed into C or Ada source code,
   and is then embedded in the satellite on-board software (OBSW).
   The controller has been tested following the *in-the-loop* simulation technique.
   
* `ACS_PIL`: Contains the simulation from the satellite's environment and equipment.
   This model is intended to be used during the Processor In-the-Loop (PIL) testing
   and communicates with the OBSW by means of a serial line, the `/dev/ttyUSB0` device.

* `ACS_SIL`: Same as `ACS_PIL`,
  but it is intended to be used during the Software In-the-Loop (SIL) testing.
  The communication between the OBSW and the SIL model is carried out via through sockets, port `5000`.
