---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (14 février 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5f96dd60652705de820e0661d417dcaee8143561
ms.sourcegitcommit: 5384200c3e33510c5b3ac31f2b22443e1076251f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2019
ms.locfileid: "390660"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-14-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent (14 février 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités inédites ou ayant fait l'objet de modifications dans Talent.

## <a name="changes-in-attract"></a>Modifications apportées à Attract
Cette version comporte des correctifs de bogues mineurs.

## <a name="changes-in-onboarding"></a>Modifications apportées à Onboard
Cette version comporte des correctifs de bogues mineurs.
 
## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR 
**Version 8.1.2146**

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a>L'entité de rémunération fixe des employés n'exporte pas tous les enregistrements.
Avec cette modification, l'entité **Rémunération fixe des employés** exporte désormais tous les enregistrements. L'entité peut être utilisée pour créer et mettre à jour les enregistrements de rémunération fixe pour les employés. 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a>La date de fin de contrat ne respecte pas les paramètres de fuseau horaire préférés de l'employé.
Les dates de fin de contrat respectent maintenant le fuseau horaire préféré de l'utilisateur au début ou à la fin d'un emploi au sein d'une société.
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a>Les adresses britanniques s'affichent dans les analyses comme des adresses de Suisse orientale.
Dans cette version, une modification a été apportée pour corriger le défaut d'adéquation des adresses dans l'état « Comptage des effectifs par site » de la **Gestion du personnel**.
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a>Le code de fin n'est pas renseigné sur l'enregistrement de l'affectation du poste de l'employé à la fin du contrat.
Une modification a été apportée pour définir par défaut le code « Motif de fin de contrat » à la fin de l'affectation du poste des employés.

### <a name="new-entity-created-for-job-compensation-levels"></a>Nouvelle entité créée pour les niveaux de rémunération des postes
Une nouvelle entité de l'infrastructure de gestion des données a été créée. L'entité propose la création et les mises à jour des niveaux de rémunération, des valeurs marchandes et des informations d'enquête pour chaque tâche définie dans le système.
