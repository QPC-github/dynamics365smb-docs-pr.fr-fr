---
title: "Procédure de préparation d'un package de configuration | Microsoft Docs"
description: "Lorsque vous configurez une nouvelle société, les relations de table sont reconnues et traitées. Les données sont importées et lettrées dans le bon ordre. Les tables d’axes analytiques sont également importées si elles sont incluses dans le package configuration."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/06/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 02192888f95f8136e349764227e0bf1aac91c5d1
ms.contentlocale: fr-fr
ms.lasthandoff: 03/22/2018

---
# <a name="prepare-a-configuration-package"></a>Préparer un package configuration
Lorsque vous configurez une nouvelle société, les relations de table sont reconnues et traitées. Les données sont importées et lettrées dans le bon ordre. Les tables d’axes analytiques sont également importées si elles sont incluses dans le package configuration.  

Pour aider votre client à utiliser le package configuration, vous pouvez ajouter un questionnaire ou un ensemble de questionnaires au package. Le questionnaire peut aider le client à comprendre les différentes options de paramétrage. En général, des questionnaires sont créés pour les tables de configuration principales, lorsqu’un client a besoin d’aide supplémentaire sur la manière de sélectionner un paramètre approprié. Pour plus d'informations, voir [Collecter les valeurs de configuration client](admin-gather-customer-setup-values.md).

