---
title: Copier un site d’e-commerce
description: Cette rubrique décrit comment copier un site de commerce électronique existant dans ou entre des environnements de commerce électronique dans le générateur de site Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 03/03/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 284a33099fecc5a8e8d5d5d31612abab51735773
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2022
ms.locfileid: "8386978"
---
# <a name="copy-an-e-commerce-site"></a>Copier un site d’e-commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cette rubrique décrit comment copier un site de commerce électronique existant dans ou entre des environnements de commerce électronique dans le générateur de site Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce prend en charge la copie ou le clonage de sites en tant qu’opération libre-service dans le générateur de site Commerce. Les sites peuvent être copiés au sein d’un même environnement de commerce électronique ou entre deux environnements de commerce électronique. L’utilisateur qui lance l’opération de copie de site doit être un administrateur client dans les environnements de commerce électronique source et de destination.

L’opération de copie de site copie tout le contenu e-commerce du site source. Ce contenu comprend des pages, des fragments, des modèles, des URL et des actifs. Avant qu’un nouveau site puisse être utilisé, il doit être initialisé via le processus d’expérience de première exécution (FRE). Les canaux peuvent être cartographiés et gérés dans le constructeur de site, à **Paramètres du site \> Canaux**.

La durée de l’opération de copie du site dépend principalement du nombre de biens sur le site source. Pour les sites exceptionnellement volumineux, nous vous recommandons d’envisager d’utiliser plutôt l’opération de copie d’environnement. (Cette opération est également appelée opération de portabilité des données).

> [!NOTE]
> - Le site source sera en lecture seule pendant toute la durée de l’opération de copie du site.
> - Seules les versions publiées des documents sont copiées. Si aucune version n’a été publiée, seules les dernières versions sont copiées.
> - L’historique des versions du contenu ne sera pas disponible sur le site de destination.

## <a name="copy-a-site-within-an-e-commerce-environment"></a>Copier un site dans un environnement de commerce électronique

Pour copier un site dans un environnement de commerce électronique, procédez comme suit.

1. Connectez-vous au générateur de site pour l’environnement dans lequel vous souhaitez effectuer l’opération de copie.
1. Ouvrez la liste des sites en sélectionnant **Commutateur de site** dans l’angle supérieur droit, puis sélectionnez **Gérer les sites**.
1. Trouvez le site que vous souhaitez copier ou cloner, puis sélectionnez-le en cochant la case en regard du nom de site.
1. Sur le volet Actions, sélectionnez **Copier le site**.
1. Dans la boîte de dialogue **Copier le site**, dans le champ **Nom du nouveau site**, entrez un nom pour le nouveau site. Le nom du nouveau site doit être unique dans l’environnement de commerce électronique. Les champs **Client source** et **Site source** sont automatiquement définis sur les informations du client actuel et du site sélectionné.
1. Sélectionnez **Créer une copie**.

