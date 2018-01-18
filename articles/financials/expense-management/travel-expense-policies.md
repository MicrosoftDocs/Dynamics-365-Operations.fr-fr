---
title: "Définir les stratégies de dépenses"
description: "Vous pouvez définir des stratégies de dépenses que vos employés doivent suivre lorsqu'ils saisissent et soumettent des états de dépenses et des demandes de voyage dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 940d6f8c3d878c2c12806ad04a092856df2acb33
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="expense-policies"></a>Stratégies des dépenses

[!include[banner](../includes/banner.md)]

Vous pouvez définir des stratégies ou règles que vos collaborateurs sont tenus de suivre lorsqu'ils entrent et soumettent des états de dépenses et des demandes de voyage. L'application de stratégies des dépenses permet une gestion efficace des dépenses. 

Par exemple, vous pouvez définir une stratégie pour les frais d'hôtel à New York, qui stipule que la dépense par nuit ne peut pas dépasser 250 USD Si un collaborateur soumet un état de dépenses ou une demande de voyage dans lequel le prix de la chambre dépasse ce montant, le système notifie à l'utilisateur qu'il a dépassé le montant prévu par la stratégie pour ces frais. Vous pouvez configurer le message que le travailleur recevra lorsque vous définissez la stratégie. 

Vous pouvez définir trois types de stratégies : 

 - Avertissement – Permet au travailleur d'envoyer un état de dépenses ou une demande de voyage, mais la dépense sera marquée pour tous les approbateurs et  
 pour un état ultérieur. 
 - Erreur – Nécessite que le travailleur modifie la dépense pour respecter la stratégie avant d'envoyer l'état de dépenses ou la demande de voyage. 
 - Justification – Nécessite que le travailleur ou un responsable entre une justification du dépassement du montant prévu par la stratégie avant d'envoyer l'état de dépenses ou la demande de voyage. 

Vous pouvez également paramétrer une plage de dates pendant laquelle les stratégies des dépenses s'appliquent. Par exemple, il se peut que le prix des vols entre le Danemark et New York soient chers pendant la période de vacances. Vous pouvez définir une règle de frais de vol limitant les frais des vols vers New York à 5 000 DKK et spécifier que cette règle s'applique entre le 15 mars et le 15 septembre. 

