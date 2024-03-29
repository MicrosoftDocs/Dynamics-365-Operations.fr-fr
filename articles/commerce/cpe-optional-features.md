---
title: Configurer les fonctionnalités facultatives pour un environnement de bac à sable dans Dynamics 365 Commerce
description: Cet article explique comment configurer des fonctionnalités facultatives pour un environnement de bac à sable Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 4935f5f6ee17cba9c09eb79132119a7cbc08d9ad
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270353"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-sandbox-environment"></a>Configurer les fonctionnalités facultatives pour un environnement de bac à sable dans Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cet article explique comment configurer des fonctionnalités facultatives pour un environnement de bac à sable Microsoft Dynamics 365 Commerce.

## <a name="prerequisites"></a>Conditions préalables

Si vous souhaitez montrer les fonctionnalités d’e-mail transactionnelles, les conditions requises suivantes doivent être remplies :

- Un serveur de messagerie disponible (serveur \[SMTP\], Simple Mail Transfer Protocol) qui peut être utilisé par l’abonnement Microsoft Azure dans lequel vous avez mis en service l’environnement de bac à sable.
- Le nom de domaine complet (FQDN)/adresse IP, le numéro de port SMTP, et les détails d’authentification disponibles.

## <a name="configure-the-image-back-end"></a>Configurer l’arrière-plan de l’image

### <a name="find-your-media-base-url"></a>Rechercher votre URL de base multimédia

