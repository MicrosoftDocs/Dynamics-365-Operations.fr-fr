---
title: Identifier et résoudre les conflits de répartition des tâches
description: Cette rubrique explique comment identifier et résoudre les conflits de répartition des tâches.
author: maertenm
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5c89d27eb8b587e8936258aae3ec1fee4574ccfb
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180919"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identifier et résoudre les conflits de répartition des tâches

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique explique comment identifier et résoudre les conflits de répartition des tâches. Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs. Ce concept est appelé répartition des tâches. Lorsque la définition d'un rôle de sécurité ou les affectations de rôle d'un utilisateur violent les règles, le conflit est consigné. Tous les conflits doivent être résolus par l'administrateur. Procédez comme suit pour identifier et résoudre les conflits. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Vérifier que les affectations des rôles utilisateurs sont conformes aux nouvelles règles de répartition des tâches
1. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Répartition des tâches > Vérifier la conformité des affectations par rôle d'utilisateur**.
2. Cliquez sur **OK**. Une notification affiche les résultats de la validation. En cas de conflit, vous pouvez ouvrir la page **Utilisateurs** et modifier les affectations des rôles de l'utilisateur. Les conflits sont également consignés sur la page **Conflits de répartition des tâches**. Pour exécuter le processus de vérification en tant que traitement par lots, sélectionnez **Traitement par lots**, puis définissez les paramètres des autres lots. Après que le traitement par lots s'exécute, vous pouvez réviser les conflits dans la page **Conflits de répartition des tâches**.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Afficher et résoudre des rôles utilisateurs en conflit
1. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Répartition des tâches > Conflits de répartition des tâches.** Sélectionnez un conflit, puis l'un des boutons suivants : **Refuser l'affectation – Refuser l'affectation de l'utilisateur au rôle de sécurité supplémentaire**. Si vous refusez une affectation de rôle automatique, l'utilisateur est marqué comme exclu du rôle. L'utilisateur exclu se voit refuser l'accès qui est associé au rôle et ne peut pas être affecté au rôle tant que l'administrateur ne supprime pas l'exclusion. Autorisez l'affectation : **remplacez** le conflit, et affectez l'utilisateur aux deux rôles de sécurité. Si vous remplacez un conflit, vous devez entrer un motif dans le champ **Motif du remplacement**.  
2. Fermez la page.
3. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Répartition des tâches > Conflits non résolus de répartition des tâches.** Sélectionnez un conflit, puis l'un des boutons suivants : **Refuser l'affectation – Refuser l'affectation de l'utilisateur au rôle de sécurité supplémentaire**. Si vous refusez une affectation de rôle automatique, l'utilisateur est marqué comme exclu du rôle. L'utilisateur exclu se voit refuser l'accès qui est associé au rôle et ne peut pas être affecté au rôle tant que l'administrateur ne supprime pas l'exclusion. Autorisez l'affectation : **remplacez** le conflit, et affectez l'utilisateur aux deux rôles de sécurité. Si vous remplacez un conflit, vous devez entrer un motif dans le champ **Motif du remplacement**.    
4. Fermez la page.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Vérifier que les rôles existants sont conformes aux nouvelles règles de répartition des tâches
1. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Répartition des tâches > Règles de répartition des tâches**. Sélectionnez une règle.  
2. Sélectionnez **Vérifier les responsabilités et les rôles**. Si des rôles existants violent la règle sélectionnée, un message s'affiche, contenant le nom du rôle et les noms des tâches en conflit. L'administrateur doit indiquer la limitation des risques de sécurité ou modifier le rôle afin qu'il ne viole pas les règles de répartition des tâches. Si aucun rôle ne viole la règle sélectionnée, un message indique que tous les rôles sont en conformité.  

