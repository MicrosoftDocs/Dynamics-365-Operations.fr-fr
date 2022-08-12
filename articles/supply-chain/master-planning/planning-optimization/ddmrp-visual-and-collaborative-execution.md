---
title: Exécution visuelle et collaborative
description: Cet article décrit comment surveiller vos points de découplage de planification des besoins en matériaux basée sur la demande (DDMRP), zones tampons, commandes planifiées et historique.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqDDMRPWorkspace, ReqDecouplingPointsStatusByNetFlow, ReqDecouplingPointStatusByOnHand, ReqPlannedOrderForm, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: e3afdd10860494b3cfe73a113a0e4e8fb07682a1
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186668"
---
# <a name="visual-and-collaborative-execution"></a>Exécution visuelle et collaborative

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Cet article décrit comment surveiller vos points de découplage de planification des besoins en matériaux basée sur la demande (DDMRP), zones tampons, commandes planifiées et historique.

## <a name="visually-track-buffers-and-quantities-for-a-selected-item"></a>Suivre visuellement les tampons et les quantités pour un article sélectionné

Dans Microsoft Dynamics 365 Supply Chain Management, vous pouvez suivre visuellement l’évolution des tampons, des quantités disponibles et des niveaux de flux nets au fil du temps pour tout produit lancé sélectionné. Suivez ces étapes pour ouvrir et examiner les graphiques.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez un poste validé configuré comme point de découplage. (Pour plus d’informations, voir [Positionnement du stock](ddmrp-inventory-positioning.md).)
1. Dans le volet Actions, sur l’onglet **Plan**, sélectionnez **Couverture de l’article**.
1. Sur la page **Couverture de l’article**, sélectionnez un enregistrement de couverture d’article qui crée un point de découplage. (Cet enregistrement affichera le nom d’un groupe de couverture configuré pour créer des points de découplage.)
1. Sélectionnez l’onglet **Disponible**. Cet onglet comprend un graphique qui montre comment les quantités en stock ont évolué au fil du temps, ainsi que la valeur du niveau en stock qui a été enregistrée pour une période spécifique chaque fois que l’optimisation de la planification est exécutée. L’onglet comprend également un tableau qui indique à laquelle des catégories suivantes appartient chaque niveau disponible enregistré :

    - **Extrêmement faible** : inférieur à la moitié du minimum pour la période.
    - **Faible** : entre la moitié du minimum et le minimum.
    - **Moyenne disponible** : entre le minimum et le minimum plus la zone verte.
    - **Supérieure à la moyenne** : plus élevée par rapport à la moyenne.

    ![Niveaux de disponibilité historiques dans l’onglet Disponible.](media/ddmrp-on-hand-graph.png "Niveaux de disponibilité historiques dans l’onglet Disponible")

    > [!NOTE]
    > Les couleurs utilisées sur l’onglet **Disponible** représentent différentes gammes que les couleurs similaires utilisées sur l’onglet **Valeurs du buffer**.

1. Pour voir comment vos valeurs de tampon ont changé au fil du temps et comment elles se comparent aux niveaux de flux disponibles et nets, sélectionnez l’onglet **Valeurs de buffer**.

    ![Niveaux historiques de disponibilité et de flux net dans l’onglet Valeurs de buffer.](media/ddmrp-buffer-values-graph.png "Niveaux historiques de disponibilité et de flux net dans l’onglet Valeurs de buffer")

## <a name="track-the-status-and-planned-orders-for-all-decoupling-points"></a>Suivre le statut et les commandes planifiées pour tous les points de découplage

L’espace de travail **MRP piloté par la demande** fournit plusieurs outils, ainsi que des indicateurs de performance clés (KPI) et des aperçus de l’état de vos éléments de point de découplage et des commandes planifiées associées. Pour l’ouvrir, accédez à **Planification générale \> Espaces de travail \> MRP piloté par la demande**.

![Espace de travail MRP piloté par la demande](media/ddmrp-workspace.png "Espace de travail MRP piloté par la demande")

## <a name="get-overviews-of-decoupling-points-and-planned-orders"></a>Obtenez des aperçus des points de découplage et des commandes planifiées

En plus de l’espace de travail **MRP piloté par la demande**, Supply Chain Management fournit plusieurs pages où vous pouvez afficher des informations sur votre configuration de la DDMRP, les points de découplage et les commandes planifiées. Certaines de ces pages fournissent également des boutons pratiques dans le volet Actions qui vous permettent de gérer les tampons, d’exécuter la planification générale et d’ouvrir d’autres vues connexes.

- Pour afficher l’état des points de découplage par niveau de débit net, accédez à **Planification générale \> Planification générale \> DDMRP \> Statut des points de découplage par flux net**.
- Pour afficher l’état des points de découplage par niveau de stock disponible, accédez à **Planification générale \> Planification générale \> DDMRP \> Statut des points de découplage par disponibilité**.
- Pour consulter les ordres prévisionnels des points de découplage, rendez-vous sur **Planification générale \> Planification générale \> DDMRP \> Commandes planifiées pour les points de découplage**.
- Pour afficher des délais découplés, accédez à **Planification \> Planification \> DDMRP \> Délai découplé**.

## <a name="clean-up-decoupling-point-buffer-values"></a>Nettoyage des valeurs du buffer au point de découplage

Au fil du temps, votre système accumulera une grande quantité de données historiques liées aux calculs de tampon en cours. Ces données historiques entraîneront une augmentation de votre volume de données et peuvent éventuellement affecter les performances de votre système. Par conséquent, nous vous recommandons de nettoyer occasionnellement les anciennes valeurs de tampon du point de découplage.

> [!WARNING]
> La tâche de nettoyage supprimera les paramètres de valeur de la marge historique et les informations sur le flux disponible/net historique. Ce n’est pas réversible.

Suivez ces étapes pour nettoyer vos valeurs tampons pour un point de découplage.

1. Accédez à **Planification \> Planification \> DDMRP \> Nettoyer les valeurs de buffer de point de découplage**.
1. Dans la boîte de dialogue **Nettoyer les valeurs de buffer de point de découplage**, définissez les champs suivants :

    - **Supprimer les enregistrements de plus de (jours)**  : spécifiez l’âge des enregistrements les plus récents à conserver, en jours. Tous les enregistrements de valeur de buffer de point de découplage qui sont plus anciens que cette valeur seront supprimés.
    - **Plan général** : sélectionnez un plan général qui inclut les éléments qui doivent être concernés par ce nettoyage. Le nettoyage s’appliquera à tous les éléments du plan une fois les paramètres **Filtrer** que vous spécifiez dans cette boîte de dialogue appliqués.

1. Pour limiter l’ensemble des enregistrements sur lequel cette tâche de traitement par lots doit être exécutée, sur le raccourci **Enregistrements à inclure**, sélectionnez **Filtrer** pour ouvrir la boîte de dialogue **Recherche**. Cette boîte de dialogue fonctionne comme pour d’autres types de [tâches d’arrière-plan](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Sur l’organisateur **Exécuter en arrière-plan**, spécifiez comment, quand et à quelle fréquence le nettoyage doit être fait. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Sélectionnez **OK** pour ajouter la nouvelle tâche à une file d’attente des traitements par lots pour exécution.
