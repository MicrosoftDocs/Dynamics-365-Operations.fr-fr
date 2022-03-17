---
title: États de valeur de stock
description: Cette rubrique décrit comment paramétrer, générer et utiliser le rapport sur la valeur du stock. Ces rapports fournissent des détails sur les quantités et les montants physiques et financiers de votre stock.
author: banluo-ms
ms.date: 10/19/2021
ms.topic: article
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: banluo
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: d78cde26d238d18744adde9a576552588736e619
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384693"
---
# <a name="inventory-value-reports"></a>États de valeur de stock

[!include [banner](../includes/banner.md)]

Les rapports sur la valeur du stock fournissent des détails sur les quantités et les montants physiques et financiers de votre stock. Vous pouvez afficher les rapports de différentes manières. Par exemple, vous pouvez afficher des totaux ou des transactions, ou filtrer par éléments ou par plage de temps. Vous pouvez afficher les valeurs du coût des marchandises vendues (COGS) ou les valeurs des travaux en cours, et définir d’autres options.

Les rapports sur la valeur du stock vous permettent d’effectuer les tâches suivantes :

- Faire le rapprochement entre la comptabilité et le stock.
- Consulter le stock disponible et les valeurs pour une période spécifique.
- Créer des configurations de rapport adaptées à un objectif spécifique.
- Enregistrer les configurations de rapport afin qu’elles puissent être utilisées plusieurs fois.
- Ajouter des plages pour filtrer les données lorsque vous exécutez un rapport.

## <a name="types-of-inventory-value-report"></a>Types de rapport sur la valeur du stock

Il existe deux types de rapports sur la valeur du stock : **Valeur du stock** (rapport standard) et **Rapport de valeur de stock (rapport de stockage)**.

### <a name="standard-inventory-value-report"></a>Rapport de valeur de stock standard

Le rapport **Valeur du stock** standard est un rapport simple qui vous permet de sélectionner les informations incluses, puis affiche celles-ci à l’écran. Il n’enregistre pas les résultats. Il ne fournit pas non plus de fonctionnalités interactives pour le filtrage, l’exploration, la navigation ou l’exportation. Pour ces raisons, nous vous recommandons d’utiliser le rapport de **Valeur de stock** pour le stockage à la place dans la plupart des cas.

### <a name="inventory-value-report-storage-report"></a>Rapport de stockage de la valeur de stock

Le rapport **stockage des valeurs des stocks** fournit la sortie au format numérique, soit en tant que page interactive dans Microsoft Dynamics 365 Supply Chain Management ou en tant que document exporté dans l’un des différents formats.

Lorsque vous affichez le rapport dans votre navigateur, les colonnes et les soldes globaux sont ajustés de façon dynamique, selon la disposition configurée. Vous pouvez trier les résultats, les filtrer, explorer les données, etc.

Les résultats de l’état sont stockés dans l’entité de données **Valeur de stock**. Par conséquent, vous pouvez filtrer et exporter les résultats dans un format tel que des valeurs séparées par des virgules (CSV) ou Microsoft Excel.

L’état **Stockage de rapport de la valeur de stock** est utile lorsque la sortie contient de nombreuses lignes. Par exemple, vous avez 50 000 articles et 300 magasins créés comme entrepôts. Dans ce cas, si vous demandez des soldes de fin de stock par article, site et entrepôt, la sortie contiendra de nombreuses lignes.

> [!NOTE]
> Le rapport **Stockage de l’état de valeur de stock** n’inclut pas les sous-totaux définis dans la disposition de l’état. Il n’inclut pas non plus les soldes comptables, même si ces soldes sont définis dans la disposition de l’état. Le rapprochement avec la comptabilité doit être effectué à l’aide de balances comptables. Cependant, le rapport **Valeur du stock** standard inclut ces sous-totaux et soldes.

## <a name="turn-the-inventory-value-report-storage-feature-on-or-off"></a>Activer ou désactiver la fonctionnalité de stockage de rapport de valeur de stock