Une fois les informations validées, une notification indique qu’un nouveau travail de copie de site a été créé. Vous pouvez surveiller la progression de la tâche dans le [volet droit de la page **Tâches des locataires**](#monitor-the-site-copy-operation). Lorsque l’opération de copie s’est terminée avec succès, le nouveau site apparaît dans la liste des sites en vue de la liste des sites.

L’illustration suivante montre un exemple de boîte de dialogue **Copier le site** dans le générateur de site.

![Boîte de dialogue Copier le site dans le générateur de site.](media/site-copy_1.png)

## <a name="copy-a-site-between-two-e-commerce-environments"></a>Copier un site entre deux environnements de commerce électronique

Pour copier un site entre deux environnements de commerce électronique, procédez comme suit.

1. Connectez-vous au générateur de site pour l’environnement de commerce électronique de destination.
1. Sur le volet Actions, sélectionnez **Copier le site**.
1. Dans la boîte de dialogue **Copier le site**, dans le champ **Nom du nouveau site**, entrez un nom pour le nouveau site. Le nom du nouveau site doit être unique dans l’environnement de commerce électronique.
1. Dans le champ **Client source**, sélectionnez le nom du client source.
1. Dans le champ **Site source**, sélectionnez le site source.
1. Sélectionnez **Créer une copie**.

> [!NOTE]
> Des autorisations d’administrateur de locataire sont requises pour les environnements de commerce électronique source et de destination.

Une fois les informations validées, une notification indique qu’un nouveau travail de copie de site a été créé. Vous pouvez surveiller la progression de la tâche dans le [volet droit de la page **Tâches des locataires**](#monitor-the-site-copy-operation). Lorsque l’opération de copie s’est terminée avec succès, le nouveau site apparaît dans la liste des sites en vue de la liste des sites.

## <a name="monitor-the-site-copy-operation"></a>Surveiller l’opération de copie du site

Pour surveiller la progression de l’opération de copie de site, procédez comme suit.

1. Connectez-vous au générateur de site pour l’environnement de commerce électronique de destination.
1. Dans le volet de gauche, sélectionnez **Tâches des locataires**.
1. Sur la page **Tâches des locataires**, recherchez et sélectionnez la tâche de copie de site dans la liste. Un volet apparaît sur la droite et affiche le statut et les détails de la tâche sélectionnée.

Vous pouvez annuler une tâche dont le statut est défini sur **En cours**. Sélectionnez la tâche dans la liste, puis sélectionnez **Annuler** sur le volet d’actions.

Vous pouvez réessayer une tâche dont le statut est défini sur **Échec** ou **Terminé avec des erreurs**. Sélectionnez la tâche dans la liste, puis sélectionnez **Réessayer** sur le volet d’actions.

> [!NOTE]
> Le traitement des ressources vidéo peut se poursuivre après la fin d’une tâche de copie de site.

L’illustration suivante montre un exemple du volet droit de la page **Tâches des locataires** dans le générateur de site.

![Détails de la tâche dans le volet droit de la page Tâches des locataires dans le générateur de site.](media/site-copy_2.png)

## <a name="initialize-a-new-site-by-using-the-fre-process"></a>Initialiser un nouveau site en utilisant le processus FRE

Avant que le nouveau site puisse être utilisé, il doit être initialisé via le processus FRE.

Pour initialiser un nouveau site à l’aide du processus FRE, procédez comme suit.

1. Connectez-vous au générateur de site pour le nouveau site.
1. Ouvrez la liste des sites en sélectionnant **Commutateur de site** dans l’angle supérieur droit, puis sélectionnez **Gérer les sites**.
1. Recherchez et sélectionnez le nouveau site que vous souhaitez initialiser.
1. Dans la boîte de dialogue **Configurer votre site**, dans le champ **Sélectionner un domaine**, sélectionnez un domaine. Tous les domaines associés à l’environnement de commerce électronique lors de l’initialisation peuvent être sélectionnés.
1. Dans le champ **Sélectionner un canal par défaut**, sélectionnez le canal de magasin en ligne associé. Le canal sélectionné fournira des assortiments et d’autres informations stockées dans Commerce Headquarters.
1. Dans le champ **Sélectionner une langue par défaut**, sélectionnez la langue de création par défaut. Toutes les langues qui ont été configurées pour le canal de magasin en ligne sélectionné peuvent être sélectionnées.
1. Dans le champ **Chemin d’accès**, la valeur se compose du domaine de base et d’un chemin d’URL facultatif que vous pouvez saisir. Vous pouvez laisser le chemin de l’URL vide si le canal sera servi à partir de la racine du domaine ou si vous souhaitez saisir ces informations ultérieurement dans la vue de configuration du canal dans le générateur de site. Le chemin d’accès du site doit être unique dans l’environnement de commerce électronique.
1. Cliquez sur **OK**. Le site est initialisé avec les informations que vous avez fournies et vous êtes renvoyé à la vue de gestion du site.

L’illustration suivante montre un exemple de boîte de dialogue **Configurer votre site** dans le générateur de site.

![Boîte de dialogue Configurer votre site dans le générateur de site.](media/site-copy_3.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déployer un nouveau client e-commerce](deploy-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-b2c-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-b2c-tenants.md)

[Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)