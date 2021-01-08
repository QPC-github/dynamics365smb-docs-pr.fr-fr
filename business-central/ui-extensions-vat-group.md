---
title: L’extension de gestion du groupe TVA | Microsoft Docs
description: Vous pouvez vous engager avec d’autres entreprises pour former un groupe TVA et agir en tant que membre ou société représentante du groupe lors de la déclaration de TVA.
author: bholtorf
manager: annbe
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: VAT, value added tax, report
ms.date: 10/06/2020
ms.author: bholtorf
ms.openlocfilehash: 5dfadee976ce39e7d7ead2c09d907050682b4a7f
ms.sourcegitcommit: 4bca699d2a5ce182eb5572d72fac4fb478c4f293
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "3989410"
---
# <a name="the-vat-group-management-extension"></a>Extension de gestion du groupe TVA

Vous pouvez rejoindre une ou plusieurs entreprises de votre pays pour consolider la déclaration de TVA sous un numéro d’enregistrement unique. Ce type d’arrangement est connu sous le nom de *Groupe TVA*. Vous pouvez vous engager avec le groupe en tant que membre ou société représentante du groupe.

## <a name="forming-a-vat-group"></a>Formation d’un groupe TVA
Les membres du groupe TVA et la société représentante du groupe peuvent utiliser le guide de configuration assisté **Configuration de la gestion des groupes TVA** pour définir leur engagement avec le groupe et créer une connexion entre leurs locataires [!INCLUDE[d365fin](includes/d365fin_md.md)]. Les membres du groupe utiliseront la connexion pour soumettre leurs déclarations de TVA à la société représentante du groupe. La société représentante soumettra la TVA aux autorités fiscales au nom du groupe en utilisant une seule déclaration de TVA. 

## <a name="vat-group-constellations"></a>Constellations du groupe TVA
La communication se fait entre les membres du groupe et la société représentante. La société représentante du groupe expose une API qui permet aux membres de soumettre leurs déclarations de TVA à la société représentante du groupe TVA. 
[!INCLUDE[d365fin](includes/d365fin_md.md)] prend en charge les déclarations de TVA inter-groupes pour les entreprises utilisant [!INCLUDE[d365fin](includes/d365fin_md.md)] sur site ou en ligne, et dans n’importe quelle combinaison. La configuration de la communication dépend de la constellation. Les sections suivantes décrivent comment configurer diverses constellations de groupe.

La liste suivante montre l’ordre recommandé des étapes de configuration d’un groupe TVA :

