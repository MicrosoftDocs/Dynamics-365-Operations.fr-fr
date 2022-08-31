---
title: Rapport Comparer le stockage du prix des articles
description: Découvrez comment générer un rapport Comparer le stockage du prix des articles, puis parcourir et/ou exporter le résultat.
author: JennySong-SH
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c6373679299b68413d75236ca8cc18ceba03e091
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334983"
---
# <a name="compare-item-prices-storage-report"></a>Comparer l’état de stockage des prix des articles

[!include [banner](../includes/banner.md)]

Cet article explique comment exécuter un rapport **Comparer le stockage du prix des articles** et rendre la sortie disponible au format numérique, soit en tant que page interactive dans Dynamics 365 Supply Chain Management ou en tant que document exporté dans l’un des différents formats.

Lorsque vous affichez le rapport dans votre navigateur, les colonnes et les soldes globaux sont ajustés de façon dynamique, selon la disposition que vous avez configurée. Vous pouvez trier les résultats, les filtrer, explorer les données, etc.

Les résultats du rapport sont stockés dans l’entité de données **Comparer le prix des articles**, qui vous permet de filtrer et d’exporter les résultats dans un format tel que CSV ou Microsoft Excel.

Le rapport **Comparer le stockage du prix des articles** est utile dans les cas où la sortie contient plusieurs lignes. Par exemple, la sortie contiendra plusieurs lignes si plus de 40 000 articles ont un prix d’article en attente dans la version d’évaluation des coûts.

## <a name="turn-the-compare-item-prices-storage-feature-on-or-off"></a>Activer ou désactiver la fonctionnalité de sauvegarde de comparaison des prix d'article

Pour pouvoir utiliser cette fonctionnalité, il doit être activé pour votre système. Depuis la version 10.0.29 de Supply Chain Management, la fonctionnalité est obligatoire et ne peut pas être désactivée. Si vous exécutez une version antérieure à 10.0.29, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Sauvegarde de comparaison des prix d'article* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="generate-a-compare-item-prices-storage-report"></a>Générer un rapport Comparer le stockage du prix des articles

Procédez comme suit pour générer et stocker un rapport **Comparer le stockage du prix des articles** :

1. Accédez à **Gestion des coûts > Recherches et états > Rapports de coûts prédéterminés > Comparer le stockage du prix des articles**.

1. Sélectionnez **Nouveau** pour ouvrir le volet **Comparer le prix des articles**. Définissez les options suivantes pour définir les prix à comparer dans votre rapport :

    - Dans le raccourci **Paramètres**, attribuez un **Nom** unique au rapport et utilisez les champs des sections **Prix en attente à comparer** et **Prix utilisés pour la comparaison** pour définir les prix et les dates à comparer.
    - Dans le raccourci **Enregistrements à inclure**, configurez des filtres et des contraintes pour définir les données à inclure dans le rapport.
    - Dans le raccourci **Exécuter en arrière-plan**, définissez comment, quand et à quelle fréquence vous souhaitez générer le rapport.
    > [!NOTE]
    > Ce rapport est toujours exécuté dans le cadre d’un traitement par lots.

1. Sélectionnez **OK** pour appliquer vos paramètres et fermer le volet.

1. Une fois le traitement par lots terminé, il sera répertorié sur la page **Comparer le stockage du prix des articles**. Vous devrez peut-être actualiser la page pour voir le rapport.

## <a name="explore-the-compare-item-prices-storage-report"></a>Explorer le rapport Comparer le stockage du prix des articles

Après avoir généré un rapport, vous pouvez l’afficher et l’explorer à tout moment comme suit :

1. Accédez à **Gestion des coûts > Recherches et états > Rapports de coûts prédéterminés > Comparer le stockage du prix des articles**.

1. Sélectionnez un rapport dans la liste.

1. Effectuez l’une des opérations suivantes :

    - Sélectionnez **Vue d’ensemble** pour obtenir une vue d’ensemble des résultats de votre rapport.
    - Sélectionnez **Afficher les détails** pour obtenir une vue plus détaillée de votre rapport

