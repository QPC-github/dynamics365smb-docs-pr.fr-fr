---
title: "Configuration des niveaux hiérarchiques pour les personnes à contacter | Microsoft Docs"
description: "Décrit les niveaux hiérarchiques pour les contacts dans Financials"
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, client, prospect
ms.date: 03/28/2017
ms.author: jswymer
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: bde26a2d5fcb7ec10dcd70fdd30c74893bcb34d5
ms.contentlocale: fr-fr
ms.lasthandoff: 05/04/2017


---
# <a name="setting-up-organizational-levels-for-contact-persons"></a>Configuration des niveaux hiérarchiques pour les personnes à contacter
Vous pouvez utiliser les niveaux hiérarchiques sur vos contacts pour qu'ils précisent leur position au sein de la société, par exemple, la direction générale. Vous pouvez utiliser ces informations lors de la saisie de données sur vos contacts.

L'utilisation de niveaux hiérarchiques sur les contacts est un processus en deux étapes. Tout d'abord, vous définissez le code de niveau hiérarchique. Vous ne devez effectuer cette étape qu'une seule fois pour niveau hiérarchique. Une fois que vous disposez d'un code de niveau hiérarchique, vous pouvez commencer à affecter ce code aux personnes contact.

## <a name="to-define-an-organizational-level-code"></a>pour définir un code de niveau hiérarchique
Le code de niveau hiérarchique définit le type ou la catégorie du niveau hiérarchique, par exemple PDG ou DF. Vous pouvez disposer de plusieurs codes de niveau hiérarchique. Pour définir le niveau hiérarchique, vous utilisez la fenêtre **Niveaux organisationnels**.

1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche** ![Page ou état pour la recherche](media/ui-search/search_small.png "Icône Page ou état pour la recherche"), entrez **Niveaux hiérarchiques**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**, et entrez un code et une désignation. Vous pouvez saisir pour le code un maximum de 11 caractères, et toute combinaison de chiffres et des lettres.

## <a name="to-assign-organizational-levels-to-a-contact-person"></a>pour affecter des niveaux hiérarchiques à une personne contact
Vous pouvez affecter des niveaux hiérarchiques aux personnes contact, mais pas aux sociétés contact. Vous ne pouvez affecter qu'un niveau hiérarchique par contact.

1. Ouvrez le contact.
2. Dans le champ **Niveaux organisationnels**, sélectionnez le code à affecter.

Une fois que vous avez affecté des niveaux hiérarchiques à vos contacts, vous pouvez utiliser ces données pour créer des segments.

Une fois que vous avez affecté des responsabilités à vos contacts, vous pouvez utiliser ces informations pour sélectionner des contacts pour vos segments. Pour plus d'informations, reportez-vous à [Procédure : ajouter des contacts à des segments](marketing-add-contact-segment.md).

## <a name="see-also"></a>Voir aussi
[Création de sociétés contact](marketing-create-contact-companies.md)  
[Création de personnes contact](marketing-create-contact-persons.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