À compter de la version 10.0.25 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Stockage de l’état de valeur de stock* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="define-inventory-value-report-configurations"></a><a name="report-configuration"></a>Définir les configurations de rapport de valeur de stock

Utilisez la page **Rapports de valeur de stock** pour configurer le contenu qui est inclus dans les différents types de rapport de valeur de stock. Vous pouvez définir un nombre illimité de types de rapports. Chaque fois que vous générez l’un ou l’autre type de rapport de valeur de stock, vous sélectionnerez un type de rapport.

1. Accédez à **Cost Management \> Paramétrage des stratégies comptables de stock \> Rapports de valeur de stock**.
1. Utilisez l’une des procédures suivantes :

    - Pour modifier un rapport existant, sélectionnez-le dans le volet de liste, puis sélectionnez **Modifier** sur le volet Actions.
    - Pour créer un rapport : dans le volet Actions, sélectionnez **Nouveau**.

1. Dans l’en-tête du rapport nouveau ou sélectionné, définissez les champs suivants :

    - **ID** – Entrez un identificateur court pour le rapport. Cette valeur doit être unique parmi toutes les configurations de rapport de valeur de stock. Elle ne peut pas être modifiée après avoir enregistré une nouvelle configuration.
    - **Nom** – Entrez un nom descriptif pour le rapport.

1. Si vous créez une configuration de rapport, sélectionnez **Enregistrer** dans le volet Actions pour rendre les champs restants disponibles.
1. Dans l’organisateur **Général**, définissez les champs suivants :

    - **Intervalle de dates** – Sélectionnez un intervalle de dates prédéfini. Vous pouvez remplacer cet intervalle de dates lorsque vous exécutez le rapport.
    - **Plage** – Sélectionnez *Date de comptabilisation* ou *Heure de la transaction*, en fonction de la date et de l’heure à utiliser lors de l’extraction des enregistrements pour le rapport.
    - **Ensemble de dimensions** – Sélectionnez l’ensemble de dimensions pour lequel exécuter les données. (Les dimensions sont définies dans la comptabilité.) Par exemple, vous pouvez exécuter les données pour *Compte principal* ou pour *Compte principal + Unité commerciale*. L’ensemble de dimensions que vous sélectionnez ne doit pas comporter plus de deux dimensions. Pour plus d’informations, voir [Ensemble de dimensions financières](../../finance/general-ledger/financial-dimension-sets.md).

