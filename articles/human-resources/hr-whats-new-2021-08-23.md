---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources - 23 août 2021
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 23 août 2021.
author: marcelbf
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-08-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 21c3448c373600ffebca82be41fb5849b952dfe1
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686825"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-23-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources - 23 août 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Microsoft Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4419.

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui auront été intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Problème | Description |
| --- | --- | --- |
| 594066 | Impossible de supprimer les informations de contact | Lorsque vous choisissez de supprimer un enregistrement d'informations de contact pour un employé, un enregistrement d'informations de contact autre que l'enregistrement sélectionné est supprimé à la place. |
| 611339 | L'ajout d'une personnalisation fait que le compte bancaire ignore le filtre et récupère le premier enregistrement | L'ajout d'une personnalisation entraîne l'exécution d'une requête de personnalisation par la liste des comptes bancaires après l'exécution de la requête de source de données ; cela entraîne la récupération du premier enregistrement, quel que soit le collaborateur pour lequel les détails sont affichés. |
| 591806 | Les tâches de date d'échéance d'intégration sont mal calculées | Les dates d'échéance sont calculées de manière incorrecte lorsque les conditions suivantes existent : les listes de contrôle qui sont créées utilisent un calendrier qui utilise une plage de temps étendue (par exemple de 2005 à 2050) et les préférences de l'utilisateur utilisent un fuseau horaire autre que CST (UTC-6). |   
| 592749 | Le solde des congés est incorrect dans le **Libre service des employés** | Si l'employé a un emploi dans plusieurs entités juridiques et que la vue des congés intersociétés est activée, le solde des congés peut être incorrect. |
| 603133 | Avertissement inattendu lors d'une demande de congé | Lors de la demande de congé, le fait de renseigner le champ **Demi-journée** avant le champ **Quantité** provoque un avertissement inattendu. |
| 606546 | Champ de sélection non visible dans Congés approuvés | La case à cocher permettant de sélectionner plusieurs demandes de congé approuvées n'était pas visible. |
| 597059 | Collaborateur non visible dans le **Calendrier des congés et absences de l'entreprise** | Un collaborateur n'est pas visible dans le **Calendrier des congés et absences de l'entreprise** si la plage de dates appliquée comprend un jour pour lequel une demande de congé lui a été refusée. |


## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation et la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Activer l’intégration simplifiée de la paie (API d’intégration de la paie) | [Activer l’intégration simplifiée avec des prestataires de paie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)|
| Activer un gestionnaire des absences pour gérer les congés | [Activer un gestionnaire des absences pour gérer les congés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Dans cette version, nous mettons à jour la vue de l’espace de travail du gestionnaire des absences. Pour plus d’informations, voir [Configurer le rôle de gestionnaire des absences](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Configurer l’exigence de pièce jointe par type de congé | [Configurer l’exigence de pièce jointe par type de congé](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurer les types de congé et d’absence](https://go.microsoft.com/fwlink/?linkid=2168108)|
| Configurer les unités de congé par type de congé | [Configurer les unités de congé par type de congé](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurer les types de congé et d’absence](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Permettre aux employés d’être marqués comme prêts à être payés | [Permettre aux employés d’être marqués comme prêts à être payés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Prêt à payer](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Bientôt disponible

Pour une liste complète des fonctionnalités planifiées et de leurs lancements planifiés, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Fonctionnalité | Détails |
| --- | --- |
| Platform update 10.0.21 (45) | Le déploiement de la mise à jour de la plateforme 10.0.21 devrait commencer avec la version du service le 4 octobre 2021. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.21 (octobre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2021 vague de publication 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
