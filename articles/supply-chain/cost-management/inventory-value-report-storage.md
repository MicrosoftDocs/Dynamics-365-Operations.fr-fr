---
title: État de stockage de la valeur de stock
description: Cette rubrique explique comment exécuter un état de stockage des valeurs des stocks et rendre la sortie disponible au format numérique, soit en tant que page interactive dans Microsoft Dynamics 365 Supply Chain Management ou en tant que document exporté dans l’un des différents formats.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 6f0c382c56ea0c576134f2871cba7a71b44e6528
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262475"
---
# <a name="inventory-value-storage-report"></a>État de stockage de la valeur de stock

Cette rubrique explique comment exécuter un état de **stockage des valeurs des stocks** et rendre la sortie disponible au format numérique, soit en tant que page interactive dans Microsoft Dynamics 365 Supply Chain Management ou en tant que document exporté dans l’un des différents formats.

Lorsque vous affichez le rapport dans votre navigateur, les colonnes et les soldes globaux sont ajustés de façon dynamique, selon la disposition configurée. Vous pouvez trier les résultats, les filtrer, explorer les données, etc.

Les résultats de l’état sont stockés dans l’entité de données **Valeur de stock**. Par conséquent, vous pouvez filtrer et exporter les résultats dans un format tel que des valeurs séparées par des virgules (CSV) ou Microsoft Excel.

L’état **Stockage de la valeur de stock** est utile lorsque la sortie contient de nombreuses lignes. Par exemple, vous avez 50 000 articles et 300 magasins créés comme entrepôts. Dans ce cas, si vous demandez des soldes de fin de stock par article, site et entrepôt, la sortie contiendra de nombreuses lignes.

> [!NOTE]
> L’état n’inclut pas les sous-totaux définis dans la disposition de l’état. Il n’inclura pas non plus les soldes comptables, même lorsqu’ils sont définis dans la disposition de l’état. Le rapprochement avec la comptabilité doit être effectué à l’aide de balances comptables.

## <a name="turn-on-the-inventory-value-storage-feature"></a>Activer la fonctionnalité de stockage de valeur de stock

Avant de pouvoir générer un état **Stockage de la valeur de stock**, vous devez activer la fonctionnalité dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module** - Gestion des coûts
- **Nom de la fonctionnalité** - Stockage de valeur de stock

## <a name="generate-an-inventory-value-storage-report"></a>Générer un état de stockage de la valeur de stock

Procédez comme suit pour générer et stocker un état **Stockage de valeur de stock**.

1. Accédez à **Gestion des coûts \> Recherches et états \> Stockage des états de valeur de stock**.
1. Sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Valeur de stock** qui apparaît, définissez les valeurs suivantes pour définir les enregistrements à inclure dans votre état :

    - Sur l’organisateur **Paramètres**, entrez un nom unique pour l’état et utilisez les champs de la section **Intervalle de dates** pour définir les enregistrements à inclure dans le rapport. Pour définir l’intervalle de dates, vous pouvez soit sélectionner une plage prédéfinie (par rapport à la date de génération du rapport) dans le champ **Code d’intervalle de dates** ou sélectionner des dates spécifiques dans les champs **Date de début** et **Date de fin**.
    - Dans l’organisateur **Enregistrements à inclure**, configurez des filtres et des contraintes pour définir les données incluses dans le rapport.
    - Sur l’organisateur **Exécuter en arrière-plan**, spécifiez comment, quand et à quelle fréquence le rapport est généré.

    > [!NOTE]
    > Ce rapport est toujours exécuté dans le cadre d’un traitement par lots.

1. Sélectionnez **OK** pour appliquer vos paramètres et fermer la boîte de dialogue.

Lorsque le traitement par lots est terminé, l’état est répertorié sur la page **Stockage de valeur de stock**. Vous devrez peut-être actualiser la page pour afficher l’état.

## <a name="explore-an-inventory-value-storage-report"></a>Explorer un état de stockage de la valeur de stock

Après avoir généré un rapport, vous pouvez l’afficher et l’explorer à tout moment en procédant comme suit :

