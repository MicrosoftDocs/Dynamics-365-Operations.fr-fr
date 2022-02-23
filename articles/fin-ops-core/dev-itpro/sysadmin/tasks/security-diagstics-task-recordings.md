---
title: Diagnostics de sécurité pour l’enregistrement des tâches
description: Cette rubrique fournit des informations sur la façon d’analyser et de gérer les exigences d’autorisation de sécurité en fonction d’un enregistrement de tâche.
author: Peakerbl
manager: AnnBe
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: 88eb90b35f1a9754cc4daa01d8f40cdf712db4f8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679788"
---
# <a name="security-diagnostics-for-task-recordings"></a>Diagnostics de sécurité pour l’enregistrement des tâches

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>Avant de commencer

Cette rubrique fournit des informations sur la façon d’analyser et de gérer les exigences d’autorisation de sécurité en fonction d’un enregistrement de tâche. Avant d’effectuer les étapes de cette rubrique, vous devez disposer d’un enregistrement de tâche du processus technique que vous souhaitez analyser. Pour enregistrer un processus métier, voir [Ressources de l’enregistreur de tâches](../../user-interface/task-recorder.md). 

## <a name="manage-security-for-a-task-recording"></a>Gérer la sécurité pour un enregistrement de tâche

1. Accédez à **Administration du système** > **Sécurité** > **Diagnostic de sécurité pour l’enregistrement des tâches**.
2. Ouvrez l’enregistrement de tâche à partir de son emplacement. Sélectionnez **Ouvrir depuis ce PC** ou **Ouvert à partir de Lifecycle Services**, puis sélectionnez **Fermer**.
3. Cela ouvrira la page **Détails des éléments du menu Sécurité** qui répertorie les objets de sécurité requis pour le processus.

 > [!NOTE]
 > Les éléments de menu **Action** et **Production** ne sont pas inclus dans la liste.

4. Dans le champ **ID utilisateur**, sélectionnez un utilisateur. Si l’utilisateur ne dispose pas d’autorisations pour certains éléments de menu, le champ **Autorisations manquantes** sera mis à jour sur **Oui**.
  
  ![Page Détails des éléments du menu Sécurité](../media/Security-Menu-Item-Details.png)

5. Sélectionnez **Ajouter une référence** pour afficher la liste des objets de sécurité, y compris les rôles, les fonctions et les privilèges qui accordent l’autorisation manquante.
6. Sélectionnez un objet de sécurité dans la liste :

    - Si **Rôle** est sélectionné, sélectionnez **Ajouter un rôle à l’utilisateur**. Cela ouvrira la page **Attribuer des utilisateurs aux rôles**. Pour plus d’informations, voir la page [Affecter des utilisateurs à des rôles de sécurité](assign-users-security-roles.md).
    - Si **Devoir** est sélectionné, sélectionnez **Ajouter le devoir au rôle**, sélectionnez les rôles auxquels le devoir doit être ajouté, puis sélectionnez **OK**.
    - Si **Privilège** est sélectionné, sélectionnez **Ajouter le privilège aux devoirs**, sélectionnez les rôles auxquels le devoir doit être ajouté, puis sélectionnez **OK**.
