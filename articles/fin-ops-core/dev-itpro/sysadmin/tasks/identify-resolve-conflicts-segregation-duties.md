---
title: Identifier et résoudre les conflits de répartition des tâches
description: Cette rubrique explique comment identifier et résoudre les conflits de répartition des tâches.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0638699c0e569bbe67024a87d6c55729642557cb085ee899aa98aa0022b12840
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748310"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identifier et résoudre les conflits de répartition des tâches

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment identifier et résoudre les conflits de répartition des tâches. Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs. Ce concept est appelé répartition des tâches. Lorsque la définition d’un rôle de sécurité ou les affectations de rôle d’un utilisateur violent les règles, le conflit est consigné. Tous les conflits doivent être résolus par l’administrateur. Procédez comme suit pour identifier et résoudre les conflits.

Une fois qu’une règle a été ajoutée, vérifiez que tous les rôles existants sont conformes. 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a>Vérifier que les rôles et les tâches existants sont conformes aux nouvelles règles de répartition des tâches
1. Accédez à **Administration système** > **Sécurité** > **Répartition des tâches** > **Règles de répartition des tâches**.
3. Sélectionnez **Vérifier les responsabilités et les rôles**. Si des rôles existants violent les règles, un message s’affiche, contenant le nom des règles, le rôle et les noms des tâches en conflit. Les rôles en conflit doivent être modifiés à l’aide de l’option **Configuration de la sécurité** et ne peut pas inclure des tâches conflictuelles. Si aucun rôle ne viole la règle sélectionnée, un message indique que tous les rôles sont en conformité.   

> [!NOTE]
> La validation n’est effectuée que pour la règle sélectionnée. Il est important de valider la conformité pour chaque règle.   

Lorsque vous créez ou modifiez un rôle, les règles de séparation des tâches sont automatiquement appliquées. Vous ne pouvez pas attribuer des tâches conflictuelles à un rôle.

Ensuite, vérifiez que toutes les attributions de rôle existantes sont conformes.

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Vérifier que les affectations des rôles utilisateurs sont conformes aux nouvelles règles de répartition des tâches
1. Accédez à **Administration système > Sécurité > Répartition des tâches > Vérifier la conformité des affectations par rôle d’utilisateur**.
2. Cliquez sur **OK**. Une notification affiche les résultats de la validation. Les conflits sont également consignés sur la page **Conflits non résolus de répartition des tâches**.   

Lorsque vous assignez des utilisateurs à des rôles, les règles de séparation des tâches sont automatiquement appliquées. Si vous essayez d’affecter un utilisateur à des rôles contenant des tâches en conflit, vous recevez un message d’erreur. Vous devez ensuite résoudre le conflit en refusant ou en autorisant l’attribution de rôle supplémentaire. Le rôle supplémentaire sera attribué une fois l’affectation autorisée. 

> [!NOTE]
> Les conflits ne sont actuellement pas vérifiés pour les utilisateurs auxquels des rôles sont attribués en fonction des groupes de domaine Active Directory.

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Afficher et résoudre des rôles utilisateurs en conflit
1. Accédez à **Administration système** > **Sécurité** > **Répartition des tâches** > **Conflits non résolus de répartition des tâches**. 
2. Sélectionnez un conflit, puis sélectionnez l’une des actions suivantes : 

  - **Refuser l’affectation** : permet de refuser l’affectation de l’utilisateur au rôle de sécurité supplémentaire. Si vous refusez une affectation de rôle automatique, l’utilisateur est marqué comme exclu du rôle. L’utilisateur exclu se voit refuser l’accès qui est associé au rôle et ne peut pas être affecté au rôle tant que l’administrateur ne supprime pas l’exclusion. 
-  **Autoriser l’affectation** : cela remplace le conflit, et affecte l’utilisateur au rôle de sécurité supplémentaire. Si vous remplacez un conflit, vous devez entrer un motif dans le champ **Motif du remplacement**. Toutes les attributions de rôle remplacées peuvent être affichées sur la page **Conflits de séparation des tâches**.  

> [!NOTE]
> Si plusieurs conflits sont répertoriés pour le même utilisateur, sélectionnez l’enregistrement utilisateur et évaluez les rôles attribués sur la page **Utilisateurs**. Pour éviter ce conflit, validez chaque règle après son ajout ou sa modification.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]