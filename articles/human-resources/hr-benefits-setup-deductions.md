---
title: Configurer les déductions
description: Utiliser les déductions dans Microsoft Dynamics 365 Human Resources pour déterminer combien, le cas échéant, déduire du salaire d’un employé pour chaque avantage.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4fac1624ce3a88b9fb4adcf303860e82f9d9165b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055554"
---
# <a name="configure-deductions"></a>Configurer les déductions

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Utiliser les déductions dans Microsoft Dynamics 365 Human Resources pour déterminer combien, le cas échéant, déduire du salaire d’un employé pour chaque avantage. Les déductions sont effectives à une certaine date, vous pouvez donc conserver un historique des informations de déductions. 

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Déductions**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Déduction** | Identifiant unique utilisé pour identifier la déduction des avantages. |
   | **Description** | Description de la déduction. |
   | **Date d’effet** | Date de début. La date par défaut est la date système actuelle. |
   | **Expiration** | Date de fin. La valeur par défaut est 12/31/2154, ce qui signifie jamais. |
   | **En-tête** | Code en-tête du système de paie que cette déduction utilisera pour la partie employé de la déduction lors du traitement des avantages dans la paie. Ceci est utilisé lorsque vous utilisez un fournisseur de paie tiers. |
   | **Référence de déduction des salaires de l’employé** | Le code de déduction du système de paie qu’utilisera cette déduction pour la partie employé de la déduction lors du traitement des avantages dans la paie. |
   | **En-tête du montant** | Code en-tête du système de paie que ce montant de déduction utilisera pour la partie employé de la déduction lors du traitement des avantages dans la paie. Ceci est normalement utilisé lorsque vous utilisez un fournisseur de paie tiers. |
   | **Suppression possible** | Spécifie si une valeur exportée de Dynamics 365 for Finance and Operations peut entraîner la suppression de la valeur dans le système de paie. |
   | **Colonnes associées** | Spécifie s’il faut exporter l’en-tête et le montant des déductions dans les colonnes adjacentes associées vers le système de paie. |
   | **Modifier la date d’effet** | Date à laquelle le changement de déduction des avantages prendra effet. À cette date, le système modifiera automatiquement la déduction de l’avantage et mettra à jour tous les plans d’avantage associés à cette déduction, tant que vous exécutez le traitement de **Mise à jour du changement de déduction**. |
   | **Modification de la déduction terminée** | La case à cocher **Modification de la déduction terminé** sera automatiquement cochée une fois que les modifications de déduction d’avantage auront été effectuées par le traitement de mise à jour de la modification de déduction. |
   
4. Pour effectuer le suivi et conserver les modifications apportées à la configuration du taux des avantages, sélectionnez **Actions**, puis sélectionnez **Tenir les versions à jour**.

5. Sélectionnez **Enregistrer**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]