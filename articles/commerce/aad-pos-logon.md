---
title: Activer l’authentification Azure Active Directory pour la connexion au PDV
description: Cette rubrique explique comment configurer l’expérience de connexion pour le point de vente (PDV) Microsoft Dynamics 365 Commerce afin d’utiliser l’authentification Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 234d19bb6659af07c65763e05671742b9581e244
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206677"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="a9ea4-103">Activer l’authentification Azure Active Directory pour la connexion au PDV</span><span class="sxs-lookup"><span data-stu-id="a9ea4-103">Enable Azure Active Directory authentication for POS sign-in</span></span>
[!include [banner](includes/banner.md)]


<span data-ttu-id="a9ea4-104">De nombreux clients qui utilisent Microsoft Dynamics 365 Commerce utilisent également d’autres services cloud Microsoft, et ils peuvent utiliser Azure Active Directory (Azure AD) pour gérer les informations d’identification de l’utilisateur pour ces services.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-104">Many customers who use Microsoft Dynamics 365 Commerce also use other Microsoft cloud services, and they might use Azure Active Directory (Azure AD) to manage user credentials for those services.</span></span> <span data-ttu-id="a9ea4-105">Dans ces cas, les clients peuvent souhaiter utiliser le même compte Azure AD dans toutes les applications.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-105">In those cases, the customers might want to use the same Azure AD account across applications.</span></span> <span data-ttu-id="a9ea4-106">Cette rubrique explique comment configurer l’expérience de connexion pour le point de vente (PDV) Commerce afin d’utiliser l’authentification Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-106">This topic explains how to configure the Commerce point of sale (POS) sign-in experience to use Azure AD authentication.</span></span>

## <a name="configure-azure-ad-authentication"></a><span data-ttu-id="a9ea4-107">Configurer l’authentification Azure AD</span><span class="sxs-lookup"><span data-stu-id="a9ea4-107">Configure Azure AD authentication</span></span>

<span data-ttu-id="a9ea4-108">Pour mettre Azure AD à disposition en tant que mode d’authentification pour la connexion au PDV pour un magasin, vous devez configurer les paramètres du profil de fonctionnalité du magasin, puis appliquer ces paramètres aux clients du PDV.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-108">To make Azure AD available as the authentication method for POS sign-in for a store, you must configure the settings of the store's functionality profile and then apply those setting to POS clients.</span></span>

<span data-ttu-id="a9ea4-109">Pour configurer un profil de fonctionnalité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a9ea4-109">To configure a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="a9ea4-110">Accédez à **Retail et Commerce** \> **Paramétrage du canal** \> **Paramétrage du PDV** \> **Profils POS** \> **Profils de fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-110">Go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS profiles** \> **Functionality profiles**.</span></span>
1. <span data-ttu-id="a9ea4-111">Sélectionnez le profil de fonctionnalité à modifier.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-111">Select the functionality profile to change.</span></span>
1. <span data-ttu-id="a9ea4-112">Sur le raccourci **Fonctions**, dans la section **Connexion du personnel au PDV**, modifiez la valeur du champ **Mode d’authentification pour la connexion** de **ID et mot de passe personnels** vers **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-112">On the **Functions** FastTab, in the **POS staff logon** section, change the value of the **Logon Authentication Method** field from **Personnel ID and Password** to **Azure Active Directory**.</span></span>

<span data-ttu-id="a9ea4-113">Par défaut, tous les profils de fonctionnalité utilisent **ID et mot de passe personnels** en tant que mode d’authentification au PDV.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-113">By default, all functionality profiles use **Personnel ID and Password** as the POS authentication method.</span></span> <span data-ttu-id="a9ea4-114">Par conséquent, vous devez modifier la valeur du champ **Mode d’authentification pour la connexion** si vous souhaitez utiliser Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-114">Therefore, you must change the value of the **Logon Authentication Method** field if you want to use Azure AD.</span></span> <span data-ttu-id="a9ea4-115">Chaque magasin de vente au détail lié au profil de fonctionnalité sélectionné sera affecté par cette modification.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-115">Every retail store that is linked to the selected functionality profile will be affected by this change.</span></span>

