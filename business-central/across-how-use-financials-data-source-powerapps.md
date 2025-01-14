---
title: Utilisez vos données pour créer une application | Microsoft Docs
description: Vous pouvez rendre vos données Business Central disponibles sous forme de source de données et spécifier une URL OData de vos services Web pour générer une application métier à l’aide de Power Apps.
author: jswymer
ms.topic: conceptual
ms.service: dynamics365-business-central
ms.search.keywords: 'OData, Power App, SOAP'
ms.date: 04/01/2023
ms.author: jswymer
---
# Connexion à vos données Business Central pour générer un application professionnelle à l’aide de Power Apps

Vous pouvez rendre vos données [!INCLUDE[prod_short](includes/prod_short.md)] disponibles sous forme de source de données dans Power Apps.  

> [!TIP]  
> La documentation Power Apps supplémentaire et nos exemples d’applications Power App présentés lors de l’événement de lancement [!INCLUDE[prod_short](includes/prod_short.md)] seront publiés ici ultérieurement dans le cadre de la 1re vague 2023. Pour en savoir plus, rendez-vous sur [Démarrer avec d’autres exemples de modèles Power Automate et Power Apps](/dynamics365/release-plan/2023wave1/smb/dynamics365-business-central/get-started-more-sample-power-automate-templates-power-apps).

## Conditions préalables

Vous devez disposer d’un compte valide avec [!INCLUDE[prod_short](includes/prod_short.md)] et avec Power Apps.  

## Ajouter [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données dans Power Apps

1. Dans votre navigateur, accédez à [powerapps.microsoft.com](https://powerapps.microsoft.com/), puis connectez-vous.
2. Sur la page d’accueil, dans la section **Commencer à partir des données**, choisissez la vignette **Autres sources de données**.  

    Cette étape permet d’ouvrir Power Apps Studio. Lors de la première connexion, vous devez spécifier le pays / la région.  
3. Dans la liste des connexions disponibles, choisissez **Business Central**, puis choisissez le bouton **Créer**.

    Power Apps se connectera à votre [!INCLUDE[prod_short](includes/prod_short.md)] à l’aide des informations d’identification avec lesquelles vous vous êtes connecté. Si vous n’êtes pas un administrateur de votre [!INCLUDE[prod_short](includes/prod_short.md)], vous devrez peut-être vous connecter avec un autre compte.  

4. Power Apps affiche la liste *Environnements et des sociétés* disponibles à partir de [!INCLUDE[prod_short](includes/prod_short.md)]. Choisissez l’environnement et la société contenant les données auxquelles vous souhaitez vous connecter, comme *PRODUCTION - Ma société*.  

5. Ensuite, une liste de tables qui sont exposées dans le cadre de l’API pour votre environnement vous sera présentée. Sélectionnez la table à laquelle vous souhaitez vous connecter, puis choisissez **Connecter**.

Ces tables sont exposées en tant que points de terminaison par le connecteur [!INCLUDE[prod_short](includes/prod_short.md)] pour Power Apps.  

> [!NOTE]
> Si vous souhaitez inclure des données d’autres tables dans [!INCLUDE[prod_short](includes/prod_short.md)] dans votre application, vous devez travailler avec un développeur pour définir une API personnalisée dans [!INCLUDE[prod_short](includes/prod_short.md)].  

À ce stade, vous êtes connecté à vos données [!INCLUDE[prod_short](includes/prod_short.md)] et vous êtes prêt à générer votre application Power App. Vous pouvez ajouter des écrans supplémentaires et vous connecter à des données supplémentaires à partir de votre [!INCLUDE[prod_short](includes/prod_short.md)]. Pour plus d’informations, voir [Créer une application de canevas à partir d’un exemple dans Power Apps](/powerapps/maker/canvas-apps/open-and-run-a-sample-app).  

Lorsque vous avez conçu et créé votre application, vous pouvez la partager avec vos collègues. Pour plus d’informations, voir [Enregistrer et publier une application de canevas dans Power Apps](/powerapps/maker/canvas-apps/save-publish-app).  

> [!NOTE]
> Si vous souhaitez vous connecter à [!INCLUDE[prod_short](includes/prod_short.md)] sur site, vous devez choisir le connecteur **Business Central (sur site)** dans l’étape 3.  

## Voir la [formation Microsoft](/training/paths/power-apps-power-automate-business-central/) associée

## Voir aussi

[Créer une application de canevas à partir d’un modèle dans Power Apps](/powerapps/maker/canvas-apps/get-started-test-drive)  
[Importation des données métier à partir d’autres systèmes financiers](across-import-data-configuration-packages.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Familiarisation avec le développement d’applications connectées pour Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
