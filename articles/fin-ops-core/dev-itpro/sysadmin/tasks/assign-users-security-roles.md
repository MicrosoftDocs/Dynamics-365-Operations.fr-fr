---
title: Affecter des utilisateurs à des rôles de sécurité
description: Pour accéder aux applications Finance and Operations, des rôles de sécurité doivent être affectés aux utilisateurs.
author: ChrisGarty
manager: AnnBe
ms.date: 09/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4daecc1acd589cd1656402244e5325382a407e7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180965"
---
# <a name="assign-users-to-security-roles"></a>Affecter des utilisateurs à des rôles de sécurité

[!include [task guide banner](../../includes/task-guide-banner.md)]

Pour utiliser autre chose que les fonctionnalités courantes, des rôles de sécurité doivent être attribués aux utilisateurs. Cette procédure explique comment les administrateurs système peuvent affecter automatiquement des utilisateurs aux rôles, selon les données commerciales. 

## <a name="automatically-assign-users-to-roles"></a>Affecter automatiquement des utilisateurs à des rôles
1. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Affecter des utilisateurs aux rôles**.
2. Sélectionnez Chef comptable dans l'arborescence. Sélectionnez le rôle pour lequel configurer la règle. Dans cet exemple, sélectionnez Chef comptable. 
3. Cliquez sur **Ajouter la règle** pour ouvrir la boîte de dialogue.
4. Dans la liste **Sélectionner une requête**, recherchez et sélectionnez l'enregistrement souhaité. Sélectionnez la requête à utiliser pour cette règle.  
5. Dans la liste **Nom de la règle d'appartenance**, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur **Modifier la requête.** Modifiez la requête, le cas échéant.  
7. Cliquez sur **OK**.

## <a name="exclude-users-from-automatic-role-assignment"></a>Exclure des utilisateurs de l'affectation automatique de rôle
1. Fermez la page.
2. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Affecter des utilisateurs aux rôles**.
3. Sélectionnez Chef comptable dans l'arborescence. Permet de sélectionner un rôle. Pour cet exemple, sélectionnez Chef comptable.  
4. Dans le menu **Utilisateurs attribués au rôle**, sélectionnez **Affecter/exclure manuellement des utilisateurs**.
5. Dans la liste **Affecter des utilisateurs au rôle ou exclure des utilisateurs du rôle**, marquez la ligne sélectionnée. Sélectionner un utilisateur.  
6. Sous le **volet Actions**, sélectionnez **Exclure du rôle**.
    
    Cliquez sur **Exclure du rôle** pour exclure les utilisateurs sélectionnés du rôle. Pour supprimer des exclusions, sélectionnez les utilisateurs à supprimer des exclusions, puis cliquez sur **Redéfinition du statut**. Lorsque vous supprimez une exclusion en réinitialisant le statut de l'utilisateur, le rôle d'utilisateur est de nouveau affecté automatiquement. Toutefois, l'utilisateur n'est pas immédiatement affecté au rôle ou exclu du rôle lorsque vous réinitialisez le statut. Au lieu de cela, l'utilisateur est affecté au rôle ou exclu de celui-ci la prochaine fois que les règles pour l'affectation de rôle automatique sont exécutées.  
