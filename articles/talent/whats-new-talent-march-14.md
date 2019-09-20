---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (14 mars 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/14/2019
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
ms.search.validFrom: 2019-03-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ee8e076174acba8e706991f3086d6299a10945ec
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742491"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-14-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent (14 mars 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités inédites ou ayant fait l'objet de modifications dans Talent.

## <a name="changes-in-attract"></a>Modifications apportées à Attract
Cette version comporte des correctifs de bogues mineurs.

## <a name="changes-in-onboarding"></a>Modifications apportées à Onboard
Cette version comporte des correctifs de bogues mineurs.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
**Version 8.1.2186**

### <a name="performance-management-not-working-in-all-scenarios-when-using-duplicate-security-roles"></a>La gestion des performances ne fonctionne pas dans tous les scénarios si vous utilisez des rôles de sécurité en double
Les modifications effectuées dans cette version rendent possibles des scénarios de gestion des performances lors de l'utilisation de rôle prêts à l'emploi ou en double.

### <a name="mass-assign-checklists-to-workers"></a>Affectation en masse de listes de contrôle aux employés
Avec cette modification, vous pouvez désormais sélectionner plusieurs employés et leur affecter en bloc une ou plusieurs listes de contrôle. 

### <a name="platform-update-24"></a>Update 24 de la plateforme
Pour en savoir plus sur Platform Update 24, voir [Nouveautés ou modifications dans Finance and Operations, Platform Update 24 (mars 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24). Les modifications importantes de Platform Update 24 sont notamment : 

- Les alertes sont activées dans Talent.
- La barre de navigation mise à jour s'aligne à présent avec l'en-tête Bureau.

### <a name="office-location-update-switches-the-context-to-the-top-of-the-worker-list"></a>La mise à jour de l'emplacement du bureau fait basculer le contexte en haut de la liste des employés
Avec cette nouvelle version, le changement d'emplacement du bureau ne fait plus basculer le contexte de l'employé que vous affichez lorsque vous affectez un bureau.

### <a name="position-assignment-end-date-doesnt-display-correctly-on-worker-hire-and-transfer-actions"></a>La date de fin de l'affectation du poste ne s'affiche pas correctement dans les actions d'embauche et de transfert d'employé
Les dates de fin d'affectation de poste s'affichent maintenant correctement selon le fuseau horaire préféré de l'utilisateur lors de l'utilisation des actions.

### <a name="common-data-service-job-entity-doesnt-allow-job-type-and-job-function-fields-to-update"></a>L'entité de tâche Common Data Service n'autorise pas la mise à jour des champs Type de poste et Fonction du poste
Les entités Common Data Service se synchronisent désormais correctement une fois mises à jour à l'aide de Common Data Service.

## <a name="coming-soon"></a>Prochainement

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Sécurité avancée de la rémunération (fixe et variable)
Nombreuses sont les organisations où les responsables des avantages et de la rémunération ne peuvent accéder qu'à certains enregistrements de rémunération. Ces enregistrements peuvent concerner des cadres ou des employés régionaux. Cette modification permet aux RH de gérer et de tenir à jour les plans de rémunération pour différents groupes d'employés au sein de l'organisation. Vous pouvez affecter des rôles de sécurité aux plans fixes et variables. Ces rôles déterminent l'accès aux plans et aux données des employés relatives aux plans, comme les enregistrements propres aux salaires ou aux primes. Seuls les rôles disposant de l'accès peuvent traiter la rémunération de ces employés.

###  <a name="email-support-for-alerts"></a>Prise en charge des alertes par e-mail
Avec Platform Update 24, les utilisateurs peuvent créer des règles d'alerte qui envoient automatiquement des notifications par e-mail aux contacts lorsque les alertes sont déclenchées par un événement.

### <a name="duplicate-employee-check-interface-changes"></a>Vérification d'employé en double : modifications de l'interface
Avec cette modification, les doublons sont détectés au moment de renseigner les champs de nom et un champ de statut affiche le nombre trouvé. Vous pouvez sélectionner le lien fourni pour ouvrir une nouvelle page pour évaluer s'il convient d'utiliser la correspondance détectée. L'écran des doublons ne s'ouvre pas automatiquement pour éviter d'interrompre la saisie des données.
