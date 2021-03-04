---
title: Nouveautés et modifications dans Dynamics 365 Talent (2 avril 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/02/2019
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
ms.search.validFrom: 2019-04-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 04b5a006d4580fe419d81986a90851bc8d611722
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528217"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-2-2019"></a>Nouveautés et modifications dans Dynamics 365 Talent (2 avril 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="approval-emails-in-attract"></a>E-mails d'approbation dans Attract
Les nouveaux e-mail d'approbation améliorent la visibilité dans le processus d'approbation. Les e-mail sont envoyés aux approbateurs lorsqu'un des scénarios suivants se produit :

- Un demandeur envoie une offre d'emploi pour approbation.
- Une offre d'emploi est rejetée ou approuvée.
- Un approbateur n'a pas agi sur une demande d'approbation dans les 24 heures.

Vous pouvez personnaliser le contenu des e-mails d'approbation avec de nouveaux modèles.

### <a name="application-and-profile-attachments"></a>Pièces jointe de candidature et de profil
Des améliorations apportées à l'onglet **Documents** dans les profils des candidatures et des viviers de talents affichent maintenant le nom et le type de document.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="coming-soon-attract-and-onboard"></a>Prochainement (Attract et Onboard)

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Intégration de LCS (Lifecycle Services) avec « signaler un problème »
Dans Attract et Onboard, les problèmes consignés par les utilisateurs à l'aide de la fonctionnalité Signaler un problème créent désormais automatiquement des sujets de support dans le projet LCS du client. Les administrateurs peuvent maintenant trier les problèmes et les soumettre à Microsoft si nécessaire. C'est cohérent avec la manière dont Core HR traite les problèmes de support utilisateur.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2216.

### <a name="platform-update-25-for-finance-and-operations"></a>Mise à jour de la plateforme 25 pour Finance and Operations
Pour plus d'informations sur Platform Update 25 pour Finance and Operations, voir [Fonctionnalités d'évaluation dans Dynamics 365 for Finance and Operations Platform Update 25 (avril 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-25).

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Sécurité avancée de la rémunération (fixe et variable)
Nombreuses sont les organisations où les responsables des avantages et de la rémunération ne peuvent accéder qu'à certains enregistrements de rémunération. Il peut s'agir d'enregistrements concernant des cadres ou des employés régionaux. Cette modification permet aux RH de gérer et de tenir à jour les plans de rémunération pour différents groupes d'employés au sein de l'organisation. Vous pouvez affecter des rôles de sécurité aux régimes fixes et variables. Ces rôles de sécurité déterminent l'accès aux plans et aux données d'employé associées, telles que les enregistrements de salaire ou de prime, de sorte que seuls ces rôles peuvent traiter la rémunération des groupes d'employés.

### <a name="upgrade-to-common-data-service"></a>Mise à niveau vers Common Data Service
Les dates butoirs pour la mise à niveau vers Common Data Service arrivent à grands pas. Connectez-vous au centre d'administration de Microsoft Power Apps pour définir si votre base de données doit être mise à niveau. Pour en savoir plus sur les dates butoirs et les étapes indispensables pour la mise à niveau, voir [Mise à niveau vers Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>En mode aperçu

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Autoriser les codes motif à être spécifiés sur les types de départ
Les organisations peuvent avoir besoin d'informations supplémentaire sur les demandes de congé. Vous pouvez désormais spécifier les codes motif des types de départ et permettre aux employés de sélectionner un code motif pour leurs demandes de congé.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Codes motif requis pour certains types d'absence dans les demandes de congés
Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient une demande de congé. Cela peut découler d'une stratégie de la société ou d'exigences réglementaires. Vous pouvez désormais spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.

## <a name="coming-soon"></a>Prochainement

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Améliorations apportées à l'interface utilisateur pour la vérification des doublons d'employé
Avec cette modification, les doublons sont détectés au moment de renseigner les champs de nom. Un champ de statut affiche le nombre de doublons trouvés. Vous pouvez sélectionner le lien fourni pour ouvrir une nouvelle page pour évaluer s'il convient d'utiliser la correspondance détectée. Pour éviter d'interrompre la saisie des données, l'écran des doublons ne s'ouvre pas automatiquement.

###  <a name="email-support-for-alerts"></a>Prise en charge des alertes par e-mail
Avec Platform Update 25 pour Finance and Operations, les utilisateurs peuvent créer des règles d'alerte qui envoient automatiquement des notifications par e-mail aux contacts lorsque les alertes sont déclenchées par un événement. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]