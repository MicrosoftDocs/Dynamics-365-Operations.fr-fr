---
title: Authentification
description: ''
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 025feca31eed8649bc319a1e1a1b6d1af3ddb128
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009064"
---
# <a name="authentication"></a><span data-ttu-id="d809f-102">Authentification</span><span class="sxs-lookup"><span data-stu-id="d809f-102">Authentication</span></span>

<span data-ttu-id="d809f-103">Cet article fournit des informations générales sur la façon de s'authentifier auprès de l'interface de programmation d'application de données (API) de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d809f-103">This article provides overview information about how to authenticate with the Microsoft Dynamics 365 Human Resources data application programming interface (API).</span></span>

## <a name="overview"></a><span data-ttu-id="d809f-104">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="d809f-104">Overview</span></span>

<span data-ttu-id="d809f-105">L'API de données pour Human Resources est une implémentation OData.</span><span class="sxs-lookup"><span data-stu-id="d809f-105">The data API for Human Resources is an OData implementation.</span></span> <span data-ttu-id="d809f-106">Pour plus d'informations, voir [Protocole Open Data (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span><span class="sxs-lookup"><span data-stu-id="d809f-106">For more information, see [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span></span>

<span data-ttu-id="d809f-107">Votre application doit s'authentifier en tant qu'appelant autorisé avant que l'API ne traite les demandes de votre application.</span><span class="sxs-lookup"><span data-stu-id="d809f-107">Your application must authenticate as an authorized caller before the API will service requests from your application.</span></span>

## <a name="fundamentals"></a><span data-ttu-id="d809f-108">Principes fondamentaux</span><span class="sxs-lookup"><span data-stu-id="d809f-108">Fundamentals</span></span>

<span data-ttu-id="d809f-109">Pour appeler l'API de données, votre application doit acquérir un jeton d'accès à partir de la plate-forme d'identité Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d809f-109">To call the data API, your application must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="d809f-110">Le jeton d'accès contient des informations sur votre application et l'autorisation dont elle dispose pour appeler des ressources dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d809f-110">The access token contains information about your application and the permission that it has to call resources in Human Resources.</span></span>

### <a name="access-token"></a><span data-ttu-id="d809f-111">Jeton d'accès</span><span class="sxs-lookup"><span data-stu-id="d809f-111">Access token</span></span>

<span data-ttu-id="d809f-112">Les jetons d'accès émis par la plate-forme d'identité Microsoft sont des jetons Web (JWT) JavaScript Object Notation (JSON) codés en base64.</span><span class="sxs-lookup"><span data-stu-id="d809f-112">Access tokens issued by the Microsoft identity platform are base64–encoded JavaScript Object Notation (JSON) Web Tokens (JWTs).</span></span> <span data-ttu-id="d809f-113">Ils contiennent des informations (revendications) que l'API de données (et d'autres API Web sécurisées par la plate-forme d'identité Microsoft) utilisent pour valider l'appelant et s'assurer que l'appelant dispose des autorisations appropriées pour effectuer l'opération qu'il demande.</span><span class="sxs-lookup"><span data-stu-id="d809f-113">They contain information (claims) that the data API (and other web APIs that are secured by the Microsoft identity platform) use to validate the caller and make sure that the caller has the correct permissions to perform the operation they're requesting.</span></span> <span data-ttu-id="d809f-114">Pendant les appels, vous pouvez traiter les jetons d'accès comme opaques.</span><span class="sxs-lookup"><span data-stu-id="d809f-114">During calls, you can treat access tokens as opaque.</span></span> <span data-ttu-id="d809f-115">Vous devez toujours transmettre les jetons d'accès sur un canal sécurisé, tel que TLS (Transport Layer Security) et HTTPS (Hypertext Transfer Protocol Secure).</span><span class="sxs-lookup"><span data-stu-id="d809f-115">You should always transmit access tokens over a secure channel, such as Transport Layer Security (TLS) and Hypertext Transfer Protocol Secure (HTTPS).</span></span>

<span data-ttu-id="d809f-116">Voici un exemple de jeton d'accès émis par la plate-forme d'identité Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d809f-116">Here is an example of an access token that is issued by the Microsoft identity platform.</span></span>

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

<span data-ttu-id="d809f-117">Pour appeler l'API de données, vous attachez le jeton d'accès en tant que jeton détenteur à l'en-tête d'autorisation dans votre demande HTTP.</span><span class="sxs-lookup"><span data-stu-id="d809f-117">To call the data API, you attach the access token as a bearer token to the authorization header in your HTTP request.</span></span> <span data-ttu-id="d809f-118">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="d809f-118">Here is an example.</span></span>

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a><span data-ttu-id="d809f-119">Enregistrement d'une nouvelle application à l'aide du portail Azure</span><span class="sxs-lookup"><span data-stu-id="d809f-119">Register a new application by using the Azure portal</span></span>

1. <span data-ttu-id="d809f-120">Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) avec un compte professionnel ou scolaire ou un compte personnel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d809f-120">Sign in to the [Microsoft Azure portal](https://portal.azure.com) with a work or school account, or a personal Microsoft account.</span></span>

2. <span data-ttu-id="d809f-121">Si votre compte vous donne accès à plusieurs locataires, sélectionnez votre compte dans le coin supérieur droit et définissez votre session de portail sur le locataire Azure Active Directory (Azure AD) que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="d809f-121">If your account gives you access to more than one tenant, select your account in the upper-right corner, and set your portal session to the Azure Active Directory (Azure AD) tenant that you want.</span></span>

3. <span data-ttu-id="d809f-122">Dans le volet gauche, sélectionnez le service **Azure Active Directory**, puis sélectionnez **Enregistrements d'applications \>Nouvel enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="d809f-122">In the left pane, select the **Azure Active Directory** service, and then select **App registrations \> New registration**.</span></span>

4. <span data-ttu-id="d809f-123">Quand la page **Enregistrer une application**apparaît, entrez les informations d'enregistrement de votre application :</span><span class="sxs-lookup"><span data-stu-id="d809f-123">When the **Register an application** page appears, enter your application's registration information:</span></span>

    - <span data-ttu-id="d809f-124">**Nom** : entrez un nom d'application significatif qui sera affiché aux utilisateurs de l'application.</span><span class="sxs-lookup"><span data-stu-id="d809f-124">**Name**: Enter a meaningful application name that will be shown to users of the app.</span></span>
    - <span data-ttu-id="d809f-125">**Types de compte pris en charge** : sélectionnez les types de compte que votre application doit prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="d809f-125">**Supported account types**: Select the types of accounts that your app should support.</span></span>

        | <span data-ttu-id="d809f-126">Types de compte pris en charge</span><span class="sxs-lookup"><span data-stu-id="d809f-126">Supported account types</span></span> | <span data-ttu-id="d809f-127">Description</span><span class="sxs-lookup"><span data-stu-id="d809f-127">Description</span></span> |
        |-------------------------|-------------|
        | <span data-ttu-id="d809f-128">Comptes dans ce répertoire organisationnel uniquement</span><span class="sxs-lookup"><span data-stu-id="d809f-128">Accounts in this organizational directory only</span></span> | <span data-ttu-id="d809f-129">Sélectionnez cette option si vous créez une application métier.</span><span class="sxs-lookup"><span data-stu-id="d809f-129">Select this option if you're building a line-of-business app.</span></span> <span data-ttu-id="d809f-130">Cette option n'est disponible que si vous enregistrez l'application dans un répertoire.</span><span class="sxs-lookup"><span data-stu-id="d809f-130">This option isn't available unless you're registering the app in a directory.</span></span><p><span data-ttu-id="d809f-131">Cette option est mappée sur **locataire unique Azure AD seulement**.</span><span class="sxs-lookup"><span data-stu-id="d809f-131">This option is mapped to **Azure AD only single-tenant**.</span></span></p><p><span data-ttu-id="d809f-132">Cette option est l'option par défaut, sauf si vous enregistrez l'application en dehors d'un répertoire.</span><span class="sxs-lookup"><span data-stu-id="d809f-132">This option is the default option unless you're registering the app outside a directory.</span></span> <span data-ttu-id="d809f-133">Dans ce cas, l'option par défaut est **Comptes Microsoft multi-locataires et personnels Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="d809f-133">In that case, the default option is **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p> |
        | <span data-ttu-id="d809f-134">Comptes dans un répertoire organisationnel</span><span class="sxs-lookup"><span data-stu-id="d809f-134">Accounts in any organizational directory</span></span> | <span data-ttu-id="d809f-135">Sélectionnez cette option pour cibler tous les clients professionnels et éducatifs.</span><span class="sxs-lookup"><span data-stu-id="d809f-135">Select this option to target all business and educational customers.</span></span><p><span data-ttu-id="d809f-136">Cette option est mappée sur **Multi-locataire Azure AD seulement**.</span><span class="sxs-lookup"><span data-stu-id="d809f-136">This option is mapped to **Azure AD only multi-tenant**.</span></span></p><p><span data-ttu-id="d809f-137">Si vous avez enregistré l'application en tant que **Locataire unique Azure AD seulement**, vous pouvez utiliser le panneau **Authentification** pour la mettre à jour sur **Multi-locataire Azure AD seulement** puis revenir à **Locataire unique Azure AD seulement**.</span><span class="sxs-lookup"><span data-stu-id="d809f-137">If you registered the app as **Azure AD only single-tenant**, you can use the **Authentication** blade to update it to **Azure AD only multi-tenant** and then back to **Azure AD only single-tenant**.</span></span></p> |
        | <span data-ttu-id="d809f-138">Comptes dans n'importe quel répertoire organisationnel et comptes Microsoft personnels</span><span class="sxs-lookup"><span data-stu-id="d809f-138">Accounts in any organizational directory and personal Microsoft accounts</span></span> | <span data-ttu-id="d809f-139">Sélectionnez cette option pour cibler le plus grand nombre de clients.</span><span class="sxs-lookup"><span data-stu-id="d809f-139">Select this option to target the widest set of customers.</span></span><p><span data-ttu-id="d809f-140">Cette option est mappée sur **Comptes Microsoft multi-locataires et personnels Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="d809f-140">This option is mapped to **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p><p><span data-ttu-id="d809f-141">Si vous avez enregistré l'application en tant que **Comptes Microsoft multi-locataires et personnels Azure AD**, vous ne pouvez pas modifier ce paramètre dans l'interface utilisateur (UI).</span><span class="sxs-lookup"><span data-stu-id="d809f-141">If you registered the app as **Azure AD multi-tenant and personal Microsoft accounts**, you can't change this setting in the user interface (UI).</span></span> <span data-ttu-id="d809f-142">Au lieu de cela, vous devez utiliser l'éditeur de manifeste d'application pour modifier les types de compte pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d809f-142">Instead, you must use the application manifest editor to change the supported account types.</span></span></p> |

    - <span data-ttu-id="d809f-143">**URI de redirection (facultatif)** - Sélectionnez le type d'application que vous créez : **Web** ou **Client public (mobile et bureau)**.</span><span class="sxs-lookup"><span data-stu-id="d809f-143">**Redirect URI (optional)** – Select the type of app that you're building: **Web** or **Public client (mobile & desktop)**.</span></span> <span data-ttu-id="d809f-144">Saisissez ensuite l'URI de redirection (ou l'URL de réponse) pour l'application.</span><span class="sxs-lookup"><span data-stu-id="d809f-144">Then enter the redirect URI (or reply URL) for the app.</span></span>

        - <span data-ttu-id="d809f-145">Pour les applications Web, indiquez l'URL de base de l'application.</span><span class="sxs-lookup"><span data-stu-id="d809f-145">For web apps, provide the base URL of the app.</span></span> <span data-ttu-id="d809f-146">Par exemple, `http://localhost:31544`peut être l'URL d'une application Web qui s'exécute sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d809f-146">For example, `http://localhost:31544` might be the URL for a web app that runs on your local machine.</span></span> <span data-ttu-id="d809f-147">Les utilisateurs utilisent ensuite cette URL pour se connecter à une application client Web.</span><span class="sxs-lookup"><span data-stu-id="d809f-147">Users then use this URL to sign in to a web client app.</span></span>
        - <span data-ttu-id="d809f-148">Pour les applications clientes publiques, fournissez l'URI qu'Azure AD utilise pour renvoyer des réponses à jeton.</span><span class="sxs-lookup"><span data-stu-id="d809f-148">For public client apps, provide the URI that Azure AD uses to return token responses.</span></span> <span data-ttu-id="d809f-149">Entrez une valeur spécifique à votre application, telle que `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="d809f-149">Enter a value that is specific to your app, such as `myapp://auth`.</span></span>

        <span data-ttu-id="d809f-150">Pour voir des exemples spécifiques d'applications Web ou d'applications natives, consultez les démarrages rapides dans [Plate-forme d'identité Microsoft (anciennement Azure Active Directory pour les développeurs)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="d809f-150">To see specific examples for web apps or native apps, see the quickstarts in [Microsoft identity platform (formerly Azure Active Directory for developers)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span></span>

5. <span data-ttu-id="d809f-151">Sous **Autorisations API**, sélectionnez **Ajouter une autorisation**.</span><span class="sxs-lookup"><span data-stu-id="d809f-151">Under **API permissions**, select **Add a permission**.</span></span> <span data-ttu-id="d809f-152">Ensuite, dans l'onglet **API que mon organisation utilise**, recherchez **Dynamics 365 Human Resources**, et ajoutez l'autorisation **user\_impersonation** à votre application.</span><span class="sxs-lookup"><span data-stu-id="d809f-152">Then, on the **APIs my organization uses** tab, search for **Dynamics 365 Human Resources**, and add the **user\_impersonation** permission to your app.</span></span> <span data-ttu-id="d809f-153">L'ID d'application pour Human Resources est f9be0c49-aa22-4ec6-911a-c5da515226ff.</span><span class="sxs-lookup"><span data-stu-id="d809f-153">The Application ID for Human Resources is f9be0c49-aa22-4ec6-911a-c5da515226ff.</span></span> <span data-ttu-id="d809f-154">Utilisez cet ID pour vous assurer que vous avez choisi la bonne application.</span><span class="sxs-lookup"><span data-stu-id="d809f-154">Use this ID to ensure you have chosen the correct application.</span></span>

6. <span data-ttu-id="d809f-155">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d809f-155">Select **Register**.</span></span>

   <span data-ttu-id="d809f-156">[![Enregistrement d'une nouvelle application dans le portail Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d809f-156">[![Registering a new app in the Azure portal](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span></span>

<span data-ttu-id="d809f-157">Azure AD attribue un ID d'application unique (ID client) à votre application et vous amène à la page **Aperçu** pour votre application.</span><span class="sxs-lookup"><span data-stu-id="d809f-157">Azure AD assigns a unique application ID (client ID) to your app, and takes you to the **Overview** page for your app.</span></span> <span data-ttu-id="d809f-158">Pour ajouter plus de fonctionnalités à votre application, vous pouvez sélectionner d'autres options de configuration, telles que des options de personnalisation et de certificats et secrets.</span><span class="sxs-lookup"><span data-stu-id="d809f-158">To add more capabilities to your app, you can select other configuration options, such as options for branding and for certificates and secrets.</span></span>

## <a name="retrieving-an-access-token"></a><span data-ttu-id="d809f-159">Récupération d'un jeton d'accès</span><span class="sxs-lookup"><span data-stu-id="d809f-159">Retrieving an access token</span></span>

<span data-ttu-id="d809f-160">Les détails sur la façon dont vous récupérez un jeton d'accès pour appeler l'API de données de Human Resources dépendront des technologies que vous utilisez pour développer votre application client.</span><span class="sxs-lookup"><span data-stu-id="d809f-160">The specifics of how you retrieve an access token for calling the Human Resources data API will depend on what technologies you're using to develop your client application.</span></span> <span data-ttu-id="d809f-161">Par exemple, vous pourriez faire un [test avec un utilitaire tiers](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (tel que Postman), développer une application de console C# ou un service Web, ou créer un client javascript/TypeScript.</span><span class="sxs-lookup"><span data-stu-id="d809f-161">For example, you might be [testing with a third party utility](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (such as Postman), developing a C# console application or web service, or building a javascript/TypeScript client.</span></span>

<span data-ttu-id="d809f-162">Exemple d'application client C# :</span><span class="sxs-lookup"><span data-stu-id="d809f-162">Example C# client application:</span></span>
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

<span data-ttu-id="d809f-163">Une fois que vous avez récupéré un jeton d'accès, vous passerez le jeton dans l'en-tête Autorisation en tant que jeton détenteur avec chaque demande que vous envoyez à l'API de données, comme décrit ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="d809f-163">Once you've retrieved an access token, you'll pass the token in the Authorization header as a bearer token with each request you send to the data API, as described above.</span></span>
