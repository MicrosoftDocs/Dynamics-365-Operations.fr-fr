---
title: États sur le coût au débarquement
description: Cet article décrit comment rechercher et utiliser les différents types de rapports disponibles pour le module Coût au débarquement.
author: Weijiesa
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 836d6b538b32d818ed3b825000d004b005ce95d8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905948"
---
# <a name="landed-cost-reports"></a>Rapports sur le coût au débarquement

[!include [banner](../../includes/banner.md)]

## <a name="outstanding-invoices"></a>Factures en attente

Le rapport des factures impayées contient une liste de toutes les factures impayées des différents niveaux de coûts associés à chaque voyage. Il est utilisé pour réconcilier les frais de voyage et de voyage avec la liste des transactions comptables sur une base régulière. Une fois que les frais généraux ont été facturés, ils sont supprimés du rapport.

Pour générer un rapport des factures impayées, procédez comme suit.

1. Aller à **Prix au débarquement \> Rapports \> Suivi \> Factures impayées**.
1. Dans la boîte de dialogue **Factures impayées**, dans le champ **À la date**, indiquez une date. Toute facture impayée à cette date ou avant sera incluse dans la sortie.
1. Sous **Afficher**, sélectionnez l’une des options suivantes :

    - **Coût non facturé** – Incluez les coûts pour les expéditions facturées qui ont une valeur estimative mais pas de coût réel.
    - **Stock non facturé** – Incluez les coûts qui ont été facturés, mais pour lesquels la commande fournisseur n’a pas encore été reçu.
    - **Tout non facturé** – Incluez les résultats des deux options **Coût non facturé** et **Stock non facturé**.

1. Définissez l’option **Inclure les nouveaux coûts** sur *Oui* pour inclure les coûts qui n’ont pas encore de coût réel et pour lesquels l’inventaire n’a pas été reçu. Si vous le définissez sur *Non*, le rapport ne comprendra que les frais facturés.
1. Dans la section **Vue**, activez chaque type de détail que vous souhaitez inclure dans le rapport.
1. Comme vous le faites pour d’autres types de rapports dans Microsoft Dynamics 365 Supply Chain Management, Utilisez le raccourci **Destination** pour sélectionner le format de sortie du rapport.
1. Comme vous le faites pour les autres types de rapports dans Supply Chain Management, utilisez le raccourci **Enregistrements à inclure** pour limiter davantage les enregistrements qui seront inclus dans le rapport.
1. Sélectionnez **OK** pour générer l’état.

## <a name="activityprovider-analysis-reports"></a>Rapports d’analyse de l’activité/fournisseur

Les rapports d’analyse des activités/prestataires vous permettent de vérifier l’exactitude de vos estimations de temps pour chaque prestataire.

Pour générer un rapport d’analyse d’activité/fournisseur, procédez comme suit.

1. Selon le type de rapport que vous souhaitez créer, procédez comme suit :

    - Aller à **Prix au débarquement \> Rapports \> Analyse de l’activité/prestataire par activité**. Dans ce cas, les estimations de temps seront regroupées par activité.
    - Aller à **Prix au débarquement \> Rapports \> Analyse de l’activité/prestataire par fournisseur**. Dans ce cas, les estimations de temps seront regroupées par fournisseur.

    La boîte de dialogue **Analyse de l’activité / prestataire par activité** ou **Analyse de l’activité / prestataire par prestataire** apparaît. Les deux boîtes de dialogue proposent les mêmes options.

1. Comme vous le faites pour d’autres types de rapports dans Supply Chain Management, Utilisez le raccourci **Destination** pour sélectionner le format de sortie du rapport.
1. Comme vous le faites pour les autres types de rapports dans Supply Chain Management, utilisez le raccourci **Enregistrements à inclure** pour limiter davantage les enregistrements qui seront inclus dans le rapport.
1. Sélectionnez **OK** pour générer l’état.

## <a name="voyage-costing-reports"></a>Rapports sur les coûts de voyage

Les rapports sur les coûts de voyage indiquent le coût des articles et les coûts d’importation par folio, conteneur d’expédition ou voyage, en fonction des options que vous sélectionnez lorsque vous générez le rapport. Chaque rapport de coût de voyage vous permet de visualiser le coût estimé d’un voyage par rapport au coût réel, et il peut être ventilé par plusieurs facteurs d’identification.

Pour générer un rapport des coût de trajet, procédez comme suit.

