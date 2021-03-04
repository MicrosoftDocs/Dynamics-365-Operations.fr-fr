---
title: Utilisateur introuvable dans le sélecteur de personnes dans Attract ou Onboard
description: Cette rubrique explique ce qu'il convient de faire lorsque les utilisateurs de l'entreprise cliente ne s'affichent pas dans le sélecteur de personnes dans les applications Dynamics 365 Talent - Attract ou Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a6d916f87ca30aa7405a51841e56ab31bbe31ac8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461207"
---
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a>Utilisateur introuvable dans le sélecteur de personnes dans Attract ou Onboard

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Sortie

Certains utilisateurs valides dans Microsoft Azure Active Directory (Azure AD) pour le client ne s'affichent pas lors de la recherche du nom dans le sélecteur de personnes dans les applications Dynamics 365 Talent: Attract ou Dynamics 365 Talent: Onboard.

## <a name="cause"></a>Cause

Certains types d'utilisateur ne sont actuellement pas pris en charge dans Attract et Onboard. Vérifiez que l'utilisateur n'est pas un utilisateur invité interentreprise Azure AD. Les informations « Type d'utilisateur » figurent dans le panneau Azure Active Directory sur le portail Azure.

Pour en savoir plus sur Azure B2B, voir [Qu'est-ce qu'un accès utilisateur invité dans Azure Active Directory B2B ?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).

Pour les utilisateurs non interentreprises, certains utilisateurs peuvent avoir une propriété « Type d'utilisateur » sur l'objet **Utilisateur**. Cela peut être vérifié et fixé à l'aide du module Azure AD Powershell. Pour plus d'informations, voir [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).

## <a name="resolution"></a>Résolution

Pour exécuter les étapes suivantes afin de résoudre le problème, vous devez avoir les autorisations « Administrateur global » sur le client Azure Active Directory ou les autorisations pour **User.ReadWrite.All**.

Pour vérifier le « Type d'utilisateur » pour l'utilisateur concerné.

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
La commande renvoie les informations suivantes.
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
Notez la propriété **UserType** de l'utilisateur. Si **UserType** est vide, par exemple pas « Membre » ou « Invité », mettez à jour le champ **UserType** à l'aide de la commande suivante.

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]