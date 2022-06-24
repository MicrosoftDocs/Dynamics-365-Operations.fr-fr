---
title: Vue d’ensemble de la gestion des clients
description: Cet article fournit une vue d’ensemble des nouvelles fonctionnalités de gestion des clients qui sont disponibles dans l’application.
author: bebeale
ms.date: 02/01/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom:
- "260624"
- intro-internal
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 3d60004367840208f239d69220b3c181109f83d8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885609"
---
# <a name="clienteling-overview"></a>Vue d’ensemble de la gestion des clients

[!include [banner](includes/banner.md)]


De nombreux détaillants, notamment les détaillants spécialisés haut de gamme, souhaitent que leurs associés commerciaux forment les relations à long terme avec leurs clients clés. Les associés sont tenus de connaître les goûts de ces clients, l’historique d’achat, les préférences de produit et les dates importantes comme les anniversaires. Les associés ont besoin d’un endroit où ils peuvent capturer ces informations et les trouver facilement, le cas échéant. Si ces informations sont disponibles dans une seule vue, les associés peuvent facilement cibler les clients qui répondent aux critères spécifiques. Par exemple, ils peuvent trouver tous les clients qui préfèrent acheter des sacs à main, ou les clients qui ont un évènement important à venir, comme un anniversaire.

## <a name="client-book"></a>Registre clients

Dans Microsoft Dynamics 365 Commerce, les détaillants peuvent utiliser la fonctionnalité de registre des clients pour aider les collaborateurs du magasin à constituer des relations à long terme avec les clients clés.

Le registre des clients comprend les fiches client qui présentent les informations de contact de chaque client, ainsi que trois propriétés supplémentaires définies par le détaillant et configurées dans Headquarters. Les détaillants peuvent décider des trois choses les plus importantes que les associés des ventes doivent connaître concernant les clients. Par exemple, un détaillant en bijoux pourrait souhaiter inclure des dates importantes comme des anniversaires, car ces dates sont des occasions où les individus achètent davantage de bijoux. De même, un détaillant dans la mode pourrait souhaiter inclure les intérêts et marques préférés du client en matière de shopping.

Le registre des clients permet également aux associés des ventes de filtrer la liste afin qu’elle n’affiche que les clients qui répondent à des critères spécifiques. Par exemple, une nouvelle collection de chaussures est arrivée en magasin, et un associé souhaite informer les clients qui aiment acheter des chaussures. Dans ce cas, l’associé peut filtrer le registre des clients pour trouver les clients pertinents, puis prendre une mesure en conséquence.

Si des clients ne sont plus considérés comme des clients clés pour une raison précise, et par conséquent ne doivent plus être gérés de manière étroite, les associés de vente peuvent les supprimer depuis leur registre de clients.

Certains détaillants ne souhaitent pas gérer les clients au niveau des associés des ventes. En lieu et place, ils souhaitent gérer une liste de clients clés au niveau du magasin. Ces détaillants peuvent afficher les clients depuis les registres des clients du magasin. Avec cette option, les détaillants peuvent voir les clients depuis les registres des clients de tous les associés des ventes dont le carnet d’adresses correspond au carnet d’adresses du magasin actuel. Ainsi, si un associé travaille dans plusieurs magasins de l’entité juridique, le registre des clients présente les clients de tous ces magasins. Cette fonctionnalité prend en charge des fonctionnalités supplémentaires. Par exemple, les clients peuvent être réaffectés d’un associé à un autre associé. Cette fonctionnalité est utile lorsque les associés sont transférés ou quittent la société.

Chaque associé des ventes peut avoir un registre de client par entité juridique, et les associés peuvent ajouter un ou plusieurs clients à leur registre de clients. Dans Commerce, chaque client peut actuellement être ajouté à un seul registre de clients. Toutefois, Microsoft prévoit d’ajouter une fonctionnalité qui laisse un client unique être ajouté à plusieurs registres de clients.

> [!NOTE]
> Contrairement à la recherche des clients, le registre des clients ne filtre pas les enregistrements client selon les carnets d’adresse du magasin.

## <a name="activities-and-notes"></a>Activités et notes

Les canaux en ligne donnent aux détaillants des façons d’apprendre les préférences des clients sans exiger que ces clients fournissent ces informations de façon explicite. En revanche, lorsque les clients interagissent avec les associés de vente en magasin, ils partagent explicitement des informations concernant leurs préférences. Malheureusement, ces informations peuvent être perdues une fois la vente terminée. Toutefois, si ces informations sont enregistrées, cela peut aider les détaillants à mieux comprendre les clients et par conséquent à les aider à fournir de meilleures recommandations et une meilleure expérience d’achat globale.

