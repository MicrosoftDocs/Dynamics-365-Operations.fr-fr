---
title: Vue d’ensemble du type de régime
description: Un type de plan dans Microsoft Dynamics 365 Human Resources est un regroupement de haut niveau de types spécifiques d’avantages. Chaque type de plan possède un code de type de plan qui détermine les règles du type de plan.
author: andreabichsel
ms.date: 06/25/2021
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
ms.openlocfilehash: 806b3839feb1e1bf889747986388a56113c3ebe1
ms.sourcegitcommit: 08797bc43e93ea05711c5a70dd7cdb82cada667a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6558271"
---
# <a name="plan-type-overview"></a>Vue d’ensemble du type de régime

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Un type de plan est un regroupement de haut niveau de types spécifiques d’avantages. Chaque type de plan possède un code de type de plan qui détermine les règles du type de plan. Par exemple, le type de régime **Assurance-vie de base** aura le code de type de régime **Vie**, car il s'agit d'un type d'assurance-vie qui doit respecter les règles édictées pour le code de type de régime **Vie**. Un autre type de régime pourrait être **Assurance-vie complémentaire**. Ce type de régime aura également le code de type de régime **Vie**.

Chaque type de plan indique si un employé peut souscrire à un plan de son type ou à plusieurs. Par exemple, un employé serait probablement en mesure de souscrire à la fois à l’assurance vie de base et à l’assurance vie supplémentaire du type de plan Vie. Un employé serait probablement autorisé à souscrire à une seule police de type médical.

Si un type de plan implique des contacts, le type de plan indique si les contacts sont des bénéficiaires ou des personnes à charge. Par exemple, un type de plan d’assurance vie de base aurait des bénéficiaires, tandis qu’un type de plan d’assurance maladie de base aurait des personnes à charge. Dans certains cas, un plan peut ne pas avoir de contacts personnels. Par exemple, un compte de dépenses flexible ou une allocation de stationnement.

Un type de plan peut définir des options de couverture. Les options de couverture sont définies dans le formulaire d’option de couverture. Une option de couverture peut spécifier le montant de l’avantage ou les contacts éligibles pour le type de plan. Par exemple, si le type de contact est Bénéficiaire, l’option de couverture doit définir les modalités de ce que le bénéficiaire est en droit de recevoir lorsque l’avantage est utilisé. Si le type de contact est Personne à charge, l’option de couverture doit définir la relation entre la personne à charge et l’employé. 

> [!IMPORTANT]
> Le formulaire comprend des données clés qui affectent les options disponibles lorsqu'un nouveau régime d'avantages est créé :
>
> - **Code type de régime** : ce champ affecte ce qui est affiché sur l'onglet **Configuration** lors de la configuration de l'avantage réel.  
> - **Inscription simultanée** : ce champ détermine si plusieurs inscriptions sont autorisées. (Pour un plan médical, ce champ est généralement défini sur **Une inscription**.)
> - **Type de contact** : ce champ permet d'ajouter des personnes à charge ou des bénéficiaires à un plan. S'il est défini sur **Aucun**, les employés qui adhèrent aux avantages n'auront pas la possibilité de sélectionner un bénéficiaire ou une personne à charge.
> - **Options de couverture** : utilisez ce champ pour lier des options de couverture aux types de plan. Il définit soit les personnes qui seront couvertes par ce type de régime, soit les montants de couverture disponibles pour ce type de régime. Par exemple, vous pouvez spécifier que la couverture d'un type de régime médical sera disponible uniquement pour l'employé, l'employé et une autre personne, ou l'employé et sa famille.

## <a name="create-plan-types"></a>Créer des types de plan

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Types de plan**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Type de plan** | Nom unique qui identifie le type de plan. |
   | **Description** | Description du type de plan. |
   | **Code de type de plan** | Sélectionnez un code de type de plan dans la liste déroulante des valeurs. La liste des codes de type de plan affiche tous les types de plan pris en charge dans la version actuelle. |
   | **Inscription simultanée** | Indique si un employé peut souscrire à plusieurs régimes de prestations du même type de régime ou à un seul régime de prestations par type de régime. |
   | **Type de contact** | Indique le rôle du contact personnel. Les valeurs sont vides, Personne à charge et Bénéficiaire. Vous pouvez laisser le **Type de contact** vide si son type de plan ne nécessite pas de personne à charge ou de bénéficiaire en fonction de l’option de couverture. |

4. Pour configurer les options d’événement de vie, sélectionnez **Actions**, puis sélectionnez **Options d’événement de vie**. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Type de plan** | Type de plan pour lequel configurer les options d’événements de vie. |
   | **ID du type d’événement de vie** | ID du type d’événement de vie. |
   | **Autoriser l’annulation** | Spécifie si un employé peut annuler un plan d’avantages pendant l’événement de vie. |
   | **Modifier l’option de couverture** | Spécifie si un employé peut les options de couverture pendant l’événement de vie. |
   | **Passer à un nouveau plan** | Spécifie si un employé peut les plans pendant l’événement de vie. |
   | **Auto-annuler le plan** | Spécifie s’il faut annuler automatiquement le plan pendant l’événement de vie. |
   | **Réouvrir automatiquement le contrôle d’éligibilité** | Spécifie s’il faut rouvrir automatiquement le contrôle d’éligibilité à l’inscription aux avantages lors de l’événement de vie. |
   | **Fenêtre de déclaration** | Spécifie la fenêtre de déclaration, en jours, de l’événement de vie. **Remarque** : si vous n’entrez pas de montant, le système suppose que la fenêtre de rapport est nulle et ne traitera pas l’événement de vie. |

5. Sélectionnez **Enregistrer**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
