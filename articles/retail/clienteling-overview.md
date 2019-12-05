---
title: Vue d'ensemble de la gestion des clients
description: Cette rubrique fournit une vue d'ensemble des nouvelles fonctionnalités de gestion des clients qui sont disponibles dans l'application de vente au détail.
author: bebeale
manager: AnnBe
ms.date: 11/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: fb58022f61f9944d6e385874db1f2342bc111866
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773961"
---
# <a name="clienteling-overview"></a>Vue d'ensemble de la gestion des clients

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

De nombreux détaillants, notamment les détaillants spécialisés haut de gamme, souhaitent que leurs associés commerciaux forment les relations à long terme avec leurs clients clés. Les associés sont tenus de connaître les goûts de ces clients, l'historique d'achat, les préférences de produit et les dates importantes comme les anniversaires. Les associés ont besoin d'un endroit où ils peuvent capturer ces informations et les trouver facilement, le cas échéant. Si ces informations sont disponibles dans une seule vue, les associés peuvent facilement cibler les clients qui répondent aux critères spécifiques. Par exemple, ils peuvent trouver tous les clients qui préfèrent acheter des sacs à main, ou les clients qui ont un évènement important à venir, comme un anniversaire.

## <a name="client-book"></a>Registre clients

Dans Microsoft Dynamics 365 Retail, les détaillants peuvent utiliser la fonctionnalité de registre des clients pour aider les associés du magasin à constituer des relations à long terme avec les clients clés.

Le registre des clients comprend les fiches client qui présentent les informations de contact de chaque client, ainsi que trois propriétés supplémentaires définies par le détaillant et configurées dans Retail Headquarters. Les détaillants peuvent décider des trois choses les plus importantes que les associés des ventes doivent connaître concernant les clients. Par exemple, un détaillant en bijoux pourrait souhaiter inclure des dates importantes comme des anniversaires, car ces dates sont des occasions où les individus achètent davantage de bijoux. De même, un détaillant dans la mode pourrait souhaiter inclure les intérêts et marques préférés du client en matière de shopping.

Le registre des clients permet également aux associés des ventes de filtrer la liste afin qu'elle n'affiche que les clients qui répondent à des critères spécifiques. Par exemple, une nouvelle collection de chaussures est arrivée en magasin, et un associé souhaite informer les clients qui aiment acheter des chaussures. Dans ce cas, l'associé peut filtrer le registre des clients pour trouver les clients pertinents, puis prendre une mesure en conséquence.

Si des clients ne sont plus considérés comme des clients clés pour une raison précise, et par conséquent ne doivent plus être gérés de manière étroite, les associés de vente peuvent les supprimer depuis leur registre de clients.

Certains détaillants ne souhaitent pas gérer les clients au niveau des associés des ventes. En lieu et place, ils souhaitent gérer une liste de clients clés au niveau du magasin. Ces détaillants peuvent afficher les clients depuis les registres des clients du magasin. Avec cette option, les détaillants peuvent voir les clients depuis les registres des clients de tous les associés des ventes dont le carnet d'adresses correspond au carnet d'adresses du magasin actuel. Ainsi, si un associé travaille dans plusieurs magasins de l'entité juridique, le registre des clients présente les clients de tous ces magasins. Cette fonctionnalité prend en charge des fonctionnalités supplémentaires. Par exemple, les clients peuvent être réaffectés d'un associé à un autre associé. Cette fonctionnalité est utile lorsque les associés sont transférés ou quittent la société.

Chaque associé des ventes peut avoir un registre de client par entité juridique, et les associés peuvent ajouter un ou plusieurs clients à leur registre de clients. Dans Retail, chaque client peut actuellement être ajouté à un seul registre de clients. Toutefois, Microsoft prévoit d'ajouter une fonctionnalité qui laisse un client unique être ajouté à plusieurs registres de clients.

> [!NOTE]
> Contrairement à la recherche des clients, le registre des clients ne filtre pas les enregistrements client selon les carnets d'adresse du magasin.

