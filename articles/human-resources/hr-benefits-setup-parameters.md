---
title: Définir les paramètres de gestion des avantages et de libre service des employés pour toutes les entreprises
description: Configurer les paramètres de gestion des avantages et de libre service des employés dans Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b50c4f71789c34f08ce810312f3c3198303b031e
ms.sourcegitcommit: d02fae79d5c02a4bc4f4b16a410c2f5ce026c204
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "4962438"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a>Définir les paramètres de gestion des avantages et de libre service des employés pour toutes les entreprises

Avant de pouvoir configurer des plans d'avantages dans Microsoft Dynamics 365 Human Resources, vous devez configurer les paramètres de gestion des avantages. Ces paramètres définissent les valeurs par défaut, les codes motif et d'autres options. 

## <a name="configure-general-parameters"></a>Configuration des paramètres généraux

1. Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres partagés Human Resources**.

2. Dans l'onglet **Gestion des avantages**, spécifiez les valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Pays/région** | Le champ **Pays/région** détermine l'ordre d'affichage des codes postaux/états. Le pays sélectionné s'affiche en premier dans la liste déroulante. |
   | **Code motif de l'inscription** | Sélectionnez un code motif par défaut à utiliser lors de la création des plans d'employé pendant le traitement de l'inscription ouverte. |
   | **Code motif de l'annulation** | Code motif à utiliser lorsqu'un régime de prestations des employés est annulé. Il s'affiche dans une boîte de dialogue pendant le processus d'annulation. Les utilisateurs peuvent modifier le **Code du motif de l'annulation** si nécessaire. |
   | **Rouvrir le code motif** | Code motif à utiliser lorsqu'un régime de prestations des employés est rouvert. Il s'affiche dans une boîte de dialogue pendant le processus d'annulation. Les utilisateurs peuvent modifier le **Rouvrir le code motif** si nécessaire. | 
   | **Code motif de l'événement de vie** | Code motif à utiliser si un événement de vie se produit. |
   | **Modifier le taux du code motif** | Code motif à utiliser lors de l'annulation et de la réouverture d'un régime de prestations des employés pendant le processus de mise à jour du changement de taux. Il indique quels enregistrements ont été modifiés par le processus de mise à jour du changement de taux. |
   | **Salaire annuel avec avantages** | Cela vous permet de définir un montant de **Salaire annuel des avantages sociaux** pour un employé. Human Resources utilise le montant **Salaire annuel des avantages sociaux** lors de la détermination des montants de couverture, au lieu du montant annuel de la rémunération fixe. |
   | **Nouvelle embauche admissible** | Spécifie si les nouvelles embauches sont admissibles. |
   | **Période d'inscription du nouvel employé** | Période pendant laquelle la nouvelle inscription est autorisée.</br></br>**Remarque** : ce paramètre remplace toute nouvelle période d'inscription à l'embauche que vous avez définie dans la règle d'admissibilité du plan. |
   | **Fréquence de paiement par défaut** | La fréquence de paie par défaut à utiliser lorsque de nouveaux employés sont ajoutés. |
   | **Événements de vie activés** | Active les événements de vie. |
   | **Masquer les écrans d'avantages existants** | Vous permet de masquer les anciens écrans d'avantages. |
   | **Vérification de l'avantage** | Texte de vérification à utiliser lors du paiement des avantages en libre-service. |
   | **Sélectionner automatiquement les bénéficiaires** | Spécifie s'il faut sélectionner automatiquement les personnes à charge et les bénéficiaires en fonction de leur éligibilité aux options du plan. |

3. Sélectionnez **Enregistrer**.

## <a name="configure-employee-self-service-parameters"></a>Configurer les paramètres du libre service employé

1. Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres Human Resources**.

2. Dans l'onglet **Gestion des avantages**, spécifiez les valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Vérification de l'avantage** | Texte de vérification à utiliser lors du paiement des avantages en libre-service. |
   | **Sélectionner automatiquement les bénéficiaires** | Spécifie s'il faut sélectionner automatiquement les personnes à charge et les bénéficiaires en fonction de leur éligibilité aux options du plan. |

3. Sélectionnez **Enregistrer**.




[!INCLUDE[footer-include](../includes/footer-banner.md)]