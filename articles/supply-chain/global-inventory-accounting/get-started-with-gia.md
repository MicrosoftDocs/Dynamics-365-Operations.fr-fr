---
title: Premiers pas avec la comptabilité globale des stocks
description: Cette rubrique décrit comment démarrer avec la comptabilité globale des stocks.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 59f9db309312bbbc88b4fa47c12c4c02f09e7c6d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301696"
---
# <a name="get-started-with-global-inventory-accounting"></a><span data-ttu-id="bbe12-103">Premiers pas avec la comptabilité globale des stocks</span><span class="sxs-lookup"><span data-stu-id="bbe12-103">Get started with Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="bbe12-104">La comptabilité globale des stocks vous permet d’effectuer plusieurs comptabilités de stock dans les différents registres de comptabilité globale des stocks que vous avez configurés.</span><span class="sxs-lookup"><span data-stu-id="bbe12-104">Global Inventory Accounting lets you do multiple inventory accountings in the Global Inventory Accounting ledgers that you've set up.</span></span> <span data-ttu-id="bbe12-105">Vous devez associer chaque registre de comptabilité globale des stocks à une *convention*.</span><span class="sxs-lookup"><span data-stu-id="bbe12-105">You must associate each Global Inventory Accounting ledger with a *convention*.</span></span> <span data-ttu-id="bbe12-106">Une convention est un ensemble des types de stratégies comptables suivants :</span><span class="sxs-lookup"><span data-stu-id="bbe12-106">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="bbe12-107">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bbe12-107">Cost object</span></span>
- <span data-ttu-id="bbe12-108">Base de la mesure en entrée</span><span class="sxs-lookup"><span data-stu-id="bbe12-108">Input measurement basis</span></span>
- <span data-ttu-id="bbe12-109">Hypothèse de flux de coût</span><span class="sxs-lookup"><span data-stu-id="bbe12-109">Cost flow assumption</span></span>
- <span data-ttu-id="bbe12-110">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bbe12-110">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="bbe12-111">Même après avoir activé la comptabilité globale des stocks, vous pouvez toujours effectuer la comptabilité de stock dans Microsoft Dynamics 365 Supply Chain Management de la manière habituelle.</span><span class="sxs-lookup"><span data-stu-id="bbe12-111">Even after you turn on Global Inventory Accounting, you can still do inventory accounting in Microsoft Dynamics 365 Supply Chain Management in the usual way.</span></span>

<span data-ttu-id="bbe12-112">Le service de comptabilité globale des stocks est un complément.</span><span class="sxs-lookup"><span data-stu-id="bbe12-112">Global Inventory Accounting is an add-in.</span></span> <span data-ttu-id="bbe12-113">Pour rendre ses fonctionnalités disponibles, vous devez l’installer à partir de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="bbe12-113">To make its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="bbe12-114">Vous pouvez choisir de l’évaluer dans un environnement de test avant de l’activer pour les environnements de production.</span><span class="sxs-lookup"><span data-stu-id="bbe12-114">You can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="bbe12-115">La comptabilité globale des stocks ne prend actuellement pas en charge toutes les fonctionnalités de gestion des coûts intégrées à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bbe12-115">Global Inventory Accounting doesn't currently support all the cost management features that are built into Supply Chain Management.</span></span> <span data-ttu-id="bbe12-116">Par conséquent, il est important d’évaluer si l’ensemble de fonctionnalités actuellement disponible répondra à vos attentes.</span><span class="sxs-lookup"><span data-stu-id="bbe12-116">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a><span data-ttu-id="bbe12-117">Comment obtenir la version préliminaire de la comptabilité globale des stocks</span><span class="sxs-lookup"><span data-stu-id="bbe12-117">How to get the Global Inventory Accounting public preview</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbe12-118">Pour utiliser la comptabilité globale des stocks, vous devez disposer d’un environnement à haute disponibilité compatible LCS (et non d’un environnement OneBox).</span><span class="sxs-lookup"><span data-stu-id="bbe12-118">To use Global Inventory Accounting, you must have an LCS-enabled high-availability environment (not a OneBox environment).</span></span> <span data-ttu-id="bbe12-119">De plus, vous devez exécuter Supply Chain Management version 10.0.19 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="bbe12-119">Additionally, you must be running Supply Chain Management version 10.0.19 or later.</span></span>

