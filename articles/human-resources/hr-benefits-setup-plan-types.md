---
title: Créer des types de plan
description: Un type de plan dans Microsoft Dynamics 365 Human Resources est un regroupement de haut niveau de types spécifiques d'avantages. Chaque type de plan possède un code de type de plan qui détermine les règles du type de plan.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 06a36f9f3fef54e7e06d616c9179374db4ce7115
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229692"
---
# <a name="create-plan-types"></a>Créer des types de plan

Un type de plan dans Microsoft Dynamics 365 Human Resources est un regroupement de haut niveau de types spécifiques d'avantages. Chaque type de plan possède un code de type de plan qui détermine les règles du type de plan. Par exemple, le type de plan Vie de base aurait le code de type de plan Vie, car il s'agit d'une sorte de plan d'assurance vie et il doit être conforme aux règles établies pour le code de type de plan Vie. Un autre type de plan peut être Vie supplémentaire, également avec le code de type de plan Vie.

Chaque type de plan indique si un employé peut souscrire à un plan de son type ou à plusieurs. Par exemple, un employé serait probablement en mesure de souscrire à la fois à l'assurance vie de base et à l'assurance vie supplémentaire du type de plan Vie. Un employé serait probablement autorisé à souscrire à une seule police de type médical.

Si un type de plan implique des contacts, le type de plan indique si les contacts sont des bénéficiaires ou des personnes à charge. Par exemple, un type de plan d'assurance vie de base aurait des bénéficiaires, tandis qu'un type de plan d'assurance maladie de base aurait des personnes à charge. Dans certains cas, un plan peut ne pas avoir de contacts personnels. Par exemple, un compte de dépenses flexible ou une allocation de stationnement.

Un type de plan peut définir des options de couverture. Les options de couverture sont définies dans le formulaire d'option de couverture. Une option de couverture peut spécifier le montant de l'avantage ou les contacts éligibles pour le type de plan. Par exemple, si le type de contact est Bénéficiaire, l'option de couverture doit définir les modalités de ce que le bénéficiaire est en droit de recevoir lorsque l'avantage est utilisé. Si le type de contact est Personne à charge, l'option de couverture doit définir la relation entre la personne à charge et l'employé. 

1. Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Types de plan**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Type de plan** | Nom unique qui identifie le type de plan. |
   | **Description** | Description du type de plan. |
   | **Code de type de plan** | Sélectionnez un code de type de plan dans la liste déroulante des valeurs. La liste des codes de type de plan affiche tous les types de plan pris en charge dans la version actuelle. |
   | **Inscription simultanée** | Indique si un employé peut souscrire à plusieurs plans d'avantages du même type de plan ou à un seul plan d'avantages par type de plan. |
   | **Type de contact** | Indique le rôle du contact personnel. Les valeurs sont vides, Personne à charge et Bénéficiaire. Vous pouvez laisser le **Type de contact** vide si son type de plan ne nécessite pas de personne à charge ou de bénéficiaire en fonction de l'option de couverture. |

4. Pour configurer les options d'événement de vie, sélectionnez **Actions**, puis sélectionnez **Options d'événement de vie**. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Type de plan** | Type de plan pour lequel configurer les options d'événements de vie. |
   | **ID du type d'événement de vie** | ID du type d'événement de vie. |
   | **Autoriser l'annulation** | Spécifie si un employé peut annuler un plan d'avantages pendant l'événement de vie. |
   | **Modifier l'option de couverture** | Spécifie si un employé peut les options de couverture pendant l'événement de vie. |
   | **Passer à un nouveau plan** | Spécifie si un employé peut les plans pendant l'événement de vie. |
   | **Auto-annuler le plan** | Spécifie s'il faut annuler automatiquement le plan pendant l'événement de vie. |
   | **Réouvrir automatiquement le contrôle d'éligibilité** | Spécifie s'il faut rouvrir automatiquement le contrôle d'éligibilité à l'inscription aux avantages lors de l'événement de vie. |
   | **Fenêtre de déclaration** | Spécifie la fenêtre de déclaration, en jours, de l'événement de vie. **Remarque** : si vous n'entrez pas de montant, le système suppose que la fenêtre de rapport est nulle et ne traitera pas l'événement de vie. |

5. Sélectionnez **Enregistrer**. 
