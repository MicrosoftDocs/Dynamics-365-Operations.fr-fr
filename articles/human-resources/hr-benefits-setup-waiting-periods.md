---
title: Configurer les périodes d’attente
description: Dans Microsoft Dynamics 365 Human Resources, les jours d’attente établissent un jalon à utiliser pour les régimes d’avantages.
author: twheeloc
ms.date: 08/25/2021
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
ms.openlocfilehash: 6dd231ef43cfac3188af23289190c6e9e4fad453
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323866"
---
# <a name="configure-waiting-periods"></a>Configurer les périodes d’attente

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dans Microsoft Dynamics 365 Human Resources, les jours d’attente établissent un jalon à utiliser pour les régimes d’avantages. Par exemple, trois mois à compter de la date d’embauche, le premier de chaque mois ou six mois.   

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Périodes d’attente**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Code d’attente** | Identificateur unique pour la période d’attente. |
   | **Description** | Description de la période d’attente. |
   | **Méthode d’attente** | Sélectionnez la méthode d’attente appropriée dans la liste déroulante des valeurs. Les options sont **Net**, **Mois en cours**, **Trimestre en cours**, **Année en cours**, and **Semaine en cours**. |
   | **Mois** | Entrez le nombre de mois à ajouter à la méthode d’attente pour calculer la date d’attente. |
   | **Jours** | Entrez le nombre de jours à ajouter à la méthode d’attente pour calculer la date d’attente. |
   | **Jour d’attente** | Sélectionnez le jour d’attente à utiliser pour calculer la date d’attente. |

4. Sélectionnez **Enregistrer**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
