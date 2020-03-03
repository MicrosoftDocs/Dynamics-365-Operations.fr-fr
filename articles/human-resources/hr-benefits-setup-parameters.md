---
title: Configuration des paramètres de gestion des avantages
description: Configurez les paramètres de gestion des avantages dans Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: ab9b1fc78ce42479d9265b80337adf899cec3866
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009023"
---
# <a name="set-benefits-management-parameters"></a>Configuration des paramètres de gestion des avantages

[!include [banner](includes/preview-feature.md)]

Avant de pouvoir configurer des plans de congés dans Microsoft Dynamics 365 Human Resources, vous devez configurer les paramètres de gestion des avantages. Ces paramètres définissent les valeurs par défaut, les codes motif et d'autres options.

## <a name="configure-general-parameters"></a>Configuration des paramètres généraux

1. Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres**.

2. Dans l'onglet **Général**, spécifiez les valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Pays/région** | Le champ **Pays/région** détermine l'ordre d'affichage des codes postaux/états. Le pays sélectionné s'affiche en premier dans la liste déroulante. |
   | **Code motif de l'inscription** | Sélectionnez un code motif par défaut à utiliser lors de la création des plans d'employé pendant le traitement de l'inscription ouverte. |
   | **Code motif de l'annulation** | Code motif à utiliser lorsqu'un plan d'avantages des employés est annulé. Il s'affiche dans une boîte de dialogue pendant le processus d'annulation. Les utilisateurs peuvent modifier le **Code du motif de l'annulation** si nécessaire. |
   | **Rouvrir le code motif** | Code motif à utiliser lorsqu'un plan d'avantages des employés est rouvert. Il s'affiche dans une boîte de dialogue pendant le processus d'annulation. Les utilisateurs peuvent modifier le **Rouvrir le code motif** si nécessaire. | 
   | **Code motif de l'événement de vie** | Code motif à utiliser si un événement de vie se produit. |
   | **Modifier le taux du code motif** | Code motif à utiliser lors de l'annulation et de la réouverture d'un plan d'avantages des employés pendant le processus de mise à jour du changement de taux. Il indique quels enregistrements ont été modifiés par le processus de mise à jour du changement de taux. |
   | **Nouvelle embauche admissible** | Spécifie si les nouvelles embauches sont admissibles. |
   | **Période d'inscription du nouvel employé** | Période pendant laquelle la nouvelle inscription est autorisée.</br></br>**Remarque** : ce paramètre remplace toute nouvelle période d'inscription à l'embauche que vous avez définie dans la règle d'admissibilité du plan. | 
   | **Amélioration du salaire annuel** | Spécifie s'il faut calculer automatiquement le montant du **Salaire annuel des avantages** dans **Détails des avantages de l'emploi**. Il est basé sur le **Taux de rémunération fixe**, les **Heures moyennes** et la **Fréquence de paiement**.</br></br>**Heures moyennes** x **Taux de salaire fixe** x **Fréquence de paiement** (nombre de périodes de paie) = **Salaire annuel des avantages** </br></br>Si l'une des valeurs des champs **Heures moyennes**, **Taux de salaire fixe** ou **Fréquence de paiement** changent, le système recalcule automatiquement le montant du **Salaire annuel des avantages** en fonction des valeurs modifiées. Le système crée un enregistrement **Date d'effet** pour identifier la date et l'heure exactes du changement. Vous pouvez modifier manuellement le montant du **Salaire annuel des avantages** si nécessaire. |
   | **Événements de vie activés** | Active les événements de vie. |
   | **Masquer les écrans d'avantages existants** | Vous permet de masquer les anciens écrans d'avantages. |

3. Sélectionnez **Enregistrer**.

## <a name="configure-employee-self-service-parameters"></a>Configurer les paramètres du libre-service employé.

1. Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres**.

2. Dans l'onglet **Libre-service employé**, spécifiez les valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Vérification de l'avantage** | Texte de vérification à utiliser lors du paiement des avantages en libre-service. |
   | **Sélectionner automatiquement les bénéficiaires** | Spécifie s'il faut sélectionner automatiquement les personnes à charge et les bénéficiaires en fonction de leur éligibilité aux options du plan. |

3. Sélectionnez **Enregistrer**.