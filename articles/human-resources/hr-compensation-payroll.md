---
title: Prêt à payer
description: Cette rubrique explique comment marquer un employé comme étant prêt pour le paiement dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a5a6fc613065dbba2d70a4b73974337b87782aae
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2022
ms.locfileid: "8533738"
---
# <a name="ready-to-pay"></a>Prêt à payer


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!NOTE]
> Si vous souhaitez marquer un employé comme prêt à payer, vous devez d’abord activer la fonctionnalité **(Version préliminaire) Intégration de la paie** dans la gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).

Cette fonctionnalité permet aux professionnels des ressources humaines de comprendre quels employés sont prêts pour le traitement de la paie et lesquels nécessitent une action avant d’être utilisés par un fournisseur de paie tiers.

## <a name="mark-employee-as-ready-to-pay"></a>Marquer un employé comme Prêt pour le paiement

La collecte et la validation des informations sur les employés peuvent prendre beaucoup de temps et être sources d’erreurs. En offrant aux professionnels des ressources humaines un moyen d’examiner et mettre à jour facilement les informations sur les employés, Dynamics 365 Human Resources permet de gagner du temps sur la préparation du traitement de la paie.

Pour marquer un collaborateur comme Prêt pour le paiement :

1. Ouvrez **Gestion des rémunérations**. L’espace de travail comporte deux vignettes : 
    - **Employés qui sont prêts à payer**
    - **Employés non prêts pour le paiement**
    ![Espace de travail de gestion des rémunérations.](./media/hr-ready-to-pay-1-workspace.png)

2. Sélectionnez la vignette **non prêts pour le paiement**.

3. Sélectionnez les employés à valider. Sur l’onglet **Paie**, dans le groupe **Prêt pour le paiement**, sélectionnez **Valider**.
    ![Valider les employés.](./media/hr-ready-to-pay-2-validate.png)

4. Pour revoir les résultats, sur l’onglet **Paie**, dans le groupe **Prêt pour le paiement**, sélectionnez **Résultats**.

## <a name="validation"></a>Validation

Avant de marquer un collaborateur comme étant prêt pour le paiement, son profil est validé par souci d’exhaustivité.

![Valider les résultats.](./media/hr-ready-to-pay-3-results.png)

| Validation | Détails |
| --- | --- |
| **Paramètre Objet de l’adresse** | Confirme que le paramètre **Utiliser les objectifs d’adresse de paie** est sélectionné. |
| **Adresse de paie** | Confirme que le profil du collaborateur comporte au moins une adresse avec l’objectif **Lieu de résidence de la paie** ou **Lieu de travail de la paie**, et qu’il n’y a qu’une seule adresse par objectif. |
| **Emploi** | Confirme que le collaborateur a au moins un emploi (actuel, antérieur ou futur). |
| **Numéro d’identification** | Confirme que le champ **Utiliser les types d’identification dans le traitement de la paie** est sur **Oui** sur la page **Paramètres des Ressources humaines**, et si le type d’identification indiqué dans le paramètre est renseigné dans le profil du collaborateur. |
| **Prénom et nom** | Confirme que les champs **Prénom** et **Nom de famille** sont remplis.|
| **Position** | Confirme que le collaborateur a un poste attribué. |
| **Date de naissance** | Confirme que le champ **Date de naissance** est rempli. |
| **Rémunération** | Confirme que le collaborateur est inscrit à un régime de rémunération fixe. |

Si l’une de ces validations échoue, vous ne pouvez pas marquer l’employé comme étant prêt à payer.

Si le champ **Prêt pour le paiement** est sur **Non**, cela indique que vous devez effectuer une action pour vous assurer que le profil du collaborateur est complet. Cela n’empêchera pas les données d’être exposées dans une entité de données. 

## <a name="process-automation"></a>Automatisation des processus

Vous pouvez automatiser la validation de tous les employés en utilisant [Automatisation des processus](/dynamics365/fin-ops-core/dev-itpro/sysadmin/process-automation). Dans l’espace de travail **Gestion de la rémunération**, accédez à **Liens** \> **Paramètres** \> **Automatisations de processus**.

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
