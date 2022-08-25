---
title: Activation de la détection du magasin selon l’emplacement
description: Cet article décrit la procédure d’activation de la détection du magasin selon l’emplacement pour votre site Dynamics 365 Commerce.
author: brianshook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 38c93e30a606d818d909a4ec014009c18c25e8c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274338"
---
# <a name="enable-location-based-store-detection"></a>Activation de la détection du magasin selon l’emplacement

[!include [banner](includes/banner.md)]

Cet article décrit la procédure d’activation de la détection du magasin selon l’emplacement pour votre site Dynamics 365 Commerce.

La détection du magasin selon l’emplacement dans Commerce vous permet de fournir le contenu approprié de site aux clients, en fonction de leur emplacement. Lorsque la détection du magasin selon l’emplacement est activée, le service d’affichage de Commerce utilise les informations de pays/région de l’adresse IP du navigateur web du client pour diriger le client vers la meilleure configuration géographique de site disponible.

## <a name="privacy-notice"></a>Avis de confidentialité

Si vous activez la fonction de détection du magasin selon l’emplacement, les informations du navigateur du client sont envoyées à un service d’emplacement Microsoft. Cette information est alors utilisée pour fournir le contenu du client approprié à l’emplacement du client. Les informations envoyées à partir du navigateur et les informations basées sur l’emplacement renvoyées au client sont soumises à des politiques de conformité des cookies et de confidentialité.

## <a name="turn-on-location-based-store-detection"></a>Activer la détection du magasin selon l’emplacement

Pour activer la détection du magasin selon l’emplacement dans Commerce, procédez comme suit.

1. Dans l’outil de création, accédez à votre site.
1. Dans le volet de navigation sur la gauche, sélectionnez **Gestion du site**.
1. Sélectionnez **Paramètres du site**.
1. Définissez l’option **Activer la détection du magasin selon l’emplacement** sur **Activé**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déployer un nouveau client e-commerce](deploy-ecommerce-site.md)

[Créer un site d’e-commerce](create-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
