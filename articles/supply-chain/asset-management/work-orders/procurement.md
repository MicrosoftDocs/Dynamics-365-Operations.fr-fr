---
title: Approvisionnement
description: Cette rubrique explique l'approvisionnement dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1678dbe2432e4be46aebb40a12e73dfd695c3e77
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875649"
---
# <a name="procurement"></a>Approvisionnement


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Dans le module Gestion des actifs, vous pouvez obtenir une vue d'ensemble des demandes d'achat et des commandes fournisseur associées aux ordres de travail. Il est également possible de créer une commande fournisseur ou une demande d'achat depuis un ordre de travail.

Dans la liste **Demande d'achat de l'ordre de travail** (**Gestion des actifs** > **Commun** > **Approvisionnement** > **Demande d'achat de l'ordre de travail**), vous voyez une liste des demandes d'achat associées aux ordres de travail.

- Sélectionnez une tâche de l'ordre de travail dans la liste **Demande d'achat de l'ordre de travail**, puis cliquez sur le bouton **Demande d'achat** pour ouvrir la demande d'achat associée.  
- Sélectionnez une tâche de l'ordre de travail dans la liste **Demande d'achat de l'ordre de travail**, puis cliquez sur le bouton **Ordre de travail** pour ouvrir l'ordre de travail associé.  
- Sélectionnez une tâche de l'ordre de travail dans la liste **Demande d'achat de l'ordre de travail**, puis cliquez sur le bouton **Cas d'emploi d'article** si vous souhaitez obtenir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée dans le module Gestion des actifs, en ce qui concerne les actifs, le type de tâche de maintenance par défaut, les pièces détachées et les ordres de travail. 

![Figure 1](media/08-work-orders.png)


Dans la liste **Demande d'achat de l'ordre de travail** (**Gestion des actifs de l'entreprise** > **Commun** > **Approvisionnement** > **Demande d'achat de l'ordre de travail**), vous voyez une liste des commandes fournisseur associées aux ordres de travail.

- Sélectionnez une tâche de l'ordre de travail dans la liste **Demande d'achat de l'ordre de travail**, puis cliquez sur le bouton **Commande fournisseur** pour ouvrir la commande fournisseur associée.  
- Sélectionnez une tâche de l'ordre de travail dans la liste **Achat d'ordre de travail**, puis cliquez sur le bouton **Ordre de travail** pour ouvrir l'ordre de travail associé.  
- Sélectionnez une tâche de l'ordre de travail dans la liste d'achat **de l'ordre de travail**, puis cliquez sur le bouton **Cas d'emploi d'article** si vous souhaitez obtenir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée dans le module Gestion des actifs, en ce qui concerne les actifs, le type de tâche de maintenance par défaut, les pièces détachées et les ordres de travail. 

![Figure 2](media/09-work-orders.png)


Dans les listes indiquées ci-dessus, une icône concernant le contrôle de la date de livraison apparaît à droite de chaque ligne. Si l'icône affiche un point d'exclamation dans un cercle rouge, cela signifie que la livraison sur la demande d'achat ou la commande d'achat associée peut être retardée.

Dans une demande d'achat, la date utilisée pour calculer le retard possible figure sur l'écran **Demandes d’achat** > organisateur **En-tête de demande d'achat** > champ **Date demandée**. Cette date est comparée à la date disponible sur l'ordre de travail ou à la tâche de l'ordre de travail de la même manière que la date de commande fournisseur.

Dans une commande fournisseur, la date utilisée pour calculer le retard possible est la date associée à la ligne de commande fournisseur, indiquée à l'écran **Commande fournisseur** > sélectionnez la ligne de commande fournisseur > organisateur **Détails de ligne** > onglet **Paramétrage** > champ **Date de livraison confirmée**. Si ce champ n'est pas renseigné, la date dans le champ **Date de livraison** sur l'organisateur **En-tête de commande fournisseur** est utilisée. Une de ces dates est comparée à la date disponible sur l'ordre de travail ou à la tâche de l'ordre de travail dans l'ordre suivant :

- Date de début réelle sur l'ordre de travail, ou  

- Date de début prévue sur la tâche de l'ordre de travail associée, ou  

- Date de début planifiée sur l'ordre de travail, ou  

- Date de début prévue sur l'ordre de travail, ou  


## <a name="create-purchase-order-from-a-work-order"></a>Création d'une commande fournisseur à partir d'un ordre de travail

Dans **Tous les ordres de travail**, sélectionnez une tâche de l'ordre de travail et créez une commande fournisseur ou une demande d'achat associée. Cela est effectué pour garantir les relations de projet entre la commande fournisseur ou la demande d'achat et l'ordre de travail.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Dans le champ **Tous les ordres de travail** ou dans la liste **Ordres de travail actifs**, sélectionnez l'ordre de travail pour lequel vous voulez créer une commande fournisseur, puis cliquez sur **Modifier**.

3. Sur l'écran **Ordre de travail** > organisateur **Tâches de maintenance de l'ordre de travail**, sélectionnez la tâche de l'ordre de travail pour laquelle créer la commande fournisseur.

4. Cliquez sur **Tâches d'article** > **Commande fournisseur de la tâche de l'ordre de travail**.

5. Sur la page de liste **Commandes fournisseur de projet**, cliquez sur **Nouveau**.

6. Créez la commande fournisseur.

>[!NOTE]
>Créer une demande d'achat est presque identique à créer une commande fournisseur. La seule différence est que dans la procédure ci-dessus, vous cliquez sur **Tâches d'article** > **Demande d'achat de la tâche de l'ordre de travail** à l'étape 2.

## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relation de projet entre l'ordre de travail et la commande fournisseur ou la demande d'achat

Une ligne de commande fournisseur ou une ligne de demande d'achat est associée à une tâche de l'ordre de travail via le projet de l'ordre de travail et le numéro d'activité de projet associé. Lorsque vous créez une commande fournisseur ou une demande d'achat d'une tâche de l'ordre de travail, le numéro d'activité de projet associé est obligatoire. Le numéro d'activité de projet est automatiquement inséré sur une commande fournisseur ou une demande d'achat si l'ordre de travail associé contient des tâches de l'ordre de travail qui utilisent toutes le même type de tâche de maintenance. Si les tâches de l'ordre de travail contiennent différents types de tâches de maintenance, le numéro de l'activité de projet doit être ajouté manuellement.

Pour afficher ou insérer le numéro d'activité associé à une ligne de commande fournisseur, ouvrez **Achat de l'ordre de travail** > sélectionnez l'enregistrement de commande fournisseur > cliquez sur la commande fournisseur dans la colonne **Commande fournisseur** > organisateur **Détails de ligne** > onglet **Projet** > champ **Numéro d'activité**.


![Figure 3](media/10-work-orders.png)


De la même façon,pour voir ou insérer le numéro d'activité associé à une ligne de demande d'achat de l'ordre de travail, ouvrez **Demande d'achat de l'ordre de travail** > sélectionnez l'enregistrement de demande d'achat > cliquez sur la demande d'achat dans la colonne **Demande d'achat** > organisateur **Détails de ligne** > onglet **Projet** > champ **Numéro d'activité**.

