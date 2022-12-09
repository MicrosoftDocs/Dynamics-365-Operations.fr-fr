---
title: Interrompre un congé
description: Vous pouvez interrompre le congé d’un employé dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SuspendLeave, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9c8262fb34175f6f9326d6be82c922b2170fc5a7
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805258"
---
# <a name="suspend-leave"></a>Suspendre les congés

>[!Important]
>La fonctionnalité indiquée dans cet article est actuellement disponible pour les clients sur Dynamics 365 Human Resources autonome. Certaines ou toutes les fonctionnalités seront disponibles dans le cadre d’une future version de l’infrastructure Finance après la version 10.0.26 de Finance.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez interrompre le congé d’un employé pour arrêter le traitement des régularisations de congés pour les types de congés sélectionnés.

## <a name="suspend-leave-and-absence-for-an-employee"></a>Suspendre les congés et les absences pour un employé

1. Dans le dossier de l’employé, sélectionnez **Congé**.

2. Sélectionnez **Suspendre les congés**.

3. Sélectionnez **Nouveau**.

4. Dans la boîte de dialogue **Suspendre la régularisation des congés**, sélectionnez **Type de congé** avec les champs **Date de début** et **Date de fin** définis pour la suspension.

5. Vous pouvez éventuellement ajouter un **Commentaire** pour la suspension. 

Si les régularisations sont traitées alors que le congé de l’employé est suspendu, aucune régularisation ne sera effectuée pour le congé de type suspendu.

> [!NOTE]
> Les demandes de congé interrompent les demandes d’absence, mais les demandes d’absence ne suspendent pas les demandes de congé.

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)
- [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md)
- [Provisionner les plans de congé et d’absence](hr-leave-and-absence-accrue.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