1. Créez la configuration dans Azure Active Directory. Pour plus d’informations, voir [Configuration requise pour l’authentification](ui-extensions-vat-group.md#requirements-for-authentication).
2. Partagez les informations techniques dont les membres du groupe TVA et la société représentante ont besoin pour connecter leur locataires [!INCLUDE[d365fin](includes/d365fin_md.md)].

  Habituellement, la société représentante du groupe TVA dispose de ces informations, telles que le nom de l’environnement de la société représentante du groupe TVA auquel les membres du groupe TVA soumettront la TVA.
3. Créez des utilisateurs dans le [!INCLUDE[d365fin](includes/d365fin_md.md)] de la société représentante du groupe TVA que les membres du groupe TVA peuvent utiliser pour s’authentifier et se connecter.
4. Exécutez le guide de configuration assistée **Configurer la gestion des groupes TVA** pour connecter les membres du groupe TVA.

  Le guide requiert certaines informations de la société représentante du groupe TVA. Pour plus d’informations, voir la section [Configuration des membres du groupe TVA](#vat-group-member-setup). Prenez note de **l’ID de membre du groupe** pour chaque membre du groupe TVA. La société représentante a besoin de ces ID pour ajouter les sociétés au groupe TVA.
5. Configurez l’extension de gestion du groupe TVA dans la société représentante du groupe TVA [!INCLUDE[d365fin](includes/d365fin_md.md)] en utilisant le guide de configuration assistée **Configurer la gestion des groupes TVA**. 

> [!NOTE]
> Pour se connecter à la société représentante du groupe TVA, les membres du groupe ont besoin d’un utilisateur ayant accès au représentant du groupe TVA [!INCLUDE[d365fin](includes/d365fin_md.md)]. La société représentante du groupe TVA doit créer au moins un utilisateur pour cela, cependant, pour des raisons de sécurité, nous vous recommandons de créer un utilisateur pour chaque membre du groupe TVA. Assurez-vous de distribuer les informations d’identification de ces utilisateurs aux membres du groupe TVA de manière sécurisée.

## <a name="understanding-the-vat-group-management-setup"></a>Comprendre la configuration de la gestion des groupes TVA

Là société représentante du groupe TVA expose une API que les membres du groupe TVA peuvent utiliser pour se connecter à leur locataire [!INCLUDE[d365fin](includes/d365fin_md.md)] et soumettre les déclarations de TVA. Les membres du groupe TVA utilisent souvent [!INCLUDE[d365fin](includes/d365fin_md.md)] dans des locataires Azure Active Directory séparés. Par conséquent, une configuration supplémentaire est nécessaire pour établir une connexion entre le membre du groupe TVA et la société représentante [!INCLUDE[d365fin](includes/d365fin_md.md)]. 
  
Les membres du groupe TVA se connectent à la société représentante en appelant un service web sur le locataire de la société représentante du groupe TVA. L’appelant doit être authentifié à l’aide d’OAuth. Lorsque l’extension de gestion du groupe TVA est configurée, il vous sera demandé de vous authentifier auprès de la société représentante du groupe TVA pour obtenir et enregistrer un jeton d’accès. Ce jeton d’accès est utilisé lors de la soumission des déclarations de TVA à la société représentante du groupe TVA. 

L’authentification est gérée par Azure Active Directory, donc votre configuration doit être effectuée dans le Azure Active Directory de la société représentante du groupe TVA pour autoriser les connexions. Un enregistrement de l’application Azure Active Directory doit être configuré avec l’accès au [!INCLUDE[d365fin](includes/d365fin_md.md)] de la société représentante du groupe TVA. Cela est également vrai si la société représentante du groupe TVA utilise [!INCLUDE[d365fin](includes/d365fin_md.md)] sur site. En outre, vous devez configurer l’authentification unique si la société représentante du groupe TVA utilise [!INCLUDE[d365fin](includes/d365fin_md.md)] sur site.

> [!NOTE]
> Pendant une durée limitée, l’authentification à l’aide d’une clé d’accès au service web est également prise en charge. Pour plus d’informations, voir [Fonctionnalités obsolètes dans la vague de lancement 1 de 2021](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#deprecated-features-in-2021-release-wave-1).

## <a name="requirements-for-authentication"></a>Configuration requise pour l’authentification 
Lorsque la société représentante du groupe TVA utilise [!INCLUDE[d365fin](includes/d365fin_md.md)] en ligne ou sur site, les membres du groupe TVA utilisent Azure Active Directory pour s’authentifier lorsqu’ils soumettent des déclarations de TVA à la société représentante du groupe TVA. Si les membres du groupe TVA utilisent également [!INCLUDE[d365fin](includes/d365fin_md.md)] en ligne, le membre du groupe TVA peut s’authentifier à l’aide des informations d’identification de l’utilisateur désignées et des informations sur le point de terminaison. Pour plus d’informations, voir [Configuration des membres du groupe TVA](ui-extensions-vat-group.md#vat-group-member-setup).

Les membres du groupe TVA qui ont [!INCLUDE[d365fin](includes/d365fin_md.md)] sur site doivent configurer une inscription d’application dans Azure Active Directory pour le locataire [!INCLUDE[d365fin](includes/d365fin_md.md)] de la société représentante du groupe TVA. L’enregistrement de l’application permettra au [!INCLUDE[d365fin](includes/d365fin_md.md)] en ligne de la société représentante du groupe TVA pour authentifier le membre du groupe. Pour plus d’informations, voir [Démarrage rapide : enregistrer une application avec la plateforme d’identité Microsoft](/azure/active-directory/develop/quickstart-register-app).

Lorsque vous créez l’inscription de l’application dans Azure Active Directory, vous devez spécifier les éléments suivants.

* Dans la section **Authentification**, ajoutez **Web** comme plateforme et utilisez les éléments **URL de redirection** suivants : https://businesscentral.dynamics.com/OAuthLanding.htm.
* Dans la section **Authentification**, dans l’option de sélection **Types de compte pris en charge**, sélectionnez **Comptes dans n’importe quel annuaire organisationnel (tout annuaire Azure AD – multi-locataires)**.
* Dans la section **Certificats et secrets**, créez un secret client et notez la valeur. Les membres du groupe TVA auront besoin du secret pour configurer la connexion à la société représentante du groupe.
* Dans la section **Autorisations API**, ajoutez des autorisations à [!INCLUDE[d365fin](includes/d365fin_md.md)]. Activez l’accès délégué à **Finances.ReadWrite.All** et **user_impersonation**.
* Dans la section **Aperçu**, notez l’**ID de l’application (client)**. Les membres du groupe TVA auront besoin de l’ID pour configurer la connexion à la société représentante du groupe. 

## <a name="vat-group-member-setup"></a>Configuration des membres du groupe TVA
Configurez le membre du groupe TVA en démarrant le guide de configuration assistée **Configurer la gestion des groupes TVA**. 

> [!NOTE]
> Avant de commencer, contactez la société représentante du groupe TVA pour obtenir les informations suivantes sur leur locataire [!INCLUDE[d365fin](includes/d365fin_md.md)] :
>
> * L’URL de l’API
> * Le nom de leur société 
> * L’ID client
> * Le secret du client
> * Les informations d’identification de connexion pour l’utilisateur dédié 

1. Choisissez l’icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Groupe TVA**, puis sélectionnez le lien associé.
2. Pour définir le rôle du groupe TVA de l’entreprise, choisissez **Membre**, puis **Suivant**.
3. Copiez la valeur de l**ID de membre du groupe**, puis partagez-le avec la société représentante du groupe TVA afin qu’elle puisse ajouter votre société en tant que membre approuvé du groupe.
4. Ajoutez l’**URL de l’API** de la société représentante du groupe TVA. En règle générale, l’URL est mise en forme comme suit : `https://api.businesscentral.dynamics.com/v2.0/[TENANT-ID]/[ENVIRONMENTNAME]`. Par exemple, `https://api.businesscentral.dynamics.com/v2.0/907869c3-b252-4aca-b9cb-17a15d25477b/UKRepresentative`. 
5. Ajoutez le nom de la société [!INCLUDE[d365fin](includes/d365fin_md.md)] de la société représentante du groupe TVA, tel que *CRONUS UK Ltd*.
6. Choisissez le **Type d’authentification**, **OAuth2**, puis **Suivant**.
7. Dans le champ **ID client**, saisissez l’ID fourni par la société représentante du groupe TVA.
8. Dans le champ **Secret du client fourni par la société représentante du groupe TVA**, saisissez le secret fourni par la société représentante du groupe TVA.
9. Dans le champ **Point de terminaison d’autorité OAuth 2.0**, entrez *https://login.microsoftonline.com/common/oauth2*.
10. Dans le champ **URL de ressource OAuth 2.0**, entrez *https://api.businesscentral.dynamics.com/*.
11. Dans le champ **URL de redirection OAuth 2.0**, entrez *https://businesscentral.dynamics.com/OAuthLanding.htm*. 
12. Lorsque vous avez spécifié les différents champs, choisissez **Suivant**, puis saisissez les informations d’identification de l’utilisateur fournies par la société représentante du groupe TVA.
13. Choisissez la configuration de déclaration de TVA que vous utilisez pour déclarer la TVA aux autorités de votre pays.

  Par exemple, au Royaume-Uni, la configuration de la déclaration de TVA serait configurée pour déclarer la TVA au HMRC. L’extension Gestion du groupe TVA copie cette configuration, mais remplace le codeunit de soumission par un codeunit qui prend en charge la soumission à la société représentante du groupe TVA plutôt qu’aux autorités fiscales. Le codeunit est fourni par Microsoft. Une fois que vous avez terminé, cliquez sur **Suivant**.

## <a name="using-the-vat-group-management-features"></a>Utilisation des fonctionnalités de gestion du groupe TVA

Les membres du groupe TVA utilisent les processus standard pour préparer les déclarations de TVA. La seule différence est de choisir la version de déclaration **VATGROUP**, qui soumet la déclaration de TVA à la société représentante du groupe TVA plutôt qu’aux autorités. Pour plus d’informations, voir [À propos de la déclaration de retours de TVA](/business-central/finance-how-report-vat#about-the-vat-return-report).

Les sections suivantes décrivent les tâches que les sociétés représentantes du groupe TVA doivent effectuer.

### <a name="vat-group-submissions"></a>Soumissions groupe TVA

La page **Soumissions groupe TVA** répertorie les déclarations de TVA que les membres ont soumises. La page sert d’emplacement provisoire pour les soumissions jusqu’à ce que la société représentante du groupe TVA les inclue dans une déclaration de TVA pour le groupe. Vous pouvez ouvrir les soumissions pour consulter la TVA pour les cases individuelles déclarées par le membre du groupe TVA.

### <a name="creating-a-group-vat-return"></a>Création d’une déclaration de TVA de groupe

Pour déclarer la TVA au nom du groupe, sur la page **Retours de TVA**, créez une déclaration de TVA pour votre entreprise uniquement. Ensuite, incluez les dernières soumissions de TVA des membres du groupe TVA en choisissant l’action **Inclure la TVA du groupe**.  

Lorsque la déclaration de TVA de la société représentante du groupe TVA a été soumise aux autorités au nom de l’ensemble du groupe, vous exécuterez normalement l’action **Calculer et comptabiliser la TVA**. Cette action ferme les écritures TVA ouvertes et transfère les montants vers le compte de déclaration de TVA. Actuellement, cette action ne prend pas en compte les soumissions de groupe. Cela signifie que seules les écritures de TVA de la société représentante du groupe TVA seront enregistrées. Les montants de soumission des membres du groupe TVA doivent être imputés manuellement au montant du règlement de la TVA, de sorte que le compte de règlement de la TVA de la société représentante du groupe TVA reflète la responsabilité de ce qui a été déclaré aux autorités. Ce comportement changera dans une prochaine mise à jour de [!INCLUDE[d365fin](includes/d365fin_md.md)], de sorte que la totalité de la TVA du groupe (le montant total sur les lignes de la déclaration de TVA) sera réglée. 

> [!NOTE]
> Les membres du groupe TVA peuvent corriger les déclarations de TVA soumises tant que la société représentante du groupe n’a pas validé la déclaration de TVA du groupe. Pour effectuer une correction, le membre du groupe TVA doit créer une déclaration de TVA pour la période de déclaration de TVA et la soumettre à la société représentante du groupe TVA. Du côté de la société représentante du groupe TVA, la dernière déclaration de TVA sera incluse dans la page **Retours de TVA**. 

## <a name="see-also"></a>Voir aussi
[Utiliser la TVA sur les ventes et les achats](finance-work-with-vat.md)  
[Configuration de la TVA](finance-setup-vat.md)