Pour capturer les informations critiques que les clients partagent, les associés de vente peuvent utiliser non seulement les attributs du registre des clients, mais utilisent également la fonctionnalité des activités et des notes. Les détaillants peuvent configurer les types d’activité, comme les informations concernant la visite en magasin, l’adresse électronique, le numéro de téléphone et les rendez-vous. Les activités que les associés créent peuvent être visualisées dans un format de calendrier au point de vente (PDV). Ils peuvent également être affichés dans l’onglet **Activités** sur la page **Tous les clients \> Général** dans Siège.

Les associés peuvent également utiliser des notes pour capturer des informations clients génériques qui peuvent être référencées avant chaque interaction. Ces notes sont enregistrées dans Siège, et peuvent être affichées dans le profil client ou sur la page des détails du client dans le centre d’appels.

> [!NOTE]
> Actuellement, toutes les notes et activités peuvent être visualisées par tout associé des ventes qui travaille pour l’entité juridique et peuvent afficher les pages des détails des clients. Les notes et activités ne sont pas limitées à l’associé qui a ajouté un client au registre des clients.

## <a name="integration-with-dynamics-365-customer-insights"></a>Intégration à Dynamics 365 Customer Insights

À l’aide de l’application Dynamics 365 Customer Insights, les détaillants peuvent regrouper les données de différents systèmes que les clients utilisent pour interagir avec la marque du détaillant. Vous pouvez ensuite utiliser ces données pour générer une seule vue du client et dériver les informations. L’intégration de Customer Insights avec Commerce permet aux détaillants de sélectionner une ou plusieurs mesures qui doivent être présentées sur la fiche client dans le registre des clients. Par exemple, les détaillants peuvent utiliser les données dans Customer Insights pour calculer la « probabilité de résiliation » pour un client et définir la « meilleure action suivante ». Si ces valeurs sont définies comme des mesures, elles peuvent être affichées sur la fiche client et peuvent fournir des informations cruciales aux associés de vente. Pour plus d’informations sur Customer Insights, voir la documentation [Dynamics 365 Customer Insights](/dynamics365/ai/customer-insights/overview). Pour plus d’informations sur les mesures, voir [Mesures](/dynamics365/ai/customer-insights/pm-measures).

## <a name="set-up-clienteling"></a>Configurer la gestion des clients

Pour activer la fonctionnalité de gestion des clients dans votre environnement, procédez comme suit.

1. Dans l’espace de travail **Gestion de fonctions**, filtrez les entités selon le module **Commerce et vente au détail**.

    ![Gestion des clients dans la liste des entités pour le module Commerce.](./media/Enable_clienteling.png "Gestion des clients dans la liste des entités pour le module Commerce et vente au détail")