1. Dans l’organisateur **Colonnes**, définissez les champs suivants. Ces champs contrôlent les colonnes incluses dans votre rapport et les types de données que ces colonnes contiennent.

    - **Stock** – Définissez cette option sur *Oui* pour afficher les valeurs de stock. Vous pouvez ensuite rapprocher ces valeurs avec les soldes des comptes généraux.
    - **Travaux en cours** – Définissez cette option sur *Oui* pour afficher les travaux en cours. Vous pouvez ensuite rapprocher ces valeurs avec les soldes du compte de travaux en cours dans la comptabilité. Lorsque vous définissez cette option sur *Oui*, le rapport n’affiche que les quantités physiques et les quantités de stock ayant le statut de travaux en cours. Les ordres de fabrication qui ont le statut de travaux en cours ont été prélevés ou signalés comme terminés, mais ils n’ont pas été terminés.
    - **COGS différé** – Définissez cette option sur *Oui* pour afficher une colonne qui indique les quantités physiques et les quantités de stock pour le COGS différé. Le COGS différé est affiché en utilisant des quantités et des montants physiques, car il compense les quantités et les montants du bon de livraison.
    - **COGS** – Définissez cette option sur *Oui* pour afficher une colonne qui indique les quantités et les montants financiers pour le COGS. Le COGS est affiché en utilisant des quantités et des montants financiers, car il compense les quantités et les montants de la facture.
    - **Pertes et profits** – Définissez cette option sur *Oui* pour afficher une colonne qui affiche le montant financier enregistré dans les comptes de pertes et profits pour le stock.
    - **Imprimer les valeurs de compte cumulées pour comparaison** – Définissez cette option sur *Oui* pour afficher une colonne qui montre le solde du compte général. De cette façon, vous n’aurez pas à vérifier la balance comptable. Cette option ne fonctionne qu’avec le rapport **Valeur de stock** standard, pas avec le rapport **Stockage du rapport de valeur de stock**. Après avoir défini cette option sur *Oui*, vous devez utiliser les champs suivants pour spécifier chaque compte général à répertorier, selon les options de **Position financière** que vous avez activées.

        > [!NOTE]
        > Si vous sélectionnez un compte *total* pour l’un de ces champs, le montant de chaque compte de stock inclus dans le compte total et le montant du compte total seront affichés.

        - **Compte de stock** – Spécifiez le compte général pour lequel afficher les informations de stock. (Les options **Stock** et **Imprimer les valeurs de compte cumulées pour comparaison** doivent être définies sur *Oui*.)
        - **Compte de travaux en cours** – Spécifiez le compte général pour lequel afficher les informations sur les travaux en cours. (Les options **Travaux en cours** et **Imprimer les valeurs de compte cumulées pour comparaison** doivent être définies sur *Oui*.)
        - **Compte COGS différé** – Spécifiez le compte général pour lequel afficher les informations sur le COGS différé. (Les options **COGS différé** et **Imprimer les valeurs de compte cumulées pour comparaison** doivent être définies sur *Oui*.)
        - **Compte COGS** – Spécifiez le compte général pour lequel afficher les informations sur COGS. (Les options **COGS** et **Imprimer les valeurs de compte cumulées pour comparaison** doivent être définies sur *Oui*.)

    - **Résumer les valeurs physiques et financières** – Définissez cette option sur *Oui* pour afficher une colonne qui indique la quantité totale du stock et le montant du stock (un résumé des valeurs de stock physiques et financières). Si cette option est définie sur *Non*, le rapport affichera les valeurs de stock physiques et financières.
    - **Inclure non comptabilisé** Définissez cette option sur *Oui* pour afficher une colonne qui montre les transactions qui n’ont jamais été comptabilisées. Les transactions pour les types d’articles suivants peuvent ne pas être comptabilisées :

        - Articles reçus et pas encore facturés lorsque l’option **Enregistrer le stock physique** est désactivée pour le groupe de modèles d’articles concerné.
        - Articles reçus et pas encore facturés lorsque l’option **Enregistrer le reçu de produit dans la comptabilité** est désactivée sur le raccourci **Réception du produit** sur l’onglet **Général** de la page **Paramètres de la comptabilité fournisseur** (**Comptabilité fournisseur \> Configurer \> Paramètres de la comptabilité fournisseur**).

    - **Calculer le coût unitaire moyen** – Définissez cette option sur *Oui* pour afficher une colonne indiquant le coût unitaire moyen. Le coût unitaire moyen est le montant total divisé par la quantité totale.
    - **Quantité et valeur totales** – Définissez cette option sur *Oui* pour afficher les colonnes qui indiquent la quantité totale du stock physique (et les quantités financières) et le montant total du stock physique (et des montants financiers). Vous pouvez définir cette option sur *Oui* uniquement si l’option **Résumer les valeurs physiques et financières** est définie sur *Non*.
    - **Dimensions du stock** – Dans cette grille, cochez la case **Afficher** pour chaque dimension à afficher sur le rapport. Seules les dimensions où l’option **Stock financier** est activée affichera les valeurs sur le rapport. Les autres dimensions n’afficheront que des colonnes vides. Pour les dimensions que vous choisissez d’afficher, vous pouvez cocher la case **Total** pour inclure les totaux aussi.
    - **ID de la ressource** – Définissez l’option **Afficher** sur *Oui* pour afficher une colonne qui identifie l’article pour chaque ligne. Définissez l’option **Total** sur *Oui* pour inclure les totaux aussi. Selon le type d’article répertorié dans chaque ligne, la colonne affiche l’un des types d’informations suivants :

        - **Matériel** – La colonne indique la valeur de champ `ItemID` pour l’enregistrement d’article pertinent.
        - **Main-d’œuvre** – La colonne indique la valeur de champ `WorkCenterID` pour l’enregistrement de main-d’œuvre pertinent.
        - **Coût indirect** – La colonne indique la valeur de champ `CodeID` pour l’enregistrement de coût pertinent.

        Si l’option **Afficher** est définie sur *Non* pour les champs **ID de la ressource** et **Groupe de ressources**, vous ne verrez qu’une valeur de stock totale basée sur les dimensions de stock que vous avez sélectionnées.

    - **Groupe de ressources** – Définissez l’option **Afficher** sur *Oui* pour afficher une colonne qui identifie de groupe de ressources pour chaque ligne. Définissez l’option **Total** sur *Oui* pour inclure les totaux aussi. Selon le type d’article répertorié dans chaque ligne, la colonne affiche l’un des types d’informations suivants :

        - **Matériel** – La colonne indique la valeur de champ `ItemGroup` pour l’enregistrement d’article pertinent.
        - **Main-d’œuvre** – La colonne indique la valeur de champ `WorkcenterGroup` pour l’enregistrement de main-d’œuvre pertinent.
        - **Coût indirect** – La colonne indique la valeur de champ `CostGroup` pour l’enregistrement de coût pertinent. (La valeur de `CostGroupType` doit être *Indirect*.)

        Si l’option **Afficher** est définie sur *Non* pour les champs **ID de la ressource** et **Groupe de ressources**, vous ne verrez qu’une valeur de stock totale basée sur les dimensions de stock que vous avez sélectionnées.

