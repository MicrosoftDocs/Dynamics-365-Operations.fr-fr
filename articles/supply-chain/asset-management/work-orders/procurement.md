---
title: Approvisionnement
description: Cette rubrique explique l'approvisionnement dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderPurchaseListPagePreviewPane, EntAssetWorkOrderPurchaseListPage, EntAssetWorkOrderPurchaseLineAmountInfoPart, EntAssetWorkOrderPurchReqListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 552b1b211460ae86af06e183af91c062a3ee569a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428084"
---
# <a name="procurement"></a>Approvisionnement

[!include [banner](../../includes/banner.md)]

Dans le module Gestion des actifs, vous pouvez obtenir une vue d'ensemble des demandes d'achat et des commandes fournisseur associées aux ordres de travail. Il est également possible de créer une commande fournisseur ou une demande d'achat depuis un ordre de travail.

La page de liste **Demande d'achat de l'ordre de travail** (**Gestion des actifs** > **Commun** > **Approvisionnement** > **Demande d'achat de l'ordre de travail**) affiche une liste des demandes d'achat associées aux ordres de travail. Lorsque vous sélectionnez une tâche d'ordre de travail dans cette page, vous pouvez utiliser les boutons du groupe **Afficher** sous l'onglet du volet d'action **Demande d'achat d'ordres de travail** pour exécuter différentes actions :

- Pour ouvrir la demande d'achat associée, sélectionnez **Demande d'achat**. 
- Pour ouvrir l'ordre de travail associé, sélectionnez **Ordre de travail**.
- Pour avoir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée, en ce qui concerne les actifs, les valeurs par défaut du type de tâche de maintenance, les pièces détachées et les ordres de travail dans Gestion des actifs, sélectionnez **Cas d'emploi d'article**. Pour plus d'informations sur cette vue d'ensemble, voir [Cas d'emploi d'article](../controlling-and-reporting/item-where-used.md).

L'illustration suivante présente un exemple de la liste de page **Demande d'achat de l'ordre de travail**.

![Figure 1](media/08-work-orders.png)


La page de liste **Achats de l'ordre de travail** (**Gestion des actifs** > **Commun** > **Approvisionnement** > **Achats de l'ordre de travail**) affiche une liste des commandes fournisseur associées aux ordres de travail. Lorsque vous sélectionnez une tâche d'ordre de travail dans cette page, vous pouvez utiliser les boutons du groupe **Afficher** sous l'onglet du volet d'action **Achats d'ordres de travail** pour exécuter différentes actions :

- Pour ouvrir la commande fournisseur associée, sélectionnez **Commande fournisseur**. 
- Pour ouvrir l'ordre de travail associé, sélectionnez **Ordre de travail**.
- Pour avoir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée, en ce qui concerne les actifs, les valeurs par défaut du type de tâche de maintenance, les pièces détachées et les ordres de travail dans Gestion des actifs, sélectionnez **Cas d'emploi d'article**. Pour plus d'informations sur cette vue d'ensemble, voir [Cas d'emploi d'article](../controlling-and-reporting/item-where-used.md).

L'illustration suivante présente un exemple de la liste de page **Achats de l'ordre de travail**.

![Figure 2](media/09-work-orders.png)


Sur la page de liste **Achats de l'ordre de travail** et la page de liste **Demande d'achat de l'ordre de travail**, un symbole lié au contrôle de la date de livraison s'affiche à droite de chaque ligne. Si le symbole est un point d'exclamation dans un cercle rouge, la livraison de la commande fournisseur ou de la demande d'achat associée peut être retardée.

Pour une commande fournisseur, la date associée à la ligne de commande fournisseur est utilisée pour calculer un retard possible. Pour afficher cette date, sur la page **Commande fournisseur**, sélectionnez la ligne de commande fournisseur. La date est affichée dans le champ **Date de livraison confirmée** sur l'onglet **Paramétrage** de l'organisateur **Détails de ligne**. Si le champ **Date de livraison confirmée** n'est pas défini, la date dans le champ **Date de livraison** sur l'organisateur **En-tête de commande fournisseur** est utilisée pour le calcul. Une de ces dates est comparée à la date disponible sur l'ordre de travail ou à la tâche de l'ordre de travail dans l'ordre suivant :

