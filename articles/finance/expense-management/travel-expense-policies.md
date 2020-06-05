---
title: Définir les stratégies de dépenses
description: Vous pouvez définir des stratégies de dépenses que vos travailleurs sont tenus de suivre lorsqu'ils entrent et soumettent des états de dépenses et des demandes de voyage dans Microsoft Dynamics 365 Finance.
author: suvaidya
manager: AnnBe
ms.date: 05/20/2020
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
ms.openlocfilehash: 22504e0e26c025d117f29dee3b59b41d508e7724
ms.sourcegitcommit: 4f90b9ddedf312e75a714e0ec7f7ee5fd43cac6a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/21/2020
ms.locfileid: "3389713"
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
* Les politiques de gestion des dépenses sont évaluées par rapport à l'entité source par défaut. Pour les scénarios intersociétés, vous pouvez définir la stratégie à évaluer par rapport à l'entité de destination (entité emprunteuse) à la place. Pour exécuter les stratégies sur l'entité de destination, activez la fonctionnalité « Évaluer la stratégie de dépenses par rapport à l'entité juridique emprunteuse » dans l'espace de travail **Gestion des fonctionnalités**.

## <a name="when-to-evaluate-policies"></a>Quand évaluer des stratégies

Dans les paramètres de gestion des dépenses, il existe une option pour évaluer les stratégies de gestion des dépenses lorsqu'une ligne est enregistrée ou lorsqu'un état de dépenses est soumis. Si vous choisissez d'évaluer lorsqu'une ligne est enregistrée cela garantit que les utilisateurs ont une visibilité antérieure de ce qu'ils doivent effectuer pour renseigner leur état de dépenses en une seule fois. Sinon, vous pouvez retarder l'évaluation de la stratégie et gagner du temps si vous effectuez une validation à la fin, lors de la soumission au workflow.
