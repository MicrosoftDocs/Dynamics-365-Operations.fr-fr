---
title: Utilisateur introuvable dans le sélecteur de personnes dans Attract ou Onboard
description: Cette rubrique explique ce qu'il convient de faire lorsque les utilisateurs de l'entreprise cliente ne s'affichent pas dans le sélecteur de personnes dans les applications Dynamics 365 for Talent Attract ou Onboard.
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
ms.openlocfilehash: a9c2324321baf0a313b8b7aa9701909336b5c34b
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742747"
---
# <a name="azure-active-directory-users-not-found-in-people-picker"></a><span data-ttu-id="72821-103">Utilisateurs Azure Active Directory introuvables dans le sélecteur de personnes</span><span class="sxs-lookup"><span data-stu-id="72821-103">Azure Active Directory users not found in People Picker</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="72821-104">Sortie</span><span class="sxs-lookup"><span data-stu-id="72821-104">Issue</span></span>

<span data-ttu-id="72821-105">Certains utilisateurs valides dans Microsoft Azure Active Directory (Azure AD) pour le client ne s'affichent pas lors de la recherche du nom dans le sélecteur de personnes dans les applications Dynamics 365 for Talent Attract ou Onboard.</span><span class="sxs-lookup"><span data-stu-id="72821-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in the Dynamics 365 for Talent Attract or Onboard applications.</span></span>

## <a name="cause"></a><span data-ttu-id="72821-106">Cause</span><span class="sxs-lookup"><span data-stu-id="72821-106">Cause</span></span>

<span data-ttu-id="72821-107">Certains types d'utilisateur ne sont actuellement pas pris en charge dans les applications Attract et Onboard.</span><span class="sxs-lookup"><span data-stu-id="72821-107">Certain user types are not currently supported in the Attract and Onboard applications.</span></span> <span data-ttu-id="72821-108">Vérifiez que l'utilisateur n'est pas un utilisateur invité interentreprise Azure AD.</span><span class="sxs-lookup"><span data-stu-id="72821-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="72821-109">Les informations « Type d'utilisateur » figurent dans le panneau Azure Active Directory sur le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="72821-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="72821-110">Pour en savoir plus sur Azure B2B, voir [Qu'est-ce qu'un accès utilisateur invité dans Azure Active Directory B2B ?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="72821-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="72821-111">Pour les utilisateurs non interentreprises, certains utilisateurs peuvent avoir une propriété « Type d'utilisateur » sur l'objet **Utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="72821-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="72821-112">Cela peut être vérifié et fixé à l'aide du module Azure AD Powershell.</span><span class="sxs-lookup"><span data-stu-id="72821-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="72821-113">Pour plus d'informations, voir [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="72821-113">For more information, see [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="72821-114">Résolution</span><span class="sxs-lookup"><span data-stu-id="72821-114">Resolution</span></span>

<span data-ttu-id="72821-115">Pour exécuter les étapes suivantes afin de résoudre le problème, vous devez avoir les autorisations « Administrateur global » sur le client Azure Active Directory ou les autorisations pour **User.ReadWrite.All**.</span><span class="sxs-lookup"><span data-stu-id="72821-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="72821-116">Pour vérifier le « Type d'utilisateur » pour l'utilisateur concerné.</span><span class="sxs-lookup"><span data-stu-id="72821-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="72821-117">La commande renvoie les informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="72821-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="72821-118">Notez la propriété **UserType** de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="72821-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="72821-119">Si **UserType** est vide, par exemple pas « Membre » ou « Invité », mettez à jour le champ **UserType** à l'aide de la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="72821-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