1. Dans le raccourci **Lignes**, définissez les champs suivants. Ces champs vous permettent d’ajouter les sous-sections liées aux travaux en cours correspondantes au rapport ou de les en supprimer.

    - **Matériel** – Définissez cette option sur *Oui* pour afficher des informations sur le matériel. *Matériel* est un type de ressource par défaut, car le matériel doit être inclus dans toutes les configurations de rapport pour créer une sortie fiable.
    - **Main-d’œuvre** – Définissez cette option sur *Oui* pour afficher les coûts de main-d’œuvre des travaux en cours.
    - **Coût indirect** – Définissez cette option sur *Oui* pour afficher les coûts indirects des travaux en cours.
    - **Externalisation directe** – Définissez cette option sur *Oui* pour afficher les coûts d’Externalisation directe des travaux en cours. Ces informations sont utiles à la sous-traitance.
    - **Niveau de détail** – Sélectionnez une option d’affichage pour le rapport :

        - *Transactions* – Afficher toutes les transactions pertinentes sur le rapport. Notez que vous pouvez rencontrer des problèmes de performances lorsque vous affichez des rapports qui incluent un grand volume de transactions. Par conséquent, si vous souhaitez utiliser cette option d’affichage, nous vous recommandons d’utiliser le rapport **Stockage du rapport de valeur de stock**.
        - *Totaux* – Voir le résultat total.

    - **Inclure le solde d’ouverture** – Définissez cette option sur *Oui* pour afficher le solde d’ouverture. Cette option est la seule disponible lorsque le champ **Niveau de détail** est défini sur *Transactions*.

## <a name="generate-an-inventory-value-report-storage-report"></a>Générer un état de stockage de rapport de valeur de stock

Procédez comme suit pour générer et stocker un état **Stockage de rapport de valeur de stock**.

