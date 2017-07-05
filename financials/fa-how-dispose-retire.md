---
title: "Procédure : céder ou annuler des immobilisations| Microsoft Docs"
description: "Décrit comment céder ou annuler des immobilisations."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: scrap
ms.date: 03/23/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: 28e4a67ae3df82a2860ced1b971ee41975c8d578
ms.contentlocale: fr-fr
ms.lasthandoff: 05/04/2017


---
# <a name="how-to-dispose-of-or-retire-fixed-assets"></a>Procédure : céder ou annuler des immobilisations
Lorsque vous commercialisez ou cédez une immobilisation, la valeur de cession doit être validée pour calculer et enregistrer le gain ou la perte. Une écriture cession doit être la dernière écriture validée pour une immobilisation. Pour les immobilisations partiellement cédées, vous pouvez valider plusieurs écritures cession. Le total de tous les montants de cession validés doit être un montant crédit.  

**Remarque :** Si vous négociez une immobilisation en échange d'une autre, vous devez enregistrer à la fois la vente de l'ancienne immobilisation (cession) et l'achat de la nouvelle (acquisition). Pour en savoir plus, voir [Procédure : acquérir les immobilisations](fa-how-acquire.md).  

## <a name="to-post-a-disposal-from-the-fixed-asset-gl-journal"></a>Valider une cession à partir d'une feuille comptabilisation immobilisation
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche** ![Page ou état pour la recherche](media/ui-search/search_small.png "Icône Page ou état pour la recherche"), entrez **Feuille comptabilisation immobilisation**, puis sélectionnez le lien associé.  
2. Créez une feuille comptable initiale et complétez les champs, le cas échéant. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Dans le champ **Type compta. immo**, sélectionnez **Cession**.  
4. Sélectionnez l'action **Insérer contrepartie immo.**. Une seconde ligne feuille est créée pour le compte contrepartie qui est configuré pour la validation de la cession.  

    **Remarque** : l'étape 4 ne fonctionne que si vous avez configuré ce qui suit : la fenêtre **Fiche groupe compta. immo.** pour le groupe de validation de l'immobilisation, le champ **Cession immobilisation** contient le compte débit général et le champ **Compte contrepartie cession** contient le compte général auquel vous souhaitez valider les écritures contrepartie pour appréciation. Pour en savoir plus, voir la section « Pour configurer des groupes de validation d'immobilisation » dans [Procédure : configurer des informations d'immobilisation générales pour les immobilisations](fa-how-setup-general.md).  
5. Sélectionnez l'action **Valider**.  

    Si vous vendez une immobilisation ou en cédez une partie, vous devez d'abord diviser l'immobilisation avant de pouvoir enregistrer la transaction cession. Pour en savoir plus, voir [Procédure : transférer, fractionner ou regrouper les immobilisations](fa-how-trans-split-combine.md).  

## <a name="to-view-disposal-ledger-entries"></a>Pour visualiser des écritures comptables cession
Lorsque vous vendez ou cédez une immobilisation, la valeur de cession est validée en comptabilité où vous pouvez afficher le résultat.  

1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche** ![Page ou état pour la recherche](media/ui-search/search_small.png "Icône Page ou état pour la recherche"), entrez **Immobilisations**, puis sélectionnez le lien associé.  
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez afficher les écritures, puis sélectionnez l'action **Lois d'amortissement**.  
3. Sélectionnez la loi d'amortissement pour laquelle vous souhaitez afficher les écritures, puis sélectionnez l'action **Écritures comptables**.  
4. Sélectionnez une ligne avec **Cession** dans le champ **Catégorie compta. immo.**, puis sélectionnez l'action **Naviguer**.  
5. Dans la fenêtre **Naviguer**, sélectionnez la ligne d'écriture comptable, puis l'action **Afficher**.  

La fenêtre **Écritures comptables** s'ouvre. Vous pouvez y voir les écritures résultant de la validation de la cession.  

## <a name="see-also"></a>Voir aussi
[Immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Finance](finance.md)  
[Bienvenue dans [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