2. Activez la fonctionnalité **Gestion des clients** en sélectionnant **Activer maintenant**.
3. Sur la page **Paramètres Commerce**, sous l’onglet **Souche de numéros**, sélectionnez la ligne **Identificateur du registre des clients**. Puis, dans le champ **Code souche de N°**, sélectionnez une séquence de numéros. Le système utilise cette souche de numéros pour attribuer un ID aux registres de clients.
4. Sélectionnez **Enregistrer**.
5. Créez un groupe d’attributs qui contient les attributs que vous souhaitez capturer pour les clients qui sont gérés dans les registres de clients. Pour des instructions, voir [Attributs et groupes d’attributs](./attribute-attributegroups-lifecycle.md).

    - Définissez les attributs exigés comme **Impossible de préciser**. Les associés de vente peuvent ensuite utiliser ces attributs pour filtrer leur registre de clients.
    - Définissez l’ordre d’affichage pour ces attributs. Cet ordre d’affichage détermine quels attributs doivent être affichés sur la fiche client dans le registre de clients. Un ordre d’affichage 1 est considéré supérieur à un ordre d’affichage 2. Par conséquent, l’attribut qui a un ordre d’affichage 1 sera affiché avant l’attribut avec un ordre d’affichage 2.

    > [!NOTE]
    > Vous pouvez mettre à disposition Customer Insights depuis la même page. Toutefois, un ID d’application Azure et un secret doivent être créés, à des fins d’authentification. (Pour en savoir plus sur les exigences, voir la section [Activer l’intégration de Customer Insights à Commerce](#turn-on-the-integration-of-customer-insights-with-commerce) ultérieurement dans cet article.) Si Customer Insights est activé, et si vous sélectionnez une ou plusieurs mesures qui doivent être affichées sur la fiche client, ces mesures seront affichées tout d’abord. Ensuite, les groupes d’attribut du registre de clients seront affichés, selon l’ordre d’affichage. Par exemple, si vous sélectionnez deux mesures depuis Customer Insights, ces deux mesures et un attribut de registre de clients seront affichés sur la fiche client. (L’attribut du registre de clients qui est affiché sera l’attribut qui a l’ordre d’affichage le plus élevé.)

6. Sur la page **Paramètres Commerce**, sous l’onglet **Gestion des clients**, dans le champ **Groupe d’attributs du registre de clients**, sélectionnez le groupe d’attributs que vous venez de créer.

    ![Groupe d’attributs du registre de clients sélectionné.](./media/Client%20book%20attributes.png "Groupe d’attributs du registre de clients sélectionné")

7. Pour effectuer les activités qui se produisent au PDV, définissez les types d’activités sur la page **Types d’activité** (**Commerce et vente au détail \> Clients \> Types d’activité**).

    > [!NOTE]
    > Les types d’activités sont extraits par Unité d’échelle commerciale lorsqu’il effectue un appel en temps réel pour la première fois. Une fois les activités extraites, elles sont mises en cache pendant quelques heures. Si vous modifiez les types d’activités, attendez jusqu’à ce que le cache ne soit plus valide. Sinon, pour les environnements hors-production, redémarrez le service Unité d’échelle commerciale.

8. Ajoutez deux boutons à la mise en page de l’écran du PDV appropriée, de sorte que les associés de ventes peuvent voir leur propre registre des clients et le registre des clients du magasin. (Les registres de clients de magasin incluent les clients de tous les registres clients de tous les associés qui partagent un carnet d’adresses avec le magasin.) Les opérations correspondantes sont nommées **Afficher les clients dans le registre de clients** et **Afficher les clients depuis les registres de clients du magasin**, respectivement. Trois opérations supplémentaires liées aux registres de clients sont disponibles. Ces opérations déterminent quels associés peuvent ajouter, supprimer et réaffecter les clients depuis le registre de clients. Ils sont nommés **Ajouter le client au registre de clients**, **Supprimer les clients du registre de clients** et **Réaffecter les clients à un registre de clients**, respectivement.
9. Exécutez les tâches suivantes dans le programme de répartition : 1040, 1150, 1110 et 1090.

Une fois cette procédure terminée, les associés de vente peuvent ouvrir la page des détails du client au PDV, et ajouter les clients à leur registre de clients, afficher et capturer les activités et les notes pour les clients, et cibler les clients en utilisant les attributs du registre des clients pour filtrer le registre des clients. L’illustration suivante présente un exemple de registre de clients.

![Exemple d’un registre de clients.](./media/client_book.png "Exemple d’un registre de clients")

## <a name="turn-on-the-integration-of-customer-insights-with-commerce"></a>Activer l’intégration de Customer Insights avec Commerce

Pour activer l’intégration de Customer Insights avec Commerce, vous devez veiller à avoir une instance active de Customer Insights dans le client où Commerce est en service. Vous devez également avoir un compte d’utilisateur Azure Active Directory (Azure AD) avec un abonnement Azure.

Procédez comme suit pour configurer l’intégration.

1. Dans le portail Azure, enregistrez une nouvelle application et notez son nom, son ID et le secret. Ces informations seront utilisées pour l’authentification de service à service entre Commerce et Customer Insights. Notez bien le secret, car il sera nécessaire de le sauvegarder dans le coffre de clés. Pour l’exemple suivant, utilisez CI_Access_name, CI_Access_AppID, CI_Access_Secret respectivement pour le nom de l’application, l’ID d’application et le secret. Pour plus d’informations, consultez [Démarrage rapide : Enregistrer une application avec la plateforme d’identités Microsoft](/azure/active-directory/develop/quickstart-register-app).

    > [!IMPORTANT]
    > Suivez la procédure afin de garder en tête le changement du secret avant son expiration. Sinon, l’intégration sera interrompue de manière inopinée.

2. Accédez à votre instance Customer Insights et recherchez le nom de l’application créée ci-dessus (dans cet exemple, « CI_Access_name »).
3. Créez un coffre de clés Azure et notez le nom et l’URL (dans cet exemple, « KeyVaultName », « KeyVaultURL »). Pour obtenir des instructions, voir [Démarrage rapide : Définir et extraire un secret du coffre de clés Azure avec le portail Azure](/azure/key-vault/quick-create-portal).
4. Enregistrez le secret (dans cet exemple, « CI_Access_Secret ») dans le coffre-fort. Lorsque ce secret est stocké dans le coffre-fort, il reçoit un nom. Notez le nom du secret (dans cet exemple, « SecretName »).
5. Pour accéder au secret depuis Azure Key Vault, vous devez créer une autre application avec un ID d’application et un secret (dans cet exemple, « KeyVault_Access_AppID » et « KeyVault_Access_Secret »). Notez bien le secret, car il ne sera plus affiché.
6. Ensuite, vous devez accorder des autorisations à l’application pour accéder au Key Vault à partir de Commerce à l’aide d’API. Accédez à la page de l’application dans le portail Azure. Sous la section **Gérer**, sélectionnez **Autorisations API**. Ajoutez l’autorisation d’accès à **Azure Key Vault**. Pour cette autorisation, sélectionnez **Stratégie d’accès**. Sélectionnez le modèle **Gestion du secret**, et sélectionnez les options **Obtenir**, **Liste**, **Décrypter**, et **Crypter**. 
5. Dans Commerce Headquarters, accédez à **Administration du système \> Paramétrage \> Paramètres Key Vault**, puis entrez les informations requises pour le coffre de clés. Puis, dans le champ **Client du coffre de clés**, saisissez l’ID d’application que vous avez utilisé à l’étape 4, afin que Commerce puisse accéder aux secrets dans le coffre de clés.
6. Pour ajouter l’application créée à l’étape 1 à la liste des applications sûres (parfois désignées sous le nom de Liste sécurisée), accédez à Customer Insights, et sélectionnez l’accès  **Affichage** à l’application. Pour les instructions, voir [Autorisations](/dynamics365/ai/customer-insights/pm-permissions).
7. Sur la page **Administration système > Paramétrage > Paramètres Key Vault** dans Commerce HQ, mettez à jour les champs comme décrit ci-dessous : 

- **URL de Key Vault** : « KeyVaultURL » (à partir de l’étape 3 ci-dessus).
- **Client Key Vault** : « KeyVault_Access_AppID » (à partir de l’étape 5 ci-dessus).
- **Clé secrète Key Vault** : « KeyVault_Access_Secret » (à partir de l’étape 5 ci-dessus).
- Sous la section **Secrets** :
    - **Nom** : N’importe quel nom, par exemple « CISecret ».
    - **Description** : N’importe quelle valeur.
    - **Secret** : **coffre** :`//<Name of key vault>/<name of secret>>` Dans cet exemple, ce sera `vault://KeyVaultName/SecretName`.

Après avoir mis à jour les champs, sélectionnez **Valider** pour vous assurer que le secret est accessible par l’application Commerce.

8. Dans Commerce, sur la page **Paramètres Commerce**, sur l’onglet **Gestion de la relation client**, sur le raccourci **Dynamics 365 Customer Insights**, définissez l’**ID d’application** sur « CI_Access_AppID » (à partir de l’étape 1 ci-dessus). Pour **Nom secret**, sélectionnez le nom du secret saisi à l’étape 7 ci-dessus (« CISecret »). Définissez l’option **Activer Customer Insights** sur **Oui**. Si le paramétrage est infructueux pour une raison quelconque, vous recevrez un message d’erreur, et cette option sera définie sur **Non**. 

Vous pouvez avoir plusieurs environnements dans Customer Insights, tels que les environnements de production et de test. Dans le champ **ID d’instance de l’environnement**, saisissez l’environnement approprié. Dans le champ **Autre ID client**, entrez la propriété dans Customer Insights qui est mise en correspondance avec le numéro de compte client. (Dans Commerce, le numéro de compte client est l’ID client.) Les trois autres propriétés sont les mesures qui seront affichées sur la fiche client dans le registre de clients. Vous pouvez sélectionner jusqu’à trois mesures à afficher sur la fiche client. Cependant, vous n’êtes pas obligé de sélectionner des mesures. Comme mentionné précédemment, le système affiche d’abord ces valeurs, puis les valeurs du groupe d’attributs du registre de clients.


[!INCLUDE[footer-include](../includes/footer-banner.md)]