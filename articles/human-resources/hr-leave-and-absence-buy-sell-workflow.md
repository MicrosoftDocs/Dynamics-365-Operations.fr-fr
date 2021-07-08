---
title: Créer un workflow de demande d’achat et de vente de congés
description: Créez un workflow de demande d’achat et de vente de congés pour gérer les demandes d’achat et de vente de congés de manière cohérente dans Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9ec21cda4779fea8c28b73d25842219da900da9d
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271478"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a>Créer un workflow de demande d’achat et de vente de congés

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous créez un workflow dans Dynamics 365 Human Resources pour gérer de manière cohérente les demandes d’achat et de vente de congés. Un workflow **Achat et vente de congés** vous permet de :

- Définir des tâches
- Déterminer qui doit effectuer les tâches
- Spécifier qui peut approuver ou rejeter les demandes

## <a name="create-a-buy-and-sell-leave-request-workflow"></a>Créer un workflow de demande d’achat et de vente de congés

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Workflows des ressources humaines**.

3. Sélectionnez **Nouveau**, puis sélectionnez **Demandes d’achat et de vente de congés**. 

4. Quand la boîte de dialogue **Ouvrir ce fichier ?** apparaît, sélectionnez **Ouvrir** et connectez-vous avec les informations d’identification de votre entreprise.

5. Utilisez l’éditeur de workflow pour créer un workflow pour vos demandes de congé. Pour plus d’informations sur l’utilisation des workflows, consultez [Créer une vue d’ensemble des workflows](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Éléments de données liés au workflow de demande de congé ou d’absence

Vous pouvez utiliser les éléments de données suivants pour créer des approbations conditionnelles ou automatiques dans les workflows de demandes d’achat et de vente de congés :

- **Montant**
- **Stratégie d’achat et de vente de congés**
- **Société**
- **Créé(e) par**
- **Date et heure de création**
- **Date de fin**
- **Type de congé**
- **Modifié(e) par**
- **Date et heure de modification**
- **ID demande**
- **Date de début**
- **État** 
- **Date de soumission**
- **Soumis par**
- **Soumis par les Ressources humaines**
- **Soumis par le Responsable**
- **Soumis au nom de**
- **Collaborateur**

## <a name="workflow-examples"></a>Exemples de workflow

Ces exemples montrent comment créer différents types de conditions de workflow à l’aide de ces éléments de données :

- Utilisez **Soumis par les Ressources humaines** et **Soumis par le Responsable** dans une action automatique pour approuver automatiquement les demandes d’achat et de vente de congés que ces rôles soumettent au nom des employés. Pour plus d’informations sur les actions automatiques, consultez [Configurer des processus d’approbation dans un workflow](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).

- Utilisez **Type de congé** dans une instruction conditionnelle ou une action automatique pour contrôler la façon dont le workflow achemine les demandes avec certains types de congés.

## <a name="see-also"></a>Voir également :

[Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)<br>
[Gérer les stratégies d’achat et de vente de congés](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)<br>
[Achat et vente de congés](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