> [!NOTE]
> Avant de pouvoir terminer cette procédure, vous devez suivre les étapes dans [Configurer votre site dans Commerce](cpe-post-provisioning.md#set-up-your-e-commerce-sites).

1. Connectez-vous au générateur de site Commerce en utilisant l’URL que vous avez notée lorsque vous avez initialisé le commerce électronique lors de la mise en service (voir [Initialiser le commerce électronique](provisioning-guide.md#initialize-e-commerce)).
1. Ouvrez le site **Fabrikam**, **Adventure Works** ou **Adventure Works Business** avec lequel vous souhaitez travailler.
1. Dans le menu à gauche, sélectionnez **Bibliothèque multimédia**.
1. Sélectionnez un actif d’image unique.
1. Dans l’inspecteur de propriété à droite, recherchez la propriété **URL publique**. La valeur est une URL. Voici un exemple :

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.

1. Remplacez le dernier identificateur de l’URL (**MA1nQC** dans l’exemple précédent) par la chaîne **search?fileName=**. Voici à quoi ressemble l’exemple d’URL après cette modification :

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    Cette URL est l’URL de votre base multimédia. Prenez-en note.

### <a name="update-the-media-base-url"></a>Mise à jour de l’URL de base multimédia

1. Connectez-vous au siège de Commerce.
1. Utilisez le menu à gauche pour accéder à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Profils du canal**.
1. Sélectionnez **Modifier**.
1. Sous **Propriétés du profil**, remplacez la valeur de la propriété **URL de base du serveur multimédia** par l’URL de base multimédia créée précédemment.
1. Sélectionnez le canal nommé **scXXXXXXXXX**.
1. Sous **Propriétés du profil**, sélectionnez **Ajouter**.
1. Pour la propriété qui a été ajoutée, sélectionnez **URL de base du serveur multimédia** comme clé de propriété. En tant que valeur de propriété, entrez l’URL de la base multimédia que vous avez créée précédemment.
1. Sélectionnez **Enregistrer**.

## <a name="configure-and-test-the-email-server"></a>Configuration et test du serveur de messagerie

> [!NOTE]
> Le serveur SMTP ou le service de messagerie que vous entrez ici doivent être accessibles à partir de l’abonnement Azure que vous utilisez pour l’environnement.

1. Connectez-vous au siège de Commerce.
1. Utilisez le menu de gauche pour accéder à **Modules \> Retail et Commerce \> Paramétrage du Siège \> Paramètres \> Paramètres de la messagerie**.
1. Sur l’onglet **Paramètres SMTP** dans le champ **Serveur de courrier sortant**, saisissez le nom de domaine complet ou l’adresse IP de votre serveur SMTP ou service de messagerie.
1. Dans le champ **Numéro de port SMTP**, entrez le numéro du port à utiliser. (Si vous n’utilisez pas Secure Sockets Layer \[SSL\], le numéro de port par défaut est **25**.)
1. Si l’authentification est requise, entrez des valeurs dans les champs **Nom d’utilisateur** et **Mot de passe**.
1. Sélectionnez **Enregistrer**.
1. Sélectionnez **Actualiser**.
1. Sur l’onglet **Tester la messagerie** dans le champ **Fournisseur de messagerie**, sélectionnez **SMTP**.
1. Dans le champ **Destinataire**, entrez l’adresse e-mail à laquelle l’e-mail de test soit remis.
1. Sélectionnez **Envoyer un e-mail de test**.

## <a name="configure-email-templates"></a>Configuration des modèles d’e-mails

Pour chaque événement transactionnel pour lequel envoyer des e-mails vous devez mettre à jour le modèle d’e-mail avec une adresse e-mail d’expéditeur valide.

1. Connectez-vous au siège de Commerce.
1. Utilisez le menu de gauche pour accéder à **Modules \> Retail et Commerce \> Paramétrage du Siège \> Paramètres \> Modèles d’e-mail d’organisation**.
1. Sélectionnez **Afficher la liste**.
1. Pour chaque modèle de la liste, procédez comme suit :

    1. Ensuite, dans le champ **E-mail de l’expéditeur**, entrez l’adresse e-mail de l’expéditeur.
    1. Facultatif : Dans le champ **Nom de l’expéditeur**, entrez le nom qui doit être utilisé comme nom d’expéditeur.

1. Sélectionnez **Enregistrer**.

## <a name="customize-email-templates"></a>Personnaliser des modèles d’e-mail

Vous souhaiterez peut-être personnaliser les modèles d’e-mails afin qu’ils utilisent des images différentes. Ou vous souhaiterez peut-être mettre à jour les liens dans les modèles afin qu’ils accèdent à votre environnement de bac à sable. Cette procédure explique le téléchargement des modèles par défaut, leur personnalisation et la mise à jour des modèles à jour dans le système.

1. Dans un navigateur web, téléchargez le [fichier .zip des modèles d’e-mails démo Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) sur votre ordinateur local. Ce fichier contient les documents HTML suivants :

    - Modèle de confirmation de commande
    - Émettre un modèle de carte cadeau
    - Nouveau modèle de commande
    - Modèle de commande emballée
    - Modèle de commande à prélever

1. Personnaliser les modèles à l’aide d’un texte ou un éditeur HTML. Voir la liste des [jetons pris en charge](#supported-tokens-in-the-email-template) plus loin dans cet article.
1. Connectez-vous à Commerce.
1. Utilisez le menu à gauche pour accéder à **Modules \> Administration de l’organisation \> Paramétrage \> Modèles d’e-mail de l’organisation**.
1. Développez la liste à gauche pour afficher tous les modèles.
1. Pour chaque modèle que vous souhaitez personnaliser, procédez comme suit :

    1. Sélectionnez le modèle dans la liste.
    1. Sous **Contenu de message électronique**, sélectionnez la version de langue appropriée dans la liste. (La langue par défaut est **en-us**.)
    1. En dessous de **Contenu du message électronique**, sélectionnez **Modifier**. Le volet **Télécharger un modèle d’e-mail** apparaît.
    1. Sélectionnez **Parcourir** et recherchez le fichier HTML contenant le contenu personnalisé.
    1. Sélectionnez **Charger**. Le modèle est chargé dans le système et un aperçu s’affiche.
    1. Cliquez sur **OK**.
    1. Facultatif : Personnalisez la propriété **Objet** du modèle.
    1. Sélectionnez **Enregistrer**.

### <a name="supported-tokens-in-the-email-template"></a>Jetons pris en charge dans le modèle d’e-mail

Au moment de l’affichage de l’e-mail, ces jetons sont remplacés par les valeurs réelles s’appliquant au client et à sa commande.

#### <a name="sales-order"></a>Commande client

Les jetons suivants s’appliquent à la commande client globale.

| Nom du jeton | Jeton |
|-------------------|-------|
| Numéro d’ordre      | %salesid% |
| Nom du client   | %customername% |
| Adresse de livraison  | %deliveryaddress% |
| Adresse de facturation   | %customeraddress% |
| Date de commande        | %shipdate% |
| Mode de distribution     | %modeofdelivery% |
| Remise          | %discount% |
| Taxe de vente         | %tax% |
| Total de la commande       | %total% |

#### <a name="sales-line"></a>Ligne de vente

Les jetons suivants sont remplacés par des valeurs pour chaque produit de la commande.

> [!NOTE]
> Mettez le jeton **Liste de produits - début** au début du bloc HTML répété pour chaque produit, et placez le jeton **Liste de produits - fin** à la fin du bloc.

| Nom du jeton      | Jeton |
|------------------------|-------|
| Liste de produits - début   | \<!--%tablebegin.salesline% --\> |
| Liste de produits - fin     | \<!--%tableend.salesline%--\> |
| Nom du produit           | %lineproductname% |
| Description            | %lineproductdescription% |
| Quantité               | %linequantity% |
| Prix unitaire de la ligne        | %lineprice% (vérifier) |
| nombre total d’articles de ligne        | %linenetamount% |
| remise ligne          | %linediscount% |
| Date d’expédition              | %lineshipdate% |
| Méthode d’approvisionnement     | %linedeliverymode% |
| adresse de livraison       | %linedeliveryaddress% |
| Unité de vente de la ligne | %lineunit% |

## <a name="additional-resources"></a>Ressources supplémentaires

[Mettre en service un environnement de bac à sable dans Dynamics 365 Commerce](provisioning-guide.md)

[Configurer un environnement de bac à sable dans Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurer le BOPIS dans un environnement de bac à sable Dynamics 365 Commerce](cpe-bopis.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portail Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site web Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
