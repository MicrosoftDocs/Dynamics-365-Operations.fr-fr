---
title: Prévisions du stock
description: Cet article décrit la fonctionnalité de prévision de l’offre et de la demande utilisable pour créer des prévisions de stock dans Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ForecastSales, ForecastPurch, ForecastInvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 10e3b6ad079dbcbc3cce429a4d9d838e584b9c54
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844523"
---
# <a name="inventory-forecasts"></a>Prévisions du stock

[!include [banner](../includes/banner.md)]

Cet article explique comment afficher et créer des prévisions de stock. Vous pouvez créer et afficher des lignes de prévision de l’offre et de la demande pour des articles, des groupes d’articles, des clés de répartition par articles, des comptes clients, des groupes de clients, des comptes fournisseurs et des groupes de fournisseurs.

Pour chaque ligne de prévision, vous pouvez sélectionner le modèle de prévision utilisé. Vous pouvez ensuite spécifier l’article ou le groupe d’articles, ainsi que la quantité ou le montant de la transaction. Vous pouvez également paramétrer un calendrier pour l’attribution de la quantité prévue.

Les lignes de prévision de l’offre et de la demande produisent une prévision de stock pour la même combinaison d’un article et d’un modèle. Cette prévision de stock représente un solde entre l’offre et la demande qui ont été saisies pour le même article. Cette valeur ne peut pas être modifiée. Les prévisions de stock aident l’équipe de gestion des stocks à examiner les modifications attendues du stock disponible d’un article au cours de la prochaine période ayant fait l’objet d’une prévision.

Après avoir saisi la demande et/ou l’offre, vous pouvez exécuter une planification des prévisions afin de déterminer les besoins bruts en matières et en capacité, et de générer des ordres prévisionnels.

## <a name="view-and-manually-enter-forecast-lines"></a><a name="manual-entry"></a>Afficher et saisir manuellement des lignes de prévision

Cette procédure permet de créer manuellement des lignes de prévision pour des produits.

Il existe également d’autres façons de créer des lignes de prévision :

- [Générer des prévisions de base statistiques](generate-statistical-baseline-forecast.md).
- [Importer les données historiques pour les prévisions de la demande](import-historical-data.md).
- [Générer la prévision à l’aide d’un service web Machine Learning Microsoft Azure](demand-forecasting-setup.md).
- [Importer des lignes de prévision de l’offre ou de la demande à l’aide du cadre de gestion des données (entités de données ForecastDemandForecastEntryStaging et ForecastSupplyForecastEntryStaging)](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages).

Comme le montre le tableau de l’étape 1, il existe différentes manières d’accéder aux pages utilisées.

1. Selon le type d’entité pour lequel vous souhaitez créer une prévision et le type de prévision que vous souhaitez créer, ouvrez une page de prévision d’offre, de demande ou de stock, comme décrit dans le tableau suivant.

    | Entité | Instructions |
    |---|---|
    | Produits lancés | <ol><li>Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</li><li>Sélectionnez le produit pour lequel créer une prévision.</li><li>Dans le volet Actions, dans l’onglet **Plan**, dans le groupe **Prévision**, sélectionnez **Prévision de la demande**, **Prévision d’approvisionnement** ou **Prévision de stock**, selon le type de prévision que vous souhaitez utiliser.</li></ol> |
    | Variantes de produit lancé | <ol><li>Accédez à **Gestion des informations sur les produits \> Produits \> Variantes de produit lancé**.</li><li>Sélectionnez la variante pour laquelle créer une prévision.</li><li>Dans le volet Actions, dans l’onglet **Plan**, dans le groupe **Prévision**, sélectionnez **Prévision de la demande**, **Prévision d’approvisionnement** ou **Prévision de stock**, selon le type de prévision que vous souhaitez utiliser.</li></ol> |
    | Groupes d’articles | <ol><li>Accédez à **Gestion des stocks \> Configuration \> Stock \> Groupes d’articles**.</li><li>Sélectionnez le groupe d’articles pour lequel créer une prévision.</li><li>Dans le volet Actions, sélectionnez **Prévision \> Demande**, **Prévision \> Approvisionnement**, ou **Prévision \> Prévision de stock**, selon le type de prévision que vous souhaitez utiliser.</li></ol> |
    | Clés de répartition par article | <ol><li>Accédez à **Gestion de l’inventaire \> Configuration \> Prévision**.</li><li>Sélectionnez la clé de répartition par article pour laquelle créer une prévision.</li><li>Dans le volet Actions, sélectionnez **Prévision de la demande**.</li></ol> |
    | Clients | <ol><li>Accédez à **Planification \> Prévision \> Entrée manuelle de la prévision \> Clients**.</li><li>Sélectionnez le client pour lequel créer une prévision.</li><li>Dans le volet Actions, sélectionnez **Définir la prévision de la demande**.</li></ol> |
    | Groupes de clients | <ol><li>Accédez à **Planification \> Prévision \> Entrée manuelle de la prévision \> Groupes de clients**.</li><li>Sélectionnez le groupe de clients pour lequel créer une prévision.</li><li>Dans le volet Actions, sélectionnez **Définir la prévision de la demande**.</li></ol> |
    | Fournisseurs | <ol><li>Accédez à **Planification \> Prévision \> Entrée manuelle de la prévision \> Fournisseurs**.</li><li>Sélectionnez le fournisseur pour lequel créer une prévision.</li><li>Dans le volet Actions, sélectionnez **Saisie** pour ouvrir la page **Prévision d’approvisionnement**.</li></ol> |
    | Groupes de fournisseurs | <ol><li>Accédez à **Planification \> Prévision \> Entrée manuelle de la prévision \> Groupes de fournisseurs**.</li><li>Sélectionnez le groupe de fournisseurs pour lequel créer une prévision.</li><li>Dans le volet Actions, sélectionnez **Saisie** pour ouvrir la page **Prévision d’approvisionnement**.</li></ol> | 
    | Toutes les lignes | <ul><li>Accédez à **Planification \> Prévision \> Lignes de prévision de la demande** ou à **Planification \> Prévision \> Lignes de prévision d’approvisionnement**, selon le type de prévision que vous souhaitez utiliser.</li></ul> |

    En fonction de votre sélection, la page **Prévision d’approvisionnement** ou **Prévision de la demande** apparaît. Elle affiche toutes les lignes de prévision existantes pour l’enregistrement que vous avez sélectionné avant d’ouvrir la page.