1. Date de début réelle sur l'ordre de travail  

2. Date de début prévue sur la tâche de l'ordre de travail associée 

3. Date de début planifiée sur l'ordre de travail 

4. Date de début prévue sur l'ordre de travail, ou 

Pour une demande d'achat, la date du champ **Date demandée** sur l'organisateur **En-tête de demande d'achat** de la page **Demandes d'achat** est utilisée pour calculer un retard possible. La date de ce champ est comparée à la date disponible sur l'ordre de travail ou à la tâche de l'ordre de travail dans le même ordre que celui utilisé pour une commande fournisseur.


## <a name="create-a-purchase-order-from-a-work-order"></a>Création d'une commande fournisseur à partir d'un ordre de travail

Sur la page de liste **Tous les ordres de travail**, vous pouvez sélectionner une tâche de l'ordre de travail, puis créer une commande fournisseur ou une demande d'achat associée. Ainsi, vous garantissez que des relations de projet existent entre la commande fournisseur ou la demande d'achat et l'ordre de travail.

1. Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail pour lequel créer une commande fournisseur, puis sélectionnez **Modifier**.

3. Sur l'organisateur **Tâches de maintenance de l'ordre de travail**, sélectionnez la tâche de l'ordre de travail pour laquelle créer la commande fournisseur.

4. Sélectionnez **Tâches d'article** > **Commande fournisseur de la tâche de l'ordre de travail**.

5. Sur la page de liste **Commandes fournisseur de projet**, cliquez sur **Nouveau**.

6. Créez la commande fournisseur.

>[!NOTE]
>Pour créer une demande d'achat associée, suivez les mêmes étapes. Toutefois, sélectionnez **Tâches d'article** > **Demande d'achat de la tâche de l'ordre de travail** à l'étape 4.


## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relation de projet entre l'ordre de travail et la commande fournisseur ou la demande d'achat

Une ligne de commande fournisseur ou une ligne de demande d'achat est associée à une tâche de l'ordre de travail via le projet de l'ordre de travail et le numéro d'activité de projet associé. Lorsque vous créez une commande fournisseur ou une demande d'achat d'une tâche de l'ordre de travail, le numéro d'activité de projet associé est obligatoire. Si toutes les tâches d'ordre de travail de l'ordre de travail associé contiennent le même type de tâche de maintenance, le numéro d'activité de projet est automatiquement entré sur la commande fournisseur ou la demande d'achat. Si les tâches d'ordre de travail ont des types de tâches de maintenance différents, vous devez entrer manuellement le numéro d'activité de projet sur la commande fournisseur ou la demande d'achat.

Pour afficher ou entrer le numéro d'activité associé à une ligne de commande fournisseur, sur la page de liste **Journal des ordres de travail**, sélectionnez l'enregistrement de commande fournisseur, puis, dans la colonne **Commande fournisseur**, sélectionnez le lien vers la commande fournisseur. Vous pouvez trouver le champ **Numéro d'activité** sur l'onglet **Projet** de l'organisateur **Détails de ligne**.

L'illustration suivante présente un exemple de la page **Commande fournisseur**, avec un focus sur le **Numéro d'activité**.

![Figure 3](media/10-work-orders.png)

De même, pour afficher ou entrer le numéro d'activité associé à une ligne de demande d'achat d'ordre de travail, sur la page de liste **Demande d'achat d'ordre de travail**, sélectionnez l'enregistrement de la demande d'achat, puis, dans la colonne **Demande d'achat**, sélectionnez le lien vers la demande d'achat. Vous pouvez trouver le champ **Numéro d'activité** sur l'onglet **Projet** de l'organisateur **Détails de ligne**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]