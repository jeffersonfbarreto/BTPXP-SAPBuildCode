
# Exercício 10 - Implante seu aplicativo no SAP BTP, tempo de execução do Cloud Foundry

Neste exercício, você aprenderá como é fácil implantar seu aplicativo diretamente do SAP Business Application Studio no SAP BTP, tempo de execução do Cloud Foundry.

## Exercício 10.1 - Crie Space no Cloud Foundry

Primeiro, você precisa criar o Space em seu ambiente do Cloud Foundry para hospedar seu aplicativo UI5 recém-criado.

1. Abra o SAP BTP Trial abrindo *https://cockpit.hanatrial.ondemand.com/cockpit/#/home/trial* em uma nova guia do navegador e clique em *Go To Your Trial Account*.
![](images/11_01_0010.png)

2. Você será redirecionado para seu SAP BTP Cockpit pessoal, onde suas subaccounts estão listadas. Clique na subaccount *trial*.

![](images/11_01_0020.png)

3. Abra *Spaces* abaixo do item de menu *Cloud Foundry* (expanda *Cloud Foundry* se necessário). Até agora, nenhum espaço foi criado por você dentro deste tutorial (mas um espaço *dev* pode já existir). Clique em *Create Space*.

![](images/11_01_0030.png)

4. No pop-up, insira o nome do Space, por exemplo, *ui5-apps* e deixe a seleção de função como está. Clique em *Create*.

![](images/11_01_0040.png)

5. O Space recém-criado é exibido.

![](images/11_01_0050.png)

6. NÃO clique no nome do Space (isso entraria no Space, do qual não precisamos agora). Se você fez isso, clique na subconta "trial" acima da área de conteúdo para navegar para cima novamente.

## Exercício 10.2 - Assinar o SAP Build Work Zone Service

Para poder exibir aplicativos UI5 implantados, precisamos do serviço "SAP Build Work Zone, standard edition" (anteriormente conhecido como "Launchpad Service") em nossa conta de teste.

1. Para assinar, clique em *Service Marketplace* no lado esquerdo abaixo de *Services* e pesquise o serviço "SAP Build Work Zone, standard edition".

2. Clique no bloco de serviço "SAP Build Work Zone, standard edition" e depois em *Create* no lado direito.

![](images/BTP_10_0010.png)

3. Na lista suspensa vazia chamada "Plan", selecione "standard - Subscription" e clique em *Create*.

![](images/BTP_10_0020.png)

4. Close the "Creation in Progress" popup. If you now click on *Instance and Subscriptions* you'll see that you have subscribed to the Launchpad Service.

![](images/BTP_10_0030.png)

## Exercício 10.3 - Login no Cloud Foundry

Agora você pode fazer login no seu ambiente Cloud Foundry diretamente do SAP Business Application Studio.

1. Abra o SAP Business Application Studio. Clique no botão mais alto na barra lateral esquerda (três linhas horizontais), depois em *Exibir* e selecione *Paleta de comandos...*. (Alternativamente, pressione `CTRL + Shift + P` no Windows/Linux, `Cmd + Shift + P` no Mac.) Em seguida, comece a digitar *CF: Login to cloud foundry* até que você possa ver e clicar na respectiva entrada.
Agora especifique suas credenciais de usuário e faça login.

![](images/11_03_0005.png)

## Exercise 10.4 - Set Organization and Space

After logging in you're asked to specify your desired Cloud Foundry organization and space. Select the *ui5-apps* space you created above and press "Apply":


![](images/11_04_0010.png)

## Exercise 10.5 - Build Your Application

Now it's time to build your application. Yeah!

1. Right-click the `mta.yaml` file in the root folder.

2. Select *Build MTA Project*. The build starts.


![](images/11_06_0010.png)

3. Once the build has finished the terminal will display messages that the MTA archive has been generated and temporary files are cleaned up:


![](images/11_06_0020.png)


## Exercise 10.6 - Deploy Your Application

The build step has created a file named `keepcool-sensormanager_0.0.1.mtar` located under `mta_archives`. This file contains your build.

1. Right-click `sensormanager/mta_archives/keepcool-sensormanager_0.0.1.mtar` and select *Deploy MTA Archive*. Deployment starts.

![](images/11_07_0010.png)

2. Deployment takes some time. Once it is complete, you'll be notified in the terminal.

![](images/11_07_0020.png)

## Exercise 10.7 - Run Your Application on SAP BTP

1. The deployed application can be started from the SAP BTP Cockpit. Go to your trial subaccount and click on the *HTML5 Applications* section at the left hand side. The application is listed there as 'keepcoolsensormanager'. Click on it to start it.

> NOTE: the application is NOT listed among *Applications* in the "ui5-apps" space, but among *HTML5 Applications* in the containing "trial" subaccount!


![](images/11_08_0010.png)

2. Congratulations! You've deployed your UI5 application to the SAP BTP, Cloud Foundry runtime.

![](images/11_08_0020.png)

## Summary
Great job! You've learned how to deploy your UI5 application from SAP Business Application Studio to the SAP BTP, Cloud Foundry runtime. From creating a space in Cloud Foundry, subscribing to the SAP Build Work Zone Service, logging into Cloud Foundry, setting up your organization and space, configuring your application, building and finally deploying your application - you've done it all!

Keep up the good work and stay curious about SAPUI5 as there is still a lot to learn! Find more information and tutorials about SAPUI5 and BTP below.

## Further Information

* UI5 Tutorials: https://sapui5.hana.ondemand.com/#/topic/8b49fc198bf04b2d9800fc37fecbb218
* SAP Tutorials: https://developers.sap.com/tutorial-navigator.html
