---
title: Rapports Comptabilité client et analyse
description: Découvrez les états et analyses disponibles dans la version standard de Business Central afin que vous puissiez suivre vos comptes client.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 07/13/2021
ms.author: edupont
ms.openlocfilehash: 76de1625ee71b666b01d6b2fef1efe5605d9a418
ms.sourcegitcommit: a486aa1760519c380b8cdc8fdf614bed306b65ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6543340"
---
# <a name="accounts-receivable-reports-and-analytics-in-business-central"></a>États comptabilité client et analyses d’immobilisation dans Business Central

Pour vous aider à gérer votre comptabilité client dans [!INCLUDE [prod_short](includes/prod_short.md)], des états et des analyses standard sont intégrés. Ils vont au-delà des contraintes des rapports traditionnels pour vous aider à concevoir efficacement divers types de rapports.  

## <a name="reports"></a>États

Le tableau suivant décrit certains des principaux états dans les états de comptabilité client.

| État | ID d’objet | Description |
|--|--|--|
| **Comptabilités client chronologiques** | 120 | Affiche le montant impayé avec les clients répartis en intervalles de temps pour le temps de retard. Le rapport affiche également la partie du solde des clients qui n’est pas due et peut être affiché avec ou sans les détails du document pour chaque client. Ce rapport est le rapport principal pour le rapprochement des écritures comptables client avec la comptabilité. En supposant que vous n’ayez pas autorisé la comptabilisation directe sur les comptes utilisés dans la comptabilité client des groupes comptabilisation, ce rapport est une spécification des montants que vous trouvez en comptabilité. |
| **Relevé client** | 1316 | Génère un relevé client pour un intervalle de temps spécifié. Il est généralement envoyé aux clients pour leur donner un aperçu des montants impayés et également pour rappeler de payer les montants en souffrance. Vous pouvez choisir d’afficher les montants en souffrance dans une section distincte. Vous pouvez inclure une tranche de vieillissement similaire à celle utilisée dans le rapport **Comptabilités chronologiques**. Pour la tranche de vieillissement, vous définissez généralement *30D*, ce qui signifie des intervalles de 30 jours tels que 30, 60, 90 et 90+ jours de retard, à compter de la date de fin, ou *1M+CM*, qui sera le mois en cours dans un intervalle séparé, puis des intervalles mensuels pour les mois précédents. **Noter** : dans la liste des clients, ce rapport a également une action distincte, **Relevés programmés**. Cette option ne filtre pas le client que vous avez sélectionné. C’est le même rapport, mais utilisé lorsque vous souhaitez envoyer un relevé à tous/plus de clients. |
| **Clients – Solde cumulé** | 121 | Affiche les écritures comptables clients ouvertes jusqu’à la date de fin. Ce rapport affiche un contenu similaire à celui du relevé client, mais sans indication si l’entrée est en retard. **Remarque** : Le filtre de date est appliqué aux écritures comptables client détaillées. Autrement dit, si vous avez des paiements postérieurs à la date de fin qui ont été appliqués à des factures dans la plage de dates, les factures apparaîtront dans l’état, car elles n’ont pas été clôturées à la date de fin. |
| **Clients –– Balance** | 129 | Affiche les soldes périodes pour les clients pour la période spécifiée dans le filtre de date ainsi que les soldes périodes depuis le début de l’exercice correspondant à la période sélectionnée. L’état est regroupé par groupes comptabilisation des clients et donne une vue différente de la comptabilité client que l’état **Comptabilités client chronologiques**. **Noter** : si vous n’avez pas configuré de période comptable, le système ne saura pas quel exercice utiliser et affichera le cumul annuel à partir du dernier exercice défini ou sélectionnera simplement la période, qui peut ou non être dès le début d’une année.|
| **Grand livre clients** | 104 | Affiche toutes les écritures comptables client dans le filtre de date spécifié. Ce rapport est généralement utilisé pour vérifier que toutes les écritures pour un client spécifique sont prises en compte, ou pour d’autres contrôles internes sur les livres des clients. |
| **Reçu paiement client** | 211 | Crée un reçu de paiement pour chaque écriture comptable client de type **Paiement**. Si le paiement a été lettré aux factures, les factures sont précisées ; à défaut, il indique simplement le montant du paiement comme non lettré. Ce rapport est utilisé pour envoyer aux clients qui souhaitent une documentation pour la réception du paiement.|
| **Concordance comptes client et fournisseur** | 33 |Affiche les écritures comptables résultant de la comptabilisation des écritures client et fournisseur réparties par compte G/L et groupes de comptabilisation. Ce rapport est utilisé pour rapprocher les soldes des livres clients et fournisseurs avec les soldes comptabilité. |
| **Clients : Balance âgée**| 109 |Il s’agit d’une ancienne version d’un échéancier des comptes clients. Nous vous recommandons d’utiliser le rapport **Comptabilités fournisseur chronologiques** à la place. |
| **Statistiques vente** |112  |[!INCLUDE [reports-sales-statistics](includes/reports-sales-statistics.md)]<br>Cet état peut également être utilisé dans la comptabilité client, car il est plus facile d’effectuer une recherche rapide des paiements, remises et ventes validés pour un client donné.|
|**Liste des clients**|101| Affiche diverses informations de base sur les clients, par exemple le groupe comptabilisation, le groupe remise, les informations sur les intérêts de retard et le paiement, le vendeur, la devise par défaut du client et le crédit autorisé dans votre devise locale (en devise société), ainsi que le solde actuel du client (en devise société). L’état permet, par exemple, de maintenir à jour les informations de la table Client.|

## <a name="see-also"></a>Voir aussi

[Analyse des états financiers dans Microsoft Excel](finance-analyze-excel.md)  
[Utilisation des axes analytiques](finance-dimensions.md)  
[Gestion des immobilisations](fa-manage.md)  
[Vue d’ensemble des fonctionnalités locales](about-localization.md)  
[Expériences de comptable dans [!INCLUDE[prod_long](includes/prod_long.md)]](finance-accounting.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]