---
title: Définir les stratégies de dépenses
description: Vous pouvez définir des stratégies de dépenses que vos travailleurs sont tenus de suivre lorsqu'ils entrent et soumettent des états de dépenses et des demandes de voyage dans Microsoft Dynamics 365 Finance.
author: ryansandness
manager: AnnBe
ms.date: 04/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d3b4a8f6cf74bb1fe7e53a4dfdd607f604e16e3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187450"
---
# <a name="define-expense-policies"></a>Définir les stratégies de dépenses

[!include [banner](../includes/banner.md)]

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

## <a name="policy-tips"></a>Conseils de stratégie
Voici quelques suggestions pour vous aider lors de la création de nouvelles stratégies pour la gestion des dépenses. 
* Les stratégies sont effectives de date et ne prennent pas effet si la stratégie est créée avec une date postérieure à la date à laquelle la dépense s'est produite. Par exemple, si vous créez une stratégie aujourd'hui pour appliquer une dépense de repas maximale de 50 $, aucune dépense existante entrée depuis d'hier n'est vérifiée par rapport à cette stratégie.
* En créant une stratégie pour une catégorie de dépenses qui peut être détaillée, envisagez d'ajouter une condition pour le type de ligne de dépense. Certaines stratégies pouvant nécessiter un reçu peuvent ne pas être utile pour les lignes détaillées et doivent être uniquement appliquées à l'en-tête de ligne ou une ligne non détaillée. 

## <a name="when-to-evaluate-policies"></a>Quand évaluer des stratégies

Dans les paramètres de gestion des dépenses, il existe une option pour évaluer les stratégies de gestion des dépenses lorsqu'une ligne est enregistrée ou lorsqu'un état de dépenses est soumis. Si vous choisissez d'évaluer lorsqu'une ligne est enregistrée cela garantit que les utilisateurs ont une visibilité antérieure de ce qu'ils doivent effectuer pour renseigner leur état de dépenses en une seule fois. Sinon, vous pouvez retarder l'évaluation de la stratégie et gagner du temps si vous effectuez une validation à la fin, lors de la soumission au workflow.
