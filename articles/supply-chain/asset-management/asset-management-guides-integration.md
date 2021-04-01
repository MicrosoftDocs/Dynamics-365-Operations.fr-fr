---
title: Intégration de Dynamics 365 Supply Chain Management (Gestion des actifs) avec Dynamics 365 Guides
description: Cette rubrique explique comment intégrer le module Gestion des actifs dans Microsoft Dynamics 365 Supply Chain Management avec Dynamics 365 Guides pour bénéficier de guides de réalité mixte dans vos workflows de service et de maintenance au quotidien.
author: kamaybac
manager: tfehr
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: e3e9e74397faec12f6eecff1f562fd9d731ac5e2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230150"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a>Intégration de Dynamics 365 Supply Chain Management (Gestion des actifs) avec Dynamics 365 Guides

Vous pouvez intégrer le module **Gestion des actifs** dans Microsoft Dynamics 365 Supply Chain Management avec Dynamics 365 Guides pour bénéficier de guides de réalité mixte dans vos workflows de service et de maintenance au quotidien. Si un guide est associé à un ordre de travail Gestion des actifs, un collaborateur qui ouvre la liste de contrôle de maintenance de l’ordre de travail dans l’application mobile Supply Chain Management (Dynamics 365) voit qu’un guide est disponible. Le collaborateur peut alors trouver et ouvrir le guide dans l’application Dynamics 365 Guides HoloLens.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir joindre des guides aux bons de travail de gestion des actifs, vous devez remplir ces conditions préalables :

- [Configurer Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 ou version ultérieure.
- [Activer la double écriture pour les applications Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).
- [Activer le vol](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) pour la fonctionnalité **MRGuidesFeature**. (Pour les environnements de production, vous devez d’abord soumettre un ticket d’assistance pour que votre locataire soit ajouté au groupe de pilotage.)
- [Activez les clés de configuration suivantes](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) sur la page **Configuration des licences** :

    - Gestion des actifs \> Gestion des actifs de réalité mixte
    - Réalité mixte \> Guide de réalité mixte

- [Configurer Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 ou version ultérieure.

## <a name="use-dynamics-365-guides-with-asset-management"></a>Utiliser Dynamics 365 Guides avec le module Gestion des actifs

Pour associer un guide, vous utilisez une ligne de liste de contrôle de maintenance dans Gestion des actifs. Vous pouvez créer l’association via un modèle de liste de contrôle de maintenance, un type de travail de maintenance ou un ordre de travail, car les trois contiennent des lignes de liste de contrôle de maintenance. Vous pouvez gagner du temps en utilisant un modèle, car un modèle peut être associé à tous les types de travaux de maintenance qui l’utilisent. Par exemple, un guide associé à un type de travail de maintenance est automatiquement associé à tous les ordres de travail qui spécifient ce type de travail. D’un autre côté, un guide associé directement à un ordre de travail n’existe que pour cet ordre de travail.

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a>Associer un guide à un modèle de liste de contrôle de maintenance

Pour associer un guide à un modèle de liste de contrôle de maintenance, suivez cette procédure.

1. Créez un guide en utilisant les applications Dynamics 365 Guides PC et HoloLens. Pour plus d’informations sur le mode de création d’un guide, consultez les rubriques suivantes :

    - [Utiliser l’application PC pour créer un guide](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [Utiliser l’application HoloLens pour placer vos hologrammes](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. Dans Supply Chain Management, [créez un modèle de liste de contrôle de maintenance](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).
1. Associez le guide que vous avez créé à une ligne de liste de contrôle de maintenance dans le nouveau modèle de liste de contrôle de maintenance :

    1. Sur le raccourci **Lignes de liste de contrôle de maintenance**, sélectionnez la ligne à laquelle vous souhaitez associer le guide.
    1. Dans le raccourci **Guides associés**, sélectionnez **Ajouter un guide**.

        ![Associer un guide à un modèle de ligne de contrôle de maintenance](media/am-guides-integration-add-guide.png "Associer un guide à un modèle de ligne de contrôle de maintenance")

    1. Dans le champ **Nom**, sélectionnez un guide, puis sélectionnez **Enregistrer**.

        ![Sélectionner un guide dans le champ Nom](media/am-guides-integration-select-guide.png "Sélectionner un guide dans le champ Nom")

1. Associer le modèle de liste de contrôle de maintenance à un type de tâche :

    1. [Créer un type de tâche de maintenance](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) ou sélectionner un type de tâche de maintenance existant.
    1. Dans le volet Actions, sélectionnez **Valeurs par défaut du type de tâche de maintenance**.

        ![Bouton Valeurs par défaut du type de tâche de maintenance](media/am-guides-integration-job-defaults.png "Bouton Valeurs par défaut du type de tâche de maintenance")

    1. Créez une ligne, puis sélectionnez **Enregistrer**.

        ![Créer une ligne](media/am-guides-integration-add-line.png "Créer une ligne").

    1. Dans le volet Actions, sélectionnez **Liste de contrôle de maintenance**.

        ![Bouton Liste de contrôle de maintenance](media/am-guides-integration-maintenance-checklist.png "Bouton Liste de contrôle de maintenance")

    1. Dans le raccourci **Lignes de liste de contrôle de maintenance**, ajoutez une ligne, puis remplacez la valeur du champ **Type** par **Modèle**.

        ![Changer la valeur Type](media/am-guides-integration-checklist-lines.png "Changer la valeur Type")

    1. Dans le raccourci **Détails de la ligne**, dans le champ **Modèle**, sélectionnez le modèle auquel vous avez associé le guide, puis sélectionnez **Enregistrer**.

        ![Sélectionner le modèle](media/am-guides-integration-checklist-line-details.png "Sélectionner le modèle")

1. [Créez un bon de travail](work-orders/manually-created-workorders.md#create-work-order), puis sélectionnez le type de tâche de maintenance qui utilise le modèle de liste de contrôle de maintenance auquel vous avez associé le guide. Le guide est automatiquement associé à l’ordre de travail.

    ![Sélectionner le type de tâche de maintenance](media/am-guides-integration-create-work-order.png "Sélectionner le type de tâche de maintenance")

1. Affichez le guide qui est associé à l’ordre de travail et aux collaborateurs :

    1. Ouvrez l’[Espace de travail mobile de gestion des actifs](asset-management-mobile-workspace.md) pour accéder à l’ordre de travail.
    1. [Ouvrez la liste de contrôle de maintenance](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) pour l’ordre de travail.
    1. Sélectionnez une ligne de liste de contrôle pour voir le guide associé.

        ![Guide associé à une ligne de liste de contrôle](media/am-guides-integration-show-guide.png "Guide associé à une ligne de liste de contrôle")

    1. Ouvrez le guide dans HoloLens.

        ![Ouvrer le guide dans HoloLens](media/am-guides-integration-hololens-select.png "Ouvrir le guide dans HoloLens")

> [!NOTE]
> Vous pouvez également associer un guide directement dans la liste de contrôle de maintenance d’un ordre de travail ou d’un type de travail.

> [!IMPORTANT]
> Il existe un problème connu où, lorsque vous associez un modèle de liste de contrôle de maintenance à un type de tâche de maintenance par défaut, le guide lié au modèle n’apparaît pas dans le raccourci **Guides associés** de la page **Valeurs par défaut du type de tâche de maintenance**. Cependant, le guide apparaîtra après que ce type de travail soit appliqué à un ordre de travail dans le raccourci **Guides associés**.

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble de la double écriture](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [Vue d’ensemble de la gestion des actifs](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]