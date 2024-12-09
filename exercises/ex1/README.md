[![solution](https://flat.badgen.net/badge/solution/available/green?icon=github)](https://github.com/SAP-samples/teched2023-AD265/tree/code/exercises/ex1)
[![demo](https://flat.badgen.net/badge/demo/deployed/blue?icon=github)](https://sap-samples.github.io/teched2023-AD283v/ex1/test/flpSandbox-cdn.html?sap-ui-xx-viewCache=false#keepcoolsensormanager-display)

# Exercício 1 - Configuração do projeto usando o SAP Business Application Studio

Neste exercício, você criará um novo aplicativo UI5 com base em um modelo fornecido pelo SAP Business Application Studio.

## Cenário

Seu cliente "Keep Cool, Inc." é um operador de várias casas de gelo em todo o país. Recentemente, eles foram atualizados com novos sensores com conexão à Internet, para que seus valores de medição estejam disponíveis como um serviço. Para fazer uso desses dados e melhorar seus fluxos de trabalho internos, a empresa nos pediu para fornecer um aplicativo aproveitando esses dados do sensor, visualizá-los e fornecer uma visão geral do estado atual de cada sensor, para que eles possam reagir rapidamente a quaisquer problemas.

## Exercício 1.1 – Criar um novo aplicativo UI5

Depois de concluir essas etapas, você terá criado seu primeiro aplicativo UI5.

1. Clique em *New Project from Template* na págna *Get Started*.
    * [Opcional] Se você fechou a página *Get Started* , clique no botão superior (três linhas horizontais, também conhecidas como 'ícone de hambúrguer') na barra de navegação à esquerda e selecione *Help* e, em seguida, selecione *Get Started* para reabrir a página.</ul>

<br>![](images/01_01_0010.png)<br><br>

2. Clique no *SAP Fiori generator* como modelo e clique em *Start*.

<br>![](images/01_01_0012.png)<br><br>

3. Na etapa *Template Selection*, selecione *Basic* como modelo de aplicativo e clique em *Next*.

<br>![](images/01_01_0013.png)<br><br>

4. Selecione *None* como Data Source, pois você desenvolve sem uma fonte de dados externa. Clique em *Next*

<br>![](images/01_01_0014.png)<br><br>

5. Insira *Sensors* como view name. (Mesmo que esta etapa seja intitulada "Entity Selection", você não seleciona um conjunto de entidades, pois começa sem um serviço de dados).
   
<br>![](images/01_01_0015.png)<br><br>

7. Insira as seguintes configurações na etapa *Project Attributes*:
    1. Insira *sensormanager* como *Module name*.
    2. Insira *Sensor Manager* como *Application title*.
    3. Insira *keepcool* como *Application namespace*.
    4. Você pode manter a descrição padrão.
    5. Mantenha o caminho da pasta do projeto como */home/user/projects*
    6. Mantenha a versão mais recente disponível da UI5 selecionada.
    7. Defina *Add deployment configuration* como *Yes*.
    8. Defina *Configure advanced options* como *Yes*. Novas opções aparecem abaixo.
    9. Na parte inferior, defina *Enable TypeScript* como *Yes* para implementar o aplicativo usando TypeScript.
    10. Clique em *Next*.
<br>![](images/01_01_0016.png)<br><br>
<br>![](images/01_01_0016b.png)<br><br>


8. In the next step, select *Cloud Foundry* as target, leave the Destination name to "None" and make sure that the *Yes* is checked for adding the application to the application router and click *Finish*.  </ul>

<br><br>![](images/01_01_0017.png)<br><br>

8. The project is now being generated, and a notification window will appear in the lower right corner once the process has completed. Wait for the message that the project has been generated!

9. A warning popup may tell you that the project "is not in current workspace"; in this case, select the left button "Add project to workspace".

<br><br>![](images/01_01_0018.png)<br><br>

10. Once the process has completed, the *Storyboard* opens, which will get useful for larger projects with external data sources. We don't make use of it in this tutorial. Instead, you can open the *Application Info* page to get an overview of the project and the list of things you can do with the project. To do so, open the Command Palette using the command `CTRL + Shift + P` (`Cmd + Shift + P` on Mac), then filter for "*Fiori: Open Application Info*" and select it.


![](images/01_01_0019.png)

## Exercise 1.2 - Try out the generated Application

It's time for a first preview of your newly created application!

1. To start the application, press the green *play* icon ("Run and Debug") on the right side of the header bar.

![](images/01_02_0010.png)

2. In the dropdown that opens in the header, select the first entry "Start sensormanager" (*without* "Local"). (For subsequent starts this selection will be remembered.)

![](images/01_02_0020.png)

3. After a few moments, the application should start up:

![](images/01_02_0030.png)

## Summary
Well done! You have successfully created and previewed a new UI5 application using SAP Business Application Studio.

You're now ready to leverage sensor data for "Keep Cool, Inc.". This foundational step puts you on track to improve their workflow and react quickly to any sensor issues. Keep up the good work as you proceed to [Exercise 2 - Add First Content](../ex2/README.md).