1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne de prévision à la grille dans la partie supérieure de la page.
1. Sur la nouvelle ligne, dans le champ **Modèle**, sélectionnez le modèle de prévision à utiliser. Saisissez ensuite les autres détails requis, tels que l’article, le groupe d’articles, le compte ou le groupe de clients ou de fournisseurs, la quantité d’articles ou le montant total de la transaction. Pour plus de détails sur les champs disponibles sur les pages **Prévision d’approvisionnement** et **Prévision de la demande**, consultez les sections suivantes de cet article.
1. Pour répartir la prévision sur la période, sur l’onglet **Aperçu**, sélectionnez **Répartir la prévision** sur la barre d’outils.
1. Dans la grille **Répartition**, passez en revue la période et les intervalles de temps utilisés pour répartir les quantités de prévision.

## <a name="supply-forecast-lines"></a>Lignes de prévision d’approvisionnement

La prévision d’approvisionnement vous permet de créer un plan pour les articles qui doivent être achetés. Il indique aux commis aux achats et à l’approvisionnement ce qu’ils sont censés commander.

Vous pouvez saisir une prévision d’approvisionnement par article, groupe d’articles, clé de répartition par article, fournisseur et groupe de fournisseurs. Pour plus d’informations sur toutes les manières d’ouvrir la page **Prévisions d’approvisionnement** pour divers entités et enregistrements, voir la section [Afficher et saisir manuellement des lignes de prévision](#manual-entry) plus haut dans cet article.

La partie supérieure de la page **Prévision d’approvisionnement** fournit une grille de lignes de prévision d’approvisionnement et un ensemble d’onglets que vous pouvez utiliser pour afficher et définir plus d’informations sur une ligne de prévision sélectionnée. La partie inférieure de la page fournit une grille **Répartition**.

Les sous-sections suivantes décrivent tous les champs disponibles sur chaque onglet et toutes les commandes disponibles dans le volet Actions de la page et dans la barre d’outils de l’onglet **Vue d’ensemble**.

### <a name="action-pane-commands-on-the-supply-forecast-page"></a>Commandes du volet Actions sur la page Prévision d’approvisionnement

Le tableau suivant décrit les commandes disponibles sur le volet Actions de la page **Prévision d’approvisionnement**.

| Commande | Description |
|---|---|
| Enregistrer | Enregistrer vos paramètres actuels. |
| Modifier | Activer les paramètres de la page pour la modification. |
| Créer | Ajouter une ligne de prévision à la grille supérieure. |
| Retirer | Supprimer la ligne de prévision sélectionnée de la grille supérieure. |
| Soldes prévus | Afficher les soldes prévus qui ont été calculés pour l’ID de modèle de la ligne sélectionnée pour l’exercice en cours. Les soldes sont fractionnés par période (mois). |
| Prévisions de flux de trésorerie | Afficher les transactions de prévision qui ont été réparties dans la comptabilité. Pour plus d’informations, voir [Prévision de la trésorerie](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Stock \> Afficher les dimensions | Sélectionner les dimensions d’inventaire qui doivent être affichées dans la grille sur l’onglet **Vue d’ensemble**. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-supply-forecast-page"></a>Commandes de la barre d’outils de l’onglet Vue d’ensemble de la page Prévision d’approvisionnement

Le tableau suivant décrit les commandes disponibles sur la barre d’outils de l’onglet **Vue d’ensemble** de la page **Prévision de la demande**.

| Commande | Description |
|---|---|
| Répartir la prévision | Si vous utilisez une méthode de répartition, générez les lignes d’échéancier individuelles pour la transaction de prévision. La quantité de la ligne est ensuite répartie par date (selon les intervalles de temps sélectionnés), quantité et montant pour tout l’horizon temporel. (Voir la section [Répartir la prévision](#allocate-forecast) plus loin dans cet article.) |
| Mise à jour par lot | Ouvrez la page **Modifier les transactions de prévision**. (Voir la section [Mettre à jour en bloc les transactions de prévision](#bulk-update), plus loin dans cet article.) |
| Prévisions de stock | Ouvrez une vue de la page **Prévision de stock** filtrée pour la combinaison article/modèle sélectionnée. (Voir la section [Prévision de stock](#inventory-forecast) plus loin dans cet article.) |
| Créer une demande d’articles | Ouvrez une boîte de dialogue dans laquelle vous pouvez créer des besoins d’article et des commandes client ou des lignes de journal d’article pour les transactions de prévision liées au projet. Bien que cette commande soit disponible à la fois pour les lignes de prévision d’approvisionnement et les lignes de prévision de la demande, elle ne peut pas être utilisée sur la page **Prévision d’approvisionnement**. |

### <a name="the-overview-tab-on-the-supply-forecast-page"></a>L’onglet Vue d’ensemble sur la page Prévision d’approvisionnement

Le tableau suivant décrit les champs de l’onglet **Vue d’ensemble** de la page **Prévision d’approvisionnement**.

| Champ | Description |
|---|---|
| **Modèle** | Modèle de prévision auquel est associée la transaction. |
| **Date** | Date de début de la transaction. |
| **Compte fournisseur** | Compte fournisseur auquel est associée la transaction. |
| **Groupe de fournisseurs** | Groupe de fournisseurs auquel est associée la transaction. |
| **numéro d’article** | Identificateur de l’article. |
| **Groupe d’articles** | Groupe d’articles auquel est associée la transaction. |
| **Clé de répartition par article** | Clé de répartition par article associée à la prévision. |
| **Quantité en PV** | Quantité prévue dans l’unité de poids variable spécifiée. |
| **Unité en PV** | Unité de poids variable dans laquelle l’article est acheté. La valeur est automatiquement récupérée à partir de la configuration de l’article. |
| **Quantité** | Quantité prévue, exprimée dans l’unité d’achat spécifiée. |
| **Unité** | Unité dans laquelle l’article est acheté. La valeur est automatiquement récupérée à partir de la configuration de l’article. Cependant, vous pouvez la modifier si des conversions d’unités sont configurées. |
| **Montant** | Montant brut, moins les remises, à hauteur duquel la transaction de prévision contribue à la prévision. |
| **Devise** | Devise utilisée pour la transaction de prévision sélectionnée. La devise par défaut est saisie automatiquement, mais vous pouvez sélectionner une devise différente. |
| (Autres dimensions) | Des dimensions supplémentaires peuvent être affichées sous forme de colonnes dans la grille. Pour sélectionner les dimensions supplémentaires affichées, sélectionnez **Dimensions d’affichage** dans le volet Actions. |

### <a name="the-general-tab-on-the-supply-forecast-page"></a>L’onglet Général sur la page Prévision d’approvisionnement

L’onglet **Général** affiche plus d’informations sur la ligne qui est actuellement sélectionnée sur l’onglet **Vue d’ensemble**. Certaines de ces informations sont répétées à partir de l’onglet **Vue d’ensemble**. Le tableau suivant décrit les champs propres à l’onglet **Général**.

| Champ | Description |
|---|---|
| Etat | Définissez cette option sur *Oui* pour inclure la transaction dans l’état. |
| Commentaires | Entrez tous vos commentaires éventuels sur la transaction de prévision. |
| Actif.ve | Activez cette case à cocher pour inclure les transactions dans les états budgétaires. |
| Inclure dans les prévisions de flux de trésorerie | Activez cette case à cocher pour affecter la transaction de prévision à la comptabilité. Le paramétrage de cette case à cocher ne peut pas être modifié pour les états de transactions. |
| Groupe de taxe de vente | Groupe de taxe utilisé pour spécifier la taxe applicable à la transaction de prévision. |
| Groupe de taxe d’article | Groupe de taxe d’article utilisé pour spécifier la taxe applicable à la transaction de prévision. |
| méthode | <p>Sélectionnez la méthode utilisée pour affecter la transaction de prévision :</p><ul><li>**Aucune** : aucune répartition n’est effectuée.</li><li>**Période** : prévoir la même quantité pour chaque période. Si vous sélectionnez cette valeur, spécifiez une quantité dans le champ **Par** et une unité de temps dans le champ **Unité**.</li><li>**Clé** : la quantité prévue est répartie en fonction de la clé de répartition par période que vous spécifiez dans le champ **Clé de période**. Cette méthode permet de prendre en compte les variations saisonnières.</li></ol>|
| Par | <p>Permet d’entrer le nombre d’intervalles de temps dans le futur couverts par la prévision. Ce champ n’est disponible que si vous avez sélectionné *Période* dans le champ **Méthode**.</p><p>Par exemple, sélectionnez *Période* dans le champ **Méthode**, entrez *1* dans le champ **Par**, et sélectionnez *Mois* dans le champ **Unité**. Dans le champ **Fin**, spécifiez une date de fin pouvant aller jusqu’à 1 an dans le futur. Dans ce cas, une ligne de prévision sera créée pour chaque mois de l’année à venir, en fonction de l’article et de la quantité spécifiés sur la ligne d’en-tête.</p> |
| Unité | Sélectionnez l’unité de l’intervalle de temps : *Jours*, *Mois* ou *Années*. La répartition correspond alors au nombre de jours, mois ou années que vous avez spécifié dans le champ **Par**.|
| Clé de période | Spécifiez la clé de répartition par période. |
| Terminer | Spécifiez la date de fin lorsque vous utilisez les champs **Par** et **Unité**. |

### <a name="the-item-tab-on-the-supply-forecast-page"></a>L’onglet Article sur la page Prévision d’approvisionnement

L’onglet **Article** présente davantage d’informations d’article sur la ligne actuellement sélectionnée sur l’onglet **Vue d’ensemble**.

La grille en haut de l’onglet **Article** répète les informations sur l’article qui sont également affichées sur l’onglet **Vue d’ensemble**. De plus, il comprend le champ **Prix unitaire**, qui indique le prix d’achat pour le nombre d’unités spécifié dans le champ **Unité**. Le prix unitaire est automatiquement récupéré de la configuration de l’article, mais vous pouvez le modifier.

Les champs sous la grille fournissent plus de détails sur l’article. Certaines de ces informations sont répétées à partir de l’onglet **Vue d’ensemble**. Le tableau suivant décrit les champs propres à l’onglet **Article**.

| Champ | Description |
|---|---|
| Unité de prix | Le nombre d’unités auquel le prix d’achat s’applique. La valeur est automatiquement récupéré de la table Articles, mais vous pouvez la modifier. |
| Frais sur les achats | Frais fixes sur le prix d’achat. Les frais sont indépendants de la quantité. |
| Pourcentage de remise | Remise exprimée en pourcentage. |
| Montant de la remise | Remise exprimée en montant par unité de vente. |
| Montant brut | Montant lorsqu’aucune remise n’est appliquée. |
| Quantité | La quantité de la transaction exprimée en unité de stock de l’article. |
| Sous-nomenclature | Numéro de nomenclature d’une sous-nomenclature spécifique. |
| Sous-gamme | Numéro de gamme d’une sous-gamme spécifique. |

### <a name="the-financial-dimensions-tab-on-the-supply-forecast-page"></a>L’onglet Dimensions financières sur la page Prévision d’approvisionnement

L’onglet **Dimensions financières** affiche toutes les valeurs de dimension financière pour la ligne actuellement sélectionnée sur l’onglet **Vue d’ensemble**.

### <a name="the-inventory-dimensions-tab-on-the-supply-forecast-page"></a>L’onglet Dimensions de stock sur la page Prévision d’approvisionnement

L’onglet **Dimensions de stock** affiche toutes les valeurs de dimension de stock pour la ligne actuellement sélectionnée sur l’onglet **Vue d’ensemble**.

### <a name="the-allocation-grid-on-the-supply-forecast-page"></a>La grille Répartition sur la page Prévision d’approvisionnement

Si vous utilisez une clé de répartition par article ou si vous avez saisi une prévision d’article pour une ou plusieurs périodes futures, vous pouvez répartir la prévision en sélectionnant **Répartir la prévision** dans la barre d’outils de l’onglet **Vue d’ensemble**. La quantité est ensuite répartie de la manière indiquée par les lignes dans la grille **Répartition**.

## <a name="demand-forecast-lines"></a>Lignes de prévision de la demande

La prévision de la demande vous permet de saisir ou de générer une demande pour un client. Elle aide les commis aux ventes et au marketing à informer les commis à la planification de la demande prévue au cours de la période de prévision à venir.

Vous pouvez saisir une prévision de la demande par article, groupe d’articles, clé de répartition par article, client et groupe de clients. Pour plus d’informations sur toutes les manières d’ouvrir la page **Prévision de la demande** pour divers entités et enregistrements, voir la section [Afficher et saisir manuellement des lignes de prévision](#manual-entry) plus haut dans cet article.

La partie supérieure de la page **Prévision de la demande** fournit une grille de lignes de prévision de la demande et un ensemble d’onglets que vous pouvez utiliser pour afficher et définir plus d’informations sur une ligne de prévision sélectionnée. La partie inférieure de la page fournit une grille **Répartition**.

Les sous-sections suivantes décrivent tous les champs disponibles sur chaque onglet et toutes les commandes disponibles dans le volet Actions de la page et dans la barre d’outils de l’onglet **Vue d’ensemble**.

### <a name="action-pane-commands-on-the-demand-forecast-page"></a>Commandes du volet Actions sur la page Prévision de la demande

Le tableau suivant décrit les commandes disponibles sur le volet Actions de la page **Prévision de la demande**.

| Commande | Description |
|---|---|
| Enregistrer | Enregistrer vos paramètres actuels. |
| Modifier | Activer les paramètres de la page pour la modification. |
| Créer | Ajouter une ligne de prévision à la grille supérieure. |
| Retirer | Supprimer la ligne de prévision sélectionnée de la grille supérieure. |
| Soldes prévus | Afficher les soldes prévus qui ont été calculés pour l’ID de modèle de la ligne sélectionnée pour l’exercice en cours. Les soldes sont fractionnés par période (mois). |
| Prévisions de flux de trésorerie | Afficher les transactions de prévision qui doivent être réparties dans la comptabilité. Pour plus d’informations, voir [Prévision de la trésorerie](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Afficher les dimensions | Sélectionner les dimensions de produit, de stockage et de suivi qui doivent être affichées dans la grille sur l’onglet **Vue d’ensemble**. |
| Aperçu comptable | Permet d’afficher les écritures de comptabilité pour la transaction sélectionnée. |
| Transférer des lignes de devis | Permet de transférer les lignes de devis vers le projet sélectionné. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-demand-forecast-page"></a>Commandes de la barre d’outils de l’onglet Vue d’ensemble de la page Prévision de la demande

Le tableau suivant décrit les commandes disponibles sur la barre d’outils de l’onglet **Vue d’ensemble** de la page **Prévision de la demande**.

| Commande | Description |
|---|---|
| Répartir la prévision | Si vous utilisez une méthode de répartition, générez les lignes d’échéancier individuelles pour la transaction de prévision. La quantité de la ligne est ensuite répartie par date (selon les intervalles de temps sélectionnés), quantité et montant pour tout l’horizon temporel. (Voir la section [Répartir la prévision](#allocate-forecast) plus loin dans cet article.)|
| Mise à jour par lot | Ouvrez la page **Modifier les transactions de prévision**. (Voir la section [Mettre à jour en bloc les transactions de prévision](#bulk-update), plus loin dans cet article.) |
| Prévisions de stock | Ouvrez une vue de la page **Prévision de stock** filtrée pour la combinaison article/modèle sélectionnée. (Voir la section [Prévision de stock](#inventory-forecast) plus loin dans cet article.) |
| Créer une demande d’articles | Ouvrez une boîte de dialogue dans laquelle vous pouvez créer des besoins d’article et des commandes client ou des lignes de journal d’article pour les transactions de prévision liées au projet. |

### <a name="the-overview-tab-on-the-demand-forecast-page"></a>L’onglet Vue d’ensemble sur la page Prévision de la demande

Le tableau suivant décrit les champs de l’onglet **Vue d’ensemble** de la page **Prévision de la demande**.

| Champ | Description |
|---|---|
| **Nom de la tâche** | Nom de la tâche de traitement par lots qui a été utilisée pour créer la ligne de prévision. |
| **Modèle** | Modèle de prévision auquel est associée la transaction. |
| **Date** | Date de début de la transaction. |
| **Compte client** | Compte client auquel est associée la transaction. |
| **Groupe de clients** | Groupe de clients auquel est associée la transaction. |
| **numéro d’article** | Identificateur de l’article. |
| **Nom du produit** | Description de l’article. |
| **Clé de répartition par article** | Clé de répartition par article utilisée pendant la répartition des prévisions de stock. |
| **Quantité vendue** | Quantité de la transaction dans l’unité de vente spécifiée. |
| **Unité** | Unité dans laquelle l’article est vendu. |
| **Montant** | Montant brut, moins les remises, à hauteur duquel la transaction de prévision contribue à la prévision. |
| **Prix de vente** | Le prix de vente pour le nombre d’unités qui est spécifié dans le champ **Prix unitaire**. La valeur est automatiquement récupérée de la configuration de l’article, mais vous pouvez la modifier. |
| **Devise de vente** | Devise utilisée pour la transaction de prévision sélectionnée. La devise par défaut est saisie automatiquement, mais vous pouvez sélectionner une devise différente. |
| **Quantité en PV** | Quantité prévue dans l’unité de poids variable spécifiée. |
| **Unité en PV** | Unité de poids variable dans laquelle l’article est vendu. La valeur est automatiquement récupérée à partir de la configuration de l’article. |
| (Autres dimensions) | Des dimensions supplémentaires de produit, de stockage et de suivi peuvent être affichées sous forme de colonnes dans la grille. Pour sélectionner les dimensions supplémentaires affichées, sélectionnez **Dimensions d’affichage** dans le volet Actions. |

### <a name="the-general-tab-on-the-demand-forecast-page"></a>L’onglet Général sur la page Prévision de la demande

L’onglet **Général** affiche plus d’informations sur la ligne qui est actuellement sélectionnée sur l’onglet **Vue d’ensemble**. Certaines de ces informations sont répétées à partir de l’onglet **Vue d’ensemble**. Le tableau suivant décrit les champs propres à l’onglet **Général**.

| Champ | Description |
|---|---|
| Numéro de souche de prévision de la demande | Numéro unique de la ligne de prévision de la demande. Ce numéro est généré à l’aide de la souche de numéros sélectionnée pour les prévisions de la demande sur la page **Paramètres de planification**. |
| Groupe d’articles | Groupe d’articles auquel est associée la transaction. |
| Etat | Définissez cette option sur *Oui* pour inclure la transaction dans l’état. |
| Commentaires | Entrez tous vos commentaires éventuels sur la transaction de prévision. |
| Actif.ve | Activez cette case à cocher pour inclure les transactions dans les états budgétaires. Le paramétrage de cette case à cocher ne peut pas être modifié pour les états de transactions. |
| Inclure dans les prévisions de flux de trésorerie | Activez cette case à cocher pour affecter la transaction de prévision à la comptabilité. Le paramétrage de cette case à cocher ne peut pas être modifié pour les états de transactions. Pour plus d’informations, voir [Prévision de la trésorerie](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Groupe de taxe de vente | Groupe de taxe utilisé pour spécifier la taxe applicable à la transaction de prévision. |
| Groupe de taxe d’article | Groupe de taxe d’article utilisé pour spécifier la taxe applicable à la transaction de prévision. |
| méthode | <p>Sélectionnez la méthode utilisée pour affecter la transaction de prévision :</p><ul><li>**Aucune** : aucune répartition n’est effectuée.</li><li>**Période** : prévoir la même quantité pour chaque période. Si vous sélectionnez cette valeur, spécifiez une quantité dans le champ **Par** et une unité de temps dans le champ **Unité**.</li><li>**Clé** : la quantité prévue est répartie en fonction de la clé de répartition par période que vous spécifiez dans le champ **Clé de période**. Cette méthode permet de prendre en compte les variations saisonnières.</li><ul>|
| Par | <p>Permet d’entrer le nombre d’intervalles de temps dans le futur couverts par la prévision. Ce champ n’est disponible que si vous avez sélectionné *Période* dans le champ **Méthode**.</p><p>Par exemple, sélectionnez *Période* dans le champ **Méthode**, entrez *1* dans le champ **Par**, et sélectionnez *Mois* dans le champ **Unité**. Dans le champ **Fin**, spécifiez une date de fin pouvant aller jusqu’à 1 an dans le futur. Dans ce cas, une ligne de prévision sera créée pour chaque mois de l’année à venir, en fonction de l’article et de la quantité spécifiés sur la ligne d’en-tête. |
| Unité | Sélectionnez l’unité de l’intervalle de temps : *Jours*, *Mois* ou *Années*. La répartition correspond alors au nombre de jours, mois ou années que vous avez spécifié dans le champ **Par**.|
| Clé de période | Spécifiez la clé de répartition par période utilisée pour répartir la prévision. Pour plus d’informations, voir [Répartition de données de planification budgétaire](../../finance/budgeting/budget-planning-data-allocation.md). |
| Terminer | Spécifiez la date de fin lorsque vous utilisez les champs **Par** et **Unité**. |

### <a name="the-item-tab-on-the-demand-forecast-page"></a>L’onglet Article sur la page Prévision de la demande

L’onglet **Article** affiche plus d’informations d’article sur la ligne qui est actuellement sélectionnée sur l’onglet **Vue d’ensemble**. Certaines de ces informations sont répétées à partir de l’onglet **Vue d’ensemble**. Le tableau suivant décrit les champs propres à l’onglet **Article**.

| Champ | Description |
|---|---|
| Unité de prix | Nombre d’unités de vente auxquelles le prix de vente s’applique. La valeur est automatiquement récupéré de la table Articles, mais vous pouvez la modifier. |
| Frais de vente | Frais fixes sur le prix de vente. Les frais sont indépendants de la quantité. |
| Prix de revient | Coût de la transaction de prévision actuelle par unité de stock. La valeur est extraite de la table Articles, mais vous pouvez la modifier. |
| Pourcentage de remise | Remise exprimée en pourcentage. |
| Montant de la remise | Remise exprimée en montant par unité de vente. |
| Montant brut | Montant lorsqu’aucune remise n’est appliquée. |
| Quantité en stock | La quantité de la transaction exprimée en unité de stock de l’article. |
| Utiliser une nomenclature spécifique | Numéro de nomenclature d’une nomenclature spécifique. |
| Utiliser une gamme spécifique | Numéro de gamme d’une sous-gamme spécifique. |

### <a name="the-project-tab-on-the-demand-forecast-page"></a>L’onglet Projet sur la page Prévision de la demande

L’onglet **Projet** affiche plus d’informations de projet sur la ligne qui est actuellement sélectionnée sur l’onglet **Vue d’ensemble**. Certaines de ces informations sont répétées à partir de l’onglet **Vue d’ensemble**, **Général** ou **Article**. Le tableau suivant décrit les champs propres à l’onglet **Projet**.

| Champ | Description |
|---|---|
| Date du projet | La date de la transaction de prévision de la demande. |
| ID projet | Identificateur du projet référencé par la transaction actuelle. |
| Source de financement | Source de financement associée à la prévision de la demande. |
| Numéro d’activité | Activité associée à la transaction de prévision de la demande. |
| Catégorie | Catégorie de coûts de la transaction actuelle. |
| Propriété de ligne | Statut auquel la transaction est associée. |
| ID transaction | Identificateur système de la transaction de prévision de la demande. |
| Montant du coût | Montant de la transaction de prévision de la demande. |
| Prix unitaire | Prix par unité. |
| Auteur de la modification | Identificateur du collaborateur qui a modifié en dernier la transaction sélectionnée. |
| Date de la facture | Permet d’entrer la date de facturation prévue. |
| Date d’élimination | Permet d’afficher ou de modifier la date d’élimination. Lorsque la prévision est créée, la date d’élimination est égale à la date de fin du projet. Si le projet n’a pas de date de fin, c’est la date du projet qui est utilisée. Ce champ s’applique aux projets à prix fixe et d’investissement. |
| Date de paiement des coûts | Permet d’entrer la date prévue du paiement des achats. |
| Date de paiement des ventes | Permet d’entrer la date prévue du paiement des ventes. |

### <a name="the-financial-dimensions-tab-on-the-demand-forecast-page"></a>L’onglet Dimensions financières sur la page Prévision de la demande

L’onglet **Dimensions financières** affiche toutes les valeurs de dimension financière pour la ligne actuellement sélectionnée sur l’onglet **Vue d’ensemble**.

### <a name="the-inventory-dimensions-tab-on-the-demand-forecast-page"></a>L’onglet Dimensions de stock sur la page Prévision de la demande

L’onglet **Dimensions de stock** affiche toutes les valeurs de dimension de stock pour la ligne actuellement sélectionnée sur l’onglet **Vue d’ensemble**.

### <a name="the-allocation-grid-on-the-demand-forecast-page"></a>La grille Répartition sur la page Prévision de la demande

Si vous utilisez une clé de répartition par article ou si vous avez saisi une prévision d’article pour une ou plusieurs périodes futures, vous pouvez répartir la prévision en sélectionnant **Répartir la prévision** dans la barre d’outils de l’onglet **Vue d’ensemble**. La quantité est ensuite répartie de la manière indiquée par les lignes dans la grille **Répartition**. (Voir la section [Répartir la prévision](#allocate-forecast) plus loin dans cet article.)

## <a name="inventory-forecast"></a><a name="inventory-forecast"></a>Prévisions de stock

Les pages des lignes de prévision d’approvisionnement et de prévision de la demande comportent un bouton **Prévision de stock** qui ouvre une vue de la page **Prévision de stock** filtrée pour la même combinaison article/modèle. La prévision de stock représente un solde entre l’offre et la demande qui ont été saisies pour le même article. Cette valeur ne peut pas être modifiée. Les prévisions de stock aident l’équipe de gestion des stocks à examiner les modifications attendues du stock disponible d’un article au cours de la prochaine période ayant fait l’objet d’une prévision.

### <a name="the-action-pane-on-the-inventory-forecast-page"></a>Le volet Actions sur la page Prévision de stock

Le tableau suivant décrit les commandes disponibles sur le volet Actions de la page **Prévision de stock**.

| Action | Description |
|---|---|
| Prévision d’approvisionnement | Ouvrez une vue de la page **Prévision d’approvisonnement** filtrée pour la même combinaison article/modèle/date. |
| Prévision de la demande | Ouvrez une vue de la page **Prévision de la demande** filtrée pour la même combinaison article/modèle/date. |
| Stock \> Afficher les dimensions | Sélectionnez les dimensions de produit, de stockage et de suivi qui doivent être affichées dans la grille **Vue d’ensemble**. |

### <a name="the-grid-on-the-inventory-forecast-page"></a>La grille sur la page Prévision de stock

Le tableau suivant décrit les champs de la grille sur la page **Prévision de stock**.

| Champ | Description |
|---|---|
| **Modèle** | Modèle de prévision auquel est associée la transaction. |
| **numéro d’article** | Identificateur de l’article. |
| **Date de budget** | La date de la transaction de prévision. |
| **Type de prévision** | La source de la transaction (*Prévision de la demande* ou *Prévision d’approvisionnement*). |
| **Quantité en PV** | Quantité prévue dans l’unité de poids variable. |
| **Quantité** | Quantité prévue exprimée dans l’unité de stock. |
| **PV cumulé** | Quantité de prévision cumulée dans l’unité de poids variable lorsque plusieurs lignes de prévision ont été cumulées pour le même article. |
| **Sous-nomenclature** | Numéro de nomenclature d’une sous-nomenclature spécifique. |
| **Sous-gamme** | Numéro de gamme d’une sous-gamme spécifique. |
| (Autres dimensions) | Des dimensions supplémentaires peuvent être affichées sous forme de colonnes dans la grille. Pour sélectionner les dimensions supplémentaires affichées, sélectionnez **Stock \> Dimensions d’affichage** dans le volet Actions. |

## <a name="allocate-forecast"></a><a name="allocate-forecast"></a>Répartir la prévision

La procédure suivante permet de traiter les lignes de transaction de prévision sélectionnées. Lorsque vous affectez une prévision, la quantité est ensuite répartie comme indiqué par les lignes de la grille **Répartition**.

1. Selon le type d’entité pour lequel vous créez une prévision et le type de prévision que vous souhaitez créer, ouvrez une page de prévision d’offre ou de demande, comme décrit dans [Afficher et saisir manuellement des lignes de prévision](#manual-entry).
1. Sur la page des lignes de prévision de l’offre ou de la demande, sélectionnez une ligne de prévision, puis, sur l’onglet **Vue d’ensemble**, sélectionnez **Répartir la prévision** sur la barre d’outils.
1. Dans la boîte de dialogue **Répartir la prévision**, définissez les champs décrits dans le tableau suivant. (La valeur que vous sélectionnez dans le champ **Méthode** détermine les autres champs disponibles.)

    | Champ | Description |
    |---|---|
    | méthode | <p>Sélectionnez la méthode utilisée pour affecter la transaction de prévision :</p><ul><li>**Aucune** : aucune répartition n’est effectuée.</li><li>**Période** : prévoir la même quantité pour chaque période. Si vous sélectionnez cette valeur, spécifiez une quantité dans le champ **Par** et une unité de temps dans le champ **Unité**.</li><li>**Clé** : la quantité prévue est répartie en fonction de la clé de répartition par période que vous spécifiez dans le champ **Clé de période**. Cette méthode permet de prendre en compte les variations saisonnières.</li><ul>|
    | Par | <p>Permet d’entrer le nombre d’intervalles de temps dans le futur couverts par la prévision. Ce champ n’est disponible que si vous avez sélectionné *Période* dans le champ **Méthode**.</p><p>Par exemple, sélectionnez *Période* dans le champ **Méthode**, entrez *1* dans le champ **Par**, et sélectionnez *Mois* dans le champ **Unité**. Ensuite, dans le champ **Fin**, spécifiez une date de fin pouvant aller jusqu’à 1 an dans le futur. Dans ce cas, une ligne de prévision sera créée pour chaque mois de l’année à venir, en fonction de l’article et de la quantité spécifiés sur la ligne d’en-tête. |
    | Unité | Sélectionnez l’unité de l’intervalle de temps : *Jours*, *Mois* ou *Années*. La répartition correspond alors au nombre de jours, mois ou années que vous avez spécifié dans le champ **Par**.|
    | Clé de période | Spécifiez la clé de répartition par période utilisée pour répartir la prévision. Pour plus d’informations, voir [Répartition de données de planification budgétaire](../../finance/budgeting/budget-planning-data-allocation.md). |
    | Terminer | Spécifiez la date de fin qui s’applique à vos paramètres dans les champs **Par** et **Unité**. |

1. Sélectionnez **OK** pour confirmer vos paramètres.
1. Vous pouvez consulter les résultats sur l’onglet **Répartition** pour la même ligne.

## <a name="bulk-update-forecast-transactions"></a><a name="bulk-update"></a>Mise à jour en bloc des transactions de prévision

Cette procédure permet de traiter des lignes de transaction de prévision existantes. Vous pouvez copier, modifier et supprimer les lignes de transaction de prévision.

1. Sur la page des lignes de prévision de la demande ou de l’approvisionnement, sélectionnez **Mise à jour en bloc**.
1. Dans la boîte de dialogue, sélectionnez **Filtrer**.
1. Sur l’onglet **Plage**, sélectionnez les critères identifiant les données de prévision source que vous souhaitez copier, modifier ou supprimer. Ces données peuvent comprendre le modèle de prévision, le numéro d’article et le compte client.
1. Sélectionnez **OK** pour confirmer votre sélection.

    Une fois les données sélectionnées, vous pouvez utiliser la boîte de dialogue **Modifier les transactions de prévision** pour définir comment vous voulez les copier, les modifier ou les supprimer.

    > [!NOTE]
    > L’étape de filtrage est un préalable à l’utilisation de la fonctionnalité **Modification en bloc**. Si vous l’ignorez, le programme sélectionne et met à jour **toutes** les lignes de prévision. Par conséquent, vous pouvez involontairement provoquer la duplication ou la suppression de transactions.

1. Dans la section **Gestion**, indiquez si vous souhaitez copier, mettre à jour ou supprimer les transactions de prévision sélectionnées.
1. Utilisez la section **Modifications des champs** pour modifier les paramètres de la prévision. Activez la case à cocher d’un paramètre, puis faites un choix parmi les options disponibles. Par exemple, activez la case à cocher **Modèle**, puis sélectionnez un numéro de modèle de prévision. Les lignes de prévision existantes sont copiées dans le modèle de prévision sélectionné.
1. Utilisez la section **Changement de période** pour déplacer les dates de début et de fin de la prévision vers l’avant ou vers l’arrière. Activez la case à cocher et utilisez les champs Quantité et Période pour définir le déplacement des dates de prévision. Vous pouvez saisir une quantité négative pour avancer la date de début (c’est-à-dire la placer plus tôt).

    Par exemple, pour retarder de six mois la date de début de la transaction de prévision, cochez la case, saisissez *6* comme quantité, et sélectionnez *Mois* comme période.

1. Utilisez la section **Corriger un champ** pour mettre à jour les données de prévision actuelles. Dans le champ **Champ**, sélectionnez les critères à modifier. Dans le champ **Facteur**, entrez un facteur de multiplication à appliquer au critère sélectionné ou entrez une constante d’addition ou de soustraction. Par exemple, sélectionnez *Quantité* comme critère, et entrez un facteur de *1,5* pour multiplier la quantité de l’article par 1,5. Vous pouvez aussi saisir une constante de *-25* pour diminuer la quantité de l’article de 25 unités.
1. Utilisez la section **Dimensions financières** pour mettre à jour les dimensions financières des lignes de prévision. Sélectionnez les dimensions financières que vous souhaitez modifier, puis entrez une valeur à appliquer aux dimensions sélectionnées.
1. Sélectionner **OK** pour appliquer vos modifications.

## <a name="use-forecasts-with-master-planning"></a>Utiliser les prévisions avec la planification générale

Après avoir saisi vos prévisions de demande et/ou d’approvisionnement, vous pouvez inclure les prévisions pendant la planification générale pour tenir compte de la demande et/ou de l’approvisionnement attendus dans votre cycle de planification. Lorsque les prévisions sont incluses dans la planification générale, les besoins bruts en matériaux et en capacité sont calculés et les ordres planifiés sont générés.

### <a name="set-up-a-master-plan-to-include-an-inventory-forecast"></a>Configurer un plan directeur pour inclure une prévision de stock

Pour configurer un plan directeur afin qu’il inclue une prévision de stock, procédez comme suit.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez un plan existant ou créez un plan.
1. Dans l’organisateur **Général**, définissez les champs suivants :

    - **Modèle de prévision** – Sélectionnez le modèle de prévision à appliquer. Ce modèle sera pris en compte lorsqu’une proposition d’approvisionnement est générée pour le plan directeur actuel.
    - **Inclure la prévision de l’approvisionnement** – Définissez cette option sur *Oui* pour inclure la prévision de l’approvisionnement dans la planification générale actuelle. Si vous la définissez sur *Non*, les transactions de prévision de l’approvisionnement ne seront pas incluses dans le plan directeur.
    - **Inclure la prévision de la demande** – Définissez cette option sur *Oui* pour inclure la prévision de la demande dans le plan général actuel. Si vous le définissez sur *Non*, les transactions de prévision de la demande ne seront pas incluses dans le plan directeur.
    - **Méthode utilisée pour réduire les besoins prévisionnels** – Sélectionnez la méthode à utiliser pour réduire les besoins prévisionnels. Pour plus d’informations, voir [Clés de réduction des prévisions](planning-optimization/demand-forecast.md#reduction-keys).

1. Sur le raccourci **Plages de temps en jours**, vous pouvez définir les champs suivants pour spécifier la période pendant laquelle la prévision est incluse :

    - **Plan prévisionnel** – Réglez cette option sur *Oui* pour remplacer la plage de temps du plan prévisionnel qui provient des groupes de couverture individuels. Réglez-le sur *Non* pour utiliser les valeurs des groupes de couverture individuels pour le plan directeur actuel.
    - **Période de prévision** – Si vous définissez l’option **Plan prévisionnel** sur *Oui*, spécifiez le nombre de jours (à partir de la date d’aujourd’hui) pendant lesquels la prévision de la demande doit être appliquée.

    > [!IMPORTANT]
    > L’option **Plan prévisionnel** n’est pas prise en charge avec l’Optimisation de la planification.

### <a name="run-a-master-plan-that-includes-an-inventory-forecast"></a>Exécuter un plan directeur comprenant une prévision de stock

Pour exécuter un plan directeur comprenant une prévision de stock, procédez comme suit.

1. Accédez à **Planification générale \> Espaces de travail \> Planification générale**.
1. Dans le champ **Planification générale**, saisissez ou sélectionnez le plan directeur que vous avez paramétré dans la procédure précédente.
1. Dans la vignette **Planification générale**, sélectionnez **Exécuter**.
1. Dans la boîte de dialogue **Planification générale**, définissez l’option **Suivre le temps de traitement** sur *Oui*.
1. Entrez un nombre dans le champ **Nombre de threads**.
1. Dans l’organisateur **Enregistrements à inclure**, sélectionnez **Filtre**.
1. Une boîte de dialogue d’éditeur de requête standard s’affiche. Sur l’onglet **Plage**, sélectionnez la ligne où le champ **Champ** est défini sur *Numéro d’article*.
1. Dans le champ **Critères**, sélectionnez le numéro d’article à inclure dans le plan.
1. Cliquez sur **OK**.

Pour afficher les besoins calculés, ouvrez la page **Besoin brut**. Par exemple, sur la page **Produits lancés**, dans le volet Actions, sur l’onglet **Planifier**, dans le groupe **Besoins**, sélectionnez **Besoin brut**.

Pour afficher les ordres planifiés générés, accédez à **Planification \> Commun \> Ordres prévisionnels**, et sélectionnez le programme de prévision approprié.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la prévision de la demande](introduction-demand-forecasting.md)
- [Paramétrage de la prévision de la demande](demand-forecasting-setup.md)
- [Générer des prévisions de base statistiques](generate-statistical-baseline-forecast.md)
- [Effectuer des ajustements manuels sur la prévision de base](manual-adjustments-baseline-forecast.md)
- [Planification avec prévisions de la demande](planning-optimization/demand-forecast.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]