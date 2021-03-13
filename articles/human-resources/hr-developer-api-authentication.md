---
title: Authentification
description: Cet article fournit des informations générales sur la façon de s'authentifier auprès de l'interface de programmation d'application de données (API) de Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 963bec2b817c59e3b5860c5ff5885e165ec8656a
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115558"
---
# <a name="authentication"></a><span data-ttu-id="0bc68-103">Authentification</span><span class="sxs-lookup"><span data-stu-id="0bc68-103">Authentication</span></span>

<span data-ttu-id="0bc68-104">Cet article fournit des informations générales sur la façon de s'authentifier auprès de l'interface de programmation d'application de données (API) de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0bc68-104">This article provides overview information about how to authenticate with the Microsoft Dynamics 365 Human Resources data application programming interface (API).</span></span>

## <a name="overview"></a><span data-ttu-id="0bc68-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="0bc68-105">Overview</span></span>

<span data-ttu-id="0bc68-106">L'API de données pour Human Resources est une implémentation OData.</span><span class="sxs-lookup"><span data-stu-id="0bc68-106">The data API for Human Resources is an OData implementation.</span></span> <span data-ttu-id="0bc68-107">Pour plus d'informations, voir [Protocole Open Data (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span><span class="sxs-lookup"><span data-stu-id="0bc68-107">For more information, see [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span></span>

<span data-ttu-id="0bc68-108">Votre application doit s'authentifier en tant qu'appelant autorisé avant que l'API ne traite les demandes de votre application.</span><span class="sxs-lookup"><span data-stu-id="0bc68-108">Your application must authenticate as an authorized caller before the API will service requests from your application.</span></span>

## <a name="fundamentals"></a><span data-ttu-id="0bc68-109">Principes fondamentaux</span><span class="sxs-lookup"><span data-stu-id="0bc68-109">Fundamentals</span></span>

<span data-ttu-id="0bc68-110">Pour appeler l'API de données, votre application doit acquérir un jeton d'accès à partir de la plate-forme d'identité Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bc68-110">To call the data API, your application must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="0bc68-111">Le jeton d'accès contient des informations sur votre application et l'autorisation dont elle dispose pour appeler des ressources dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0bc68-111">The access token contains information about your application and the permission that it has to call resources in Human Resources.</span></span>

### <a name="access-token"></a><span data-ttu-id="0bc68-112">Jeton d'accès</span><span class="sxs-lookup"><span data-stu-id="0bc68-112">Access token</span></span>

<span data-ttu-id="0bc68-113">Les jetons d'accès émis par la plate-forme d'identité Microsoft sont des jetons Web (JWT) JavaScript Object Notation (JSON) codés en base64.</span><span class="sxs-lookup"><span data-stu-id="0bc68-113">Access tokens issued by the Microsoft identity platform are base64–encoded JavaScript Object Notation (JSON) Web Tokens (JWTs).</span></span> <span data-ttu-id="0bc68-114">Ils contiennent des informations (revendications) que l'API de données (et d'autres API Web sécurisées par la plate-forme d'identité Microsoft) utilisent pour valider l'appelant et s'assurer que l'appelant dispose des autorisations appropriées pour effectuer l'opération qu'il demande.</span><span class="sxs-lookup"><span data-stu-id="0bc68-114">They contain information (claims) that the data API (and other web APIs that are secured by the Microsoft identity platform) use to validate the caller and make sure that the caller has the correct permissions to perform the operation they're requesting.</span></span> <span data-ttu-id="0bc68-115">Pendant les appels, vous pouvez traiter les jetons d'accès comme opaques.</span><span class="sxs-lookup"><span data-stu-id="0bc68-115">During calls, you can treat access tokens as opaque.</span></span> <span data-ttu-id="0bc68-116">Vous devez toujours transmettre les jetons d'accès sur un canal sécurisé, tel que TLS (Transport Layer Security) et HTTPS (Hypertext Transfer Protocol Secure).</span><span class="sxs-lookup"><span data-stu-id="0bc68-116">You should always transmit access tokens over a secure channel, such as Transport Layer Security (TLS) and Hypertext Transfer Protocol Secure (HTTPS).</span></span>

<span data-ttu-id="0bc68-117">Voici un exemple de jeton d'accès émis par la plate-forme d'identité Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bc68-117">Here is an example of an access token that is issued by the Microsoft identity platform.</span></span>

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

<span data-ttu-id="0bc68-118">Pour appeler l'API de données, vous attachez le jeton d'accès en tant que jeton détenteur à l'en-tête d'autorisation dans votre demande HTTP.</span><span class="sxs-lookup"><span data-stu-id="0bc68-118">To call the data API, you attach the access token as a bearer token to the authorization header in your HTTP request.</span></span> <span data-ttu-id="0bc68-119">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="0bc68-119">Here is an example.</span></span>

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a><span data-ttu-id="0bc68-120">Enregistrement d'une nouvelle application à l'aide du portail Azure</span><span class="sxs-lookup"><span data-stu-id="0bc68-120">Register a new application by using the Azure portal</span></span>

1. <span data-ttu-id="0bc68-121">Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) avec un compte professionnel ou scolaire ou un compte personnel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bc68-121">Sign in to the [Microsoft Azure portal](https://portal.azure.com) with a work or school account, or a personal Microsoft account.</span></span>

2. <span data-ttu-id="0bc68-122">Si votre compte vous donne accès à plusieurs locataires, sélectionnez votre compte dans le coin supérieur droit et définissez votre session de portail sur le locataire Azure Active Directory (Azure AD) que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="0bc68-122">If your account gives you access to more than one tenant, select your account in the upper-right corner, and set your portal session to the Azure Active Directory (Azure AD) tenant that you want.</span></span>

3. <span data-ttu-id="0bc68-123">Dans le volet gauche, sélectionnez le service **Azure Active Directory**, puis sélectionnez **Enregistrements d'applications \>Nouvel enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="0bc68-123">In the left pane, select the **Azure Active Directory** service, and then select **App registrations \> New registration**.</span></span>

4. <span data-ttu-id="0bc68-124">Quand la page **Enregistrer une application** apparaît, entrez les informations d'enregistrement de votre application :</span><span class="sxs-lookup"><span data-stu-id="0bc68-124">When the **Register an application** page appears, enter your application's registration information:</span></span>

    - <span data-ttu-id="0bc68-125">**Nom** : entrez un nom d'application significatif qui sera affiché aux utilisateurs de l'application.</span><span class="sxs-lookup"><span data-stu-id="0bc68-125">**Name**: Enter a meaningful application name that will be shown to users of the app.</span></span>
    - <span data-ttu-id="0bc68-126">**Types de compte pris en charge** : sélectionnez les types de compte que votre application doit prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="0bc68-126">**Supported account types**: Select the types of accounts that your app should support.</span></span>

        | <span data-ttu-id="0bc68-127">Types de compte pris en charge</span><span class="sxs-lookup"><span data-stu-id="0bc68-127">Supported account types</span></span> | <span data-ttu-id="0bc68-128">Description</span><span class="sxs-lookup"><span data-stu-id="0bc68-128">Description</span></span> |
        |-------------------------|-------------|
        | <span data-ttu-id="0bc68-129">Comptes dans ce répertoire organisationnel uniquement</span><span class="sxs-lookup"><span data-stu-id="0bc68-129">Accounts in this organizational directory only</span></span> | <span data-ttu-id="0bc68-130">Sélectionnez cette option si vous créez une application métier.</span><span class="sxs-lookup"><span data-stu-id="0bc68-130">Select this option if you're building a line-of-business app.</span></span> <span data-ttu-id="0bc68-131">Cette option n'est disponible que si vous enregistrez l'application dans un répertoire.</span><span class="sxs-lookup"><span data-stu-id="0bc68-131">This option isn't available unless you're registering the app in a directory.</span></span><p><span data-ttu-id="0bc68-132">Cette option est mappée sur **locataire unique Azure AD seulement**.</span><span class="sxs-lookup"><span data-stu-id="0bc68-132">This option is mapped to **Azure AD only single-tenant**.</span></span></p><p><span data-ttu-id="0bc68-133">Cette option est l'option par défaut, sauf si vous enregistrez l'application en dehors d'un répertoire.</span><span class="sxs-lookup"><span data-stu-id="0bc68-133">This option is the default option unless you're registering the app outside a directory.</span></span> <span data-ttu-id="0bc68-134">Dans ce cas, l'option par défaut est **Comptes Microsoft multi-locataires et personnels Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="0bc68-134">In that case, the default option is **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p> |
        | <span data-ttu-id="0bc68-135">Comptes dans un répertoire organisationnel</span><span class="sxs-lookup"><span data-stu-id="0bc68-135">Accounts in any organizational directory</span></span> | <span data-ttu-id="0bc68-136">Sélectionnez cette option pour cibler tous les clients professionnels et éducatifs.</span><span class="sxs-lookup"><span data-stu-id="0bc68-136">Select this option to target all business and educational customers.</span></span><p><span data-ttu-id="0bc68-137">Cette option est mappée sur **Multi-locataire Azure AD seulement**.</span><span class="sxs-lookup"><span data-stu-id="0bc68-137">This option is mapped to **Azure AD only multi-tenant**.</span></span></p><p><span data-ttu-id="0bc68-138">Si vous avez enregistré l'application en tant que **Locataire unique Azure AD seulement**, vous pouvez utiliser le panneau **Authentification** pour la mettre à jour sur **Multi-locataire Azure AD seulement** puis revenir à **Locataire unique Azure AD seulement**.</span><span class="sxs-lookup"><span data-stu-id="0bc68-138">If you registered the app as **Azure AD only single-tenant**, you can use the **Authentication** blade to update it to **Azure AD only multi-tenant** and then back to **Azure AD only single-tenant**.</span></span></p> |
        | <span data-ttu-id="0bc68-139">Comptes dans n'importe quel répertoire organisationnel et comptes Microsoft personnels</span><span class="sxs-lookup"><span data-stu-id="0bc68-139">Accounts in any organizational directory and personal Microsoft accounts</span></span> | <span data-ttu-id="0bc68-140">Sélectionnez cette option pour cibler le plus grand nombre de clients.</span><span class="sxs-lookup"><span data-stu-id="0bc68-140">Select this option to target the widest set of customers.</span></span><p><span data-ttu-id="0bc68-141">Cette option est mappée sur **Comptes Microsoft multi-locataires et personnels Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="0bc68-141">This option is mapped to **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p><p><span data-ttu-id="0bc68-142">Si vous avez enregistré l'application en tant que **Comptes Microsoft multi-locataires et personnels Azure AD**, vous ne pouvez pas modifier ce paramètre dans l'interface utilisateur (UI).</span><span class="sxs-lookup"><span data-stu-id="0bc68-142">If you registered the app as **Azure AD multi-tenant and personal Microsoft accounts**, you can't change this setting in the user interface (UI).</span></span> <span data-ttu-id="0bc68-143">Au lieu de cela, vous devez utiliser l'éditeur de manifeste d'application pour modifier les types de compte pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0bc68-143">Instead, you must use the application manifest editor to change the supported account types.</span></span></p> |

    - <span data-ttu-id="0bc68-144">**URI de redirection (facultatif)** - Sélectionnez le type d'application que vous créez : **Web** ou **Client public (mobile et bureau)**.</span><span class="sxs-lookup"><span data-stu-id="0bc68-144">**Redirect URI (optional)** – Select the type of app that you're building: **Web** or **Public client (mobile & desktop)**.</span></span> <span data-ttu-id="0bc68-145">Saisissez ensuite l'URI de redirection (ou l'URL de réponse) pour l'application.</span><span class="sxs-lookup"><span data-stu-id="0bc68-145">Then enter the redirect URI (or reply URL) for the app.</span></span>

        - <span data-ttu-id="0bc68-146">Pour les applications Web, indiquez l'URL de base de l'application.</span><span class="sxs-lookup"><span data-stu-id="0bc68-146">For web apps, provide the base URL of the app.</span></span> <span data-ttu-id="0bc68-147">Par exemple, `http://localhost:31544`peut être l'URL d'une application Web qui s'exécute sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="0bc68-147">For example, `http://localhost:31544` might be the URL for a web app that runs on your local machine.</span></span> <span data-ttu-id="0bc68-148">Les utilisateurs utilisent ensuite cette URL pour se connecter à une application client Web.</span><span class="sxs-lookup"><span data-stu-id="0bc68-148">Users then use this URL to sign in to a web client app.</span></span>
        - <span data-ttu-id="0bc68-149">Pour les applications clientes publiques, fournissez l'URI qu'Azure AD utilise pour renvoyer des réponses à jeton.</span><span class="sxs-lookup"><span data-stu-id="0bc68-149">For public client apps, provide the URI that Azure AD uses to return token responses.</span></span> <span data-ttu-id="0bc68-150">Entrez une valeur spécifique à votre application, telle que `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="0bc68-150">Enter a value that is specific to your app, such as `myapp://auth`.</span></span>

        <span data-ttu-id="0bc68-151">Pour voir des exemples spécifiques d'applications Web ou d'applications natives, consultez les démarrages rapides dans [Plate-forme d'identité Microsoft (anciennement Azure Active Directory pour les développeurs)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="0bc68-151">To see specific examples for web apps or native apps, see the quickstarts in [Microsoft identity platform (formerly Azure Active Directory for developers)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span></span>

5. <span data-ttu-id="0bc68-152">Sous **Autorisations API**, sélectionnez **Ajouter une autorisation**.</span><span class="sxs-lookup"><span data-stu-id="0bc68-152">Under **API permissions**, select **Add a permission**.</span></span> <span data-ttu-id="0bc68-153">Ensuite, dans l'onglet **API que mon organisation utilise**, recherchez **Dynamics 365 Human Resources**, et ajoutez l'autorisation **user\_impersonation** à votre application.</span><span class="sxs-lookup"><span data-stu-id="0bc68-153">Then, on the **APIs my organization uses** tab, search for **Dynamics 365 Human Resources**, and add the **user\_impersonation** permission to your app.</span></span> <span data-ttu-id="0bc68-154">L'ID d'application pour Human Resources est f9be0c49-aa22-4ec6-911a-c5da515226ff.</span><span class="sxs-lookup"><span data-stu-id="0bc68-154">The Application ID for Human Resources is f9be0c49-aa22-4ec6-911a-c5da515226ff.</span></span> <span data-ttu-id="0bc68-155">Utilisez cet ID pour vous assurer que vous avez choisi la bonne application.</span><span class="sxs-lookup"><span data-stu-id="0bc68-155">Use this ID to ensure you have chosen the correct application.</span></span>

6. <span data-ttu-id="0bc68-156">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0bc68-156">Select **Register**.</span></span>

   <span data-ttu-id="0bc68-157">[![Enregistrement d'une nouvelle application dans le portail Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0bc68-157">[![Registering a new app in the Azure portal](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span></span>

<span data-ttu-id="0bc68-158">Azure AD attribue un ID d'application unique (ID client) à votre application et vous amène à la page **Aperçu** pour votre application.</span><span class="sxs-lookup"><span data-stu-id="0bc68-158">Azure AD assigns a unique application ID (client ID) to your app, and takes you to the **Overview** page for your app.</span></span> <span data-ttu-id="0bc68-159">Pour ajouter plus de fonctionnalités à votre application, vous pouvez sélectionner d'autres options de configuration, telles que des options de personnalisation et de certificats et secrets.</span><span class="sxs-lookup"><span data-stu-id="0bc68-159">To add more capabilities to your app, you can select other configuration options, such as options for branding and for certificates and secrets.</span></span>

## <a name="retrieving-an-access-token"></a><span data-ttu-id="0bc68-160">Récupération d'un jeton d'accès</span><span class="sxs-lookup"><span data-stu-id="0bc68-160">Retrieving an access token</span></span>

<span data-ttu-id="0bc68-161">Les détails sur la façon dont vous récupérez un jeton d'accès pour appeler l'API de données de Human Resources dépendront des technologies que vous utilisez pour développer votre application client.</span><span class="sxs-lookup"><span data-stu-id="0bc68-161">The specifics of how you retrieve an access token for calling the Human Resources data API will depend on what technologies you're using to develop your client application.</span></span> <span data-ttu-id="0bc68-162">Par exemple, vous pourriez faire un [test avec un utilitaire tiers](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (tel que Postman), développer une application de console C# ou un service Web, ou créer un client javascript/TypeScript.</span><span class="sxs-lookup"><span data-stu-id="0bc68-162">For example, you might be [testing with a third party utility](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (such as Postman), developing a C# console application or web service, or building a javascript/TypeScript client.</span></span>

<span data-ttu-id="0bc68-163">Exemple d'application client C# :</span><span class="sxs-lookup"><span data-stu-id="0bc68-163">Example C# client application:</span></span>
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

<span data-ttu-id="0bc68-164">Une fois que vous avez récupéré un jeton d'accès, vous passerez le jeton dans l'en-tête Autorisation en tant que jeton détenteur avec chaque demande que vous envoyez à l'API de données, comme décrit ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="0bc68-164">Once you've retrieved an access token, you'll pass the token in the Authorization header as a bearer token with each request you send to the data API, as described above.</span></span>
