---
title: Affecter des utilisateurs à des rôles de sécurité
description: Pour accéder aux applications Finance and Operations, les utilisateurs doivent être affectés à des rôles de sécurité.
author: Peakerbl
manager: AnnBe
ms.date: 05/06/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a6d904ae3df23dd1c602cfdfecc40411aba5724
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569872"
---
# <a name="assign-users-to-security-roles"></a>Affecter des utilisateurs à des rôles de sécurité

[!include [banner](../../includes/banner.md)]

Pour utiliser autre chose que les fonctionnalités courantes dans les applications Finance and Operations, des rôles de sécurité doivent être attribués aux utilisateurs. Vous pouvez affecter des utilisateurs à des rôles automatiquement, en fonction des règles et des données d’entreprise, exclure les utilisateurs de l’attribution automatique des rôles ou ajouter des utilisateurs aux rôles manuellement.

## <a name="automatically-assign-users-to-roles"></a>Affecter automatiquement des utilisateurs à des rôles
Cette procédure explique comment les administrateurs système peuvent affecter automatiquement des utilisateurs aux rôles, selon les données commerciales. 
1. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Affecter des utilisateurs aux rôles**.
2. Sélectionnez Chef comptable dans l’arborescence. Sélectionnez le rôle pour lequel configurer la règle. Dans cet exemple, sélectionnez Chef comptable. 
3. Sélectionnez **Ajouter une règle** pour ouvrir le menu de la boîte de dialogue.
4. Dans la liste **Sélectionner une requête**, recherchez et sélectionnez l’enregistrement souhaité. Sélectionnez la requête à utiliser pour cette règle.  
5. Dans la liste **Nom de la règle d’appartenance**, cliquer sur le lien dans la ligne sélectionnée.
6. Sélectionnez **Modifier une requête**. Modifiez la requête, le cas échéant.  
7. Cliquez sur **OK**.
8. Sélectionnez **Exécuter l’affectation automatique de rôle**.
9. Accédez à **Volet Navigation > Modules > Administration système > Utilisateurs > Utilisateurs** (idéalement dans un onglet distinct du navigateur).
10. Examinez les rôles affectés à différents utilisateurs pour confirmer que la requête d’affectation du rôle était correcte. Ajustez et réexécutez si nécessaire.

## <a name="exclude-users-from-automatic-role-assignment"></a>Exclure des utilisateurs de l’affectation automatique de rôle
1. Fermez la page.
2. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Affecter des utilisateurs aux rôles**.
3. Sélectionnez Chef comptable dans l’arborescence. Permet de sélectionner un rôle. Pour cet exemple, sélectionnez Chef comptable.  
4. Dans le menu **Utilisateurs attribués au rôle**, sélectionnez **Affecter/exclure manuellement des utilisateurs**.
5. Dans la liste **Affecter des utilisateurs au rôle ou exclure des utilisateurs du rôle**, marquez la ligne sélectionnée. Sélectionner un utilisateur.  
6. Sous le **volet Actions**, sélectionnez **Exclure du rôle**.
7. Sélectionnez **Exclure du rôle** pour exclure les utilisateurs sélectionnés du rôle. Pour supprimer des exclusions, sélectionnez les utilisateurs à supprimer des exclusions, puis cliquez sur **Redéfinition du statut**. Lorsque vous supprimez une exclusion en réinitialisant le statut de l’utilisateur, le rôle d’utilisateur est affecté automatiquement. Toutefois, l’utilisateur n’est pas immédiatement affecté au rôle ou exclu du rôle lorsque vous réinitialisez le statut. Au lieu de cela, l’utilisateur est affecté au rôle ou exclu de celui-ci la prochaine fois que les règles pour l’affectation de rôle automatique sont exécutées.  

## <a name="manually-assign-users-to-roles"></a>Affecter manuellement des utilisateurs à des rôles
Les utilisateurs qui reçoivent des rôles de sécurité manuellement doivent également être supprimés manuellement par l’administrateur. Ces utilisateurs ne seront pas supprimés des rôles par des règles d’attribution de rôle automatiques.

1. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Affecter des utilisateurs aux rôles**.
2. Dans l’arborescence, sélectionnez un rôle et dans le menu **Utilisateurs attribués au rôle**, sélectionnez **Affecter/exclure manuellement des utilisateurs**.
4. Dans **Attribuer ou exclure des utilisateurs du rôle**, les utilisateurs auxquels le rôle n’a pas été attribué sont répertoriés avec le **Mode d’affectation** défini sur **Aucun**. Sélectionnez un ou plusieurs utilisateurs auxquels le rôle doit être attribué.
5. Sous le **volet Actions**, sélectionnez **Affecter au rôle**. Le **Mode d’affectation** est mis à jour en **Manuel** et les utilisateurs se voient désormais attribuer un nouveau rôle.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]