## <a name="activities-and-notes"></a>Activités et notes

Les canaux en ligne donnent aux détaillants des façons d'apprendre les préférences des clients sans exiger que ces clients fournissent ces informations de façon explicite. En revanche, lorsque les clients interagissent avec les associés de vente en magasin, ils partagent explicitement des informations concernant leurs préférences. Malheureusement, ces informations peuvent être perdues une fois la vente terminée. Toutefois, si ces informations sont enregistrées, cela peut aider les détaillants à mieux comprendre les clients et par conséquent à les aider à fournir de meilleures recommandations et une meilleure expérience d'achat globale.

Pour capturer les informations critiques que les clients partagent, les associés de vente peuvent utiliser non seulement les attributs du registre des clients, mais utilisent également la fonctionnalité des activités et des notes. Les détaillants peuvent configurer les types d'activité, comme les informations concernant la visite en magasin, l'adresse électronique, le numéro de téléphone et les rendez-vous. Les activités que les associés créent peuvent être visualisées dans un format de calendrier au point de vente (PDV). Ils peuvent également être affichés dans l'onglet **Activités** sur la page **Tous les clients \> Général** dans Retail Headquarters.

Les associés peuvent également utiliser des notes pour capturer des informations clients génériques qui peuvent être référencées avant chaque interaction. Ces notes sont enregistrées dans Retail Headquarters, et peuvent être affichées dans le profil client ou sur la page des détails du client dans le centre d'appels.

> [!NOTE]
> Actuellement, toutes les notes et activités peuvent être visualisées par tout associé des ventes qui travaille pour l'entité juridique et peuvent afficher les pages des détails des clients. Les notes et activités ne sont pas limitées à l'associé qui a ajouté un client au registre des clients.

## <a name="integration-with-dynamics-365-customer-insights"></a>Intégration à Dynamics 365 Customer Insights

