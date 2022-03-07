---
title: Paramètres d’intégration de la paie
description: Cette rubrique décrit les paramètres d’intégration de la paie de Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-17
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0c489b99d5d05ddac46d222e701512288aeb10583a5e829212e0e1c924622f16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712071"
---
# <a name="payroll-integration-parameters"></a>Paramètres d’intégration de la paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Avant d’utiliser l’intégration de la paie Dynamics 365 Human Resources, vous devez définir les paramètres décrits dans cette rubrique.

## <a name="enable-payroll-address"></a>Activer l’adresse de paie

Pour pouvoir utiliser l’adresse de la paie, vous devez l’activer à partir du [formulaire de paramètres partagés](hr-setup-shared-parameters.md) dans l’onglet Intégration de la paie.

## <a name="define-the-identification-type"></a>Définir le type d’identification

Pour exposer l’ID du type d’identification dans l’[entité d’employé de la paie](hr-admin-integration-payroll-api-payroll-employee.md), vous devez [configurer les paramètres des ressources humaines](hr-setup-shared-parameters.md) pour chaque entreprise.

1. Dans l’espace de travail **Gestion de la rémunération**, sous les liens, sélectionnez **Paramètres de ressources humaines**. 
2. Dans l’onglet **Intégration de la paie**, spécifiez la valeur des champs suivants.

| Champ | Description  |
| --- | --- |
| Utiliser les types d’identification dans le traitement de la paie | Lorsque cette option est sélectionnée, l’ID de type sélectionné sera exposé dans l’entité de l’employé de la paie. |
| Type d’identification | Le type d’identification à exposer dans le champ **mshr_payrollemployeeentityid** de l’[entité d’employé de la paie](hr-admin-integration-payroll-api-payroll-employee.md). |

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
