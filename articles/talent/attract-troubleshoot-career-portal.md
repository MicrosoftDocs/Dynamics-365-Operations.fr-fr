---
title: Les utilisateurs Attract ne peuvent pas soumettre leur candidature depuis le portail de carrière
description: Cette rubrique explique comment résoudre un problème où les utilisateurs Attract ne peuvent pas postuler à des emplois à partir du portail carrière.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461128"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a>Les utilisateurs Attract ne peuvent pas soumettre leur candidature depuis le portail de carrière

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Sortie

Les utilisateurs Attract ne peuvent pas soumettre leur candidature depuis le portail de carrière. Lorsqu'ils essaient de postuler pour un emploi créé dans Dynamics 365 Talent: Attract, le navigateur charge la page en continu et ne termine pas l'action.

## <a name="cause"></a>Cause

Ce problème se produit lorsque l'équipe de relations Talent n'a pas le rôle d'utilisateur Talent.

## <a name="resolution"></a>Résolution

Attribuez le rôle d'utilisateur Talent à l'équipe de relations Talent.

1. Connectez-vous au [centre d'administration Power Platform](https://admin.powerplatform.microsoft.com) avec l'une des informations d'identification d'administrateur suivantes :

   - Administrateur Dynamics 365
   - Administrateur général
   - Administrateur Power Platform

2. Dans le volet de navigation, sélectionnez **Environnements**, puis sélectionnez l'environnement dans lequel attribuer le rôle d'utilisateur Talent à l'équipe de relations Talent.

   ![Sélectionner un environnement](./media/attract-troubleshoot-career-portal-select-environment.png)

3. Dans le volet **Environnements**, sélectionnez l'**URL d'environnement** et connectez-vous au portail d'administration de l'environnement (par exemple, https:<orgname>.crm.dynamics.com).

4. Sélectionnez **Paramètres**, sélectionnez **Système**, puis **Sécurité**.

   ![Accédez à la sécurité](./media/attract-troubleshoot-career-portal-security.png)

5. Sélectionnez **Équipes**.

   ![Sélectionnez Équipes](./media/attract-troubleshoot-career-portal-security-teams.png)

6. Rechercher **Équipe des relations Talent** dans la zone de recherche, puis sélectionnez l'équipe dans les résultats de la recherche.

7. Sélectionnez **GÉRER LES RÔLES** dans le ruban.

8. Dans la boîte de dialogue **Gérer les rôles de l'équipe**, sélectionnez **Utilisateur Talent** dans la liste des rôles disponibles, puis sélectionnez **OK** pour appliquer le rôle.

   ![Appliquer le rôle](./media/attract-troubleshoot-career-portal-apply-role.png)

9. Testez vos modifications :

   1. Connectez-vous au portail des carrières à partir d'une nouvelle fenêtre de navigateur.
   2. Postulez à l'emploi depuis le portail carrière. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]