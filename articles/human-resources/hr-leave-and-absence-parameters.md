---
title: Configuration des paramètres de congé et d'absence
description: Définissez les paramètres des ressources humaines pour les congés et les absences dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008997"
---
# <a name="configure-leave-and-absence-parameters"></a>Configuration des paramètres de congé et d'absence

Avant de configurer des plans de congé et d'absence dans Dynamics 365 Human Resources, il est judicieux de vérifier la configuration de tous les paramètres des ressources humaines associés, notamment :

- Souche de numéros pour les demandes de congé
- Paramètres relatifs au Family Medical and Leave Act (FMLA)
- Paramètres en libre-service des employés pour les demandes de congé et d'absence
- Paramètres de congé et d'absence

## <a name="view-and-change-human-resources-parameters"></a>Afficher et modifier les paramètres des ressources humaines

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres des ressources humaines**.

3. Sur l'onglet **Souches de numéros**, vérifiez le **Code souche de N°** pour **ID de demande de congé** et changez si nécessaire. Ce paramètre détermine la souche utilisée pour attribuer automatiquement les ID aux demandes de congé.

4. Sur l'onglet **FMLA**, vérifiez les paramètres FMLA et modifiez-les si nécessaire.

5. Sur l'onglet **Libre-service employé**, indiquez si les gestionnaires peuvent saisir des demandes de congé et d'absence au nom de leurs employés.

6. Sur l'onglet **Types de congé et d'absence**, vérifiez les paramètres FMLA et modifiez-les si nécessaire.

7. Sélectionnez **Enregistrer**.

## <a name="configure-calendar-parameters"></a>Configurer les paramètres de calendrier

Si vous avez activé la fonction d'aperçu du calendrier des congés et des absences, vous devez configurer des paramètres supplémentaires. 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> Pour la version préliminaire du 3 février 2020, seules les **Demandes de congé en attente** sont activées.

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres des ressources humaines**.

3. Sur l'onglet **Calendrier**, modifiez les paramètres de calendrier si nécessaire.

4. Sélectionnez **Enregistrer**.

## <a name="see-also"></a>Voir également :

- [Vue d'ensemble des congés et des absences](hr-leave-and-absence-overview.md)
