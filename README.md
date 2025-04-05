# ModRTU_InjectX

**ModRTU__InjectX** is a Python-based software tool with a graphical user interface (GUI), specifically developed for research and educational purposes to enable a practical demonstration of the industrial communication protocol Modbus RTU. The platform also provides capabilities to simulate and log various cyber threats based on command injection techniques.

The software can establish a connection to a serial interface (e.g., COM port), allowing passive monitoring of data traffic and logging the entire communication flow on the bus. Events can be exported to a text file for further analysis. Moreover, the platform is capable of detecting and capturing unique incoming communication data frames, facilitating the review and identification of protocol structures.

This functionality enables users to assemble synthetically generated—fictitious—data packets, which can then be injected into the communication channel. The injection mechanism is based on an event-driven logic, constituting a core feature of the software.

During command injection, users can craft manipulated Modbus frames by defining custom parameters (Header, Payload, CRC, End). These packet blocks are automatically transmitted to the bus when a request-response pair matching the predefined header is received within a specified time window (Trigger Time). The packet transmission occurs instantaneously to ensure that the legitimate response remains valid only briefly before being overridden by the attacker’s manipulated message.

The number of transmission cycles can be configured via the Counter parameter. If set to zero, injection is performed continuously without interruption.

The program allows for the dynamic configuration of multiple independent command injection blocks, each with individually controlled start, stop, and parameter settings. This makes it possible to simulate parallel attack scenarios. Each block consists of three primary segments according to the Modbus RTU standard: Header, Payload, and End, which are linked by an automatically generated CRC code.

The GUI offers functionality to configure the data packets intended for injection and to start or stop them individually or simultaneously.

The software evaluates the success of the injected messages and records them in statistical logs. Injected packets that fail to elicit a meaningful response (i.e., the target system did not execute the manipulated command) are also logged. Additionally, statistics on successfully executed command injections are compiled.

## Legal Notice

- Author: Zoltán Dobrady
- Website: www.cyberseclab.eu
- Contact: zoltan.dobrady@hotmail.com
- License: Creative Commons BY-NC 4.0
- Version: v2025.x
- Copyright: © 2024–2025

This software is for educational and research purposes only or other non-commercial use.  
Use in an industrial environment is strictly forbidden.  
The author must be credited in all use cases.  
Commercial use requires written permission.