1. Une fois que la vue sélectionnée s’ouvre, vous pouvez effectuer les opérations suivantes :

    - Sélectionner presque tous les en-têtes de colonne pour trier ou filtrer la table selon les valeurs de cette colonne, comme avec la plupart des formulaires standard dans Supply Chain Management. Notez qu’il n’est pas possible de trier ou de filtrer la colonne **% prix modification nette**, car il s’agit d’un champ calculé.
    - Sélectionner **Affichage des dimensions** pour ouvrir un volet dans lequel vous pouvez choisir la colonne de dimension à inclure dans le formulaire. Définissez **Enregistrer le paramétrage** sur **Oui** si vous souhaitez enregistrer ces paramètres afin qu’ils soient conservés lors de la prochaine ouverture du rapport. Sélectionnez **OK** pour appliquer vos paramètres et fermer.
    - Sélectionner une ligne du formulaire, puis sélectionner **Afficher les détails** pour afficher plus d’informations sur l’élément sélectionné. Vous pourrez ensuite explorer les données.
    - Sélectionner une ligne du formulaire, puis sélectionner **Afficher le graphique de comparaison** pour afficher une représentation graphique interactive de vos résultats en relation avec l’élément sélectionné. Vous pouvez explorer ces résultats en sélectionnant divers éléments graphiques dans le graphique et sa légende.
    - Sélectionner une ligne du formulaire, puis sélectionner **Afficher les détails du calcul** pour afficher plus d’informations sur les calculs associés à l’élément sélectionné. Vous pourrez ensuite explorer les données.

## <a name="export-the-compare-item-prices-storage-report"></a>Exporter le rapport Comparer le stockage du prix des articles

Chaque rapport que vous générez est stocké dans l’entité de données **Comparer le prix des articles**. Vous pouvez utiliser les fonctionnalités de gestion des données standard de Supply Chain Management pour exporter les données de cette entité dans un format de données pris en charge, y compris CSV ou Microsoft Excel.

L’exemple suivant montre comment exporter un rapport **Comparer le stockage du prix des articles** :

1. Accédez à **Administration système > Espaces de travail > Gestion des données**.

1. Sélectionnez le bouton **Exporter** dans la section **Gestion des données**.

1. La page **Exporter** s’ouvre pour vous permettre de configurer votre tâche d’exportation. Commencez par attribuer un **Nom de groupe** à votre tâche.

1. Dans la section **Entités sélectionnées**, sélectionnez **Ajouter une entité** pour ouvrir une boîte de dialogue dans laquelle vous pouvez définir les options suivantes :

    - **Nom de l’entité** : sélectionnez **Comparer le prix des articles**.
    - **Format des données cibles** : choisissez le format d’exportation.

1. Sélectionnez **Ajouter** pour ajouter la nouvelle ligne, puis sélectionnez **Fermer** pour fermer la boîte de dialogue.

1. Généralement, vous exporterez un rapport à la fois. Pour ce faire, définissez un **Filtre** pour la ligne que vous venez d’ajouter au volet **Recherche**. Cela vous permettra de définir les rapports de l’entité **Comparer le prix des articles** que vous souhaitez inclure dans votre exportation. Définissez les options de filtre suivantes pour exporter un rapport :

    - Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une nouvelle ligne.
    - Définissez **Table** sur **Comparer le prix des articles**.
    - Définissez **Table dérivée** sur **Comparer le prix des articles**.
    - Définissez **Champ** sur le champ que vous souhaitez filtrer. Généralement, vous utiliserez **Nom d’exécution** ou **Temps d’exécution**.
    - Définissez **Critères** sur la valeur du champ sélectionné que vous souhaitez rechercher (soit le nom du rapport, soit l’heure de génération du rapport).
    - Si nécessaire, ajoutez d’autres lignes à la table **Plage** jusqu’à ce que vous ayez identifié de manière unique le rapport que vous recherchez.

1. Sélectionnez **OK** pour enregistrer vos paramètres et fermer.

1. Sélectionnez **Enregistrer** pour enregistrer vos paramètres d’exportation.

1. Ouvrez l’onglet **Options d’exportation** et sélectionnez **Exporter maintenant** pour générer le fichier d’exportation.

1. La page **Résumé de l’exécution** s’ouvre pour vous permettre d’afficher le statut de votre tâche d’exportation et la liste des entités exportées. Sélectionnez l’entité **Comparer le prix des articles** répertoriée dans la zone **Statut de traitement de l’entité**, puis sélectionnez **Télécharger le fichier** pour télécharger les données exportées depuis cette entité.

Pour plus d’informations sur l’utilisation de la gestion des données pour exporter des données, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]