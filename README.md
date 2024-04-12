## Table of Content
1. [Design of an Optical Inspection System and a Mechatronic Test Shell on a Motion Stage](#design-of-an-optical-inspection-system-and-a-mechatronic-test-shell-on-a-motion-stage)
2. [Scope of the project](#scope-of-the-project)
3. [Architectural Overview](#architectural-overview)
4. [Design the optical inspection system](#design-the-optical-inspection-system)
5. [Creation of a Python-based software shell specifically for testing the optical inspection system](#creation-of-a-python-based-software-shell-specifically-for-testing-the-optical-inspection-system)
6. [Summary](#summary)

<!-- Design of an Optical Inspection System and a Mechatronic Test Shell on a Motion Stage -->
## Design of an Optical Inspection System and a Mechatronic Test Shell on a Motion Stage
The project, titled "Design of an Optical Application on a Motion Stage and Design and Test of a Mechatronic Test Shell in Python," represents a collaborative effort between NTS and TU/e EngD in  Automotive System Design(ASD) and Mechatronics System Design (MSD). NTS is a specialized company with expertise in motion systems and has a clear vision of advancing functionality in future designs. This project is structured into two key components, each contributing to the advancement of technology and expertise.

The first component of the project focuses on the design and implementation of an optical inspection system tailored for semiconductor applications. This task encompasses a multidisciplinary approach, involving the integration of optics, mechatronics, and motion control hardware. The primary objective is to develop a versatile system that can inspect a glass plate with chrome dots on it which can be used for measurement and calibration purpose.

The optical inspection system will be designed to meet the stringent requirements of the semiconductor industry. It will enable NTS to achieve highly accurate measurements and calibrations, essential for the semiconductor manufacturing process. Furthermore, the system's design will be flexible and scalable, with future plans to expand its capabilities to inspect a variety of surfaces beyond glass plates, enhancing its utility in various applications.

The second component of the project involves the creation of a Python-based software shell specifically for testing the gantry system. This software shell is an integral part of the project as it facilitates communication with the mechatronic components of the inspection system. It enables comprehensive testing and validation of the entire system, ensuring that all components work seamlessly together.

This Python-based mechatronic test shell will be developed to meet the project's specific requirements, providing a robust platform for testing and fine-tuning the gantry system. It will serve as a critical tool in the development process, helping to identify and resolve any issues or inefficiencies in the system's performance.

In summary, this collaborative project not only serves as a valuable training opportunity for individuals in the field of mechatronics and design but also significantly enhances NTS's capabilities in motion systems and standardized testing. The core goal is to expand the scope of applications for the existing XY-motion platform. At its heart, this project seeks to develop a cutting-edge optical inspection system designed to inspect a glass plate with chrome dots for precise measurement and calibration while also laying the foundation for future expansion into a wider range of surface inspection applications. This innovation aligns with NTS's vision for advanced functionality in motion systems and standardized testing, ultimately strengthening their position in the industry.

## Scope of the project
To achieve the client's objective, the team shall develop a design of an optical inspection system assembly for semiconductor applications. This optical system should be a microscope-type which is capable of inspecting surfaces. For this, an optical design is required combined with ACS controller and camera, to enable focusing on the surface under inspection. The selection of optical components and focusing hardware along with the development of a CAD model of the assembly is required to complete the scope. The team will be responsible for conducting a literature review to figure out the best approach, explore the available technologies, and develop system architecture for the solution.
The other scope is to create a Python shell that can be used to execute tests on the gantry system. This concerns the creation of Python scripts that can communicate with the ACS controller and camera in the gantry setup via standardized libraries/protocols. 

- Camera, Lens, and Lighting:
In this phase of the project, we will undertake a thorough examination of camera, lens, and lighting components. Our goal is to shortlist and configure these critical elements in the optical system. This process involves a meticulous comparative analysis of different options, taking into account factors such as resolution, focal length, aperture, and illumination intensity. The outcome of this analysis will lead to well-informed recommendations for the selection of specific components that align precisely with the project's requirements. Additionally, we will obtain CAD models of the chosen components, ensuring design compatibility.

- Focusing Technology:
Another aspect of the optical system is the focusing technology. We shortlisted existing focusing technologies available in the market. Subsequently, we conducted an in-depth comparison of these technologies, considering factors like speed, accuracy, and adaptability to the inspection task. The objective is to make a well-informed decision regarding the final selection of the focusing method and associated components. This choice will significantly impact the system's performance, ensuring the utmost precision and reliability in surface inspection.

- Mechanical Frame and Mounting:
In the realm of mechanical design, our focus will be on creating a robust and meticulously engineered frame that seamlessly integrates all the selected components. Our scope in the project is limited to delivering CAD design of the optical inspection system. The mechanical frame design plays a pivotal role in ensuring stability, accuracy, and longevity. This phase of the project will involve careful planning, precise measurements, and the consideration of material choices to construct a frame that can withstand the demands of the inspection process. By designing a solid mechanical frame, we ensure the alignment and coordination of all the elements within the system, thus contributing to its overall functionality and reliability.
In summary, the project scope within "Optics and Illumination" involves a comprehensive evaluation of camera, lens, lighting, and focusing technology components, with a strong emphasis on comparative analysis to make informed selections. On the other hand, "Mechanical Frame and Mounting" encompasses the design and construction of a sturdy frame that will serve as the foundation for integrating these components. These endeavors are crucial steps toward achieving a reliable and high-precision surface inspection system.

- Python Communication:
To control the motion of the gantry stage, NTS uses SPiiPlus motion controller from ACS. It is designed to meet the needs of OEMs with demanding multi-axis motion control applications. The SPiiPlus Motion Control Platform controls ACS products in the and 3rd party EtherCAT devices, providing flexibility for the motion control system designer. ACS supports Modbus communication which is a request-response protocol implemented using a master-slave relationship. In a master-slave relationship, communication always occurs in pairs where one device must initiate a request and then wait for a response—and the initiating device (the master) is responsible for initiating every interaction. The Modbus protocol uses character serial communication lines, Ethernet, or the Internet protocol suite as a transport layer. 
Using the pyModbus library, we can communicate via Modbus with ACS controller using the python. Pymodbus is a full Modbus protocol implementation using a synchronous or asynchronous core.

## Architectural Overview

An architecture diagram provides a visual representation of the intricate interactions among physical components, revealing their connections and roles within the project. It offers a comprehensive overview of the project's hardware, infrastructure, and communication networks.
The inspection system's architecture, as depicted in the following figure , illustrates the physical communication between the gantry system and other optical components, including the camera, lens, and illumination system.

![ISA](https://github.com/farahfadel/NTS_Project/assets/120414397/14800cd8-3f4b-4790-bb9a-2a12a6e395c5)

## Design the optical inspection system
This system is comprised of various mechatronic components, each with a primary purpose: facilitating precise motion control for the purpose of focusing and positioning on the target surface under inspection. The central elements of this setup encompass the camera, lens, and lighting system. Extensive research has been undertaken to identify the optimal camera, lens, and focusing technology that aligns seamlessly with our project objectives. Furthermore, we have developed the most effective illumination method and a customized mounting solution for the gantry, using Computer-Aided Design (CAD). The intricate integration of the inspection system is illustrated in the CAD design provided below.

![CAD10](https://github.com/farahfadel/NTS_Project/assets/120414397/30c721d4-1604-44b2-a6fe-5d168e9dbc08)

## Creation of a Python-based software shell specifically for testing the optical inspection system
To control the motion of the gantry stage, NTS uses SPiiPlus motion controller from ACS. It is designed to meet the needs of OEMs with demanding multi-axis motion control applications. The SPiiPlus Motion Control Platform controls ACS products in the and 3rd party EtherCAT devices, providing flexibility for the motion control system designer. ACS supports Modbus communication which is a request-response protocol implemented using a master-slave relationship. In a master-slave relationship, communication always occurs in pairs where one device must initiate a request and then wait for a response—and the initiating device (the master) is responsible for initiating every interaction. The Modbus protocol uses character serial communication lines, Ethernet, or the Internet protocol suite as a transport layer. 
Using the pyModbus library, we can communicate via Modbus with ACS controller using the python. Pymodbus is a full Modbus protocol implementation using a synchronous or asynchronous core. The library consist of 4 parts:
- Client, connect to your favorite device
- item Server, simulate your favorite device
- Repl, a text based client/server simulator 
- Simulator, a html based server simulator
  
To test the repeatability of an X-Y gantry machine, several steps are required using precision measurement tools and software. First, we select the test points after we determine a set of test points that cover the range of motion and positions the gantry machine will operate in. These points should be spaced out to evaluate repeatability across the entire workspace. Then, after ensuring that the gantry machine is set up correctly and initialized at zero position to establish a reference point. Then, precision measurement tools are used to measure the actual position of the gantry at each test point. Execute a test sequence where the gantry machine moves to each of the predefined test points and stops. Record the actual position of the gantry machine at each point. After making adjustments or performing maintenance, re-run the repeatability test to verify that the improvements have been achieved.


## Summary

In summary, this collaborative project not only serves as a valuable training opportunity for individuals in the field of mechatronics and design but also significantly enhances NTS's capabilities in motion systems and standardized testing. The core goal is to expand the scope of applications for the existing XY-motion platform. At its heart, this project seeks to develop a cutting-edge optical inspection system designed to inspect a glass plate with chrome dots for precise measurement and calibration while also laying the foundation for future expansion into a wider range of surface inspection applications. This innovation aligns with NTS's vision for advanced functionality in motion systems and standardized testing, ultimately strengthening their position in the industry.
