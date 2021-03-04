---
title: Module Partage social
description: Cette rubrique couvre les modules de partage social et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 82a8795360f453cdee19fa6e9e376a42e8276849
ms.sourcegitcommit: 510ca8b14d8b5334e50aca1b15d636c65fcc9888
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4412398"
---
# <a name="social-share-module"></a>Module Partage social

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de partage social et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les modules de partage social permettent aux utilisateurs de partager des URL de page de site d’e-commerce sur les médias sociaux, tels que Facebook, Twitter, Pinterest et LinkedIn. Les URL des pages du site peuvent également être partagées par e-mail. Les modules de partage social sont couramment utilisés sur les pages de détails sur les produits (PDP) pour aider les utilisateurs à partager des informations sur les produits.

Chaque module de partage social est un conteneur pour les modules d’éléments de partage social. Chaque module d’élément de partage social peut être configuré pour pointer vers un média social spécifique. Intégration avec Facebook, Twitter, Pinterest, LinkedIn et les e-mails sont pris en charge par défaut. Lorsqu’un utilisateur du site sélectionne un symbole de réseau social, un iframe HTML est lancé pour le site de réseau social respectif. Dans l’iframe, l’utilisateur peut se connecter et publier le contenu de la page qu’il consultait.

Chaque plateforme de média social peut suivre les cookies, ce module oblige donc les utilisateurs du site à accepter le message de notification de consentement aux cookies. Lorsque le consentement aux cookies n’est pas accepté, le module est masqué sur la page. Pour plus d’informations, voir [Conformité des cookies](cookie-compliance.md).

L’illustration suivante met en évidence un exemple de module de partage social utilisé sur une page de détails de produit.

![Exemple de module de partage social](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a>Propriétés du module Partage social

| Nom de la propriété             | Valeur                 | Description |
|---------------------------|-----------------------|-------------|
| Légende                  | Détails | Cette propriété spécifie une légende pour le module. |
| Orientation | **Horizontal** ou **Vertical**  | Cette propriété définit l’orientation de la mise en page des éléments de médias sociaux. |

## <a name="social-share-item-module-properties"></a>Propriétés du module d’élément Partage social
| Nom de la propriété             | Valeur                 | Description |
|---------------------------|-----------------------|-------------|
| Réseaux sociaux              | **Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **E-mail** | Un menu déroulant avec une liste de plateformes de médias sociaux. |
| Icône |Image    | Ce sera l’image qui sera affichée pour les médias sociaux respectifs. En tant que meilleure pratique, reportez-vous au Kit de développement logiciel (SDK) de la plateforme de médias sociaux pour obtenir l’image recommandée à utiliser pour chaque plateforme. |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a>Ajouter un module de partage social à un module de zone d’achat

Pour ajouter un module de partage social à un module de zone d’achat, procédez comme suit.

1. Dans le site Fabrikam, sélectionnez **Pages**, puis la page **DefaultPDP** pour ouvrir la page des détails du produit. 
1. Dans l’emplacement **Zone d’achat (obligatoire)**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Partage social**, puis sélectionnez **OK**.
1. Dans l’emplacement **Partage social**, sélectionnez le bouton (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **SocialShare**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module **SocialShare**, sous **Orientation**, sélectionnez **Horizontal**. Ajoutez une légende si nécessaire.
1. Dans l’emplacement **SocialShare**, sélectionnez le bouton (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **SocialShareItem**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module **SocialShareItem**, sous **Réseau social**, sélectionnez **Facebook**.
1. Dans le volet des propriétés du module **SocialShareItem**, sous **Icône**, sélectionnez **+ Ajouter une image**.
1. Dans la boîte de dialogue **Sélecteur multimédia**, sélectionnez l’image du logo Facebook, puis sélectionnez **OK**. Si aucune image du logo Facebook n’est présente, sélectionnez **Importer un nouvel élément multimédia** pour en charger une.
1. Ajoutez et configurez des modules **SocialShareItem** selon les besoins.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. La page affichera le module de partage social.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Zone d’achat](add-buy-box.md)

[Conformité des cookies](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]