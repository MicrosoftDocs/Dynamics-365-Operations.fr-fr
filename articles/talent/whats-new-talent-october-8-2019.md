---
title: Nouveautés ou modifications dans Dynamics 365 Talent (8 octobre 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/08/2019
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
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 40898ca7f54089337180def964b8942e8653663b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529478"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-8-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (8 octobre 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications qui sont décrites dans cette section s'appliquent au numéro de version 8.1.2542. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="removal-of-benefits-open-enrollment-from-public-preview"></a>Suppression de l'inscription en cours aux avantages de la version préliminaire publique

Conjointement à notre annonce dans la publication de blog [Investissements stratégiques dans Core HR optimisent l'excellence opérationnelle](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence/), Microsoft supprime la fonctionnalité d'inscription en cours aux avantages de la version préliminaire publique le 18 octobre 2019. Au lieu de cela, la nouvelle fonctionnalité est lancée à l'avenir. L'utilisation de production de la fonctionnalité d'inscription en cours aux avantages actuellement en version préliminaire publique ne sera pas prise en charge. 

### <a name="common-data-service-integration-is-now-turned-off-by-default-on-new-provisions-343675"></a>L'intégration de Common Data Service est désactivée par défaut dans les nouvelles provisions (343675)
 
Lorsque de nouveaux environnements sont mis en service, l'intégration de Common Data Service est désormais désactivée. Pour plus d'informations, voir [Configuration de l'intégration de Common Data Service](hr-common-data-service-integration.md).

### <a name="streamlined-employee-entry-and-navigation"></a>Navigation et entrée d'employé simplifiées

La fonctionnalité pour l'entrée et la navigation de l'employé est désormais disponible dans tous les environnements. Pour activer cette fonction, accédez à **Administration du système \> Liens \> Paramétrage \> Paramètres système \> Fonctions d'aperçu**, puis sélectionnez **Formulaire Collaborateur et navigation améliorés**. La fonction est ensuite activée pour tous les utilisateurs. Vous pouvez désactiver cette option à tout moment.

Pour plus d'informations, voir [Navigation et entrée d'employé simplifiées](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/streamlined-employee-data-entry) dans Dynamics 365 : 2e partie du lancement 2019.

### <a name="attract-and-onboard-create-inactive-workers-in-core-hr-380517"></a>Attract et Onboard créent des collaborateurs inactifs dans Core HR (380517)

La version de cette semaine corrige un problème dans lequel Attract et Onboard créent des collaborateurs inactifs dans Core HR.

### <a name="the-workflow-fails-when-the-manager-is-signed-in-to-another-company-while-terminating-an-employee-346852"></a>Le workflow échoue lorsque le responsable est connecté à une autre société tout en mettant un terme au contrat d'un collaborateur (346852)

Le workflow n'échoue plus en fonction de l'entité juridique à laquelle le responsable est connecté.

### <a name="missing-information-on-hcmonboardingworkerchecklisttaskentity-349591"></a>Informations manquantes dans HcmOnboardingWorkerChecklistTaskEntity (349591)

Cette version inclut des informations supplémentaires sur **HcmOnboardingWorkerChecklistTaskEntity**. Voici quelques exemples :

- **Nom du groupe** lorsque le type affecté est **groupe**
- **Nom de l'employé** lorsque le type affecté est **employé**
- **Nom du responsable** lorsque le type affecté est **responsable**

### <a name="entities-arent-listed-in-alphabetical-order-in-common-data-service-administration-377414"></a>Les entités ne sont pas répertoriées par ordre alphabétique dans l'administration de Common Data Service (377414)

Les entités sont désormais répertoriées par ordre alphabétique sur la page **Administration de CDS**.

### <a name="changing-the-employment-type-with-a-future-date-doesnt-allow-a-position-assignment-339958"></a>La modification du type d'emploi avec une date future n'autorise pas une affectation de poste (339958)

Cette modification permet des affectations de poste lorsque les types de collaborateur sont modifiés (par exemple, d'employé à fournisseur).

### <a name="updating-the-common-data-service-leave-bank-transaction-entity-creates-a-new-record-in-talent-352938"></a>La mise à jour de l'entité Transaction bancaire de congé Common Data Service crée un enregistrement dans Talent (352938)

La transaction de congé est désormais mise à jour lors d'une mise à jour est effectuée dans les transactions bancaires de congés Common Data Service.

### <a name="the-title-of-attachments-for-feedback-items-shows-the-feedback-description-343765"></a>Le titre des pièces jointes pour les éléments de rétroaction affiche la description de la rétroaction (343765)

La description de la rétroaction n'apparaît plus dans le titre de la pièce jointe.

### <a name="compensation-workflow-comments-field-shows-incorrect-content-339297"></a>Le champ Commentaires sur le workflow de rémunération affiche un contenu incorrect (339297)

Cette modification affiche le contenu du champ **%HcmActionState.HcmWorkerActionComment.Comments%**.

### <a name="workcalendarentity-and-workcalendardayentity-arent-exposed-through-odata-376329"></a>WorkCalendarEntity et WorkCalendarDayEntity ne sont pas exposés via OData (376329)

Dans cette version, **WorkCalendarEntity** et **WorkCalendarDayEntity** sont désormais disponibles via OData (Open Data Protocol).

### <a name="hcmworkerentity-is-slow-when-odata-is-used-375221"></a>HCMWorkerEntity est lent lorsque OData est utilisé (375221)

Les modifications améliorent les performances de **HCMWorkerEntity** lorsque le concepteur de classeurs Microsoft Excel est utilisé.

### <a name="manager-performance-journal-entry-shows-an-error-after-deleting-a-performance-journal-and-creating-a-new-one-336061"></a>L'entrée du journal des performances du responsable affiche une erreur après avoir supprimé un journal de performances et en avoir créé un (336061)

Cette version corrige un problème qui se produit après qu'un journal des performances est supprimé et qu'un nouveau est créé immédiatement après. Cette correction modifie le comportement du libre service du responsable.

## <a name="coming-soon"></a>Prochainement

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Voir [Imprimer les examens des performances](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) dans Dynamics 365 : 2e partie du lancement 2019.


[!INCLUDE[footer-include](../includes/footer-banner.md)]