---
title: Créer un workflow de demande d’absence
description: Créez un workflow de demande de congé et d’absence pour gérer les demandes de congé de manière cohérente dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a4ce8d0a121e2fa24e3c221a30eb13debd6e44ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855084"
---
# <a name="create-a-leave-request-workflow"></a>Créer un workflow de demande de congé

> [!Important]
> La fonctionnalité indiquée dans cet article est actuellement disponible pour les clients sur Dynamics 365 Human Resources autonome. Certaines ou toutes les fonctionnalités seront disponibles dans le cadre d’une future version de l’infrastructure Finance après la version 10.0.26 de Finance.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous créez un workflow dans Dynamics 365 Human Resources pour gérer de manière cohérente les demandes de congé et d’absence. Un workflow **Congé et absence** vous permet de :

- Définir des tâches
- Déterminer qui doit effectuer les tâches
- Spécifier qui peut approuver ou rejeter les demandes

## <a name="create-a-leave-and-absence-request-workflow"></a>Créer un workflow de demande de congé ou d’absence

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Workflows des ressources humaines**.

3. Sélectionnez **Nouveau**, puis sélectionnez **Demande de congé et d’absence**. 

4. Quand la boîte de dialogue **Ouvrir ce fichier ?** apparaît, sélectionnez **Ouvrir** et connectez-vous avec les informations d’identification de votre entreprise.

5. Utilisez l’éditeur de workflow pour créer un workflow pour vos demandes de congé. Pour plus d’informations sur l’utilisation des workflows, consultez [Créer une vue d’ensemble des workflows](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Éléments de données liés au workflow de demande de congé ou d’absence

Vous pouvez utiliser les éléments de données suivants pour créer des approbations conditionnelles ou automatiques dans les workflows pour les demandes de congé et d’absence :

- **Montant**
- **Commentaire**
- **Société**
- **Créateur**
- **Date et heure de création**
- **Date de fin**
- **Type de congé**
- **Modifiées par**
- **Date et heure de modification**
- **Code motif**
- **ID demande**
- **Date de début**
- **État** 
- **Date de soumission**
- **Soumis par**
- **Soumis par les Ressources humaines**
- **Soumis par le Responsable**
- **Soumis au nom de**
- **Collaborateur**
- **Type de collaborateur**

Ces exemples montrent comment créer différents types de conditions de workflow à l’aide de ces éléments de données :

- Utilisez **Code de raison** dans une instruction conditionnelle pour acheminer les demandes de congé maladie avec le code de motif **Chirurgie** aux RH pour approbation, tout en acheminant tous les autres codes de motif au responsable. Pour plus d’informations sur les instructions conditionnelles, consultez [Configurer des décisions conditionnelles dans un workflow](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md). 

- Utilisez **Soumis par les Ressources humaines** et **Soumis par le Responsable** dans une action automatique pour approuver automatiquement les demandes de congé que ces rôles soumettent au nom des employés. Pour plus d’informations sur les actions automatiques, consultez [Configurer des processus d’approbation dans un workflow](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).

- Utilisez **Type de congé** dans une instruction conditionnelle ou une action automatique pour contrôler la façon dont le workflow achemine les demandes avec certains types de congés.

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
