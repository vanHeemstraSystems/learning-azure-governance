[![Quarto Publish](https://github.com/vanHeemstraSystems/learning-azure-governance/actions/workflows/publish.yml/badge.svg)](https://github.com/vanHeemstraSystems/learning-azure-governance/actions/workflows/publish.yml)

learning-azure-governance
# Learning Azure Governance

Part of "Learning" at https://github.com/vanHeemstraSystems/learning

Can be read as "Learning - Azure Governance" at https://app.gitbook.com/o/mhLLz4wi0Rs2JPkBGvCd/s/quwM6FgG3FcADTsy3XGb/

Can be browsed as "Learning - Azure Governance" at https://vanheemstrasystems.github.io/learning-azure-governance/

Documentation of this repository is automatically done with Quarto using GitHub Actions as described at https://github.com/vanHeemstraSystems/quarto-to-github-pages/blob/main/300/300/README.md

Based on "C4-PlantUML" at https://github.com/plantuml-stdlib/C4-PlantUML

C4-PlantUML combines the benefits of PlantUML and the C4 model for providing a simple way of describing and communicate software architectures.

Based on "C4-PlantUML" at https://github.com/plantuml-stdlib/C4-PlantUML

Based on "Intro to C4 Architecture Diagrams and C4 PlantUML extension" at https://www.youtube.com/watch?v=n-e1FDAtBuM

Based on "C4 Model with PlantUML" at https://medium.com/software-architecture-foundations/software-architecture-modeling-with-c4-model-e9e61d952121

Based on "Diagrams as Code – C4 diagrams with Azure icons" at https://andysprague.com/2023/01/11/diagrams-as-code-c4-diagrams-with-azure-icons/

Based on "sprague.andy.plantuml.c4" at https://github.com/andysprague44/sprague.andy.plantuml.c4

Based on "PlantText - A Free PlantUML Online Editor" at https://www.planttext.com/

Based on "Plant UML in Visual Studio Code // Config file" at https://stackoverflow.com/questions/66709936/plant-uml-in-visual-studio-code-config-file?rq=1

C4-PlantUML combines the benefits of PlantUML and the C4 model for providing a simple way of describing and communicate software architectures. The addition of Azure icons helps to visualize Azure systems too.

## 100 - Introduction

- Read "Diagrams as Code – C4 diagrams with Azure icons" at https://andysprague.com/2023/01/11/diagrams-as-code-c4-diagrams-with-azure-icons/

- Read "How to use PlantUML in VSCode" at https://spencerfeng.medium.com/how-to-use-plantuml-in-vscode-389896215876

## 200 - Requirements

- PlantUML Extension for Visual Studio Code

**How to install**
Launch VS Code Quick Open (Ctrl+P), paste the following command, and press enter.

```
ext install plantuml
```

Also Graphviz is required. On Linux you can install Graphviz as follows:

```
$ sudo apt install graphviz
```

Install extension 'plantuml' and leave all default settings. Test correct installation by opening testdot.wsd and previewing with Alt + D. Should see preview with PlantUML version, and message "Installion seems OK". 

**Note**: If you have not installed GraphViz first, you may get an error as a message instead of an OK.

### To update diagram

- Open the relevant .wsd file
- Preview with Alt + D (or, right-click -> Preview Current Diagram)
- Once done, right click - > Export Current Diagram, choose png format
- View rendered diagram in 'out' folder

### To generate custom sprites

See <https://plantuml.com/sprite> e.g.
- java -jar plantuml.jar -encodesprite 16z prius.svg   

If plantuml.jar is not on your PATH, look for it in a folder 

java -jar "C:\Program Files\PlantUML\plantuml.jar" -encodesprite 16z prius.svg 

## 300 - Building Our Application

Preview Diagram, whilst your cursor is active inside of your pulm file between the @startuml and @enduml syntax Press Alt + D to start PlantUML preview (option + D on MacOS).

Also you can generate images from your puml files (e.g. ```C1_SystemContext.wsd```) as follows:

```
$ cd docs/diagrams
$ java -jar plantuml-1.2023.10.jar C1_SystemContext.wsd
```

**NOTE**: If your diagram is clipped by the image size, you can extend the size of the image (to say 8192 pixels) as follows:

```
$ java -DPLANTUML_LIMIT_SIZE=8192 -jar plantuml-1.2023.10.jar C1_SystemContext.wsd
```

An updated image with the name of the diagram (see first line inside file, e.g. "@startuml C1_Azure_Governance_SystemContext") will be autogenerated a subdirectory (e.g., ```C1_SystemContext```) in the ```out``` directory with the latest changes reflected, e.g. C1_Yieldstar_PnP_Platform_SystemContext.png.

![C1_Azure_Governance_SystemContext.png](https://github.com/vanHeemstraSystems/learning-azure-governance/docs/diagrams/out/C1_SystemContext/C1_Azure_Governance_SystemContext.png)

C1_Azure_Governance_SystemContext.png

## 400 - Conclusion

Requirements:

- GraphViz (install as follows: ```$ sudo apt install graphviz```)
- Java Runtime version 1.8.*, check with ```java -version```

Generate images as follows:

1) [Download](https://plantuml.com/download) and place the plantuml-1.2023.10.jar file inside docs/diagrams directory.

2) Run the following command from your terminal whilst inside docs/diagrams directory:

```
$ java -jar plantuml-1.2023.10.jar C1_SystemContext.wsd
```

3) A new edition of an image called ```C1_Azure_Governance_SystemContext.png``` will be generated in a subdirectory ```C1_SystemContext``` of the adjacent ```out``` directory, reflection the last changes to C1_SystemContext.wsd file.

You can follow the same instructions for all C4 Models: Context, Container, Component, Code.

See "The C4 model for visualising software architecture" for more information on C4 Models at https://c4model.com
