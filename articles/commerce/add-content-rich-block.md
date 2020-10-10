---
title: Module de bloc de texte
description: Cette rubrique couvre les modules de bloc de texte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c6527ad00e74fa105f3873036eb56557b98b05aa
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817376"
---
# <a name="text-block-module"></a>Module de bloc de texte

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de bloc de texte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de bloc de texte est un module utilisé pour ajouter du contenu textuel. Ce contenu peut être informationnel ou promotionnel.

Les modules de bloc de texte sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page. Ils sont autonomes et ne dépendent du contexte de page ou d'un autre module.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Exemples de modules de bloc de texte dans le commerce électronique

Les modules de bloc de texte peuvent être utilisés comme suit :

* Pour présenter des fonctionnalités de produit sur une page de détails des produits.
* À titre indicatif sur n'importe quelle page. Par exemple, ils peuvent expliquer les avantages des programmes de fidélité, décrire les stratégies d'expédition et de retour, répondre aux questions fréquentes, ou offrir du contenu « À propos de nous ».
* Pour ajouter des messages personnalisés sur une page de détails des produits. (par exemple, « Expédition gratuite pour les commandes de plus de 50 $ »).
* Pour les exclusions de responsabilité et les détails de contact sur les pages de détails des produits, des pages de panier, les pages de caisse et d'autres pages (par exemple, « L'expédition et les retours sont soumis à des stratégies de magasin »).

L'image suivante montre un exemple de module de bloc de texte utilisé sur une page d'accueil.

![Exemple d'un module de bloc de texte](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a>Propriétés de module de bloc de texte

| Nom de la propriété     | Valeur                                            | Description |
|-------------------|--------------------------------------------------|-------------|
| Texte enrichi         | Texte enrichi                                        | Texte du paragraphe. Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques. |
| Nom de classe personnalisé | Un nom de classe de feuilles de style en cascade (CSS)        | Le nom d'une classe CSS personnalisée qu'un développeur fournit pour formater ce module. Le nom de classe doit être défini dans le pack de thème. |
| Taille de la police         | **Petit**, **Moyen**, **Grand** ou **X-Large** | La taille de police du contenu. |

## <a name="add-a-text-block-module-to-a-page"></a>Ajouter un module de bloc de texte à une page

Pour ajouter un module de bloc de texte à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de contenu**.
1. Dans l'emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Page par défaut**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle de contenu**. Sous **Nom de la page**, entrez **Page de contenu**, puis sélectionnez **OK**.
1. Dans l'emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans le volet de propriétés du module conteneur, définissez la propriété **Largeur** sur **Remplir le conteneur**.
1. Dans l'emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Bloc de texte**, puis sélectionnez **OK**. 
1. Dans le volet des propriétés du module de bloc de texte, ajoutez du texte au champ **RTF**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Bannière promotionnelle](add-alert.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de contenu](add-hero-module.md)

[Module de lecture vidéo](add-video-player.md)