<span data-ttu-id="a9ea4-116">Pour appliquer les paramètres aux clients du PDV, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-116">To apply the settings to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="a9ea4-117">Accédez à **Retail et Commerce** \> **Informatique Retail et Commerce** \> **Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-117">Go to **Retail and Commerce** \> **Retail and Commerce IT** \> **Distribution schedule**.</span></span>
1. <span data-ttu-id="a9ea4-118">Exécutez le programme de distribution **1070** (**Configuration du canal**).</span><span class="sxs-lookup"><span data-stu-id="a9ea4-118">Run the **1070** (**Channel configuration**) distribution schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="a9ea4-119">L’authentification Azure AD nécessite une connexion Internet.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-119">Azure AD authentication requires an internet connection.</span></span> <span data-ttu-id="a9ea4-120">Cela ne fonctionne pas si le PDV est en mode Hors connexion.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-120">It won't work when POS is in offline mode.</span></span>
> 
> <span data-ttu-id="a9ea4-121">Actuellement, la fonction **remplacement par le responsable** ne prend pas en charge Azure AD comme méthode d’authentification.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-121">Currently, the **Manager override** function doesn't support Azure AD as an authentication method.</span></span> <span data-ttu-id="a9ea4-122">Un ID opérateur et un mot de passe sont requis même si Azure AD est configuré comme méthode d’authentification pour la connexion de PDV.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-122">An operator ID and password are required even if Azure AD is configured as the authentication method for POS sign-in.</span></span>

## <a name="associate-an-azure-ad-account-with-a-worker"></a><span data-ttu-id="a9ea4-123">Associer un compte Azure AD à un collaborateur</span><span class="sxs-lookup"><span data-stu-id="a9ea4-123">Associate an Azure AD account with a worker</span></span>

<span data-ttu-id="a9ea4-124">Avant qu’un employé de magasin puisse utiliser un compte Azure AD pour se connecter à l’application de PDV, le compte Azure AD doit être associé à ce collaborateur.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-124">Before a store worker can use an Azure AD account to sign in to the POS application, the Azure AD account must be associated with that worker.</span></span>

<span data-ttu-id="a9ea4-125">Pour associer un compte Azure AD à un collaborateur, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-125">To associate an Azure AD account with a worker, follow these steps.</span></span>

1. <span data-ttu-id="a9ea4-126">Accédez à **Retail et Commerce** \> **Employés** \> **Collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-126">Go to **Retail and Commerce** \> **Employees** \> **Workers**.</span></span>
1. <span data-ttu-id="a9ea4-127">Ouvrez la page des détails pour un collaborateur.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-127">Open the details page for a worker.</span></span>
1. <span data-ttu-id="a9ea4-128">Sur le volet Actions, sous l’onglet **Commerce**, dans le groupe **Identité externe**, cliquez sur **Associer l’identité existante**.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-128">On the Action Pane, on the **Commerce** tab, in the **External identity** group, select **Associate existing identity**.</span></span>
1. <span data-ttu-id="a9ea4-129">Dans la boîte de dialogue **Utiliser l’identité externe existante**, sélectionnez **Rechercher à l’aide de l’e-mail**, entrez une adresse électronique Azure AD, puis sélectionnez **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-129">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="a9ea4-130">Sélectionnez le compte Azure AD renvoyé, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-130">Select the Azure AD account that is returned, and then select **OK**.</span></span>

<span data-ttu-id="a9ea4-131">Les champs **Alias**, **UPN** et **Sous-identifiant externe** de l’onglet **Commerce** de la page des détails du collaborateur seront remplis.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-131">The **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

> [!NOTE]
> <span data-ttu-id="a9ea4-132">Une fois qu’un enregistrement de collaborateur est mis à jour, par exemple si un nouveau compte Azure AD est associé, un mot de passe est modifié ou un carnet d’adresses des employés est mis à jour, il est recommandé d’exécuter le programme de distribution **1060** (**Personnel**) pour synchroniser les dernières informations sur le personnel avec le canal.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-132">After a worker record is updated, for example if a new Azure AD account is associated, a password is changed, or an employee address book is updated, it’s recommended that you run **1060** (**Staff**) distribution schedule to synchronize the latest staff information to the channel.</span></span> <span data-ttu-id="a9ea4-133">De cette façon, l’application POS peut extraire les données correctes pour l’authentification des utilisateurs et la vérification des autorisations.</span><span class="sxs-lookup"><span data-stu-id="a9ea4-133">That way, the POS application can fetch the correct data for user authentication and authorization check.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9ea4-134">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a9ea4-134">Additional resources</span></span>

[<span data-ttu-id="a9ea4-135">Paramétrer une fonctionnalité de connexion étendue pour MPOS et CPOS</span><span class="sxs-lookup"><span data-stu-id="a9ea4-135">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="a9ea4-136">Créer un profil de fonctionnalité de vente au détail</span><span class="sxs-lookup"><span data-stu-id="a9ea4-136">Create a retail functionality profile</span></span>](retail-functionality-profile.md)

[<span data-ttu-id="a9ea4-137">Configurer un collaborateur</span><span class="sxs-lookup"><span data-stu-id="a9ea4-137">Configure a worker</span></span>](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)


[!INCLUDE[footer-include](../includes/footer-banner.md)]