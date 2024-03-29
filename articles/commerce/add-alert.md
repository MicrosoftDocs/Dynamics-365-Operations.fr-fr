---
title: Module Bannière promotionnelle
description: Cet article couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: fbde146923d1448e382cbf2458880f7e300f605c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279733"
---
# <a name="promo-banner-module"></a>Module Bannière promotionnelle

[!include [banner](includes/banner.md)]

Cet article couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Les modules de bannière promotionnelle sont utilisés pour afficher des messages d’information intégrés dans une page. Ils peuvent être utilisés pour afficher des promotions à l’échelle du site qui figurent sur toutes les pages d’un site de commerce électronique. 

Les modules de bannière promotionnelle prennent en charge un texte et un lien. Si plusieurs messages sont ajoutés à un module de bannière promotionnelle, il devient une bannière carrousel tournante qui permet aux clients de parcourir tous les messages. 

Les modules de bannière promotionnelle sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n’importe quelle page.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Exemples d’utilisation de bannières promotionnelles dans l’e-commerce

Les bannières promotionnelles peuvent être utilisées dans l’en-tête du site pour afficher des promotions ou des messages à l’échelle du site, comme dans les exemples suivants.

« Les soldes annuelles se terminent dans 10 jours »

« Réalisez des économisez avec les soldes de la rentrée. Achetez dès maintenant. »

« Profitez des soldes de Thanksgiving ! » 

L’image suivante montre un exemple d’une bannière promotionnelle.

![Exemple d’un module de bannière promotionnelle.](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a>Propriétés du module de bannière promotionnelle

| Nom de la propriété             | Valeur                              | Description |
|---------------------------|------------------------------------|-------------|
| Messages de bannière           | Texte et liens                     | Un groupe de texte et de liens. |
| Lire automatiquement                  | **Vrai** ou **Faux**              | Une valeur qui indique si les messages sont automatiquement parcourus, si plusieurs messages sont configurés. |
| Intervalle de transition entre les diapositives | Un certain nombre de millisecondes (ms)      | L’intervalle qui est utilisé pour parcourir les messages. |
| Ignorer             | **Vrai** ou **Faux**              | Si la valeur est définie sur **Vrai**, les clients peuvent ignorer l’alerte. |
| Afficher le flipper du carrousel     | **Vrai** ou **Faux**              | Valeur qui indique si les flippers du carrousel doivent être affichés, afin que les clients puissent parcourir manuellement plusieurs éléments de bannière. |
| Alignement du texte            | **Droite**, **Gauche** ou **Centre** | L’alignement du texte dans le module de bannière promotionnelle. |
| Lien                      | Une URL                              | URL pour un lien supplémentaire. |
|Alignement du texte             | **Droite**, **Gauche** ou **Centre** | Cette propriété est disponible en tant qu’extension de thème dans le thème Adventure Works. Elle permet à un utilisateur de définir l’alignement du texte dans la bannière promotionnelle. |

> [!IMPORTANT]
> Le thème Adventure Works est disponible à partir de la version 10.0.20 de Dynamics 365 Commerce.

## <a name="add-a-promo-banner-module-to-a-page"></a>Ajouter un module de bannière promotionnelle à une page 

Pour ajouter un module de bannière promotionnelle à une page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de bannière promotionnelle**, puis cliquez sur **OK**.
1. Dans **Contour de la page**, ajoutez un module **Page par défaut** à l’emplacement **Corps**. 
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier. 
1. Utilisez le modèle que vous venez de générer pour créer une page qui s’appelle **page de bannière promotionnelle**. 
1. À l’emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur. 
1. Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Dans **Contour de la page**, ajoutez un module bannière promotionnelle au module conteneur.
1. Dans les paramètres du module de bannière, ajoutez un ou plusieurs messages de bannière. Chaque message peut avoir du texte avec un lien. Vous pouvez modifier les autres propriétés pour personnaliser davantage le module.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. En haut de la page, vous devez voir une alerte avec le texte que vous avez ajouté.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

> [!NOTE]
> Une bannière promotionnelle est généralement utilisée dans l’emplacement d’en-tête de page ou un emplacement de sous-titre.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de texte](add-content-rich-block.md)

[Module de bloc de contenu](add-hero-module.md)

[Module de lecture vidéo](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
