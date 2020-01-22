---
title: Nouveautés ou modifications dans Dynamics 365 Talent (16 juillet 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/16/2019
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
ms.search.validFrom: 2019-07-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6dce39bc529bf6dd6079ed900af12510c0773f9a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899080"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-16-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (16 juillet 2019)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Bientôt dans Attract
#### <a name="job-approvals-appear-on-the-home-page"></a>Les approbations des missions s'affichent dans la page d'accueil

Les approbations apparaissent dans une section **Approbations** du tableau de bord. Les approbateurs peuvent analyser leurs approbations sous **Affecté à vous**, qui affiche l'ID de mission, l'intitulé, les autres approbateurs, et la date à laquelle le poste a été affecté. Les utilisateurs qui soumettent une mission pour approbation peuvent analyser leurs missions sous **Demandé par vous**, qui affiche les approbateurs qui doivent toujours approuver la mission envoyée.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2390.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Entités Common Data Service prenant maintenant en charge les champs personnalisés

- BusinessProcessCalendar                     
- BusinessProcessGroupAssignment         
- BusinessProcessStage                          
- BusinessProcessTemplateHeader          
- BusinessProcessTemplateTask            
- HcmBenefitOption                              
- HcmBenefitType                                  
- HcmCompensationGrid                            
- HcmCompensationLevel                          
- HcmCompensationPayFrequency                 
- HcmCompensationReferencePointSetup        
- HcmCompensationReferencePointSetupLine 
- HcmCompensationRegion                     
- HcmCompFixedPlanTable                     
- HcmEmployment                                
- HcmEthnicOrigin                                
- HcmFixedCompensationEvent                 
- HcmJob                                           
- HcmJobFunction
- HcmJobType
- HcmLanguageCode
- HcmPayrollCalculationFrequency
- HcmPosition
- HcmPositionType
- HcmSkillType
- HcmVeteranStatus
- HcmWorkCalendarHoliday
- HcmWorkCalendarHolidayLine
- HcmWorker
- HcmWorkerPersonalDetail
- LeaveType
- OMDepartment
- OMLegalEntity
- PayCycle
- PayPeriod
- PayrollBenefitCalculationRate
- PayrollBenefitCalculationRateDetail
- PayrollEarningCode

### <a name="unable-to-see-goals-and-reviews-in-manager-self-service"></a>Impossible d'afficher les objectifs et les révisions dans la gestion en libre-service

Les modifications de cette semaine permettent maintenant d'afficher et de modifier les objectifs et les révisions des responsables hiérarchiques dans la gestion en libre-service.

### <a name="goal-form-cannot-be-closed-after-a-user-edits-any-goal-field"></a>Le formulaire Objectif ne peut pas être fermé après modification d'un champ d'objectif par un utilisateur

Cette version corrige le problème où le formulaire Objectif ne se ferme pas lorsque vous sélectionnez **Fermer**.

### <a name="creating-new-goals-and-saving-displays-error"></a>Une erreur s'affiche lors de la création de nouveaux objectifs et de l'enregistrement

Cette version corrige un problème lors de l'enregistrement des objectifs dans la page en libre-service pour les employés et les responsables.

### <a name="unable-to-add-a-field-to-position-details"></a>Impossible d'ajouter un champ aux détails du poste 

Avec cette version, les champs personnalisés sont maintenant pris en charge dans les détails du poste.
 
### <a name="unable-to-set-up-expiring-date-on-the-earning-code-through-data-management"></a>Impossible de définir la date d'expiration du code de rémunération par le biais de la gestion des données

Les modifications vous permettent maintenant de définir les dates d'expiration des codes de rémunération dans la gestion des données.

### <a name="new-custom-fields-dont-sync-quickly-enough"></a>Les nouveaux champs personnalisés ne sont pas synchronisés assez rapidement

Les performances de synchronisation des champs personnalisés avec Common Data Service ont été améliorés avec la version de cette semaine.

### <a name="entity-export-to-database-jobs-fail-with-error-message-format-of-the-initialization-string-does-not-conform-to-specification-starting-at-index-0"></a>Les tâches d'exportation de l'entité vers la base de données échouent avec le message d'erreur suivant : « Le format de la chaîne d'initialisation n'est pas conforme à la spécification commençant à l'index 0 ».

Cette version corrige le problème où les traitements par lots de la base de données échouent. Pour effectuer une mise à jour manuelle :

1. Accédez à **Gestion des données**.
2. Sélectionnez **Configurer l'exportation de l'entité vers la base de données**.
3. Entrez à nouveau la chaîne de connexion à la base de données cible et sélectionnez **Enregistrer**.

### <a name="smtp-email-configuration-suddenly-fails-with-error-message-the-smtp-server-requires-a-secure-connection-or-the-client-was-not-authenticated"></a>La configuration de la messagerie SMTP échoue brusquement avec le message d'erreur : « Le serveur SMTP nécessite une connexion sécurisée ou le client n'a pas été authentifié ».

Cette version corrige une configuration de messagerie SMTP qui échoue brusquement. Pour effectuer une mise à jour manuelle :

1. Accédez à **Administration du système**.
2. Sélectionnez **Paramètres de messagerie**.
3. Sélectionnez **Paramètres SMTP**. 
4. Entrez à nouveau le nom d'utilisateur et le mot de passe utilisés pour le serveur SMTP et sélectionnez **Enregistrer**.

## <a name="in-preview"></a>En mode aperçu

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Les fonctions d'aperçu sont uniquement activées dans les instances de bac à sable

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est **Production** ou **Bac à sable**. Les instances du type **Bac à sable** permettent de tester les nouvelles fonctions en avant-première. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance **Production**. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance **Bac à sable** (sandbox), contactez le [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) pour initier la demande de modification.

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitation des types d'absence dans les demandes de congés

Les organisations peuvent proposer plusieurs types de congés aux employés. Toutefois, il peut ne pas être pertinent que des employés soumettent leurs demandes de congé pour certains types d'absence. Ces types d'absence peuvent être traités par le service RH. Avec cette version, vous pouvez configurer pour quels types d'absence les employés peuvent envoyer des demandes de congés. 

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Afficher les informations de performances pour les états directs et étendus dans la gestion en libre service

Une nouvelle option permet aux responsables d'afficher les performances des états directs et de leurs états étendus. Actuellement, les chefs hiérarchiques peuvent affecter et mettre à jour les objectifs de performances et publier de nouvelles révisions. En outre, les responsables directs et leurs employés peuvent gérer et tenir à jour les journaux de performances pour garantir que le processus d'examen des performances est fluide. Lorsque cette modification est mise en œuvre, les responsables peuvent afficher et tenir à jour les informations relatives aux performances pour leurs états étendus en plus de leurs états directs.
