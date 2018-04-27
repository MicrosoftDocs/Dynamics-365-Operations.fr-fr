--- 
title: "Affecter des utilisateurs à des rôles de sécurité"
description: "Pour accéder à Microsoft Dynamics 365 for Finance and Operations, des rôles de sécurité doivent être affectés aux utilisateurs."
author: maertenm
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: da96ec8357ea209fd958e32ab438b13e668735df
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---
# <a name="assign-users-to-security-roles"></a>Affecter des utilisateurs à des rôles de sécurité

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Pour accéder à Microsoft Dynamics 365 for Finance and Operations, des rôles de sécurité doivent être affectés aux utilisateurs. Cette procédure explique comment les administrateurs système peuvent affecter des utilisateurs aux rôles automatiquement, selon les données commerciales. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="automatically-assign-users-to-roles"></a>Affecter automatiquement des utilisateurs à des rôles
1. Allez dans Administration du système > Sécurité > Affecter des utilisateurs aux rôles.
2. Sélectionnez Chef comptable dans l'arborescence.
    * Sélectionnez le rôle pour lequel configurer la règle. Dans cet exemple, sélectionnez Chef comptable.  
3. Cliquez sur Ajouter la règle pour ouvrir la boîte de dialogue.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la requête à utiliser pour cette règle.  
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur Modifier la demande.
    * Modifiez la requête, le cas échéant.  
7. Cliquez sur OK.

## <a name="exclude-users-from-automatic-role-assignment"></a>Exclure des utilisateurs de l'affectation automatique de rôle
1. Fermez la page.
2. Allez dans Administration du système > Sécurité > Affecter des utilisateurs aux rôles.
3. Sélectionnez Chef comptable dans l'arborescence.
    * Permet de sélectionner un rôle. Pour cet exemple, sélectionnez Chef comptable.  
4. Cliquez sur Affecter/exclure manuellement des utilisateurs.
5. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionner un utilisateur.  
6. Cliquez sur Exclure du rôle.
    * Cliquez sur Exclure du rôle pour exclure les utilisateurs sélectionnés du rôle. Pour supprimer des exclusions, sélectionnez les utilisateurs à supprimer des exclusions, puis cliquez sur Redéfinition du statut. Lorsque vous supprimez une exclusion en réinitialisant le statut de l'utilisateur, le rôle d'utilisateur est de nouveau affecté automatiquement. Toutefois, l'utilisateur n'est pas immédiatement affecté au rôle ou exclu du rôle lorsque vous réinitialisez le statut. Au lieu de cela, l'utilisateur est affecté au rôle ou exclu de celui-ci la prochaine fois que les règles pour l'affectation de rôle automatique sont exécutées.  


