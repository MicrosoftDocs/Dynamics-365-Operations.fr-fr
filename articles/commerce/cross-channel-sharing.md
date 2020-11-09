---
title: Activer et utiliser le partage intercanal
description: Cette rubrique décrit comment activer et utiliser la fonctionnalité de partage intercanal du générateur de site Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/16/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 77284045bda193500117978102c0565c5f15ec6d
ms.sourcegitcommit: b063bf3a52f19baa11ddba31ef9313d58a0f610e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4019516"
---
# <a name="enable-and-use-cross-channel-sharing"></a>Activer et utiliser le partage intercanal

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment activer et utiliser la fonctionnalité de partage intercanal du générateur de site Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Le partage intercanal permet aux détaillants de réutiliser et de partager du contenu entre plusieurs canaux d'un site. Cette fonctionnalité est utile lorsque la langue de base des canaux du site est compatible ou lorsque ces canaux ont de nombreux éléments de contenu en commun.

Pour que le partage intercanal fonctionne, un canal par défaut doit être activé. Il servira pour rechercher du contenu disponible lorsqu'une version spécifique au canal du contenu demandé n'est pas trouvée. Le contenu destiné à être partagé entre les canaux est créé dans le canal par défaut. Ce contenu peut être localisé pour tous les paramètres régionaux utilisés sur n'importe quel canal de site.

## <a name="when-to-use-cross-channel-sharing"></a>Quand utiliser le partage intercanal

Le partage intercanal est utile lorsque plusieurs canaux d'un même site peuvent partager du contenu. Par exemple, un détaillant qui possède plusieurs marques et vitrines regroupées dans un même site peut partager du contenu entre certaines ou toutes les vitrines. Ce contenu partagé peut inclure des pages pour les conditions générales, les conditions de paiement, les modes d'expédition et les questions fréquentes (FAQ).

Le partage intercanal prend également en charge les fragments. Par conséquent, une page de contenu contenant des fragments spécifiques au canal peut être créée en tant que contenu intercanal. Dans ce cas, bien que la plupart du contenu soit partagé entre les canaux, les fragments spécifiques au canal sur une page intercanal ne seront rendus que lorsqu'ils sont demandés à partir du canal de vitrine correspondant.

Les sites qui n'ont qu'un seul canal, ou les sites qui ont plusieurs canaux qui ne peuvent pas partager de contenu, ne profiteront pas du partage intercanal.

## <a name="enable-cross-channel-sharing"></a>Activer le partage intercanal

Le partage intercanal est activé au niveau du site. Cette opération est unidirectionnelle. Cela signifie qu'une fois que le partage intercanal est activé, il ne peut pas être désactivé.

Pour activer le partage intercanal dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Paramètres du site \> Fonctionnalités**.
1. Définissez l'option pour la fonctionnalité **Intercanal** sur **Activé**.

    ![Option Intercanal définie sur Activé dans le générateur de site Commerce](./media/enabling-cross-channel-sharing.png)

Une fois que vous avez activé le partage intercanal, les informations intercanal s'affichent dans la section **Canaux** sous **Paramètres du site \> Fonctionnalités** , comme illustré ci-dessous.