Vérifiez que vous vous trouvez dans le tableau de bord Responsable de l'implémentation de RapidStart Services. Pour plus d'informations, voir [Utiliser le tableau de bord Responsable de l'implémentation de RapidStart Services](admin-how-to-use-the-rapidstart-services-role-center-to-track-progress.md).

> [!IMPORTANT]  
>  Lorsque vous exportez et importez des packages de configuration entre deux bases de données de votre société, les bases de données doivent avoir le même schéma pour garantir la réussite du transfert de toutes les données. Cela signifie que les bases de données doivent avoir la même table et structure de champ, dans lesquelles les tables ont les mêmes clés primaires et les champs ont les mêmes codes et types de données.  
>   
>  Vous pouvez importer un package de configuration qui a été exporté d'une base de données qui a un schéma différent que cette base de donnée cible. Toutefois, tous les tables ou champs du package de configuration manquants dans la base de données cible ne seront pas importés. Les tables avec des clés primaires différentes et des champs avec des types de données différents ne seront pas importés avec succès. Par exemple, si le package de configuration inclut une table **50000, Client** dont la clé primaire est **Code20** et que la base de données dans laquelle vous importez le package inclut la table **50000, Compte bancaire client** dont la clé primaire est **Code20 + Code 20**, les données ne seront pas importées.  

## <a name="to-create-a-configuration-package"></a>Pour créer un package configuration  
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Packages configuration**, puis sélectionnez le lien connexe.  
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs du raccourci **Général**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. Pour exclure les questionnaires de configuration, les modèles de configuration et les tables de feuille configuration du package, activez la case à cocher **Exclure les tables de configuration**. Sinon, ces tables sont automatiquement ajoutées à la liste de tables de package lorsque vous exportez le package.  
5. Sélectionnez l'action **Extraire tables**. La fenêtre de traitement par lots **Extraire tables package** s'ouvre.  
6. Choisissez le champ **Sélectionner des tables**. La fenêtre **Sélection de config.** s’ouvre.  
7. Choisissez l'action **Sélectionner tout** pour ajouter toutes les tables au package, ou activez la case à cocher **Sélectionné** pour chaque table dans la liste à ajouter.
8. Cliquez sur le bouton **OK**. Le nombre de tables que vous avez sélectionnées s’affiche dans le champ **Sélectionner des tables**. Spécifiez les options supplémentaires, puis cliquez sur le bouton **OK**. Les tables [!INCLUDE[d365fin](includes/d365fin_md.md)] sont ajoutées aux lignes de la fenêtre **Package config**.  

    > [!NOTE]  
    >  Vous pouvez également le faire dans la feuille configuration. Sélectionnez les tables que vous souhaitez inclure dans le package, puis choisissez l'action **Affecter package**.

9. Pour sélectionner les champs que vous souhaitez inclure à partir d’une table, sélectionnez la table puis, sous l'onglet **Lignes**, sélectionnez l'action **Champs**.
Spécifiez les champs qui sont inclus dans le package. Par défaut, tous les champs sont inclus.

    - Pour sélectionner uniquement les champs que vous souhaitez inclure, sélectionnez l'action **Effacer Inclus**. Pour ajouter tous les champs, choisissez l'action **Définir inclus**.  
    - Pour indiquer que les données de champ ne doivent pas être validées, désactivez la case à cocher **Champ Valider** pour le champ.  

10. Déterminez si vous avez introduit des erreurs potentielles en choisissant l'action **Valider package**. Cela peut arriver lorsque vous n’incluez pas les tables sur lesquelles votre configuration se fonde.  
11. Cliquez sur le bouton **OK**.  

Une fois que vous avez redéfini la liste des champs à inclure à partir d’une table, vous pouvez vérifier les résultats sous Excel.  

### <a name="to-filter-and-review-your-dataset"></a>Pour filtrer et réviser votre ensemble de données  
1. Pour filtrer un certain ensemble d’enregistrements à inclure dans le package, sous l'onglet **Lignes**, sélectionnez l'action **Filtres**, puis spécifiez les valeurs de filtre appropriées.  
2. Sur la fiche du package, sous l'onglet **Lignes**, sélectionnez l'action **Exporter vers Excel**.  
3. Confirmez le message qui permet d’exporter les données vers Excel. Le fichier.xlsx s’ouvre. Examinez les enregistrements qui ont été exportés.  
4. Fermez Excel.  

### <a name="to-include-a-template-for-application-to-a-table"></a>Pour inclure un modèle à appliquer dans une table  
Pour certaines tables (par exemple, une telle table qui contiendra les données de base), vous pouvez spécifier un modèle à appliquer aux données. Le modèle peut inclure les champs obligatoires que vous souhaitez appliquer à toutes les données de base que vous ne souhaitez pas voir varier. Par exemple, vous pouvez créer un modèle qui peut être utilisé pour les données client. Le modèle peut contenir tous les champs obligatoires, qui permet d’importer des informations standard de manière cohérente. Les informations qui ne peuvent pas être normalisées (par exemple, le nom du client), sont traitées lorsque vous importez des données client.

1. Dans la fenêtre **Fiche package config.**, sélectionnez une table, puis cliquez sur le champ **Modèle données**. Une liste de modèles s’affiche en fonction de la table.
2. Sélectionnez un modèle et cliquez sur le bouton **OK**.  

Une fois le package terminé, suivez la procédure suivante pour enregistrer le package dans un fichier. Vous pouvez ensuite donner le package à un client ou à un partenaire.

### <a name="to-save-and-export-a-configuration-package"></a>Pour enregistrer et exporter un package configuration  
- Dans la fenêtre **Fiche package config.**, choisissez l'action **Exporter package**.  

Le package est créé dans un fichier .rapidstart, qui fournit le contenu du package sous un format compressé. Des questionnaires de configuration, des modèles de configuration et la feuille de configuration sont ajoutés automatiquement au package, à moins que vous ne décidiez de les exclure.  

Vous pouvez enregistrer le fichier avec un nom qui est a un sens pour vous, mais vous ne pouvez pas modifier l'extension du fichier. Celle-ci doit être .rapidstart.  

### <a name="to-copy-a-configuration-package"></a>Pour copier un package configuration  
Après avoir créé un package qui répond à la plupart de vos besoins, vous pouvez l’utiliser comme base de création de packages similaires. Ceci peut accélérer la durée d’implémentation et améliorer l’aspect répétitif de RapidStart Services.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Packages configuration**, puis sélectionnez le lien connexe.  
2. Sélectionnez un package dans la liste, puis sélectionnez l'action **Copier package**.  
3. Dans le champ **Nouveau code package**, entrez un code pour le nouveau package.  
4. Cochez la case **Copier données** si vous souhaitez également copier les données de la base de données depuis le package existant.  
5. Cliquez sur le bouton **OK**.

## <a name="to-customize-a-configuration-package"></a>Pour personnaliser un package configuration
La feuille configuration permet de collecter et de définir les catégories des informations que vous souhaitez utiliser pour configurer une nouvelle société, et réorganiser les tables d’une manière logique. La mise en forme dans la feuille est basée sur une hiérarchie unique : des zones contiennent des groupes, qui contiennent des tables. Les zones et les groupes sont facultatifs, mais nécessaires si vous souhaitez afficher un aperçu du processus de configuration dans le tableau de bord RapidStart Services.

1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuille configuration**, puis sélectionnez le lien connexe.  
2.  Dans le champ **Type ligne**, choisissez **Zone**. Saisissez un nom descriptif dans le champ **Nom**.  
3.  Dans le champ **Type ligne**, choisissez **Groupe**. Saisissez un nom descriptif dans le champ **Nom**.  
4.  Dans le champ **Type ligne**, choisissez **Table**. Dans le champ **ID table**, sélectionnez la table que vous souhaitez inclure dans la feuille.  

Vous pouvez désormais affecter les tables aux packages configuration spécifiques que vous avez créés ou que vous prévoyez de créer. Pour plus d’informations, consultez la section « Pour affecter une table à un package configuration ».

## <a name="to-work-with-promoted-tables"></a>Pour utiliser les tables promues  
1. Activez la case à cocher **Table promue** pour indiquer une table qui est souvent utilisée lors du processus de paramétrage par un client typique, par exemple, la table **Compte général**. Lorsqu’une table a cette désignation, un client pourra facilement filtrer sa feuille pour afficher uniquement la liste des tables promues qui nécessitent une attention particulière.  
2. Pour afficher la vue filtrée, choisissez l'action **Promu uniquement**. La liste des tables contient uniquement les tables dont la case à cocher a été activée.  

## <a name="to-assign-a-table-to-a-configuration-package"></a>Pour affecter une table à un package configuration  
Après avoir défini les tables à traiter dans le cadre de votre configuration, vous pouvez facilement affecter les tables à des packages configuration. Vous pouvez affecter une table à un package uniquement. Dans la procédure suivante, vous affectez le package à partir de la feuille configuration.  

> [!NOTE]  
>  Vous pouvez également créer un package directement, puis ajouter des tables au package. Pour plus d’informations, consultez la section « Pour créer un package configuration ».

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuille configuration**, puis sélectionnez le lien connexe.
2. Dans la feuille de configuration, sélectionnez une ligne ou un groupe de lignes que vous souhaitez affecter à un package configuration, puis sélectionnez l'action **Affecter package**.  
3.  Sélectionnez un package de la liste, ou choisissez l'action **Nouveau** pour créer un package, puis cliquez sur le bouton **OK**.  

    Si une table n’est pas encore incluse dans le package, elle y sera ajoutée. Le champ Code package sur la ligne feuille sera complété avec le code du package auquel la table est associée.  
4. Si vous choisissez un package existant, vous pouvez visualiser le nombre de tables qui se trouvent déjà dans le package en consultant les informations du champ **Nombre de tables**.

## <a name="to-review-or-customize-existing-database-data"></a>Pour vérifier ou personnaliser les données existantes de base de données
Lors de la création d’un package configuration pour une solution, vous pouvez consulter et personnaliser les données de base de données disponibles pour les adapter aux besoins de votre client. La table de base de données doit être associée à une page.  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuille configuration**, puis sélectionnez le lien connexe.
2. Dans la feuille configuration, identifiez les tables dont vous souhaitez afficher ou personnaliser les données.  

    > [!NOTE]  
    >  Assurez-vous que chaque table dispose d’un ID page qui lui est affecté. Pour les tables [!INCLUDE[d365fin](includes/d365fin_md.md)] standard, cette valeur est automatiquement insérée. Pour les tables personnalisées, vous devez fournir l'ID.

3. Choisissez l'action **Données base de données**. La fenêtre de la page associée s’ouvre.
4. Révisez les informations disponibles. Modifiez-les selon vos besoins en supprimant les enregistrements qui ne sont pas appropriés ou en ajoutant de nouveaux enregistrements.    

## <a name="to-copy-data-from-a-test-environment-to-a-production-environment"></a>Pour copier des données d'un environnement de test vers un environnement de production  
Une fois que vous avez contrôlé et testé toutes vos informations de paramétrage, vous pouvez copier des données vers votre environnement de production. Vous créez une société dans la même base de données.

1. Ouvrez et initialisez la nouvelle société.  
2. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuille configuration**, puis sélectionnez le lien connexe.  
3. Sélectionnez l'action **Copier les données de la société**.  
4. Dans la fenêtre **Copier les données de la société**, choisissez le champ **Copier de**. La fenêtre **Sociétés** s’ouvre.  
5. Sélectionnez la société depuis laquelle copier des données, puis cliquez sur le bouton **OK**. Une liste de tables sélectionnées dans la feuille configuration s’ouvre. Seules les tables qui contiennent des enregistrements sont incluses dans cette liste.
6. Sélectionnez les tables à partir desquelles vous souhaitez copier des données, puis choisissez l'action **Copier données**. Dans la fenêtre **Copier les données de la société**, choisissez **OK**.  

## <a name="see-also"></a>Voir aussi  
[Collecter les valeurs de configuration client](admin-gather-customer-setup-values.md)  
[Configurer une société](admin-set-up-company-configuration.md)  
[Configuration d'une société avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
