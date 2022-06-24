---
title: Configurer une connexion SharePoint
description: Cet article explique comment configurer une connexion pour que la facturation électronique puisse accéder à un site Microsoft SharePoint.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: fb4258190b9480c1302060dd7b75145f80bb7f18
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856578"
---
# <a name="configure-a-sharepoint-connection"></a>Configurer une connexion SharePoint

[!include [banner](../includes/banner.md)]

Le service de facturation électronique peut lire les fichiers de Microsoft SharePoint et télécharger des fichiers vers SharePoint. Pour s’assurer que la facturation électronique peut accéder à un site SharePoint, vous devez fournir les informations d’identification du site au service de facturation électronique. De plus, pour vous assurer que les identifiants sont stockés en toute sécurité, ne les fournissez pas directement. Au lieu de cela, stockez-les dans un coffre de clés Azure et fournissez une clé secrète Azure Key Vault.

## <a name="grant-access-to-a-sharepoint-folder"></a>Accorder l’accès à un dossier SharePoint

1. Créez un enregistrement d’application dans le client où Regulatory Configuration Service (RCS) est installé.

    1. Connectez-vous au [portail Azure](https://portal.azure.com/).
    2. Accédez à **Enregistrements d’application**.
    3. Sélectionnez **Nouvelle inscription**.
    4. Entrer un nom, tel que **Application SharePoint pour la facturation électronique**, et terminer l’enregistrement
    5. Sélectionnez l’enregistrement de la nouvelle application.
    6. Sur l’onglet **Authentification**, activez l’option **Autoriser les flux client publics**.
    4. Sur l’onglet **Certificats et clés secrètes**, sélectionnez **Nouvelle clé secrète client** pour créer une clé secrète client.
    5. Copiez la valeur de la clé secrète créée.

    Procédez comme suit :

    - N’utilisez pas le même enregistrement d’application pour différents services.
    - Suivez les [recommandations de stratégie en matière de mot de passe](/microsoft-365/admin/misc/password-policy-recommendations?view=o365-worldwide).
    - Configurez la rotation des mots de passe. Pendant la rotation, créez une clé secrète client pour l’enregistrement de l’application, mettez à jour le coffre de clés, puis supprimez l’ancienne clé secrète.

2. Enregistrez les valeurs **Clé secrète d’enregistrement de l’application** et **ID de l’application (client)** comme deux nouvelles clés secrètes dans le coffre de clés dans la configuration de votre environnement de facturation électronique.
3. Ajoutez les clés secrètes créées dans les paramètres Key Vault dans la configuration de votre environnement de facturation électronique dans RCS.
4. Dans le portail Azure, autorisez l’accès à SharePoint. Cette étape doit être effectuée par l’administrateur client.

    1. Sélectionnez l’enregistrement de l’application que vous avez créée.
    2. Sur l’onglet **Autorisations API**, sélectionnez **Ajouter une autorisation**.
    3. Sélectionnez **Microsoft Graph (Autorisations d’application)** \> **Sites.Selected**.
    4. Sélectionnez **Accorder le consentement administrateur au \<user&nbsp;name\>**.
    5. Passez en revue le champ **Statut** pour vous assurer que les autorisations sont accordées.

        ![Autorisations accordées dans l’onglet Autorisations de l’API.](media/configured-permissions.jpg)

    6. Ouvrez [Afficheur Graph – Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer), et connectez-vous.
    7. Dans le volet de gauche, sur l’onglet **Exemples de requêtes**, sous **Sites SharePoint**, sélectionnez **Obtenir un site SharePoint basé sur le chemin d’accès relatif du site**.
    8. Remplissez les paramètres **\{host-name\}** et **\{server-relative-path\}**. Par exemple, remplissez `<domain>.sharepoint.com` pour **\{host-name\}** et `sites/<siteName>` pour **\{server-relative-path\}**.

        > [!NOTE]
        > Pour le site Web par défaut, laissez le paramètre **\{server-relative-path\}** vide.

    9. Sélectionnez **Exécuter la requête** et enregistrez le résultat.
    10. Configurez la requête suivante.

        `POST https://graph.microsoft.com/v1.0/sites/{site-id}/permissions`

        Dans cette requête, **\{site-id\}** est la valeur du nœud **id** depuis la réponse à la requête précédente.

        Voici le corps de la requête.

        ```json
        {
            "roles": [
                "read",
                "write"
            ],
            "grantedToIdentities": [
                {
                    "application": {
                        "id": "{app-id}",
                        "displayName": "{app-name}"
                    }
                }
            ]
        }
        ```

        Dans ce corps de requête, **\{app-id\}** est la valeur **ID de l’application (client)** et **\{app-name\}** est la valeur **Nom de l’application**.

        ![Requête POST.](media/app-id-query.jpg)

    11. Sur l’onglet **Modifier les autorisations**, sélectionnez **Ouvrir le panneau des autorisations**, puis sélectionnez **Sites** \> **Sites.FullControl.All**\> **Consent**.
    12. Sélectionnez **Exécuter une requête**.

Le service de facturation électronique a désormais accès à votre site SharePoint.