1. Accédez à **Gestion des coûts \> Recherches et états \> Stockage des états de valeur de stock**.
1. Sélectionnez un état dans la liste.
1. Sélectionner **Afficher les détails** pour afficher le contenu du rapport.
1. Explorez le rapport en suivant l’une de ces étapes :

    - Comme avec la plupart des pages dans Supply Chain Management, vous pouvez sélectionner presque tous les en-têtes de colonne pour trier ou filtrer la grille selon les valeurs de cette colonne.
    - Utilisez le champ **Filtre** pour filtrer le rapport selon n’importe quelle valeur dans l’une des colonnes disponibles.
    - Utilisez le menu d’affichage (au-dessus du champ **Filtre**) pour enregistrer et charger vos combinaisons préférées d’options de tri et de filtrage.

## <a name="export-an-inventory-value-storage-report"></a>Exporter un état de stockage de la valeur de stock

Chaque rapport que vous générez est stocké dans l’entité de données **Valeur de stock**. Vous pouvez utiliser les fonctionnalités de gestion des données standard de Supply Chain Management pour exporter les données de cette entité dans un format de données pris en charge, comme CSV ou Excel.

L’exemple suivant montre comment exporter un état **Rapport sur la valeur de stock**.

1. Allez dans **Administration système \> Espaces de travail \> Gestion des données**.
1. Dans la section **Importer/Exporter**, sélectionnez la vignette **Exporter**. 
1. Sur la page **Exporter** qui s’affiche, vous allez configurer la tâche d’exportation. Commencez par entrer le nom du groupe pour la tâche.
1. Dans la section **Entités sélectionnées**, sélectionnez **Ajouter une entité**.
1. Dans la boîte de dialogue qui s’affiche, sélectionnez les champs suivants :

    - **Nom de l’entité** - Sélectionnez **Valeur de stock**.
    - **Format de données cible** - Sélectionnez le format vers lequel exporter les données.

1. Sélectionnez **Ajouter** pour ajouter la nouvelle ligne, puis sélectionnez **Fermer** pour fermer la boîte de dialogue.
1. Généralement, vous exporterez un état à la fois. Pour exporter un seul rapport, configurez un filtre pour la ligne que vous venez d’ajouter à la boite de dialogue **Recherche**. De cette façon, vous pouvez définir quel rapport de l’entité **Valeur de stock** est incluse dans votre exportation. Procédez comme suit pour définir les options de filtre suivantes pour exporter un rapport :

    1. Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne.
    2. Définissez le champ **Table** sur **Valeur de stock**.
    3. Définissez le champ **Table dérivée** sur **Valeur de stock**.
    4. Définissez le champ **Champ** sur le champ que vous souhaitez filtrer. Généralement, vous utiliserez le champ **Nom de l’exécution** et/ou le champ **Heure de l’exécution**.
    5. Définissez le champ **Critères** sur la valeur à rechercher dans le champ sélectionné. (Si vous avez sélectionné le champ **Nom de l’exécution** à l’étape précédente, cette valeur sera le nom du rapport. Si vous avez sélectionné **Heure d’exécution**, ce sera l’heure à laquelle le rapport a été généré.)
    6. Ajoutez d’autres lignes à l’onglet **Plage** au besoin, jusqu’à ce que vous ayez identifié de manière unique le rapport que vous recherchez.

1. Sélectionnez **OK** pour enregistrer vos paramètres et fermer la boîte de dialogue.
1. Sélectionnez **Enregistrer** pour enregistrer vos paramètres d’exportation.
1. Sous l’onglet **Options d’exportation**, sélectionnez **Exporter maintenant** pour générer le fichier d’exportation.
1. Sur la page **Résumé de l’exécution** qui s’ouvre, vous pouvez afficher le statut de votre tâche d’exportation et la liste des entités exportées. Dans la section **Statut de traitement de l’entité**, sélectionnez l’entité **Valeur de stock**, puis sélectionnez **Télécharger le fichier** pour télécharger les données exportées depuis cette entité.

Pour plus d’informations sur l’utilisation de la gestion des données pour exporter des données, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]