---
title: Configuration de programmes de crédits flexibles
description: Vous pouvez utiliser des programmes de crédits flexibles dans Microsoft Dynamics 365 Human Resources pour inscrire les employés aux avantages selon un nombre prédéterminé de crédits flexibles.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitCreditPrograms
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d27d0f7f3f7e7db62b5d46b3b689d11194a85253
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009031"
---
# <a name="set-up-flex-credit-programs"></a>Configuration de programmes de crédits flexibles

[!include [banner](includes/preview-feature.md)]

Vous pouvez utiliser des programmes de crédits flexibles dans Microsoft Dynamics 365 Human Resources pour inscrire les employés aux avantages selon un nombre prédéterminé de crédits flexibles. Les employés peuvent choisir comment allouer leurs crédits flexibles. Par exemple, si un employé est couvert par le régime d'assurance maladie de son conjoint, il peut vouloir utiliser les crédits qu'il aurait autrement utilisés sur la couverture maladie pour d'autres avantages. 

1. Dans l'espace de travail **Gestion des avantages**, sous **Plans**, sélectionnez **Programmes de crédits flexibles**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | ID de crédit d'avantage | Identifiant unique du programme de crédits flexibles. |
   | Description | Description du programme de crédits flexibles. | 
   | Date de début | Date et heure d'activation du programme de crédits flexibles. |
   | Au | Date de fin du programme de crédits flexibles. Vous pouvez laisser la valeur par défaut (31/12/2154) pour indiquer que le programme de crédit flexible n'a pas d'expiration planifiée. |
   | Valeur de crédit total | Nombre de crédits que chaque employé devra utiliser pour ses avantages. |
   | Règle au prorata | Règle à utiliser pour la répartition proportionnelle des crédits flexibles lorsqu'un employé est embauché au milieu de la période de crédit flexible. </br></br><ul><li>**Aucun** - L'employé ne reçoit aucun crédit flexible s'il est embauché après le début de la période du programme de crédit flexible.</li><li>**Crédit total** - L'employé reçoit le montant total des crédits flexibles, quel que soit le moment de son embauche.</li><li>**Calculer au prorata** - L'employé reçoit un montant proportionnel de crédits flexibles en fonction de sa date de début.</li></ul> |
   | Formule de calcul au prorata des crédits flexibles | Règle à utiliser pour la répartition proportionnelle des crédits flexibles lorsque les employés sont embauchés au milieu d'une période d'avantage pour le programme de crédit flexible. La répartition est basée sur la date de début de l'emploi. Ce champ est uniquement utilisé si vous sélectionnez **Calculer au prorata** dans le champ **Règle au prorata**. </br></br><ul><li>**Quotidien** - Calcule au prorata le nombre de crédits flexibles qu'un employé reçoit au niveau quotidien. Le nombre total de crédits flexibles est divisé par le nombre de jours de la période. Par exemple, si votre période d'avantages est de 400 jours, le système divisera le nombre total de crédits flexibles par 400 pour calculer le nombre de crédits flexibles que les employés reçoivent par jour.</li><li>**Mois en cours** - Calcule au prorata le nombre de crédits flexibles qu'un employé reçoit au niveau du mois, arrondi au mois en cours. Le nombre total de crédits flexibles est divisé par le nombre de mois de la période. Par exemple, si votre période d'avantages est de 15 mois, le système divisera le nombre total de crédits flexibles par 15 pour calculer le nombre de crédits flexibles que les employés reçoivent par mois.</li><li>**Mois suivant** - Calcule au prorata le nombre de crédits flexibles qu'un employé reçoit au niveau du mois, arrondi au mois suivant. Le nombre total de crédits flexibles est divisé par le nombre de mois de la période. Par exemple, si votre période d'avantages est de 15 mois, le système divise le nombre total de crédits flexibles par 15 pour calculer le nombre de crédits flexibles que les employés reçoivent par mois.</li></ul> |
   
