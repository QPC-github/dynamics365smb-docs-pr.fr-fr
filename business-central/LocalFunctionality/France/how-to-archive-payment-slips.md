---
title: "Procédure d'archivage des bordereaux paiement"
description: "Lorsqu'un bordereau paiement a été entièrement traité, vous pouvez le séparer des bordereaux paiement actifs en l'archivant."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: d1258744cae6384bbee45fe79c321f49e2d44cdc
ms.contentlocale: fr-fr
ms.lasthandoff: 03/22/2018

---
# <a name="archive-payment-slips"></a>Archiver les bordereaux de paiement
Lorsqu'un bordereau paiement a été entièrement traité, vous pouvez le séparer des bordereaux paiement actifs en l'archivant.  

Vous pouvez archiver le bordereau paiement à l'aide des méthodes suivantes :  

- Manuellement pour des bordereaux paiement individuels.  
- Automatiquement pour un lot de bordereaux paiement.  

## <a name="to-archive-a-payment-slip"></a>Pour archiver un bordereau paiement  

1.  Sélectionnez l'icône ![Page ou état pour la recherche](../../media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Bordereaux paiement**, puis sélectionnez le lien approprié.  
2.  Sélectionnez le bordereau paiement concerné, puis cliquez sur l'action **Modifier**.  
3.  Dans la fenêtre **Bordereau paiement**, sélectionnez **Archiver**.  
4.  Cliquez sur le bouton **Oui** pour archiver le bordereau paiement.  

    > [!NOTE]  
    >  Si le statut actuel du bordereau paiement n'autorise pas l'archivage, un message s'affiche.  

## <a name="to-archive-a-batch-of-payment-slips"></a>Pour archiver un lot de bordereaux paiement  

1.  Sélectionnez l'icône ![Page ou état pour la recherche](../../media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Archiver les bordereaux de paiement**, puis sélectionnez le lien approprié.  
2.  Dans la fenêtre **Archiver les bordereaux de paiement**, sur le raccourci **En-tête bordereau**, sélectionnez les filtres appropriés.  
3.  Cliquez sur le bouton **OK**.  

Les bordereaux paiement sont archivés.  

> [!NOTE]  
>  Ce traitement par lots archive uniquement les bordereaux paiement dont la case **Archivage autorisé** est cochée dans la fenêtre **Statut règlement**. Pour plus d'informations, voir [Paramétrer des statuts règlement](how-to-set-up-payment-statuses.md).  

## <a name="see-also"></a>Voir aussi  
 [Gestion des paiements](payment-management.md)   
 [Paramétrer des types de règlement](how-to-set-up-payment-classes.md)   
 [Paramétrer des statuts règlement](how-to-set-up-payment-statuses.md)   
 [Paramétrer des étapes règlement](how-to-set-up-payment-steps.md)   
 [Configurer des adresses de paiement](how-to-set-up-payment-addresses.md)   
 [Créer bordereaux paiement](how-to-create-payment-slips.md)   
 [Valider des bordereaux paiement](how-to-post-payment-slips.md)
