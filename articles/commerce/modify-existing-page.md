---
title: Modifier une page de site existante
description: Cet article décrit comment modifier une page existante du site dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: fb5348c2f29625647f06e48233f877a847677486
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286916"
---
# <a name="modify-an-existing-site-page"></a>Modifier une page existante du site

[!include [banner](includes/banner.md)]

Cet article décrit comment modifier une page existante du site dans Microsoft Dynamics 365 Commerce.

Si vous devez modifier une page, la première étape consiste à l’ouvrir dans l’éditeur de page. Accédez au site qui contient votre page, puis, dans la liste des pages, recherchez la page que vous souhaitez. Si vous ne trouvez pas la page, vous pouvez utiliser la fonctionnalité de recherche enrichie de l’outil de création. Tapez le nom exact de la page, ou tapez les premières lettres de celle-ci, puis un astérisque (\*). Une liste filtrée des pages s’affiche. Vous pouvez utiliser cette liste pour rechercher la page de votre choix. Après avoir trouvé la page appropriée, sélectionnez le nom de la page pour ouvrir la page dans l’éditeur de page.

> [!TIP]
> Si votre page est visible dans le contrôleur de page, vous pouvez sélectionner **Modifier** et archiver la page avant de l’ouvrir dans l’éditeur de page. De cette manière, vous pouvez vérifier plusieurs pages simultanément.

Une fois la page ouverte dans l’éditeur de page, vous devez vous assurer qu’elle est extraite pour vous. La barre de commande dans l’outil de création est dynamique, contextuelle, et sensible à l’état. Par conséquent, elle n’affiche que les actions que vous pouvez actuellement exécuter sur la page. Par exemple, si la page n’est pas extraite pour vous, les boutons **Enregistrer** et **Terminer les modifications** n’apparaissent pas dans la barre de commande. L’état de la page est également affiché sur le côté droit de la fenêtre.

Si la page n’est pas déjà extraite pour vous, sélectionnez **Modifier** sur la barre de commande. La barre de commande change pour refléter le nouvel état de la page. Vous recevez également une notification indiquant que la page a été extraite pour vous.

L’étape suivante consiste à apporter vos modifications réelles. Souvent, vous allez utiliser l’arborescence de contour de page à gauche pour rechercher et sélectionner le module à modifier, puis apporter des modifications dans le volet de propriétés à droite. 

Toutefois, votre modification peut impliquer parfois d’ajouter ou de supprimer des modèles ou des fragments. Pour ajouter un fragment ou un module, utilisez l’arborescence de contour de page pour rechercher l’emplacement auquel vous souhaitez ajouter le module ou le fragment, puis sélectionnez le bouton des points de suspension (**...**) pour cet emplacement. Un menu apparaît qui inclut des commandes pour ajouter un module ou un fragment. Pour supprimer un module ou un fragment, recherchez et sélectionnez-le dans l’arborescence de contour de page, sélectionnez le bouton des points de suspension, puis sélectionnez la commande pour supprimer le module ou le fragment.

> [!TIP]
> Vous pouvez également afficher et modifier les propriétés d’un module qui est visible dans l’aperçu du générateur de page visuel en le sélectionnant directement.

Après avoir fini d’apporter vos modifications et prévisualisé leurs effets, vous devez archiver la page en sélectionnant **Terminer les modifications** sur la barre de commande. 

Pour publier vos modifications immédiatement, sélectionnez **Publier** dans la barre de commande. La dernière version archivée de la page que vous avez modifiée est publiée et devient disponible aux utilisateurs externes qui regardent votre site. 

## <a name="example-change-the-video-on-the-home-page"></a>Exemple : Modifier la vidéo dans la page d’accueil

L’exemple suivant montre comment modifier la page d’accueil en modifiant la vidéo qui apparaît dans le module de lecteur de vidéo.

1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation sur la gauche, sélectionnez **Pages**.
1. Recherchez et sélectionnez la page d’accueil pour l’ouvrir dans l’éditeur de page.
1. Dans la barre de commande, sélectionnez **Modifier**.
1. Dans le contour de page, sélectionnez l’emplacement **Principal**.
1. Sous l’emplacement **Principal**, développez tous les modules de conteneur fluides.
1. Recherchez et sélectionnez le module de lecteur vidéo.
1. Dans le volet de propriétés de droite, sélectionnez la propriété **vidéo**. Le sélecteur d’actif s’affiche.
1. Dans le sélecteur d’actifs, sélectionnez un actif vidéo disponible, ou sélectionnez **Chargement de nouvel actif** pour charger un nouvel actif vidéo.
1. Cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Dans le champ **Commentaires**, entrez **A modifié la vidéo**, puis sélectionnez **OK**.
1. Sélectionnez **Aperçu** pour afficher un aperçu de la page mise à jour. Lorsque vous avez terminé, fermez l’onglet d’aperçu pour revenir à l’outil de création.
1. Sélectionnez **Publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter une nouvelle page de site](add-new-page.md)

[Sélectionner des dispositions de page](select-page-layouts.md)

[Gestion des métadonnées SEO](manage-seo-metadata.md)

[Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md)

[Enrichir une page de produit](enrich-product-page.md)

[Enrichir une page d’arrivée de catégorie](enrich-category-page.md)

[Vérifier l’accessibilité du contenu de la page](verify-accessibility.md)

[Créer des pages e-commerce dynamiques basées sur des paramètres d’URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