À l'aide de l'application Dynamics 365 Customer Insights, les détaillants peuvent regrouper les données de différents systèmes que les clients utilisent pour interagir avec la marque du détaillant. Vous pouvez ensuite utiliser ces données pour générer une seule vue du client et dériver les informations. L'intégration de Customer Insights avec Retail permet aux détaillants de sélectionner une ou plusieurs mesures qui doivent être présentées sur la fiche client dans le registre des clients. Par exemple, les détaillants peuvent utiliser les données dans Customer Insights pour calculer la « probabilité de résiliation » pour un client et définir la « meilleure action suivante ». Si ces valeurs sont définies comme des mesures, elles peuvent être affichées sur la fiche client et peuvent fournir des informations cruciales aux associés de vente. Pour plus d'informations sur Customer Insights, voir la documentation [Dynamics 365 Customer Insights](https://docs.microsoft.com/dynamics365/ai/customer-insights/overview). Pour plus d'informations sur les mesures, voir [Mesures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="set-up-clienteling"></a>Configurer la gestion des clients

Pour activer la fonctionnalité de gestion des clients dans votre environnement, procédez comme suit.

1. Dans l'espace de travail **Gestion de fonctions**, filtrez les entités selon le module **Commerce et vente au détail**.

    ![Gestion des clients dans la liste des entités pour le module Commerce et vente au détail](./media/Enable_clienteling.png "Gestion des clients dans la liste des entités pour le module Commerce et vente au détail")

2. Activez la fonctionnalité **Gestion des clients** en sélectionnant **Activer maintenant**.
3. Sur la page **Paramètres des ventes au détail**, sous l'onglet **Souche de numéros**, sélectionnez la ligne **Identificateur du registre des clients**. Puis, dans le champ **Code souche de N°**, sélectionnez une séquence de numéros. Le système utilise cette souche de numéros pour attribuer un ID aux registres de clients.
4. Sélectionnez **Enregistrer**.
5. Créez un groupe d'attributs qui contient les attributs que vous souhaitez capturer pour les clients qui sont gérés dans les registres de clients. Pour des instructions, voir [Attributs et groupes d'attributs](https://docs.microsoft.com/dynamics365/retail/attribute-attributegroups-lifecycle).

    - Définissez les attributs exigés comme **Impossible de préciser**. Les associés de vente peuvent ensuite utiliser ces attributs pour filtrer leur registre de clients.
    - Définissez l'ordre d'affichage pour ces attributs. Cet ordre d'affichage détermine quels attributs doivent être affichés sur la fiche client dans le registre de clients. Un ordre d'affichage 1 est considéré supérieur à un ordre d'affichage 2. Par conséquent, l'attribut qui a un ordre d'affichage 1 sera affiché avant l'attribut avec un ordre d'affichage 2.

    > [!NOTE]
    > Vous pouvez mettre à disposition Customer Insights depuis la même page. Toutefois, un ID d'application Azure et un secret doivent être créés, à des fins d'authentification. (Pour en savoir plus sur les exigences, voir la section [Activer l'intégration de Customer Insights à Retail](#turn-on-the-integration-of-customer-insights-with-retail) ultérieurement dans cette rubrique.) Si Customer Insights est activé, et si vous sélectionnez une ou plusieurs mesures qui doivent être affichées sur la fiche client, ces mesures seront affichées tout d'abord. Ensuite, les groupes d'attribut du registre de clients seront affichés, selon l'ordre d'affichage. Par exemple, si vous sélectionnez deux mesures depuis Customer Insights, ces deux mesures et un attribut de registre de clients seront affichés sur la fiche client. (L'attribut du registre de clients qui est affiché sera l'attribut qui a l'ordre d'affichage le plus élevé.)

6. Sur la page **Paramètres de vente au détail**, sous l'onglet **Gestion des clients**, dans le champ **Groupe d'attributs du registre de clients**, sélectionnez le groupe d'attributs que vous venez de créer.

    ![Groupe d'attributs du registre de clients sélectionné](./media/Client%20book%20attributes.png "Groupe d'attributs du registre de clients sélectionné")

7. Pour effectuer les activités qui se produisent au PDV, définissez les types d'activités sur la page **Types d'activité** (**Vente au détail \> Clients \> Types d'activité**).

    > [!NOTE]
    > Les types d'activités sont extraits par Retail Server lorsqu'il effectue un appel en temps réel pour la première fois. Une fois les activités extraites, elles sont mises en cache pendant quelques heures. Si vous modifiez les types d'activités, attendez jusqu'à ce que le cache ne soit plus valide. Sinon, pour les environnements hors-production, redémarrez le service Retail Server.

8. Ajoutez deux boutons à la mise en page de l'écran du PDV appropriée, de sorte que les associés de ventes peuvent voir leur propre registre des clients et le registre des clients du magasin. (Les registres de clients de magasin incluent les clients de tous les registres clients de tous les associés qui partagent un carnet d'adresses avec le magasin.) Les opérations correspondantes sont nommées **Afficher les clients dans le registre de clients** et **Afficher les clients depuis les registres de clients du magasin**, respectivement. Trois opérations supplémentaires liées aux registres de clients sont disponibles. Ces opérations déterminent quels associés peuvent ajouter, supprimer et réaffecter les clients depuis le registre de clients. Ils sont nommés **Ajouter le client au registre de clients**, **Supprimer les clients du registre de clients** et **Réaffecter les clients à un registre de clients**, respectivement.
9. Exécutez les tâches suivantes dans le programme de répartition : 1040, 1150, 1110 et 1090.

Une fois cette procédure terminée, les associés de vente peuvent ouvrir la page des détails du client au PDV, et ajouter les clients à leur registre de clients, afficher et capturer les activités et les notes pour les clients, et cibler les clients en utilisant les attributs du registre des clients pour filtrer le registre des clients. L'illustration suivante présente un exemple de registre de clients.

![Exemple d'un registre de clients](./media/client_book.png "Exemple d'un registre de clients")

## <a name="turn-on-the-integration-of-customer-insights-with-retail"></a>Activer l'intégration de Customer Insights avec Retail

Pour activer l'itnégration de Customer Insights avec Retail, vous devez veiller à avoir une instance active de Customer Insights dans le client où Retail est en service. Vous devez également avoir un compte d'utilisateur Azure Active Directory (Azure AD) avec un abonnement Azure.

Procédez comme suit pour configurer l'intégration.

1. Dans le portail Azure, enregistrez une application Cette application sera utilisée pour s'authentifier avec Customer Insights. Pour obtenir des instructions, voir [Démarrage rapide : Enregistrer une application avec la plateforme d'identités Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).
2. Générez un secret pour l'application. Faites une note du secret et conservez-la dans un endroit sûr, car vous en aurez besoin ultérieurement. Sélectionnez également la durée d'expiration du secret.

    > [!IMPORTANT]
    > Suivez la procédure afin de garder en tête le changement du secret avant son expiration. Sinon, l'intégration sera interrompue de manière inopinée.

3. Créez un coffre de clés Azure et enregistrez le secret d'application. Pour obtenir des instructions, voir [Démarrage rapide : Définir et extraire un secret du coffre de clés Azure avec le portail Azure](https://docs.microsoft.com/azure/key-vault/quick-create-portal).
4. Activez l'accès au coffre de clés Azure depuis Retail. Pour procéder comme suit, vous devez avoir un ID d'application et un secret. L'application peut être la même application que celle que vous avez créée à l'étape 1, ou il peut s'agir d'une nouvelle application. (Autrement dit, vous pouvez utiliser l'application créé à l'étape 1 pour l'accès au coffre de clés et au service Customer Insights, ou vous pouvez créer une seule application pour chaque type d'accès.) Pour obtenir des instructions, voir [Enregistrer les informations d'identification principales du service dans le coffre de clés de la pile Azure](https://docs.microsoft.com/azure-stack/user/azure-stack-key-vault-store-credentials?view=azs-1908#create-a-service-principal).
5. Dans Retail Headquarters, accédez à **Administration du système \> Paramétrage \> Paramètres du coffre de clés**, puis entrez les informations requises pour le coffre de clés. Puis, dans le champ **Client du coffre de clés**, saisissez l'ID d'application que vous avez utilisé à l'étape 4, afin que Retail puisse accéder aux secrets dans le coffre de clés.
6. Pour ajouter l'application créée à l'étape 1 à la liste des applications sûres (parfois désignées appelée Liste verte), accédez à Customer Insights, et fournissez l'accès **Affichage** à l'application. Pour les instructions, voir [Autorisations](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-permissions).
7. Dans Retail, sur la page **Paramètres de Retail**, sur l'onglet **Gestion des clients**, sur l'organisateur **Dynamics 365 Customer Insights**, procédez comme suit :

    1. Dans le champ **ID d'application**, entrez l'ID d'application que vous avez utilisé à l'étape 1.
    2. Dans le champ **Nom secret**, entrez le nom du secret du coffre de clés que vous avez créé à l'étape 5.
    3. Définissez l'option **Activer Customer Insights** sur **Oui**. Si le paramétrage est infructueux pour une raison quelconque, vous recevrez un message d'erreur, et cette option sera définie sur **Non**.
    4. Vous pouvez avoir plusieurs environnements dans Customer Insights, tels que les environnements de production et de test. Dans le champ **ID d'instance de l'environnement**, saisissez l'environnement approprié.
    5. Dans le champ **Autre ID client**, entrez la propriété dans Customer Insights qui est mise en correspondance avec le numéro de compte client. (Dans Retail, le numéro de compte client est l'ID client.)
    6. Les trois propriétés restantes sont les mesures qui seront indiquées sur la fiche client dans le registre des clients. Vous pouvez sélectionner jusqu'à trois mesures à afficher sur la fiche client. (Toutefois, vous n'avez pas à sélectionner de mesures.) Comme il a été mentionné précédemment, le système présente ces valeurs tout d'abord, puis il affiche les valeurs pour le groupe d'attributs du registre de clients.