1. Accédez à **Gestion des coûts \> Recherches et états \> Stockage des états de valeur de stock**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Valeur du stock**, sur le raccourci **Paramètres**, définissez les champs suivants :

    - **Nom** – Entrez un nom unique pour le rapport.
    - **ID** – Sélectionnez la [configuration du rapport de valeur de stock](#report-configuration) à utiliser pour le rapport. La configuration établit des options pour les colonnes et les lignes qui seront incluses dans votre rapport.
    - **Intervalle de dates** – Utilisez les champs de cette section pour définir les enregistrements à inclure dans le rapport. Pour définir l’intervalle de dates, vous pouvez soit sélectionner une plage prédéfinie (par rapport à la date de génération du rapport) dans le champ **Code d’intervalle de dates** ou sélectionner des dates spécifiques dans les champs **Date de début** et **Date de fin**.

1. Dans l’organisateur **Enregistrements à inclure**, configurez des filtres et des contraintes pour définir les données incluses sur le rapport. Sélectionnez **Filtrer** pour ouvrir une boîte de dialogue d’Éditeur de requête standard, dans laquelle vous pouvez définir des critères de sélection, des critères de tri et des jointures. Les champs fonctionnent comme pour d’autres types de requêtes dans Supply Chain Management. Tous ces filtres seront appliqués aux transactions de stock mais pas au solde comptable. Gardez ce comportement à l’esprit lorsque vous configurez vos filtres. Sinon, vous pourriez voir un écart entre le stock et la comptabilité.
1. Sur l’organisateur **Exécuter en arrière-plan**, spécifiez comment, quand et à quelle fréquence le rapport est généré. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.

    > [!NOTE]
    > Ce rapport est toujours exécuté dans le cadre d’un traitement par lots.

1. Sélectionnez **OK** pour appliquer vos paramètres et fermer la boîte de dialogue.

Lorsque le traitement par lots est terminé, l’état est répertorié sur la page **Stockage de valeur de stock**. Vous devrez peut-être actualiser la page pour afficher l’état.

> [!IMPORTANT]
> Dans la configuration de rapport de valeur de stock sélectionnée, vous pouvez obtenir un solde d’ouverture incorrect si vous sélectionnez la même date dans les champs **Date de début** et **Date de fin**, et si vous définissez également l’option **Inclure le solde d’ouverture** sur *Oui*.

## <a name="explore-an-inventory-value-report-storage-report"></a>Explorer un rapport de stockage de rapport de valeur de stock

Après avoir généré un rapport, vous pouvez l’afficher et l’explorer à tout moment en procédant comme suit :

1. Accédez à **Gestion des coûts \> Recherches et états \> Stockage des états de valeur de stock**.
1. Sélectionnez un état dans la liste. La page affiche les détails de la [configuration du rapport de valeur de stock](#report-configuration) qui a été utilisé pour générer le rapport sélectionné.
1. Dans le volet Actions, sélectionnez **Afficher les détails** pour afficher le contenu du rapport.
1. Explorez le rapport en suivant l’une de ces étapes :

    - Comme avec la plupart des pages dans Supply Chain Management, vous pouvez sélectionner presque tous les en-têtes de colonne pour trier ou filtrer la grille selon les valeurs de cette colonne.
    - Utilisez le champ **Filtre** pour filtrer le rapport selon n’importe quelle valeur dans l’une des colonnes disponibles.
    - Utilisez le menu d’affichage (au-dessus du champ **Filtre**) pour enregistrer et charger vos combinaisons préférées d’options de tri et de filtrage.

## <a name="export-an-inventory-value-report-storage-report"></a>Exporter un état de stockage de rapport de valeur de stock

Chaque rapport que vous générez est stocké dans l’entité de données **Valeur de stock**. Vous pouvez utiliser les fonctionnalités de gestion des données standard de Supply Chain Management pour exporter les données de cette entité dans un format de données pris en charge, comme CSV ou Excel.

L’exemple suivant montre comment exporter un état **Stockage de rapport sur la valeur de stock**.

1. Allez dans **Administration système \> Espaces de travail \> Gestion des données**.
1. Dans la section **Importer/Exporter**, sélectionnez la vignette **Exporter**.
1. Sur la page **Exporter** qui s’affiche, vous allez configurer la tâche d’exportation. Commencez par entrer le nom du groupe pour la tâche.
1. Dans la section **Entités sélectionnées**, sélectionnez **Ajouter une entité**.
1. Dans la boîte de dialogue qui s’affiche, sélectionnez les champs suivants :

    - **Nom de l’entité** - Sélectionnez *Valeur de stock*.
    - **Format de données cible** - Sélectionnez le format vers lequel exporter les données.

1. Sélectionnez **Ajouter** pour ajouter la nouvelle ligne, puis sélectionnez **Fermer** pour fermer la boîte de dialogue.
1. Généralement, vous exporterez un état à la fois. Pour exporter un seul rapport, configurez un filtre pour la ligne que vous venez d’ajouter à la boite de dialogue **Recherche**. De cette façon, vous pouvez définir quel rapport de l’entité **Valeur de stock** est incluse dans votre exportation. Procédez comme suit pour définir les options de filtre suivantes pour exporter un rapport :

    1. Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne.
    2. Définissez le champ **Table** sur *Valeur de stock*.
    3. Définissez le champ **Table dérivée** sur *Valeur de stock*.
    4. Définissez le champ **Champ** sur le champ que vous souhaitez filtrer. Généralement, vous utiliserez le champ **Nom de l’exécution** et/ou le champ **Heure de l’exécution**.
    5. Définissez le champ **Critères** sur la valeur à rechercher dans le champ sélectionné. (Si vous avez sélectionné le champ **Nom de l’exécution** à l’étape précédente, cette valeur sera le nom du rapport. Si vous avez sélectionné **Heure d’exécution**, ce sera l’heure à laquelle le rapport a été généré.)
    6. Ajoutez d’autres lignes à l’onglet **Plage** au besoin, jusqu’à ce que vous ayez identifié de manière unique le rapport que vous recherchez.

1. Sélectionnez **OK** pour enregistrer vos paramètres et fermer la boîte de dialogue.
1. Sélectionnez **Enregistrer** pour enregistrer vos paramètres d’exportation.
1. Sous l’onglet **Options d’exportation**, sélectionnez **Exporter maintenant** pour générer le fichier d’exportation.
1. Sur la page **Résumé de l’exécution** qui s’ouvre, vous pouvez afficher le statut de votre tâche d’exportation et la liste des entités exportées. Dans la section **Statut de traitement de l’entité**, sélectionnez l’entité **Valeur de stock**, puis sélectionnez **Télécharger le fichier** pour télécharger les données exportées depuis cette entité.

Pour plus d’informations sur l’utilisation de la gestion des données pour exporter des données, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

## <a name="generate-a-standard-inventory-value-report"></a>Générer un rapport de valeur de stock standard

Utilisez la procédure suivante pour générer un rapport **Valeur du stock** standard.

1. Accédez à **Gestion des coûts \> Recherches et états \> Rapports Comptabilité du stock – Statut \> Valeur de stock**.
1. Dans la boîte de dialogue **Rapport de valeur du stock**, sur le raccourci **Paramètres**, définissez les champs suivants :

    - **Nom** – Entrez un nom unique pour le rapport.
    - **ID** – Sélectionnez la [configuration du rapport de valeur de stock](#report-configuration) à utiliser pour le rapport. La configuration établit des options pour les colonnes et les lignes qui seront incluses dans votre rapport.
    - **Intervalle de dates** – Utilisez les champs de cette section pour définir les enregistrements à inclure dans le rapport. Pour définir l’intervalle de dates, vous pouvez soit sélectionner une plage prédéfinie (par rapport à la date de génération du rapport) dans le champ **Code d’intervalle de dates** ou sélectionner des dates spécifiques dans les champs **Date de début** et **Date de fin**.

1. Dans l’organisateur **Enregistrements à inclure**, configurez des filtres et des contraintes pour définir les données incluses sur le rapport. Sélectionnez **Filtrer** pour ouvrir une boîte de dialogue d’Éditeur de requête standard, dans laquelle vous pouvez définir des critères de sélection, des critères de tri et des jointures. Les champs fonctionnent comme pour d’autres types de requêtes dans Supply Chain Management.
1. Sur l’organisateur **Exécuter en arrière-plan**, spécifiez comment, quand et à quelle fréquence le rapport est généré. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Sélectionnez **OK** pour appliquer vos paramètres et fermer la boîte de dialogue. L’état s’affiche.

## <a name="reading-inventory-value-reports"></a>Lecture des rapports de valeur de stock

Cette section fournit des conseils sur la façon de lire et de comprendre un rapport sur la valeur de stock.

Supply Chain Management prend en charge les deux concepts importants suivants liés au statut du stock :

- **Mise à jour financière** – Ce concept indique que les transactions de stock sont déjà facturées. Pour les ordres de fabrication, il indique la fin d’un ordre de fabrication.
- **Mise à jour physique** – Ce concept indique que les transactions de stock n’ont pas encore été facturées, mais qu’elles ont été reçues ou expédiées. Pour les ordres de fabrication, cela indique que l’article a été prélevé ou que l’ordre de fabrication a été déclaré comme terminé.

Lorsque vous comprenez ces deux concepts, il devient facile de comprendre les colonnes suivantes dans la sortie du rapport :

- **Stock : quantité financière** – La quantité a été mise à jour financièrement.
- **Stock : montant financier** – La valeur du montant du stock a été mise à jour financièrement.
- **Stock : quantité ohysique enregistrée** – La quantité a été mise à jour physiquement.
- **Stock : montant financier enregistré** – La valeur du montant du stock a été mise à jour physiquement.
- **Inventaire : quantité physique non enregistrée** – La quantité avec transactions de stock qui n’a pas été enregistrée dans la comptabilité. Par exemple, vous avez un groupe de modèles d’article où les options **Valider le stock physique** et **Valider le stock financier** sont désactivées et vous disposez d’un article lié à ce groupe. Vous créez ensuite une commande fournisseur, la recevez et la facturez. À ce stade, si vous examinez le rapport de valeur de stock pour l’article, vous verrez que la quantité et la valeur sur la commande fournisseur sont affichées dans les colonnes **Stock : Quantité physique non enregistrée** et **Stock : montant physique non enregistré**.
- **Stock : montant physique non enregistré** – Vous pouvez paramétrer vos rapports pour qu’ils affichent les montants non comptabilisés. Cependant, si vous utilisez le rapport pour le rapprochement des stocks, n’utilisez pas cette valeur. Sinon, le montant n’est pas enregistré dans la comptabilité.
- **Stock : quantité** – La quantité totale de toutes les colonnes de quantité du rapport.
- **Stock : montant** – La quantité totale de toutes les colonnes de montant du rapport. Lorsque vous effectuez un rapprochement de stock, n’utilisez pas cette colonne si votre rapport inclut la colonne **Stock : montant physique non enregistré**. Dans ce cas, vous devez exclure le montant **Stock : montant physique non enregistré** du montant total.
- **Coût unitaire moyen** – Le montant total divisé par la quantité totale.

En règle générale, vous utiliserez un rapport de valeur de stock pour afficher la valeur de stock et la quantité. Cependant, il arrive que le rapport n’affiche pas toutes les dimensions de stock pertinentes. Si vous ne voyez pas les dimensions que vous attendez, validez les paramètres suivants :

- Vérifiez les groupes de stock d’article et de dimension de suivi. Seules les dimensions où l’option **Stock financier** est activée peuvent s’afficher sur le rapport.
- Accédez à **Cost Management \> Configuration des stratégies de comptabilité de stock \> Rapports de valeur de stock**, sélectionnez la configuration de rapport que vous avez utilisée pour générer le rapport et assurez-vous que les dimensions de stock requises sont sélectionnées dans la colonne **Vue**.

Par exemple, vous avez un article qui a le numéro d’article *A0001*. Dans le groupe de dimensions de stockage, seul le site est activé pour le stock financier. Le site et l’entrepôt sont tous deux activés pour le stock physique. Dans le groupe de dimensions de suivi, le numéro de lot est activé pour le stock physique mais pas pour le stock financier. Vous utilisez ensuite une configuration de rapport où le site, l’entrepôt et le numéro de lot sont tous sélectionnés. Lorsque vous affichez le rapport, vous voyez une valeur uniquement pour le site. Les colonnes pour l’entrepôt et le numéro de lot sont vides. Comme le montre cet exemple, les rapports sur la valeur de stock peuvent afficher uniquement la dimension de stock qui est activée pour le stock financier.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
