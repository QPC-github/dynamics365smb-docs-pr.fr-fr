---
title: FAQ relative aux applications mobiles
description: Consultez les réponses aux questions fréquemment posées sur l’utilisation de Business Central sur votre téléphone ou votre tablette.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: phone, tablet
ms.date: 10/15/2020
ms.author: edupont
ms.openlocfilehash: 3b00eb417f2e51d87a58885a50e1262150837d93
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5385448"
---
# <a name="mobile-apps-faq"></a>FAQ relative aux applications mobiles

Cet article répond aux questions que nos utilisateurs expérimentés posent souvent à propos des applications mobiles pour [!INCLUDE [prod_short](includes/prod_short.md)].  

## <a name="is-there-an-app-for-my-device"></a>Existe-t-il une application pour mon appareil ?

Probablement ! Installez l’application [!INCLUDE[prod_short](includes/prod_short.md)] sur votre périphérique mobile en la téléchargeant à partir de Windows Store, d’App Store ou de Google Play.

- [Windows Store](https://go.microsoft.com/fwlink/?LinkId=734848) (PC uniquement)
- [Plate-forme de téléchargement des applications](https://go.microsoft.com/fwlink/?LinkId=734847)
- [Google Play](https://go.microsoft.com/fwlink/?LinkId=734849)

## <a name="is-it-the-same-experience-in-the-apps-as-in-the-browser"></a>Est-ce la même expérience dans les applications que dans le navigateur ?

Non, pas exactement. Par exemple, nous montrons uniquement le groupe d’activité **Accueil** en raison de la taille d’écran limitée sur les appareils mobiles. De même, les raccourcis clavier ne sont pas disponibles, car vous utilisez principalement la fonction tactile plutôt qu’un clavier pour naviguer sur les appareils mobiles.

Le tableau suivant décrit certaines des différences et limitations les plus courantes que vous pouvez rencontrer lors de l’utilisation de [!INCLUDE [prod_short](includes/prod_short.md)] sur les appareils mobiles, par rapport au navigateur.

| Concept | Sur les tablettes | Sur les téléphones | Exemple depuis le navigateur |
|--|--|--|--|
| Groupes d’activités | Seule le groupe d’activités **Accueil** s’affiche. | Seule le groupe d’activités **Accueil** s’affiche. | **Accueil** et **Documents validés** sur le tableau de bord `Sales Order Processor`. |  |
| Sélection de plusieurs enregistrements dans des listes | Non disponible. | Non disponible. | `Ctrl+A` ou `Ctrl+Click` sur les lignes d’une liste dans le navigateur. |
| Actions dans la barre d’actions | Seules les actions sponsorisées sont affichées. | Seules les actions sponsorisées sont affichées. |  |
| Récapitulatifs | Non affiché sur les pages de liste ou les pages de feuille de travail. | Non affiché sur les pages de liste ou les pages de feuille de travail. | Liste `Customer` sur le tableau de bord `Small Business`. |
| Filtres avancés | Aucun filtrage spécifique à la colonne n’est disponible. | Aucun filtrage spécifique à la colonne n’est disponible. | Sur la page de liste `Customer`. |
| Tell Me | Pas encore disponible. | Pas encore disponible. | Voir [Recherche de pages et d’informations avec Tell Me](ui-search.md). |  |
| Explorateur de rôles | Pas encore disponible. | Pas encore disponible. | Voir [Recherche de pages avec l’explorateur de rôles](ui-role-explorer.md). |
| Champs dans les raccourcis | Les champs dans les raccourcis des pages de liste ne sont pas affichés. Seule la commande de répéteur est affichée dans la zone de contenu de la page. | Non disponible. |  |
| Sélectionner dans la liste complète | Non disponible sur les recherches. Les utilisateurs ne sont pas en mesure d’exécuter des actions sur une page de recherche et ils ne peuvent pas accéder à l’ensemble complet des enregistrements. | Non disponible sur les recherches. Les utilisateurs ne sont pas en mesure d’exécuter des actions sur une page de recherche et ils ne peuvent pas accéder à l’ensemble complet des enregistrements. | Sur la `Item Card` lors de la sélection des **Unités de mesure de base**. |
| Rechercher dans les colonnes de la liste | Partiellement pris en charge. La recherche n’inclura pas FlowFields. | Partiellement pris en charge. La recherche n’inclura pas FlowFields. | Voir des exemples sur la page de liste `Customers`. |
| Consultations | Disponible. | Disponible, à la différence que les recherches avancées et simples se comportent de la même manière sur le téléphone. La recherche n’affiche pas la fiche, affiche les Récapitulatifs ou aucun groupe de champs. | Voir des exemples sur la page `Customer Card`. |
| Contrôles de la matrice | Non disponible. | Non disponible. | Voir l’exemple dans `G/L Budget`. |
| Télécharger le fichier | Disponible. Impossible de télécharger plusieurs fichiers en même temps. | Disponible. Impossible de télécharger plusieurs fichiers en même temps. | État `Trial Balance` dans la case à cocher **Imprimer vers Excel**. |
| Pages de feuille de travail | Disponible. | Indisponible ; un message d’erreur s’affiche. | Feuille de travail `Sales Price` ou`Cash Flow`. |
| Listes | Disponible. | Disponible, à la différence que ceux-ci sont affichés dans une disposition en brique. | Pages Commandes vente ou client. |
| Indentation dans les commandes du répéteur | Disponible. | Non disponible. Le contrôle de répéteur sera rendu comme une disposition de brique plate régulière. | Pages du plan comptable et de la liste de contacts. |
| Mise au point automatique sur le premier champ modifiable d’une page | Non disponible. | Non disponible. | Page `Customer Card`.<BR /><BR />Dans le navigateur, le focus sera automatiquement sur le premier champ modifiable (tel que le champ `Name`), vous permettant de modifier la valeur immédiatement.<BR /><BR />Dans les applications pour tablettes et téléphones, ce champ ne sera pas mis au point ; au lieu de cela, vous devrez d’abord sélectionner manuellement le champ afin d’apporter des modifications.|

## <a name="is-it-the-same-experience-on-tables-and-phones"></a>Est-ce la même expérience sur les tables et les téléphones ?

Presque, mais pas tout à fait. Voir la liste dans la section [Est-ce la même expérience dans les applications que dans le navigateur ?](#is-it-the-same-experience-in-the-apps-as-in-the-browser).  

## <a name="can-i-connect-the-app-to-our-on-premises-solution"></a>Puis-je connecter l’application à notre solution sur site ?

Oui, vous pouvez ! C’est une façon légèrement différente de se connecter, c’est tout. Pour plus d’informations, voir [Utilisation de Business Central en local ?](install-mobile-app.md#using-business-central-on-premises).  

## <a name="see-also"></a>Voir aussi

[Obtention de Business Central sur votre périphérique mobile](install-mobile-app.md)  
[Installer l’application Business Central pour Microsoft Teams](across-install-app-for-teams.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]