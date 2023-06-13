# UPMSat-2 Simulink models

## Overview

This repository contains the Simulink models used during the development and testing activities
from the UPMSat-2 Attitude Control System (ACS).

## General Structure:

* [`ACS_MIL`](ACS_MIL): Contains the simulation from the satellite's environment and equipment.
   This model is intended to be used during the Model In-the-Loop (MIL) testing,
   where the algorithm is tested inside the Simulink simulation environment.
   
* [`ACS_PIL`](ACS_PIL): Contains the simulation from the satellite's environment and equipment.
   This model is intended to be used during the Processor In-the-Loop (PIL) testing
   and communicates with the OBSW by means of a serial line, the `/dev/ttyUSB0` device.

* [`ACS_SIL`](ACS_SIL): Same as `ACS_PIL`,
  but it is intended to be used during the Software In-the-Loop (SIL) testing.
  The communication between the OBSW and the SIL model is carried out via through sockets, port `5000`.

* [`Control_Algorithm`](Control_Algorithm): Contains the `control.slx` Simulink model
   that corresponds to the implementation of the UPMSat-2 ACS controller.
   This model is transformed into C or Ada source code,
   and is then embedded in the satellite on-board software (OBSW).
   The controller has been tested following the *in-the-loop* simulation technique.

## License

> _Copyright (C) Universidad Politécnica de Madrid_
>
> _Copyright (C) Institudo de Microgravedad Ignacio da Riva_

The UPMSat-3 OBSW was developed by the [IDR Institute](https://www.idr.upm.es/index.php/) at the [Universidad Politécnica de Madrid](https://www.upm.es/). These models are distributed under the [**GNU General Public License v3**](LICENSE).