1. Selon le type de rapport que vous souhaitez créer, procédez comme suit :

    - Aller à **Prix au débarquement \> Rapports \> évaluation des coûts \> Coût du voyage par coût individuel**. Dans ce cas, l’option de coût individuel affichera les coûts d’importation par zone de coût par code de type de coût.
    - Aller à **Prix au débarquement \> Rapports \> évaluation des coûts \> Coût du voyage par catégorie de rapport**. Dans ce cas, le coût d’importation sera ventilé dans les différentes catégories de déclaration. Les types de coûts sont regroupés par catégories de rapports.

    La boîte de dialogue **Coût du voyage par coût individuel** ou **Coût du voyage par catégorie de rapport** apparaît. Ces boîtes de dialogue sont similaires. Toutes les différences sont notées dans le reste de cette procédure.

1. Si vous avez ouvert la boîte de dialogue **Coût du voyage par catégorie de rapport**, dans le champ **Coût**, sélectionnez l’une des valeurs suivantes :

    - **Valeur de coût** – La valeur est calculée à l’aide des coûts automatiques ou créée manuellement dans le domaine de coûts.
    - **Estimé** – Une fois les marchandises reçues, le coût estimé est fixé.
    - **Réel** – Une fois la commande facturée, le coût réel est fixé au coût figurant sur la facture.
    - **Meilleur** – Le système utilisera celle des trois options précédentes qui est la plus précise. (Nous vous recommandons de Sélectionner cette option.)

1. Définissez l’option **Par objet** sur *Oui* pour montrer le coût de chaque article. Réglez-le sur *Non* pour montrer les coûts par voyage.
1. Dans la section **Vue**, sélectionnez les catégories par lesquelles ventiler le coût.
1. Dans la section **Dimensions**, sélectionnez les dimensions à inclure dans le rapport.
1. Comme vous le faites pour d’autres types de rapports dans Supply Chain Management, Utilisez le raccourci **Destination** pour sélectionner le format de sortie du rapport.
1. Comme vous le faites pour les autres types de rapports dans Supply Chain Management, utilisez le raccourci **Enregistrements à inclure** pour limiter davantage les enregistrements qui seront inclus dans le rapport.
1. Sélectionnez **OK** pour générer l’état.

## <a name="shipping-container-receipts-list"></a>Liste des accusés de réception du conteneur d’expédition

La liste des reçus des conteneurs d’expédition contient toutes les quantités non reçues qui sont dues à une date prévue ou avant. Le personnel de l’entrepôt peut utiliser ce rapport pour identifier les marchandises attendues sur un conteneur d’expédition. Il peut également être utilisé pour valider manuellement les marchandises au fur et à mesure de leur réception sur un conteneur d’expédition.

Pour générer une liste de reçus de conteneurs d’expédition, procédez comme suit.

1. Aller à **Prix au débarquement \> Rapports \> Suivi \> Liste des reçus des conteneurs d’expédition**.
1. Dans la boîte de dialogue **Liste des reçus des conteneurs d’expédition**, dans le champ **Date prévue**, indiquez une date. Toute les quantités reçues à cette date ou avant sera incluse dans la sortie.
1. Dans la section **Dimensions**, sélectionnez les dimensions à inclure dans le rapport.
1. Comme vous le faites pour d’autres types de rapports dans Supply Chain Management, Utilisez le raccourci **Destination** pour sélectionner le format de sortie du rapport.
1. Comme vous le faites pour les autres types de rapports dans Supply Chain Management, utilisez le raccourci **Enregistrements à inclure** pour limiter davantage les enregistrements qui seront inclus dans le rapport.
1. Sélectionnez **OK** pour générer l’état.

## <a name="expected-delivery-report"></a>Le rapport de livraison prévue

Le rapport de livraison prévue contient des informations de base sur le voyage, le conteneur d’expédition, le folio, les articles et la date de livraison prévue.

Pour générer un rapport de livraison prévue, procédez comme suit.

1. Aller à **Prix au débarquement \> Rapports \> Suivi \> Livraison prévue**.
1. Dans la boîte de dialogue **Livraison prévue**, dans le champ **Date prévue**, sélectionnez la date à laquelle la livraison des marchandises à l’entrepôt de destination finale est prévue. Toute ligne de voyage dont la date prévue est égale ou antérieure à cette date, et qui n’a pas encore été reçue, sera incluse dans la sortie.
1. Facultatif : dans le champ **Compte fournisseur**, sélectionnez un compte fournisseur pour inclure uniquement les livraisons d’un fournisseur spécifique.
1. Dans la section **Dimensions**, sélectionnez les dimensions à inclure dans le rapport.
1. Comme vous le faites pour d’autres types de rapports dans Supply Chain Management, Utilisez le raccourci **Destination** pour sélectionner le format de sortie du rapport.
1. Comme vous le faites pour les autres types de rapports dans Supply Chain Management, utilisez le raccourci **Enregistrements à inclure** pour limiter davantage les enregistrements qui seront inclus dans le rapport.
1. Sélectionnez **OK** pour générer l’état.
