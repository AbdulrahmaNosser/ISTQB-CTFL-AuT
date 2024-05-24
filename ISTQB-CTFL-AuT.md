# 1 Introduction
This is a summary of ISTQB-CTFL-AuT syllabus version 2.0.2. It is based on the learning objectives that are covered in the exam and is not a substitute of the original document. I recommend going through the syllabus in full then refer to this document as a review. 
![[Cognitive levels]]
**Exam structure**
![[Pasted image 20231010071924.png]]
>[!abstract] Useful links
>[More information](https://www.istqb.org/certifications/automotive-software-tester)
>[Syllabus](https://istqb-main-web-prod.s3.amazonaws.com/media/documents/ISTQB-CT-AuT_Syllabus_v1.0_2018.pdf)
>
>[Exam 1](https://astqb.org/assets/documents/CTFL_AuT_2018_engl_SAMPLE_PAPER.pdf)
>[Answers 1](https://astqb.org/assets/documents/CTFL_AuT_2018_engl_SOL_SAMPLE_PAPER.pdf)
>
>[Exam 2](https://istqb-main-web-prod.s3.amazonaws.com/media/documents/ISTQB_CT-AuT_Sample-Exam-A-Questions_v2.2.pdf)
>[Answers 2](https://istqb-main-web-prod.s3.amazonaws.com/media/documents/ISTQB_CT-AuT_Sample-Exam-A-Answers_v2.2.pdf)
## 1.1 Requirements from divergent project objectives and increasing product complexity (K2)
- Increasing number of models & complexity
- Increasing number of configurations
- Increasing range of functionality
- Increased quality requirements
## 1.2 Project aspects influenced by standards (K1)
- Time
- Cost
- Quality
- Risk (project, product)

> [!Note]
> Standards increase the efficiency of processes, it reduces the development time or cost at a stable quality.
## 1.3 The six generic phases in the system lifecycle (K1)
1. **Concept** (test planning )
2. **Development** (test analysis, design, implementation, execution, evaluation and report)
3. **Production** (end of line test)
4. **Utilization** (no test activities)
5. **Support** (maintenance test)
6. **Retirement** (migration test)
## 1.4 The contribution/participation of the tester in the release process (K1)
- Tests the test item
- Provide feedback about the test item
- Provides recommendations
	- Implementation order
	- SW release
	- Further testing 
# 2 Standards for the testing of E/E systems
## 2.1 Automotive SPICE (ASPICE)
### 2.1.1 Design and structure of the standard
#### 2.1.1.1 The two dimensions of ASPICE (K1)
1. [[#2.1.1.2 Process categories in the process dimension (K1)|Process dimension]]
2. [[#2.1.1.3 Capability levels in the capability dimension (K2)|Capability dimension]]
#### 2.1.1.2 Process categories in the process dimension (K1)
ASPICE groups the processes into **8** groups within **3** process categories:
- Primary processes
	- Acquisition **ACQ**
	- Supply **SPL**
	- System engineering **SYS**
	- Software engineering **SWE**
- Organizational processes
	- Management **MAN**
	- Process improvement **PIM**
	- Reuse **REU**
- Supporting processes **SUP**
#### 2.1.1.3 Capability levels in the capability dimension (K2)
- **Level 0 incomplete**: does not exist or does not achieve its purpose.
- **Level 1 performed**: performed without planning.
- **Level 2 managed**: planned, performed, and adapts to changes. 
- **Level 3 established**: process is standardized and findings are used for improvement.

>[!info]-
>Informative levels not considered in the exam
> - **Level 4 Predictable**
> - **Level 5 Optimized**
> These levels are **NOT** requested by OEMs to be performed.
### 2.1.2 Requirements of the standard
#### 2.1.2.1 Test specific processes (K1)
1. **SW unit verification** (SWE.4), asses against detailed design (SWE.3).
2. **SW Integration test** (SWE.5) assessed against SW architecture (SWE.2).
3. **SW qualification test** (SWE.6) assessed against SW requirements (SWE.1).
4. **System integration test** (SYS.4) assessed against system architecture (SYS.3).
5. **System qualification test** (SYS.5) assessed against system requirements (SYS.2).
![[#^e6e1f3]]
#### 2.1.2.2 Assessment levels and capability indicators (K2)
**From levels 0 to 3 the processes is assessed based on the following process attributes:**
- PA 1.1: Process performance (the tester is oriented by means of the fundamental test process).
- PA 2.1: Performance management (the tester plans, supervises and controls the test activities among other things).
- PA 2.2: Work product management (the tester checks the quality of the test documentation among other things).
- PA 3.1: Process definition (the person responsible for the test process defines a general project strategy among other things).
- PA 3.2: Process deployment (the tester applies the test strategy defined in PA 3.1).

**Each process attribute is assigned an implementation level indicator as follows:**
- N (None): not fulfilled (0% ≤ PA ≤ 15%)
- P (Partly): partly fulfilled (15% < PA ≤ 50%)
- L (Largely): largely fulfilled (50% < PA ≤ 85%)
- F (Fully): fully fulfilled (85% < PA ≤ 100%)

>[!note]
>For a process to reach a certain capability level, the indicators of the capability level to be achieved must be “largely fulfilled (L)”. The indicators of the lower capability levels must be “fully fulfilled (F)”.

>[!example]
>What is the ASPICE level based on this table
>>![[Pasted image 20231007182835.png]]
>>>[!Success]- Answer
>>Here the ASPICE level is 0
#### 2.1.2.3 Test strategy and regression test strategy (K2)
ASPICE requires a test strategy for each test specific process. Early testing and cost define which tests should be executed at which test level and test environment.
#### 2.1.2.4 Test documentation in ASPICE (K1)
ASPICE requires many work products (WP) some of which are:
- **WP 08-50 Test specification**: test design, test case and test procedure specification
- **WP 08-52 Test plan & strategy**: according to ISO/IEC/IEEE 29119-3 and included strategy WP 19-00
- **WP 13-50 Test result**: test log, incident/deviation report and test summary report
#### 2.1.2.5 Verification strategy and criteria for unit verification (SWE.4) (K3)
>[!Note]
>Verification of the software units (SWE.4) ASPICE requires a verification strategy. SWE.5/SWE.6/SYS.4/SYS.5 require a test strategy.
>Test strategy considers dynamic testing only, while verification strategy considers static testing also.

If a unit is changed the strategy of unit verification will include regressions strategy.
- Confirmation testing
- Regression testing
- static and dynamic testing

The following criteria are possible criteria for the verification of units:
- Unit test cases
- Test coverage
- Tool supported static analysis
- Code reviews
#### 2.1.2.6 Traceability in Automotive SPICE (ASPICE) (K2)
**Bidirectional traceability is required to:**
- Analyze the impact
- Evaluate coverage
- Track execution
- Ensure consistency
	- Textual
	- Semantically

**There are 2 types of traceability:**
- **Vertical**: stakeholder requirements linked in the SW components over all development levels.
- **Horizontal**: between WP of development and WP of testing.

Bidirectional traceability between change requests and work products affected by the change requests.
## 2.2 ISO 26262
### 2.2.1 Functional safety and safety culture
#### 2.2.1.1 Objective of functional safety for E/E systems (K2)
Risk of erroneous action is high due to the complexity of the system. Mitigate their possible impact to an acceptable level of risk.
>[!quote] Functional Safety definition
>The absence of unreasonable risk due to hazards caused by malfunction behaviour of E/E systems.
>
^4d8290

>[!info]-
>Safety in the working environment and cybersecurity are not in the focus of ISO 26262. Yet cybersecurity contributes to product safety.
#### 2.2.1.2 Contribution of the tester to the safety culture (K1)
The tester participate throughout the software development life cycle.
### 2.2.2 Integration of the tester in the safety lifecycle (K2)
**Safety lifecycle phases**:
1. **Product concept**: Test planing mostly and search for risks but occurs in all phases.
2. **Product development**: Test execution mostly occurs between the transfer of sub phases of product development.
3. **Product production and maintenance**.

The tester works mostly in the first two phases. Changes in the third phase cause a return to the first or second phase.
  
**Tester participation**:
- Test planning
- Test case design
- Test techniques selection
- Test execution
- Test reporting
### 2.2.3 Structure and test specific parts of the standard
#### 2.2.3.1 Design and structure of the standard (info)
![[Pasted image 20231008195543.png]]
#### 2.2.3.2 Relevant volumes (parts) for the tester (K1)
1. **VOL.4** System development _(most relevant)_.
2. **VOL.5** Hardware development.
3. **VOL.6** Software development. _(most relevant)_
4. **VOL.8** Support processes.
### 2.2.4 The influence of criticality on the extent of the test
#### 2.2.4.1 The criticality levels of ASIL (K1)
> [!quote]  ASIL definition
> (”Automotive Safety Integrity Level“) is a measure for the required risk reduction by measures of the [[#^4d8290|Functional Safety]].

**Criticality levels**:
1. QM (quality management)
2. ASIL A
3. ASIL B
4. ASIL C
5. ASIL D

 >[!Note]  Criticality level assignment matrix
![[Pasted image 20231008203147.png]]
#### 2.2.4.2 Influence of ASIL on test techniques, test types and the extent of the test (K2)
| Recommendation level | Description                                                                                |
| -------------------- | ------------------------------------------------------------------------------------------ |
| ++    (highly recommended)     | **Must be used** or an alternative could be used with evidence of equal or better results documented |
| +               (recommended)  | **Should be used** or an alternative could be used or could be discarded with justification          | 
| o            (optional)        | **Can be used**, Usually not covered without justification                    |
### 2.2.5 Application of content from CTFL® in the context of ISO 26262 (K3)
>[!question] Which tests must be applied for ASIL C?
>![[test techniques ASIL recommendation example.png]]
>>[!Success]- answer
>>> **2, 3, 4b** 
## 2.3 [[AUTOSAR]]
>[!quote] AUTOSAR 
>**AUT**omotive **O**pen **S**ystem **AR**chitecture
### 2.3.1 Objectives of AUTOSAR (K1)
1. Portability (transferability).
2. Scalability.
3. Supports different functional domains.
4. Open architecture, that is maintainable, adjustable and expandable.
5. SW availability, reliability, and maintainability.
6. Sustainable use of natural resources.
7. Collaboration.
8. Standardization of basic software functionality.
9. Support of automotive standards for vehicles and state of the art technologies.
### 2.3.2 General structure of AUTOSAR (K1)
1. **BSW** HW oriented layer with standardized basic SW.
2. **RTE** AUTOSAR runtime environment that controls data exchange between SW units.
3. **SW-C** application layer that is independent from HW.
### 2.3.3 Influence of AUTOSAR on the work of the tester (K1)
- SW unit and SW integration tests are run in SiL with virtual BSW and RTE.
- SW test and SW integration tests on an ECU with real RTE.
- AUTOSAR acceptance test, ensures the compliance of AUTOSAR functionality at the communication and application levels (optional).
- System integration test.
## 2.4 Comparison
### 2.4.1 Objectives of ASPICE and ISO 26262 (K1)
**ASPICE**: Determines the capability of product development process.

**ISO 26262**: Presents requirements and processes, to avoid risks from systematic failures in the development and hardware failures in the operation.
### 2.4.2 Comparison of the test levels (K2)
| ISTQB                   | ISO 26262                                        | ASPICE 3.0                             |
|:----------------------- | ------------------------------------------------ | -------------------------------------- |
| Acceptance test         | Safety validation                                | No equivalent                          |
| System of systems test  | Item integration and test                        | System qualification test (SYS.5)      |
| System integration test | Item integration and test                        | System integrations test (SYS.4)       |
| System test             | Verification of the Software safety requirements | Software qualification test (SWE.6)    |
| Component integration   | and Software integration and test                | Software integration test (SWE.5) |
| Component test          | Software-Unit-Test                               | Software unit verification (SWE.4)     |
![[Pasted image 20231013185410.png]]
# 3 Testing in a virtual environment
## 3.1 Test environment in general
### 3.1.1 Motivation for a test environment in the automotive development (K1)
1. Start testing as early as possible.
2. Test before the product or ECU availability.
3. Test scenarios that are difficult to reproduce in real world.
### 3.1.2 General parts of a test environment (K1)
- **Hardware** (computer, test bench, development kit, …).
- **Software** (operating system, simulation software, environment models).
- **Facilities of communication** (access to networks, data logger).
- **Tools** (oscilloscope, measuring tools).
- **Laboratory** (protection from electromagnetic radiation and noise).
## 3.1.3 Differences between Closed-Loop and Open-Loop (K2)
#### 3.1.3.1 Open-Loop-System
In an open-loop system, the outputs of the system have no relation to the inputs. The system is open
ended and there is no feedback. In this case the inputs of the test item are directly defined by the tester
in the test procedure.
Preferred for for test items with reactive behaviour or if it mirrors a state machine.
#### 3.1.3.2 Closed-Loop-System
>[!info]-
>Also known as in-the-loop.

Outputs is linked directly or indirectly to inputs via an environment model.
Used to test control systems and models.
### 3.1.4 Essential interfaces, databases and communication protocols of a electronic control unit (K1)
Analogue and digital inputs
To access diagnosis functions in the control unit the following protocols could be used:
- ASAM MCD2 D.
- Open Diagnostic Data Exchange.
- Unified Diagnostic Services.
## 3.2 Testing in XiL test environments
- Model in the Loop (MiL),
- Software in the Loop (SiL),
- Processor in the Loop22 (PiL),
- Hardware in the Loop (HiL) and
- Vehicle in the Loop23 (ViL)
## 3.2.1 Model in the Loop (MiL)
#### 3.2.1.1 Structure of a MiL test environment (K1)
1. Test item (model)
2. Simulation software.
3. Test environment (modeled in the same development model might include an environmental model)
4. Computer.

The tester can observe the test item via access points which can be placed an any of the models mentioned.
#### 3.2.1.2 Application areas and boundary conditions of a MiL test environment (K2)
**Application areas**:
- Testing functional system during development.
- Test single component or an entire model.
- Testing over all development levels at the early phase of development (left side of the V-Model).

**Boundary conditions**:
Aspects of reality and environmental factors are very complex. The execution times for the models also increases disproportionately. Therefore, the effort to implement a MiL test environment is no longer worthwhile from a certain phase of the development.
Not common to enable the environment model to simulate bus or diagnosis functions or physical behaviour (such as cable breaks or shorts). These tasks can be carried out more easily and at less cost with other test environments.
Test execution does not take place in real time.
The tester can pause the simulation at any time to execute detailed analysis and assessments.

### 3.2.2 Software in the Loop (SiL)
#### 3.2.2.1 Structure of a SiL test environment (K1)
1. Test item (compiled code)
2. Computer
3. Wrapper
4. Environment model

The computer does not need special hardware.
The wrapper defines the access points to the test item but does not perform its functional tasks.
#### 3.2.2.2 Application areas and boundary conditions of a SiL test environment (K1)
If the code is generated from a model, then its behavior could be different from the model due to the following differences between them:
1. Data types
2. Memory spaces

Same as MiL, this is a simulation time test, which could be faster or slower than a real time test. This enables the tester to pause the simulation to analyze.
**Test types could be done in SiL**:
1. Functional
2. Interface
3. Regression

**Test types dependant on HW that cannot be evaluated in SiL**:
1. Performance
2. Reliability
### 3.2.3 Hardware in the Loop (HiL)
#### 3.2.3.1 Structure of a HiL test environment (K1)
1. Power supply.
2. Real time capable computer for the environment model to run on.
3. Parts that are not implemented in the environment model.
4. Signal processor.
5. Fault insertion unit ([[ISTQB-CTFL-AuT#4.2.3 Fault injection testing (K2)|FIU]]).
6. Breakout box as an additional access interface in the cable harness.
7. Bus simulation.
#### 3.2.3.2 Application areas and boundary conditions of a HiL test environment (K2)
**HiL test environment can be used for**:
1. Component tests (testing a single ECU for its functionality).
2. Integration tests.
3. System tests (testing a combination of ECUs for data exchange between them).
4. Functional and non-functional tests for SW & HW.

HiL testing is always real time, pausing is not possible, thus a real time capable computer is needed to collect and send signals
### 3.2.4 Comparison of the XiL test environments
#### 3.2.4.1 Advantages and disadvantages of testing in the XiL test environments (K2)
| Criteria                                  | MiL                                                            | SiL                                         | HiL                          |
| ----------------------------------------- | -------------------------------------------------------------- | ------------------------------------------- | ---------------------------- |
| Reality                                   | Low (Abstracted characteristics. Focus on logic and structure) | Medium (Compiled actual SW without HW)      | High (SW integrated with HW) |
| Time and effort of debugging              | Low                                                            | Medium                                      | High                         |
| Effort for implementation and maintenance | Low (env model)                                                | Medium (env model & wrapper)                | High (env model & HW wiring) |
| Effort for test preparation               | Low                                                            | Medium                                      | High                         |
| Necessary level of test item maturity     | Low                                                            | Medium                                      | High                         |
| Level of detail of test basis             | Medium                                                         | Medium to High                              | High                         |
| Access to the test item                   | High (all signals of the model can be observed and controlled) | Medium (only wrapper signals are available) | Low (HW signals or through Com protocols)                             |
#### 3.2.4.2 Allocation of test cases to one or more test environments (K3)
#### 3.2.4.3 Classification of the XiL test environments (MiL, SiL, HiL) in the general V-model (K1)
![[Pasted image 20230930174923.png]] ^e6e1f3
* MiL for the system design
* SiL for unit and integration
* HiL for system test
With a correct assignment of the test environment to the test levels, the entire test process can be optimized according to the following three aspects:
- Minimizing the product risks:
	- Finding test level specific failure types (for example performance tests at system level within a HiL environment).
- Minimizing the test cost
	- For every test type the adequate test levels are required.
	- Transfer of tests to earlier, less costly and virtual test levels.
- Conformity to standards
	- ISO 26262 method tables recommend test environments depending on ASIL.
# 4 Automotive-specific [[ISTQB-CTFL#3 Static Testing |static]] and [[ISTQB-CTFL#3.1.3 Differences between Static and Dynamic Testing |dynamic]] test techniques
## 4.1 [[ISTQB-CTFL#3 Static Testing |Static test]] techniques
### 4.1.1 The MISRA-C: 2012 Guidelines (K2)
**Objectives of MISRA-C guidelines**:
* Avoid anomalies in the software
* Improving maintainability
* Improving portability

**Two types of guidelines**:
1. Verifiable **rules** by static analytic tools (source code does not include nested comments).
2. **Directives** are not entirely verifiable by static analytic tools (sufficient documentation of the implementation).

**Levels of obligation**:
* **Advisory** guidelines should be followed by the developer if the effort is appropriate.
* **Required** guidelines may only be neglected by the developer if he can conclusively explain it.
* **Mandatory** guidelines must be followed by the developer. Exceptions are not allowed.
### 4.1.2 Quality characteristics for reviews of requirements (K3)
* **Verifiable**: Each requirement can be verified by static or dynamic tests.
* **Unambiguous**: Each requirement contains clear test conditions.
* **Consistent**: Each requirement is consistent in itself and with other requirements.
* **Complete**: Each requirement considers all possible cases (also error, abort and exception scenarios). At the same time, all tables and diagrams used are labelled; abbreviations and terms used are defined.
* **Traceable**: Each requirement is clearly marked (for example by an ID).
* **Bounded**: (for a set of requirements): It is clearly defined, what is the scope to be developed and tested.
* **Singular**: No requirement can be divided into sensible partial requirements.

## 4.2 [[ISTQB-CTFL#3.1.3 Differences between Static and Dynamic Testing|Dynamic test]] techniques
### 4.2.1 Condition testing, multiple condition testing, modified condition/decision testing (K3)
> [!question]- Why MC/DC
> To test only important combinations of conditions and limit test costs.
> > [!abstract]- How 
> > By extending branch and [[ISTQB-CTFL#4.3.2 Decision Testing and Coverage|decision coverage]] by requiring that each condition should affect the decision outcome independently.
> > <iframe width="560" height="315" src="https://www.youtube.com/embed/DivaWCNohdw?si=DHP89yn3hlC7f3B_&amp;start=48" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
### 4.2.2 Back-to-Back-Testing (K2)
> [!info] AKA comparative test
Is more of an approach to testing than a test design technique.
> > [!abstract]- How 
> > By executing the same test case on all variants and compares the results. For example:
> > - Different versions of the same SW
> > - Automatically generated code vs manual coding
### 4.2.3 Fault injection testing (K2)
> [!info]
   More of an approach to testing than a test design technique. Tests error handling serve the purpose of making the system react to internal and external defects in a robust and safe way.

>[!abstract] How
> By selectively inserting defects into the system at the following points:
> - **External components**: test for detection of implausible values from sensors.
> - **Interfaces**: short circuits or lost messages.
> - **Software faults**: system detection and reaction to internal defects.
### 4.2.4 Requirements-based testing (K1)
The steps of requirements-based testing are as follows:
1. Analyze the requirements.
2. Derive test conditions.
3. Design test cases.
4. Execute.
5. Analyze results to refine the tests.

> [!warning]
> - Incompleteness or inconsistency of requirements will reflect on the tests.
> - Over detailing requirements hinders testers ability to test all requirements fully.
### 4.2.5 Context-dependent selection of test techniques (K3)
ISO 26262 suggests test techniques depending on the ASIL level. The techniques choice is also influenced by the following factors:
- State of the art
- Test basis
- Risk
- Test level