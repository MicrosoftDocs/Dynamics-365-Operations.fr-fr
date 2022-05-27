---
title: Traiter l’éligibilité à l’inscription
description: Cette rubrique explique comment exécuter le processus d’éligibilité à l’inscription.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 78a7de6dbb8d8ed13392eb7eb9aa02b15db2e009
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693169"
---
# <a name="process-enrollment-eligibility"></a>Traiter l’éligibilité à l’inscription


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique explique comment exécuter le processus d’éligibilité à l’inscription.

1. Dans l’espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Processus d’éligibilité à l’inscription**.

2. Dans la boîte de dialogue **Exécuter le processus d’éligibilité à l’inscription aux avantages**, spécifiez des valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Période d’inscription** | La période d’inscription pour traiter l’éligibilité. |
   | **Entité juridique** | L’entité juridique pour laquelle traiter l’éligibilité. |
   | **Collaborateur** | Le collaborateur pour lequel traiter l’éligibilité. Si vous laissez ce champ vide, l’éligibilité à l’inscription sera traitée pour tous les collaborateurs. |
   | **Plan d’avantage** | Le régime de prestations pour lequel traiter l’éligibilité.

3. Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus s’exécutera avec les paramètres que vous définissez.

4. Cliquez sur **OK**.

## <a name="view-process-results"></a>Afficher les résultats du processus

Cette rubrique explique comment afficher les résultats du processus d’éligibilité.

1.  Dans l’espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Résultats du processus**.

2.  Dans la page **Résultats du processus**, les champs suivants sont spécifiés :

   | Champ | Description  |
   | --- | --- |
   | **ID processus** | ID unique pour la combinaison de Collaborateur, Entité juridique et exécution de processus. |
   | **Type de processus** | Cela identifie le processus qui a été exécuté. Par exemple : Inscription. |
   | **Horodatage** | Heure à laquelle le processus d’éligibilité a été exécuté. |
   | **Entité juridique** | L’entité juridique spécifiée lors du processus d’inscription. |
   | **Collaborateur** | Collaborateur ayant été traité. |
   | **Plan | Le régime de prestations pour lequel l’inscription a été tentée. |
   | **Règle d’éligibilité** | La règle d’éligibilité qui a été traitée. Si une erreur s’est produite avant l’exécution de l’éligibilité, elle sera vide. Par exemple : si la rémunération n’a pas été définie pour un collaborateur, le processus d’éligibilité ne s’exécutera pas et ce champ sera laissé vide. |
   | **Statut du résultat** | Il s’agit du statut Éligible ou Inéligible. Le statut du résultat est défini sur Ineligible si le collaborateur n’a pas répondu aux critères de règle d’éligibilité, si le collaborateur n’a pas les informations requises comme la fréquence de paiement ou la rémunération fixe, ou si des informations manquent sur le régime de prestations qui empêche l’inscription des collaborateurs. |
   | **Message de résultat** | Indique pourquoi un collaborateur n’est pas admissible à un régime de prestations sociales ou si la règle d’admissibilité a été adoptée. |



[!INCLUDE[footer-include](../includes/footer-banner.md)]
