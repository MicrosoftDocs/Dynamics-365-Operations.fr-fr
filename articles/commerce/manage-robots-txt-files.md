---
title: Gérer les fichiers robots.txt
description: Cet article décrit comment gérer les fichiers robots.txt dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.search.industry: retail
ms.search.form: ''
ms.openlocfilehash: b66d6f725c345ff82d3f3f8c33d609fa770addf1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286409"
---
# <a name="manage-robotstxt-files"></a>Gérer les fichiers robots.txt

[!include [banner](includes/banner.md)]

Cet article décrit comment gérer les fichiers robots.txt dans Microsoft Dynamics 365 Commerce.

La norme d’exclusion des robots, ou robots.txt, est une norme que les sites web utilisent pour communiquer avec les robots web. Elle indique aux robots web les zones d’un site web qui ne doivent pas être visitées. Les robots sont souvent utilisés par les moteurs de recherche pour indexer les sites web.

Pour exclure des robots d’un serveur, vous créez un fichier sur le serveur. Dans ce fichier, vous spécifiez une stratégie d’accès pour les robots. Le fichier doit être accessible via HTTP à l’URL locale **/robots.txt**. Le fichier robots.txt aide les moteurs de recherche à indexer le contenu de votre site.

Dynamics 365 Commerce vous permet de télécharger un fichier robots.txt pour votre domaine. Pour chaque domaine de votre environnement Commerce, vous pouvez télécharger un fichier robots.txt et l’associer à ce domaine.

Pour plus d’informations sur le fichier robots.txt, visitez [Les pages de robots web](https://www.robotstxt.org/).

## <a name="upload-a-robotstxt-file"></a>Charger un fichier robots.txt

Après avoir créé et modifié votre fichier robots.txt conformément à la [norme d’exclusion des robots](https://www.robotstxt.org/orig.html), assurez-vous que le fichier est accessible sur l’ordinateur sur lequel vous utiliserez les outils de création de Commerce. Le fichier doit être nommé **robots.txt**. Pour de meilleurs résultats, il doit être dans le format indiqué dans la norme. Chaque client Commerce est responsable de la validation et de la maintenance du contenu de son fichier robots.txt. Pour charger un fichier robots.txt, vous devez être connecté à Commerce en tant qu’administrateur système.

Pour charger un fichier robots.txt dans Commerce, suivez ces étapes.

1. Connectez-vous à Commerce en tant qu’administrateur système.
2. Dans le volet de navigation de gauche, sélectionnez **Paramètres de l’abonné** (à côté du symbole d’engrenage) pour l’agrandir.
3. Sous **Paramètres abonné**, sélectionnez **Robots.txt**. Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.
4. Sélectionnez **Gérer** pour charger un fichier robots.txt pour un domaine dans votre environnement.
5. Dans le menu de droite, sélectionnez le bouton **Télécharger** (la flèche pointant vers le haut) à côté du domaine associé au fichier robots.txt. Une boîte de dialogue de navigateur de fichier apparaît.
6. Dans la boîte de dialogue, parcourez et sélectionnez le fichier robots.txt que vous souhaitez charger pour le domaine associé, puis sélectionnez **Ouvrir** pour terminer le chargement.

> [!NOTE] 
> Pendant le chargement, Commerce vérifie que le fichier est un fichier texte, mais il ne valide pas le contenu du fichier.

## <a name="download-a-robotstxt-file"></a>Télécharger un fichier robots.txt

Pour télécharger un fichier robots.txt dans Commerce, suivez ces étapes.

1. Connectez-vous à Commerce en tant qu’administrateur système.
2. Dans le volet de navigation de gauche, sélectionnez **Paramètres abonné** (à côté du symbole d’engrenage) pour l’agrandir.
3. Sous **Paramètres abonné**, sélectionnez **Robots.txt**. Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.
4. Sélectionnez **Gérer** pour télécharger un fichier robots.txt pour un domaine dans votre environnement.
5. Dans le menu de droite, sélectionnez le bouton **Télécharger** (la flèche pointant vers le bas) à côté du domaine associé au fichier robots.txt. Une boîte de dialogue de navigateur de fichier apparaît.
6. Dans la boîte de dialogue, accédez à l’emplacement souhaité sur votre lecteur local, confirmez ou entrez un nom de fichier, puis sélectionnez **Enregistrer** pour terminer le téléchargement.

> [!NOTE]
> Cette procédure peut être utilisée pour télécharger uniquement les fichiers robots.txt qui ont été précédemment chargés via les outils de création de Commerce.

## <a name="delete-a-robotstxt-file"></a>Supprimer un fichier robots.txt

Pour supprimer un fichier robots.txt dans Commerce, suivez ces étapes.

1. Connectez-vous à Commerce en tant qu’administrateur système.
2. Dans le volet de navigation de gauche, sélectionnez **Paramètres abonné** (à côté du symbole d’engrenage) pour l’agrandir.
3. Sous **Paramètres abonné**, sélectionnez **Robots.txt**. Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.
4. Sélectionnez **Gérer** pour supprimer un fichier robots.txt pour un domaine dans votre environnement.
5. Dans le menu de droite, sélectionnez le bouton **Supprimer** (le symbole de corbeille) à côté du domaine associé au fichier robots.txt. Une fenêtre de navigateur de fichier apparaît.
6. Dans la fenêtre de navigateur de fichier, parcourez et sélectionnez le fichier robots.txt que vous souhaitez supprimer pour le domaine, puis sélectionnez **Ouvrir**. Une zone de message d’avertissement apparaît.
7. Dans la zone de message, sélectionnez **Supprimer** pour confirmer la suppression du fichier robots.txt.

> [!NOTE] 
> Cette procédure peut être utilisée pour supprimer uniquement les fichiers robots.txt qui ont été précédemment chargés via les outils de création de Commerce.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration de votre nom de domaine](configure-your-domain-name.md)

[Déployer un nouveau abonné e-commerce](deploy-ecommerce-site.md)

[Créer un site e-commerce](create-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Chargement de redirections URL en masse](upload-bulk-redirects.md)

[Configurer un abonné B2C dans Commerce](set-up-B2C-tenant.md)

[Configurer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs abonnés B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d’un réseau de distribution de contenu (CDN)](add-cdn-support.md)

[Activer la détection du magasin selon l’emplacement](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
