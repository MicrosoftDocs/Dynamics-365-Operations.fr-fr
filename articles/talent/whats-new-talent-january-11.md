---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (11 janvier 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e6a89ba455acbed9724da6826ac4d41c6a481490
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "856136"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-11-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (11 janvier 2019)

[!include [banner](includes/banner.md)]

**Version 8.1.2100**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.

## <a name="changes"></a>Modifications

### <a name="validate-leave-requests-by-forecasting-available-balance"></a>Valider les demandes de congés en prévoyant le solde disponible
Les modifications apportées dans cette version permettent aux employés de demander un congé à venir sans le soustraire de son solde actuel. Les workflows standard seront utilisées pour toute demande ultérieure. Pour plus d'informations, voir [Accorder des congés sur la base des heures travaillées](leave-accrue-hours-worked.md).

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a>Afficher le solde des congés prévus dans ESS et People
Cette fonction permet d'afficher les soldes pour les périodes de congés à venir par les RH, les responsables et les employés. Les employés peuvent afficher les futurs soldes dans l'espace de travail **Libre-service employé** et les RH ont accès aux mêmes informations via l'espace de travail **Personnes**.

### <a name="notifications-for-changing-leave-balances"></a>Notifications pour modifier les soldes de congés
Les soldes de congés afficheront le solde actuel des employés. Les futurs soldes sont disponibles dans les espaces de travail **Libre-service employé** et **Personnes** en saisissant une « Date à compter de » pour calculer le solde prévu.

La navigation a été ajoutée pour visualiser les soldes prévues dans les zones suivantes :
  - Carte **Congés** sur l'espace de travail **Libre-service employé**.
  - Carte **Congés et absences** sur l'espace de travail **Libre-service Responsable**.
  - Page**Congés et absences** sur l'espace de travail **Personnes**.

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a>Autoriser les décimales pour les régimes de rémunération variable (plans de disponibilités)
Les primes de disponibilités variables et les plans ont désormais la flexibilité supplémentaire pour les montants et les remplacements pour les valeurs avec des montants en décimaux.

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a>Impossibilité de modifier les dates sur les inscriptions à la rémunération variable une fois que le plan est enregistré
Cette modification autorise la mise à jour de la date finale du plan (étendue ou expirée) une fois le plan enregistré. Vous pouvez encore activer ou désactiver les plans indépendamment des dates de début ou de fin.

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a>Les informations relatives aux salaires disponibles lors de l'attribution du rôle de sécurité de l'administrateur des salaires
Le rôle Administrateur des salaires a été mis à jour pour accéder aux informations relatives aux salaires pendant le processus de demande.

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Libre-service employé | Hiérarchie des postes, depuis la vignette échoue à obtenir un nœud parent
Les modifications ont été apportées pour supprimer une erreur qui survenait lors de l'ajout de la hiérarchie des postes à de nouveaux espaces de travail et de l'accès à la structure organisationnelle.

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a>Nouveau message de validation lorsque la souche de nombre personnel est utilisée
Une modification a été apportée pour clarifier le problème lorsque vous engagez un employé et que le numéro du personnel suivant est utilisé.

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a>L'espace de travail Libre-service employé sélectionné comme page de démarrage initial
Lorsque l'espace de travail **Libre-service employé** est sélectionné comme page de démarrage initial pour un utilisateur et qu'un utilisateur n'a pas le rôle d'employé, le système redirigera vers le tableau de bord par défaut.

### <a name="termination-reason-code-updates-position-assignment-record"></a>Le code du motif de résiliation du contrat met à jour l'enregistrement d'attribution de poste
Le code du motif de résiliation mettra désormais à jour l'attribution de poste lors de la résiliation du contrat d'un employé et la fin du poste. 
