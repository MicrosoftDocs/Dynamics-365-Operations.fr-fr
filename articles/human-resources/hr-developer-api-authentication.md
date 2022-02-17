---
title: Authentification
description: Cet article fournit des informations générales sur la façon de s’authentifier auprès de l’interface de programmation d’application de données (API) de Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3396f0ae6d089f43c39f318dc9d92a88a7db3d7c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070866"
---
# <a name="authentication"></a>Authentification


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article fournit des informations générales sur la façon de s’authentifier auprès de l’interface de programmation d’application de données (API) de Microsoft Dynamics 365 Human Resources.

## <a name="overview"></a>Vue d’ensemble

L’API de données pour Human Resources est une implémentation OData. Pour plus d’informations, voir [Protocole Open Data (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).

Votre application doit s’authentifier en tant qu’appelant autorisé avant que l’API ne traite les demandes de votre application.

## <a name="fundamentals"></a>Principes fondamentaux

Pour appeler l’API de données, votre application doit acquérir un jeton d’accès à partir de la plate-forme d’identité Microsoft. Le jeton d’accès contient des informations sur votre application et l’autorisation dont elle dispose pour appeler des ressources dans Human Resources.

### <a name="access-token"></a>Jeton d’accès

Les jetons d’accès émis par la plate-forme d’identité Microsoft sont des jetons Web (JWT) JavaScript Object Notation (JSON) codés en base64. Ils contiennent des informations (revendications) que l’API de données (et d’autres API Web sécurisées par la plate-forme d’identité Microsoft) utilisent pour valider l’appelant et s’assurer que l’appelant dispose des autorisations appropriées pour effectuer l’opération qu’il demande. Pendant les appels, vous pouvez traiter les jetons d’accès comme opaques. Vous devez toujours transmettre les jetons d’accès sur un canal sécurisé, tel que TLS (Transport Layer Security) et HTTPS (Hypertext Transfer Protocol Secure).

Voici un exemple de jeton d’accès émis par la plate-forme d’identité Microsoft.

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

Pour appeler l’API de données, vous attachez le jeton d’accès en tant que jeton détenteur à l’en-tête d’autorisation dans votre demande HTTP. Voici un exemple :

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a>Enregistrement d’une nouvelle application à l’aide du portail Azure

1. Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) avec un compte professionnel ou scolaire ou un compte personnel Microsoft.

2. Si votre compte vous donne accès à plusieurs locataires, sélectionnez votre compte dans le coin supérieur droit et définissez votre session de portail sur le locataire Azure Active Directory (Azure AD) que vous souhaitez.

3. Dans le volet gauche, sélectionnez le service **Azure Active Directory**, puis sélectionnez **Enregistrements d’applications \>Nouvel enregistrement**.

4. Quand la page **Enregistrer une application** apparaît, entrez les informations d’enregistrement de votre application :

    - **Nom** : entrez un nom d’application significatif qui sera affiché aux utilisateurs de l’application.
    - **Types de compte pris en charge** : sélectionnez les types de compte que votre application doit prendre en charge.

        | Types de compte pris en charge | Description |
        |-------------------------|-------------|
        | Comptes dans ce répertoire organisationnel uniquement | Sélectionnez cette option si vous créez une application métier. Cette option n’est disponible que si vous enregistrez l’application dans un répertoire.<p>Cette option est mappée sur **locataire unique Azure AD seulement**.</p><p>Cette option est l’option par défaut, sauf si vous enregistrez l’application en dehors d’un répertoire. Dans ce cas, l’option par défaut est **Comptes Microsoft multi-locataires et personnels Azure AD**.</p> |
        | Comptes dans un répertoire organisationnel | Sélectionnez cette option pour cibler tous les clients professionnels et éducatifs.<p>Cette option est mappée sur **Multi-locataire Azure AD seulement**.</p><p>Si vous avez enregistré l’application en tant que **Locataire unique Azure AD seulement**, vous pouvez utiliser le panneau **Authentification** pour la mettre à jour sur **Multi-locataire Azure AD seulement** puis revenir à **Locataire unique Azure AD seulement**.</p> |
        | Comptes dans n’importe quel répertoire organisationnel et comptes Microsoft personnels | Sélectionnez cette option pour cibler le plus grand nombre de clients.<p>Cette option est mappée sur **Comptes Microsoft multi-locataires et personnels Azure AD**.</p><p>Si vous avez enregistré l’application en tant que **Comptes Microsoft multi-locataires et personnels Azure AD**, vous ne pouvez pas modifier ce paramètre dans l’interface utilisateur (UI). Au lieu de cela, vous devez utiliser l’éditeur de manifeste d’application pour modifier les types de compte pris en charge.</p> |

    - **URI de redirection (facultatif)** – Sélectionnez le type d’application que vous créez : **Web** ou **Client public (mobile et bureau)**. Saisissez ensuite l’URI de redirection (ou l’URL de réponse) pour l’application.

        - Pour les applications Web, indiquez l’URL de base de l’application. Par exemple, `http://localhost:31544`peut être l’URL d’une application Web qui s’exécute sur votre ordinateur local. Les utilisateurs utilisent ensuite cette URL pour se connecter à une application client Web.
        - Pour les applications clientes publiques, fournissez l’URI qu’Azure AD utilise pour renvoyer des réponses à jeton. Entrez une valeur spécifique à votre application, telle que `myapp://auth`.

        Pour voir des exemples spécifiques d’applications Web ou d’applications natives, consultez les démarrages rapides dans [Plate-forme d’identité Microsoft (anciennement Azure Active Directory pour les développeurs)](/azure/active-directory/develop/#quickstarts).

5. Sous **Autorisations API**, sélectionnez **Ajouter une autorisation**. Ensuite, dans l’onglet **API que mon organisation utilise**, recherchez **Dynamics 365 Human Resources**, et ajoutez l’autorisation **user\_impersonation** à votre application. L’ID d’application pour Human Resources est f9be0c49-aa22-4ec6-911a-c5da515226ff. Utilisez cet ID pour vous assurer que vous avez choisi la bonne application.

6. Sélectionnez **Enregistrer**.

   [![Enregistrement d’une nouvelle application dans le portail Azure.](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)

Azure AD attribue un ID d’application unique (ID client) à votre application et vous amène à la page **Aperçu** pour votre application. Pour ajouter plus de fonctionnalités à votre application, vous pouvez sélectionner d’autres options de configuration, telles que des options de personnalisation et de certificats et secrets.

## <a name="retrieving-an-access-token"></a>Récupération d’un jeton d’accès

Les détails sur la façon dont vous récupérez un jeton d’accès pour appeler l’API de données de Human Resources dépendront des technologies que vous utilisez pour développer votre application client. Par exemple, vous pourriez faire un [test avec un utilitaire tiers](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (tel que Postman), développer une application de console C# ou un service Web, ou créer un client javascript/TypeScript.

Exemple d’application client C# :
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

Une fois que vous avez récupéré un jeton d’accès, vous passerez le jeton dans l’en-tête Autorisation en tant que jeton détenteur avec chaque demande que vous envoyez à l’API de données, comme décrit ci-dessus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
