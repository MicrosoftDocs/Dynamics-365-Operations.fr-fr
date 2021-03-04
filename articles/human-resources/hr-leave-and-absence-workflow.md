---
title: Créer un workflow de demande d'absence
description: Créez un workflow de demande de congé et d'absence pour gérer les demandes de congé de manière cohérente dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 209f0ec7236778cc0a828102e554b02206b45b73
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418440"
---
# <a name="create-a-leave-request-workflow"></a>Créer un workflow de demande d'absence

Vous créez un workflow dans Dynamics 365 Human Resources pour gérer de manière cohérente les demandes de congé et d'absence. Un workflow **Congé et absence** vous permet de :

- Définir des tâches
- Déterminer qui doit effectuer les tâches
- Spécifier qui peut approuver ou rejeter les demandes

## <a name="create-a-leave-and-absence-request-workflow"></a>Créer un workflow de demande de congé ou d'absence

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Workflows des ressources humaines**.

3. Sélectionnez **Nouveau**, puis sélectionnez **Demande de congé et d'absence**. 

4. Quand la boîte de dialogue **Ouvrir ce fichier ?** apparaît, sélectionnez **Ouvrir** et connectez-vous avec les informations d'identification de votre entreprise.

5. Utilisez l’éditeur de workflow pour créer un workflow pour vos demandes de congé. Pour plus d’informations sur l’utilisation des workflows, consultez [Créer une vue d’ensemble des workflows](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Éléments de données liés au workflow de demande de congé ou d’absence

Vous pouvez utiliser les éléments de données suivants pour créer des approbations conditionnelles ou automatiques dans les workflows pour les demandes de congé et d'absence :

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

Ces exemples montrent comment créer différents types de conditions de workflow à l'aide de ces éléments de données :

- Utilisez **Code de raison** dans une instruction conditionnelle pour acheminer les demandes de congé maladie avec le code de motif **Chirurgie** aux RH pour approbation, tout en acheminant tous les autres codes de motif au responsable. Pour plus d'informations sur les instructions conditionnelles, consultez [Configurer des décisions conditionnelles dans un workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow). 

- Utilisez **Soumis par les Ressources humaines** et **Soumis par le Responsable** dans une action automatique pour approuver automatiquement les demandes de congé que ces rôles soumettent au nom des employés. Pour plus d’informations sur les actions automatiques, consultez [Configurer des processus d’approbation dans un workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).

- Utilisez **Type de congé** dans une instruction conditionnelle ou une action automatique pour contrôler la façon dont le workflow achemine les demandes avec certains types de congés.

## <a name="see-also"></a>Voir également :

- [Vue d'ensemble des congés et des absences](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]