---
title: Nouveautés et modifications dans Dynamics 365 Talent (23 avril 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/23/2019
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
ms.search.validFrom: 2019-04-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: cbafea9063844dd3f19e5828ab37632e04591f18
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897890"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-23-2019"></a>Nouveautés et modifications dans Dynamics 365 Talent (23 avril 2019)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2253. Les numéros entre parenthèses se rapportent aux numéros de support dans Lifecycle Services (LCS).

### <a name="common-data-service-entity-support-for-custom-fields"></a>Prise en charge de l'entité Common Data Service pour les champs personnalisés
Avec la version de cette semaine, les entités suivantes prennent en charge les champs personnalisés : Niveau de rémunération, Option d'avantage, Type de compétence et Région de rémunération.

### <a name="additional-odata-entities-302992"></a>Entités OData supplémentaires (302992)
Les entités suivantes sont désormais prises en charge dans OData : Expérience professionnelle du collaborateur et formation du collaborateur.
   
### <a name="performance-journal-attachments-for-managers-and-employees-308248"></a>Pièces jointes du journal de performances des gestionnaires et des employés (308248)
Avec cette version, les pièces jointes sont désormais disponibles pour les responsables et les employés lors de la création et la mise à jour des entrées du journal des performances.

### <a name="employee-rehire-flag-always-available-310047"></a>Indicateur de réembauche de l'employé toujours disponible (310047)
L'option de réembauche d'employé est désormais disponible pour la mise à jour en dehors du processus de fin de contrat. 

### <a name="cannot-change-the-name-of-my-payment-method-308815"></a>Impossible de modifier le nom **Mon mode de paiement** (308815)
La personnalisation a été activée pour autoriser l'étiquette **Mon mode de paiement** à être modifié dans le libre service de l'employé.

### <a name="financial-dimensions-against-a-position-cant-be-deleted-293908"></a>Impossible de supprimer des dimensions financières par rapport à un poste (293908)
Les dimensions financières peuvent désormais être supprimées lors d'une demande de modification pour un poste existant et les dimensions financières dans les limites de société croisée. 

### <a name="customer-is-unable-to-publish-back-data-into-talent-when-opening-the-data-from-excel-302955"></a>Le client ne peut pas republier des données dans Talent lors de l'ouverture des données dans Excel (302955)
Cette modification corrige un problème de publication lors de l'utilisation de tableaux associés.

## <a name="in-preview"></a>En mode aperçu

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Autoriser les codes motif à être spécifiés sur les types de départ
Les organisations peuvent avoir besoin d'informations supplémentaire sur les demandes de congé. Vous pouvez désormais spécifier les codes motif des types de départ et permettre aux employés de sélectionner un code motif pour leurs demandes de congé.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Codes motif requis pour certains types d'absence dans les demandes de congés
Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient une demande de congé. Cela peut découler d'une stratégie de la société ou d'exigences réglementaires. Vous pouvez désormais spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Fournir une liste de transactions de départ et d'absence pour les RH
Le suivi des congés des employés et la compréhension du calcul des congés aide non seulement les RH à répondre aux questions des employés, mais assure aussi l'attribution exacte des durées de congé aux employés. Les RH disposent désormais d'une nouvelle vision des transactions (dotations, cumuls, ajustements et demandes) pour voir les causes des soldes.

## <a name="coming-soon"></a>Prochainement

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Améliorations apportées à l'interface utilisateur pour la vérification des doublons d'employé
Avec cette modification, les doublons sont détectés au moment de renseigner les champs de nom. Un champ de statut affiche le nombre de doublons trouvés. Vous pouvez sélectionner le lien fourni pour ouvrir une nouvelle page pour évaluer s'il convient d'utiliser la correspondance détectée. Pour éviter d'interrompre la saisie des données, l'écran des doublons ne s'ouvre pas automatiquement.
## <a name="known-issues"></a>Problèmes connus

### <a name="email-support-for-alerts"></a>Prise en charge des alertes par e-mail
Dans Platform Update 26 pour Finance and Operations, les utilisateurs peuvent créer des règles d'alerte qui envoient automatiquement des notifications par e-mail aux contacts lorsque des notifications sont déclenchées par un événement.
