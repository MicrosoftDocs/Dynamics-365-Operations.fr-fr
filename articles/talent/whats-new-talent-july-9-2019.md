---
title: Nouveautés ou modifications dans Dynamics 365 Talent (9 juillet 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/09/2019
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
ms.search.validFrom: 2019-07-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: feb39966d98fa7bde9a6bfad26b07fbd224da59b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528030"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-9-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (9 juillet 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Bientôt dans Attract

#### <a name="job-approvals-appear-on-the-home-page"></a>Les approbations des missions s'affichent dans la page d'accueil

Les approbations apparaissent dans une section **Approbations** du tableau de bord. Les approbateurs peuvent analyser leurs approbations sous **Affecté à vous**, qui affiche l'ID de mission, l'intitulé, les autres approbateurs, et la date à laquelle le poste a été affecté. Les utilisateurs qui soumettent une mission pour approbation peuvent analyser leurs missions sous **Demandé par vous**, qui affiche les approbateurs qui doivent toujours approuver la mission envoyée.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2374.

### <a name="platform-update-28-for-finance-and-operations"></a>Mise à jour de la plateforme 28 pour Finance and Operations

Pour des informations complémentaires sur Platform Update 28 pour Finance and Operations, voir [Fonctionnalités en version préliminaire dans Dynamics 365 Finance and Operations Platform Update 28 (juillet 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-28).

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Prise en charge par les entités des champs personnalisés dans Common Data Service 

Les entités suivantes prennent en charge les champs personnalisés : 

- **Régime fixe de rémunération**
- **Paramétrage des points de référence de rémunération**
- **Ligne de paramétrage des points de référence de rémunération**
- **Code de rémunération de la paie**
- **Période de rémunération**
- **Événement de rémunération fixe**
- **Grille de rémunération**

Pour afficher toutes les entités mises à jour dans Talent :

1. Sélectionnez **Administration du système**, sélectionnez **Liens**, puis sélectionnez **Configuration de Common Data Service**.
2. Sélectionnez le menu déroulant **Nom de l'entité CDS**. Toutes les entités répertoriées sont disponibles sur la dernière version. 

###  <a name="full-name-added-to-worker-entity-in-common-data-service"></a>Nom complet ajouté à l'entité Collaborateur dans Common Data Service

Le champ **Nom complet** a été ajouté à l'entité **Collaborateur**.

### <a name="full-time-equivalent-higher-than-10"></a>Équivalent temps plein supérieur à 1.0

Un avertissement s'affiche maintenant si une valeur supérieure à 1.0 est entrée pour un employé à temps plein pour un poste. 

### <a name="a-warning-no-longer-displays-on-the-worker-page-when-there-is-no-future-dated-employment"></a>Un avertissement ne s'affiche plus sur la page Collaborateur lorsqu'il n'existe aucun emploi portant une date ultérieure

Vous ne recevrez plus de message indiquant qu'un emploi futur existe lorsque vous accédez à la page **Collaborateur** dans la liste **Employés ayant quitté la société** de l'espace de travail **Gestion du personnel**. 

### <a name="unable-to-delete-a-business-process-in-talent"></a>Impossible de supprimer un processus d'entreprise dans Talent

Vous pouvez maintenant supprimer des processus d'entreprise dans l'espace de travail **Processus d'entreprise**.

### <a name="leave-balance-no-longer-displays-zero-for-plans-with-no-accruals-when-using-balance-as-of-accrual-period"></a>Le solde de départ n'affiche plus zéro pour les plans sans régularisations lorsque le solde est utilisé à compter de la période de régularisation

Les plans paramétrés sans régularisations peuvent maintenant afficher un solde.

## <a name="in-preview"></a>En mode aperçu

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Les fonctions d'aperçu sont uniquement activées dans les instances de bac à sable

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est **Production** ou **Bac à sable**. Les instances du type **Bac à sable** permettent de tester les nouvelles fonctions en avant-première. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance **Production**. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance **Bac à sable** (sandbox), contactez le [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) pour initier la demande de modification.

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitation des types d'absence dans les demandes de congés

Les organisations peuvent proposer plusieurs types de congés aux employés. Toutefois, il peut ne pas être pertinent que des employés soumettent leurs demandes de congé pour certains types d'absence. Ces types d'absence peuvent être traités par le service RH. Avec cette version, vous pouvez configurer pour quels types d'absence les employés peuvent envoyer des demandes de congés. 

## <a name="coming-soon-in-core-hr"></a>Prochainement dans Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Afficher les informations étendues des performances dans la gestion en libre service

Une nouvelle option permet aux responsables d'afficher les performances des états directs et de leurs états étendus. Actuellement, les chefs hiérarchiques peuvent affecter et mettre à jour les objectifs de performances et publier de nouvelles révisions, qui sont co-gérées par leurs collaborateurs. En outre, les responsables directs et leurs employés peuvent gérer et tenir à jour les journaux de performances pour garantir que le processus d'examen des performances est fluide. Lorsque cette modification est mise en œuvre, les responsables peuvent afficher et tenir à jour les informations relatives aux performances pour leurs états étendus en plus de leurs états directs. 

### <a name="entities-supporting-custom-fields"></a>Entités prenant en charge les champs personnalisés

Les entités suivantes seront activées pour les champs personnalisés dans Common Data Service : 

- **Type de départ**
- **Compte bancaire du collaborateur**
- **Calendrier de travail**
