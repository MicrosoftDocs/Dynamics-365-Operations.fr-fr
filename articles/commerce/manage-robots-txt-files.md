---
title: Gérer les fichiers robots.txt
description: Cette rubrique décrit comment gérer les fichiers robots.txt dans Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2e25a584121b700e566c29dbfe3fbbd72bf998cc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982539"
---
# <a name="manage-robotstxt-files"></a>Gérer les fichiers robots.txt


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment gérer les fichiers robots.txt dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

La norme d'exclusion des bots, ou robots.txt, est une norme que les sites web utilisent pour communiquer avec les bots web. Elle indique aux bots web les zones d'un site web qui ne doivent pas être visitées. Les bots sont souvent utilisés par les moteurs de recherche pour indexer les sites web.

Pour exclure des bots d'un serveur, vous créez un fichier sur le serveur. Dans ce fichier, vous spécifiez une stratégie d'accès pour les bots. Le fichier doit être accessible via HTTP à l'URL locale **/robots.txt**. Le fichier robots.txt aide les moteurs de recherche à indexer le contenu de votre site.

Dynamics 365 Commerce vous permet de télécharger un fichier robots.txt pour votre domaine. Pour chaque domaine de votre environnement Commerce, vous pouvez télécharger un fichier robots.txt et l'associer à ce domaine.

Pour plus d'informations sur le fichier robots.txt, visitez [Les pages de bots web](https://www.robotstxt.org/).

## <a name="upload-a-robotstxt-file"></a>Charger un fichier robots.txt

Après avoir créé et modifié votre fichier robots.txt conformément à la [norme d'exclusion des bots](https://www.robotstxt.org/orig.html), assurez-vous que le fichier est accessible sur l'ordinateur sur lequel vous utiliserez les outils de création de Commerce. Le fichier doit être nommé **robots.txt**. Pour de meilleurs résultats, il doit être dans le format indiqué dans la norme. Chaque client Commerce est responsable de la validation et de la maintenance du contenu de son fichier robots.txt. Pour charger un fichier robots.txt, vous devez être connecté à Commerce en tant qu'administrateur système.

Pour charger un fichier robots.txt sur votre site dans Commerce, procédez comme suit.

1. Connectez-vous à Commerce en tant qu'administrateur système.
2. Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.
3. En dessous de **Paramètres client**, sélectionnez **Robots.txt**. Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.
4. Sélectionnez **Gérer** pour charger un fichier robots.txt pour un domaine dans votre environnement.
5. Dans le menu de droite, cliquez sur le bouton **Télécharger** (flèche pointant vers le haut) à côté du domaine associé au fichier robots.txt. Une boîte de dialogue d'explorateur de fichiers apparaît.
6. Dans la boîte de dialogue, recherchez et sélectionnez le fichier robots.txt que vous souhaitez charger pour le domaine associé, puis sélectionnez **Ouvrir** pour terminer le chargement.

> [!NOTE] 
> Pendant le chargement, Commerce vérifie que le fichier est un fichier texte, mais il ne valide pas le contenu du fichier.

## <a name="download-a-robotstxt-file"></a>Télécharger un fichier robots.txt

Pour télécharger un fichier robots.txt sur votre site dans Commerce, procédez comme suit.

1. Connectez-vous à Commerce en tant qu'administrateur système.
2. Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.
3. En dessous de **Paramètres client**, sélectionnez **Robots.txt**. Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.
4. Sélectionnez **Gérer** pour télécharger un fichier robots.txt pour un domaine dans votre environnement.
5. Dans le menu de droite, cliquez sur le bouton **Télécharger** (flèche pointant vers le bas) à côté du domaine associé au fichier robots.txt. Une boîte de dialogue d'explorateur de fichiers apparaît.
6. Dans la boîte de dialogue, accédez à l'emplacement souhaité sur votre lecteur local, confirmez ou entrez un nom de fichier, puis sélectionnez **Enregistrer** pour terminer le téléchargement.

> [!NOTE]
> Cette procédure peut être utilisée pour télécharger uniquement les fichiers robots.txt qui ont été précédemment chargés via les outils de création de Commerce.

## <a name="delete-a-robotstxt-file"></a>Supprimer un fichier robots.txt

Pour supprimer un fichier robots.txt sur votre site dans Commerce, procédez comme suit.

1. Connectez-vous à Commerce en tant qu'administrateur système.
2. Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.
3. En dessous de **Paramètres client**, sélectionnez **Robots.txt**. Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.
4. Sélectionnez **Gérer** pour supprimer un fichier robots.txt pour un domaine dans votre environnement.
5. Dans le menu de droite, cliquez sur le bouton **Supprimer** (symbole de corbeille) à côté du domaine associé au fichier robots.txt. Une fenêtre de l'explorateur de fichiers apparaît.
6. Dans la fenêtre de l'explorateur de fichiers, recherchez et sélectionnez le fichier robots.txt que vous souhaitez supprimer pour le domaine, puis sélectionnez **Ouvrir**. Une zone de message d'avertissement apparaît.
7. Dans la zone de message, sélectionnez **Supprimer** pour confirmer la suppression du fichier robots.txt.

> [!NOTE] 
> Cette procédure peut être utilisée pour supprimer uniquement les fichiers robots.txt qui ont été précédemment chargés via les outils de création de Commerce.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déployer un nouveau client e-commerce](deploy-ecommerce-site.md)

[Créer un site d’e-commerce](create-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]