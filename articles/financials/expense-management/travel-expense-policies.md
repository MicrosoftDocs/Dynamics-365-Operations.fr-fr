---
title: "Définir les stratégies de dépenses"
description: "Vous pouvez définir des stratégies de dépenses que vos employés doivent suivre lorsqu'ils saisissent et soumettent des états de dépenses et des demandes de voyage dans Microsoft Dynamics 365 for Finance and Operations."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 3b2a28fe6acf03e52c292048a797ce997f58bcce
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="expense-policies"></a>Stratégies des dépenses

[!include[banner](../includes/banner.md)]

Vous pouvez définir des stratégies ou règles que vos collaborateurs sont tenus de suivre lorsqu'ils entrent et soumettent des états de dépenses et des demandes de voyage.         
L'application de stratégies des dépenses permet une gestion efficace des dépenses.         

Par exemple, vous pouvez définir une stratégie pour les frais d'hôtel à New York, qui stipule que la dépense par nuit ne peut pas dépasser 250 USD       
Si un travailleur soumet un état de dépenses ou une demande de déplacement dans lesquels le taux de la chambre dépasse ce montant, le système notifie le        
travailleur qu'il a dépassé le montant prévu par la stratégie pour ces frais. Vous pouvez configurer le message que le travailleur recevra lorsque vous        
définissez la stratégie.      
        
Vous pouvez définir trois types de stratégies :         
        
- Avertissement – Permet au travailleur d'envoyer un état de dépenses ou une demande de voyage, mais la dépense sera marquée pour tous les approbateurs et        
pour un état ultérieur.        

- Erreur – Nécessite que le travailleur modifie la dépense pour respecter la stratégie avant d'envoyer l'état de dépenses ou la demande de voyage.       
 
 - Justification – Nécessite que le travailleur ou un responsable entre une justification du dépassement du montant prévu par la stratégie avant d'envoyer l'état de dépenses ou la demande de voyage.        
 
 Vous pouvez également paramétrer une plage de dates pendant laquelle les stratégies des dépenses s'appliquent. Par exemple, il se peut que le prix des vols entre le Danemark      
 et New York soient chers pendant la période de vacances. Vous pouvez définir une règle de frais de vol limitant      
 les frais des vols vers New York à 5 000 DKK et spécifier que cette règle s'applique entre le 15 mars et      
 le 15 septembre.

