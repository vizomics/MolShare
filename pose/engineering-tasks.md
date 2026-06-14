# POSE Phase 1 Engineering Task Inventory

## Goals
- Develop an in-depth understanding of iCn3D, assess its current scalability as a community driven OS framework for Molecular Visualization and Analysis, from the perspective of external contributors (with professional-level coding skills)
- Establish an independent engineering testbed to investigate, isolate and enhance iCn3D components; the immersive IR2 platform from Inside Reality was chosen because of the similarity of its architectural foundation (Three.js), as well as its capability to test advanced VR capabilities for education and collaboration via group immersion and advanced navigation, which was available out of the box (IR2 was made available free of charge for this project)
- Present results at ISMB/ECCB 2025 in Liverpool to collect feedback from research community
- Use insights gained through iCn3D POSE 1 engineering tasks to propose way forward for POSE 2 grant proposal to establish a rapidly growing community around iCn3D based on a fork of the latest iCn3D implementation, using advanced rendering components of the Mol* framework
- Experiment with concepts for fusing both frameworks, iCn3D and Mol*, identify architectural challenges and assess feasibility of such an integration

## Task Inventory

### Core Tasks

1. **Separated architectural components such as rendering and user interface**  
   Why: Using UI of external app instead of iCn3D UI; without UI components, renderer would not work  
   What: Made copy of iCn3D, removed UI portions  
   Learnings: Make more modular architecture, clear separation of concerns
   *Impact*: Any external app can now embed iCn3D renderer cleanly.

2. **Upgraded Three.js version to the latest (iCn3D used 151, jumped to 177)**  
   Why: Three.js version used by IR2 and iCn3D were incompatible  
   What: Major differences in color and light management, necessitating rewrite of shaders, fixing breaking changes  
   Learnings: Always keep up to date on framework dependencies
   *Impact*: Modern rendering quality + compatibility with current VR stacks.

3. **Improved rendering quality and performance for large models in external app**  
   Why: Rendering quality of iCn3D needed to be improved based on feedback  
   What: Introduction of more modern PBR lighting model  
   Learnings: Re-using external viewing capabilities improved quality for free

4. **Removed third-party dependencies wherever possible**  
   Why: enable own choices for use of frameworks, e.g. UI in form of JQuery  
   What: removed jQuery and iCn3D UI components  
   Learnings: Requirement for higher reuse by diverse community requirements

5. **Implemented support for all iCn3D parsers in external app**  
   Why: Test parsers as potential components for third party apps  
   What: Used IR2 as testbed to integrate components to be tested  
   Learning: Now parsers can be fully reused in any other context, individual component without external dependencies

### Additional Tasks

6. **Experimental implementation of Property Mapping and Property Filtering**  
7. **Exporter with texture mapping to glTF, reuse tested in Unreal Engine**  
8. **App-style change of molecule target for switching, rather than reloading a page, using URL sharing**  
9. **Implemented 6 DOF movements for precise and intuitive navigation (iCn3D standard does not allow all views)**  
10. **Align/Vast+ implementation and server proxy due to CORS blockage**  
11. **Interactions, Highlighting and Show/Hide toggle**  
12. **Prototype implementation of MLP**  
13. **Addition of easy-to-use dat.GUI User Interface (popular lib used often by beginners)**  
14. **Fog implementation for Group Immersion**  
15. **Headlamp and three-point lighting for Group Immersion**  
16. **Experimentation with BCF for application independent View Exchange and Commenting**  
17. **Transpiling of Mol* components for use as iCn3D Rendering Components**  
18. **Translation of Mol* generated geometry into Three.js compatible assets for direct use in iCn3D**  
19. **Integration of Mol* model formats for PDB, CIF, mmCIF, binaryCIF**  
20. **Support for MolViewSpec, i.e. generating iCn3D based structures that renders Mol* geometry with direct parsing**  
21. **Use Mol* (mol-geo) for key molecular representations**

Last updated: 2026-06-14
