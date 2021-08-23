---
title: Prêt à payer
description: Cette rubrique explique comment marquer un employé comme étant prêt pour le paiement dans Dynamics 365 Human Resources.
author: marcelbf
ms.date: 07/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 70b3f31db459fe021caf08fe09b2e44a597294d1992ee16a69efd8745941a4bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732415"
---
# <a name="ready-to-pay"></a>Prêt à payer

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

> [!NOTE]
> Si vous souhaitez marquer un employé comme prêt à payer, vous devez d'abord activer la fonctionnalité **(Version préliminaire) Intégration de la paie** dans la gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).

Cette fonctionnalité permet aux professionnels des ressources humaines de comprendre quels employés sont prêts pour le traitement de la paie et lesquels nécessitent une action avant d'être utilisés par un fournisseur de paie tiers.

## <a name="mark-employee-as-ready-to-pay"></a>Marquer un employé comme Prêt pour le paiement

La collecte et la validation des informations sur les employés peuvent prendre beaucoup de temps et être sources d'erreurs. En offrant aux professionnels des ressources humaines un moyen d'examiner et mettre à jour facilement les informations sur les employés, Dynamics 365 Human Resources permet de gagner du temps sur la préparation du traitement de la paie.

Pour marquer un collaborateur comme Prêt pour le paiement :

1. Ouvrez **Gestion des rémunérations**. L'espace de travail comporte deux vignettes 
    - **Employés qui sont prêts à payer**
    - **Employés non prêts pour le paiement**
    ![Espace de travail de gestion des rémunérations.](./media/hr-ready-to-pay-1-workspace.png)

2. Sélectionnez la vignette **non prêts pour le paiement**.

3. Sélectionnez les employés à valider. Sur l'onglet **Paie**, dans le groupe **Prêt pour le paiement**, sélectionnez **Valider**.
    ![Valider les employés.](./media/hr-ready-to-pay-2-validate.png)

4. Pour revoir les résultats, sur l'onglet **Paie**, dans le groupe **Prêt pour le paiement**, sélectionnez **Résultats**.

## <a name="validation"></a>Validation

Avant de marquer un employé comme étant prêt pour le paiement, le système effectuera une validation de base d'après l'exhaustivité du profil.

![Valider les résultats.](./media/hr-ready-to-pay-3-results.png)

Le tableau suivant fournit des informations sur chacune des validations effectuées. 

| Validation | Détails |
| --- | --- |
| Paramètre Objet de l’adresse | Valide si le paramètre **Utiliser les objectifs d'adresse de paie** est activé. |
| Adresse de paie | Valide si le profil du collaborateur comporte au moins une adresse avec l'objectif « Lieu de résidence de la paie » ou « Lieu de travail de la paie », et qu'il n'y a qu'une seule adresse par objectif. |
| Emploi | Vérifiez si le collaborateur a au moins un emploi (actuel, antérieur ou futur). |
| Numéro d’identification | Valide si le paramètre « Utiliser les types d'identification dans le traitement de la paie » est sur Oui, et si le type d'identification indiqué dans le paramètre est renseigné dans le profil du collaborateur. |
| Prénom et nom | Valide si le profil du collaborateur est valide, en vérifiant si les champs **Nom** et **Nom de famille** sont remplis.|
| Position | Vérifiez si le collaborateur a un poste attribué. |
| Date de naissance | Valide si le profil du collaborateur est valide, en vérifiant si le champ **Date de naissance** est rempli. |
| Rémunération | Vérifie si le collaborateur est inscrit à un régime de rémunération fixe. |

Si l'une de ces validations échoue, vous ne pouvez pas marquer l'employé comme étant prêt à payer.

Si le champ **Prêt pour le paiement** est sur **Non**, cela indique que vous devez effectuer une action pour vous assurer que le profil du collaborateur est complet. Cela n'empêchera pas les données d'être exposées dans une entité de données. 

## <a name="known-issues"></a>Problèmes connus

- Vous devez désactiver la fonctionnalité **Entrée d'employé simplifiée** dans la gestion des fonctionnalités. Les vignettes de l'espace de travail de gestion de la rémunération ne fonctionneront pas correctement si vous utilisez cette fonctionnalité.
- Dans le formulaire de collaborateur, l'onglet **Paie**, le groupe **Prêt pour le paiement** est disponible pour n'importe quel rôle d'utilisateur. 

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