<span data-ttu-id="bbe12-120">Pour vous inscrire à la version préliminaire publique de la comptabilité globale des stocks, envoyez votre ID d’environnement LCS par e-mail à l’[Équipe Comptabilité globale des stocks](mailto:GlobalInventoryAccounting@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="bbe12-120">To sign up for the Global Inventory Accounting public preview, send your LCS environment ID by email to the [Global Inventory Accounting team](mailto:GlobalInventoryAccounting@service.microsoft.com).</span></span> <span data-ttu-id="bbe12-121">Une fois que vous avez été approuvé pour le programme, l’équipe vous enverra un e-mail de suivi contenant une clé bêta de Comptabilité globale des stocks et vos points de terminaison de service.</span><span class="sxs-lookup"><span data-stu-id="bbe12-121">After you're approved for the program, the team will send you a follow-up email that contains a Global Inventory Accounting beta key and your service endpoints.</span></span> <span data-ttu-id="bbe12-122">Après avoir reçu la clé bêta, vous pourrez [installer le complément](#install).</span><span class="sxs-lookup"><span data-stu-id="bbe12-122">After you receive the beta key, you can [install the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="bbe12-123">Gestionnaire de licences</span><span class="sxs-lookup"><span data-stu-id="bbe12-123">Licensing</span></span>

<span data-ttu-id="bbe12-124">Le complément Comptabilité globale des stocks est concédé sous licence avec les fonctionnalités standard de la comptabilité des stocks disponibles pour Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bbe12-124">Global Inventory Accounting is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="bbe12-125">Vous n’avez pas besoin d’acheter une licence supplémentaire pour utiliser la comptabilité globale des stocks.</span><span class="sxs-lookup"><span data-stu-id="bbe12-125">You don't have to purchase an additional license to use Global Inventory Accounting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bbe12-126">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="bbe12-126">Prerequisites</span></span>

### <a name="set-up-microsoft-power-platform-integration"></a><span data-ttu-id="bbe12-127">Paramétrer l’intégration à Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="bbe12-127">Set up Microsoft Power Platform integration</span></span>

<span data-ttu-id="bbe12-128">Avant de pouvoir activer la fonctionnalité de complément, vous devez l’intégrer à Microsoft Power Platform en suivant les étapes ci-après.</span><span class="sxs-lookup"><span data-stu-id="bbe12-128">Before you can enable add-in functionality, you must integrate with Microsoft Power Platform by following these steps.</span></span>

1. <span data-ttu-id="bbe12-129">Ouvrez l’environnement LCS dans lequel vous souhaitez ajouter le service.</span><span class="sxs-lookup"><span data-stu-id="bbe12-129">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="bbe12-130">Accédez à **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="bbe12-131">Dans la section **Intégration Power Platform**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-131">In the **Power Platform Integration** section, select **Setup**.</span></span>
1. <span data-ttu-id="bbe12-132">Dans la boîte de dialogue **Configuration de l’environnement Power Platform**, cochez la case, puis sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-132">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="bbe12-133">En règle générale, la configuration prend entre 60 et 90 minutes.</span><span class="sxs-lookup"><span data-stu-id="bbe12-133">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="bbe12-134">Une fois la configuration de l’environnement Microsoft Power Platform terminée, la page affiche le nom de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="bbe12-134">After setup of the Microsoft Power Platform environment is completed, the page shows the name of your environment.</span></span> <span data-ttu-id="bbe12-135">De plus, la section **Intégration de Power Platform** affiche la déclaration suivante : « La configuration de l’environnement Power Platform est terminée. »</span><span class="sxs-lookup"><span data-stu-id="bbe12-135">Additionally, the **Power Platform Integration** section shows the statement, "Power Platform environment setup is complete."</span></span> <span data-ttu-id="bbe12-136">La comptabilité globale des stocks ne nécessite pas d’application à double écriture.</span><span class="sxs-lookup"><span data-stu-id="bbe12-136">Global Inventory Accounting doesn't require a dual-write application.</span></span>

<span data-ttu-id="bbe12-137">Pour plus d’informations, voir [Configurer après le déploiement de l’environnement](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span><span class="sxs-lookup"><span data-stu-id="bbe12-137">For more information, see [Set up after environment deployment](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span></span>

### <a name="set-up-dataverse"></a><span data-ttu-id="bbe12-138">Configuration de Dataverse</span><span class="sxs-lookup"><span data-stu-id="bbe12-138">Set up Dataverse</span></span>

<span data-ttu-id="bbe12-139">Avant de configurer Dataverse, ajoutez les principaux de service Comptabilité globale des stocks à votre locataire en suivant les étapes ci-après.</span><span class="sxs-lookup"><span data-stu-id="bbe12-139">Before you set up Dataverse, add the Global Inventory Accounting service principles to your tenant by following these steps.</span></span>

1. <span data-ttu-id="bbe12-140">Installez le module Azure AD pour Windows PowerShell v2 comme décrit dans [Installer Azure Active Directory PowerShell pour Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="bbe12-140">Install Azure AD Module for Windows PowerShell v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
1. <span data-ttu-id="bbe12-141">Exécutez la commande suivante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbe12-141">Run the following PowerShell command.</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

<span data-ttu-id="bbe12-142">Ensuite, créez des utilisateurs d’application pour la comptabilité globale des stocks dans Dataverse en suivant les étapes ci-après.</span><span class="sxs-lookup"><span data-stu-id="bbe12-142">Next, create application users for Global Inventory Accounting in Dataverse by following these steps.</span></span>

1. <span data-ttu-id="bbe12-143">Ouvrez l’URL de votre environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="bbe12-143">Open the URL of your Dataverse environment.</span></span>
1. <span data-ttu-id="bbe12-144">Aller à **Paramètre avancé \> Système \> Sécurité \> Utilisateurs** et créez un utilisateur d’application.</span><span class="sxs-lookup"><span data-stu-id="bbe12-144">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="bbe12-145">Utilisez le champ **Vue** pour changer la vue de page en *Utilisateurs de l’application*.</span><span class="sxs-lookup"><span data-stu-id="bbe12-145">Use the **View** field to change the page view to *Application users*.</span></span>
1. <span data-ttu-id="bbe12-146">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-146">Select **New**.</span></span>
1. <span data-ttu-id="bbe12-147">Définissez le champ **ID application** sur *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span><span class="sxs-lookup"><span data-stu-id="bbe12-147">Set the **Application ID** field to *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span></span>
1. <span data-ttu-id="bbe12-148">Sélectionner **Attribuer un rôle**, puis *Administrateur système*.</span><span class="sxs-lookup"><span data-stu-id="bbe12-148">Select **Assign Role**, and then select *System Administrator*.</span></span> <span data-ttu-id="bbe12-149">S’il y a un rôle nommé *Utilisateur Common Data Service*, sélectionnez-le aussi.</span><span class="sxs-lookup"><span data-stu-id="bbe12-149">If there is a role that is named *Common Data Service User*, select it too.</span></span>
1. <span data-ttu-id="bbe12-150">Répétez les étapes précédentes, mais définissez le champ **ID d’application** sur *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span><span class="sxs-lookup"><span data-stu-id="bbe12-150">Repeat the preceding steps, but set the **Application ID** field to *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span></span>

<span data-ttu-id="bbe12-151">Pour plus d’informations, voir [Créer un utilisateur d’application](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="bbe12-151">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

<span data-ttu-id="bbe12-152">Si la langue par défaut de votre installation Dataverse n’est pas l’anglais, suivez les étapes ci-après.</span><span class="sxs-lookup"><span data-stu-id="bbe12-152">If the default language of your Dataverse installation isn't English, follow these steps.</span></span>

1. <span data-ttu-id="bbe12-153">Accédez à **Paramètres avancés \> Administration \> Langues**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-153">Go to **Advanced Setting \> Administration \> Languages**.</span></span>
1. <span data-ttu-id="bbe12-154">Sélectionnez *Anglais* (*LanguageCode=1033*), puis sélectionnez **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-154">Select *English* (*LanguageCode=1033*), and then select **Apply**.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="bbe12-155">Installer le complément</span><span class="sxs-lookup"><span data-stu-id="bbe12-155">Install the add-in</span></span>

<span data-ttu-id="bbe12-156">Suivez ces étapes pour installer le complément afin de pouvoir utiliser la comptabilité globale des stocks.</span><span class="sxs-lookup"><span data-stu-id="bbe12-156">Follow these steps to install the add-in so that you can use Global Inventory Accounting.</span></span>

1. <span data-ttu-id="bbe12-157">[S’inscrire](#sign-up) pour la version préliminaire de Comptabilité globale des stocks.</span><span class="sxs-lookup"><span data-stu-id="bbe12-157">[Sign up](#sign-up) for the Global Inventory Accounting public preview.</span></span>
1. <span data-ttu-id="bbe12-158">Connectez-vous à [LCS](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="bbe12-158">Sign in to [LCS](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="bbe12-159">Accédez à **Gestion des fonctionnalités d’aperçu**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-159">Go to **Preview feature management**.</span></span>
1. <span data-ttu-id="bbe12-160">Sélectionnez le signe plus (**+**).</span><span class="sxs-lookup"><span data-stu-id="bbe12-160">Select the plus sign (**+**).</span></span>
1. <span data-ttu-id="bbe12-161">Dans le champ **Code**, entrez votre clé bêta du complément Comptabilité globale des stocks.</span><span class="sxs-lookup"><span data-stu-id="bbe12-161">In the **Code** field, enter your add-in beta key for Global Inventory Accounting.</span></span> <span data-ttu-id="bbe12-162">(Vous devriez avoir reçu votre clé bêta par e-mail lors de votre inscription.)</span><span class="sxs-lookup"><span data-stu-id="bbe12-162">(You should have received your beta key by email when you signed up.)</span></span>
1. <span data-ttu-id="bbe12-163">Sélectionnez **Débloquer**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-163">Select **Unblock**.</span></span>
1. <span data-ttu-id="bbe12-164">Ouvrez l’environnement LCS dans lequel vous souhaitez ajouter le service.</span><span class="sxs-lookup"><span data-stu-id="bbe12-164">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="bbe12-165">Accédez à **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-165">Go to **Full details**.</span></span>
1. <span data-ttu-id="bbe12-166">Accédez à **Intégration Power Platform** et sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-166">Go to **Power Platform Integration**, and select **Setup**.</span></span>
1. <span data-ttu-id="bbe12-167">Dans la boîte de dialogue **Configuration de l’environnement Power Platform**, cochez la case, puis sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-167">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="bbe12-168">En règle générale, la configuration prend entre 60 et 90 minutes.</span><span class="sxs-lookup"><span data-stu-id="bbe12-168">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="bbe12-169">Une fois la configuration de l’environnement Microsoft Power Platform terminée, dans le raccourci **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-169">After setup of the Microsoft Power Platform environment is completed, on the **Environment add-ins** FastTab, select **Install a new add-in**.</span></span>
1. <span data-ttu-id="bbe12-170">Sélectionnez **Comptabilité globale des stocks**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-170">Select **Global inventory accounting**.</span></span>
1. <span data-ttu-id="bbe12-171">Suivez le guide d’installation, et acceptez les conditions générales du contrat.</span><span class="sxs-lookup"><span data-stu-id="bbe12-171">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="bbe12-172">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-172">Select **Install**.</span></span>
1. <span data-ttu-id="bbe12-173">Dans le raccourci **Compléments d’environnement**, vous devriez voir que le complément Comptabilité globale des stocks est en cours d’installation.</span><span class="sxs-lookup"><span data-stu-id="bbe12-173">On the **Environment add-ins** FastTab, you should see that Global Inventory Accounting is being installed.</span></span> <span data-ttu-id="bbe12-174">Après quelques minutes, le statut devrait passer de *Installation* à *Installé*.</span><span class="sxs-lookup"><span data-stu-id="bbe12-174">After a few minutes, the status should change from *Installing* to *Installed*.</span></span> <span data-ttu-id="bbe12-175">(Vous devrez peut-être actualiser la page pour voir cette modification.) À ce stade, le complément Comptabilité globale des stocks est prêt à être utilisé.</span><span class="sxs-lookup"><span data-stu-id="bbe12-175">(You might have to refresh the page to see this change.) At that point, Global Inventory Accounting is ready to use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="bbe12-176">Paramétrage de l’intégration</span><span class="sxs-lookup"><span data-stu-id="bbe12-176">Set up the integration</span></span>

<span data-ttu-id="bbe12-177">Suivez les étapes ci-après pour configurer l’intégration entre Comptabilité globale des stocks et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bbe12-177">Follow these steps to set up the integration between Global Inventory Accounting and Supply Chain Management.</span></span>

1. <span data-ttu-id="bbe12-178">Connectez-vous à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bbe12-178">Sign in to Supply Chain Management.</span></span>
1. <span data-ttu-id="bbe12-179">Accédez à **Administration système \> Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-179">Go to **System administration \> Feature Management**.</span></span>
1. <span data-ttu-id="bbe12-180">Sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-180">Select **Check for updates**.</span></span>
1. <span data-ttu-id="bbe12-181">Sur l’onglet **Tout**, recherchez l’entité nommée *Comptabilité globale des stocks*.</span><span class="sxs-lookup"><span data-stu-id="bbe12-181">On the **All** tab, search for the feature that is named *Global inventory accounting*.</span></span>
1. <span data-ttu-id="bbe12-182">Sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-182">Select **Enable now**.</span></span>
1. <span data-ttu-id="bbe12-183">Accédez à **Comptabilité globale des stocks \> Installer \> Paramètres de la comptabilité globale des stocks \> Paramètres d’intégration**.</span><span class="sxs-lookup"><span data-stu-id="bbe12-183">Go to **Global inventory accounting \> Setup \> Global inventory accounting parameters \> Integrations parameters**.</span></span>
1. <span data-ttu-id="bbe12-184">Dans les champs **Point de terminaison du service de données** et **Point de terminaison de Comptabilité globale des stocks**, saisissez les URL de l’e-mail que l’équipe Comptabilité globale des stocks vous a envoyé lorsque vous vous êtes inscrit à la version préliminaire.</span><span class="sxs-lookup"><span data-stu-id="bbe12-184">In the **Data service endpoint** and **Global inventory accounting endpoint** fields, enter the URLs from the email that the Global Inventory Accounting team sent when you signed up for the preview.</span></span>

<span data-ttu-id="bbe12-185">Comptabilité globale des stocks est maintenant prêt à être utilisé.</span><span class="sxs-lookup"><span data-stu-id="bbe12-185">Global Inventory Accounting is now ready to use.</span></span>