![Informations sur les canaux visibles après l'activation du partage intercanal](./media/channels-cross-channel.png)

De plus, après avoir activé le partage intercanal, le champ **Canal** dans le coin supérieur droit du générateur de site Commerce inclura une option **Magasin en ligne intercanal** que vous pouvez utiliser pour gérer le contenu intercanal, comme illustré ci-dessous.

![Option de magasin en ligne intercanal dans le champ Canaux une fois le partage intercanal activé](./media/cross-channel-dropdown.png)

## <a name="create-and-use-cross-channel-content"></a>Créer et utiliser du contenu intercanal

Vous pouvez créer et utiliser du contenu intercanal de plusieurs manières. Par exemple, vous pouvez créer des fragments intercanal, créer des pages intercanal qui utilisent du contenu intercanal et du contenu spécifique au canal, et remplacer des fragments intercanal par des versions de fragments spécifiques au canal.

### <a name="create-a-cross-channel-fragment"></a>Créer un fragment intercanal

Pour créer un fragment intercanal dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Fragments** , puis cliquez sur **Nouveau** pour créer un fragment.
1. Dans la boîte de dialogue **Nouveau fragment** , sélectionnez le module **Bannière promotionnelle** , puis, sous **Nom du fragment** , entrez un nom (par exemple, **Bannière intercanal** ). Puis sélectionnez **OK**.
1. Dans le volet de propriétés du module **Bannière promotionnelle** , sélectionnez **Ajouter un message** , puis sélectionnez **Message**.
1. Dans la boîte de dialogue **Message** , sous **Texte** , entrez **Intercanal** et sélectionnez **OK**. 
1. Sélectionnez **Enregistrer** , **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

Ce fragment intercanal peut être utilisé sur des pages intercanal ou spécifiques à un canal qui sont créées sur n'importe quel canal de site.

### <a name="create-a-cross-channel-page-that-uses-cross-channel-content"></a>Créer une page intercanal qui utilise du contenu intercanal

Les pages intercanal peuvent être utilisées sur n'importe quel canal de votre site. Par conséquent, vous pouvez créer une fois une page de contenu partagé et effectuer toutes les mises à jour ultérieures en un seul endroit. Par exemple, une page intercanal **Conditions générales** dont l'URL est `/toc` peut être partagée entre tous les canaux d'un site. Si les URL de base des canaux du site sont `www.fabrikam.com/brand1` et `www.fabrikam.com/brand2`, la même page **Conditions générales** intercanal et partagée sera disponible à partir des deux URL des canaux du site, à l'adresse `www.fabrikam.com/brand1/toc` et `www.fabrikam.com/brand2/toc`, respectivement. Si la page **Conditions générales** doit être mise à jour ultérieurement, vous devez mettre à jour uniquement la page partagée.

Pour créer une page intercanal qui utilise du contenu intercanal dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Pages** , puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Choisir un modèle** , sélectionnez un modèle, par exemple **Marketing**.
1. Dans **Nom de la page** , entrez un nom pour la page (par exemple, **Page intercanal** ).
1. Sous **URL de la page** , entrez une URL de page (par exemple, **examplepage** ), puis sélectionnez **OK**.
1. À l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension ( **...** ), puis le sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Ajouter un fragment** , sélectionnez le fragment intercanal que vous avez créé précédemment et qui contient une bannière promotionnelle, puis sélectionnez **OK**.
1. Cliquez sur **Enregistrer** , puis sur **Aperçu** pour afficher un aperçu de la page. La bannière promotionnelle indiquant "Intercanal" doit s'afficher.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

### <a name="create-a-channel-specific-page-that-uses-cross-channel-content"></a>Créer une page spécifique à un canal qui utilise du contenu intercanal

En utilisant du contenu intercanal sur des pages spécifiques à un canal, vous pouvez créer une fois un fragment de contenu partagé, puis l'utiliser sur des pages spécifiques au canal. Cette "source unique" est utile pour le contenu partagé tel que les conditions générales, les conditions de paiement ou les coordonnées.

Pour créer une page spécifique à un canal qui utilise du contenu intercanal dans le générateur de site Commerce, procédez comme suit.

1. Depuis un canal spécifique, tel que **Magasin en ligne étendu Fabrikam** , accédez à **Pages** , puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Choisir un modèle** , sélectionnez un modèle, par exemple **Marketing**.
1. Dans **Nom de la page** , entrez un nom pour la page (par exemple, **Page spécifique au canal** ).
1. Sous **URL de la page** , entrez une URL de page (par exemple, **channelspecificpage** ), puis sélectionnez **OK**.
1. À l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension ( **...** ), puis le sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Ajouter un fragment** , sous **Canal** , sélectionnez **Magasin en ligne intercanal**. Le fragment intercanal que vous avez créé précédemment doit apparaître dans la liste. Sélectionnez-le, puis sélectionnez **OK**.
1. Cliquez sur **Enregistrer** , puis sur **Aperçu** pour afficher un aperçu de la page. La bannière promotionnelle indiquant "Intercanal" doit s'afficher.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

### <a name="create-a-channel-specific-version-of-a-cross-channel-page"></a>Créer une version spécifique à un canal d'une page intercanal

Le partage intercanal prend en charge le remplacement du contenu intercanal. Par exemple, tous les canaux de votre site, sauf un, partagent le même contenu. Ce canal de site nécessite un contenu différent. Pour implémenter les différents contenus pour ce canal, vous remplacez le contenu intercanal par un contenu spécifique au canal en créant une version spécifique au canal de la page intercanal.

Pour créer une version spécifique à un canal d'une page intercanal dans le générateur de site Commerce, procédez comme suit.

1. Dans le champ **Canal** situé dans le coin supérieur droit, sélectionnez **Magasin en ligne intercanal**.
1. Ouvrez la page intercanal que vous avez créée précédemment.
1. Dans le champ **Canal** situé dans le coin supérieur droit, sélectionnez le canal qui doit avoir un contenu spécifique. L'éditeur de page affiche un message qui vous invite à créer une variante de la page.
1. Sélectionnez **Créer une variante de la page**.
1. Dans l’emplacement **Principal** de la variante de la page, sélectionnez le bouton représentant des points de suspension ( **...** ), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module** , sélectionnez le module **Bannière promotionnelle** , puis sélectionnez **OK**.
1. Dans le volet de propriétés du module **Bannière promotionnelle** , sélectionnez **Ajouter un message** , puis sélectionnez **Message**.
1. Dans la boîte de dialogue **Message** , sous **Texte** , entrez **Spécifique au canal** et sélectionnez **OK**.
1. Cliquez sur **Enregistrer** , puis sur **Aperçu** pour afficher un aperçu de la page. La bannière promotionnelle indiquant "Spécifique au canal" doit s'afficher.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

Désormais, si vous utilisez l'URL de base du canal et accédez à l'URL de la page intercanal sur ce site, vous verrez le contenu spécifique au canal au lieu du contenu intercanal.

## <a name="additional-resources"></a>Ressources supplémentaires

[Manières d’ajouter du contenu](add-manage-content.md)

[Glossaire sur le modèle de page](page-elements-overview.md)

[États et cycle de vie des documents](document-states-overview.md)

[Utilisation de groupes de publication](publish-groups.md)
