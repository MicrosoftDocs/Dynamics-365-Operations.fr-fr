---
title: Configurer un canal pour une utiliser une hiérarchie de navigation du canal
description: Cette rubrique décrit comment configurer un canal pour utiliser une hiérarchie de navigation de canal dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3dcba743e6557b1bd366ac79ecb49ead831dceb4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001023"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a>Configurer un canal pour une utiliser une hiérarchie de navigation du canal


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment configurer un canal pour utiliser une hiérarchie de navigation de canal dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Les hiérarchies de navigation de canal organisent les produits en catégories afin de pouvoir les parcourir dans un site de commerce électronique ou dans des points de vente (PDV). Les canaux de vente au détail et en ligne doivent être configurés avec des hiérarchies de navigation des canaux.

## <a name="configure-the-channel"></a>Configurer le canal

Pour configurer un canal afin d'utiliser une hiérarchie de navigation de canal, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.
1. Sélectionnez le canal à configurer.
1. Sur le volet Actions, sélectionnez **Paramétrer les métadonnées d'attribut**.
1. Dans la liste déroulante **Hiérarchie de catégories**, sélectionnez la hiérarchie de navigation de canal adéquate.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Sous **Groupe d'attributs**, ajoutez tous les groupes d'attributs qui seront des attributs globaux pour tous les nœuds.

L'image suivante montre comment configurer un canal afin d'utiliser une hiérarchie de navigation de canal.

![Exemple de configuration de canal](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a>Paramétrer les métadonnées d'attribut

La définition des métadonnées d'attribut permettra la configuration des attributs sur chaque nœud.

Procédez comme suit pour configurer les métadonnées d'attributs.

1. Sur le volet Actions, sélectionnez **Paramétrer les métadonnées d'attribut**.
1. Pour chaque nœud, sélectionnez **Attributs de produit de canal**.
1. Définissez **Afficher l'attribut sur le canal** sur **Oui** et **Peut être affiné** sur **Oui**, pour activer des affinements sur ce canal.
1. Après avoir configuré chaque nœud comme vous le souhaitez, dans le **Volet Actions**, sélectionnez le bouton **Enregistrer**.
1. Sélectionnez la **X** dans le coin supérieur droit pour quitter cet écran et revenir à la page **Catégories de canal et attributs de produit**.

L'image suivante montre un exemple d'ensemble d'attributs de produit de canal configuré sur un nœud de catégorie de canal.

![Attributs de canal sur un nœud de catégorie de canal](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a>Publier des modifications

Pour que les modifications prennent effet, vous devrez publier les modifications.

Pour publier des modifications, procédez comme suit.

1. Dans le volet Actions, sélectionnez **Publier les mises à jour du canal**.
1. Dans le volet **Publier les mises à jour du canal**, sélectionnez **OK**.

L'image suivante montre comment publier les mises à jour du canal.

![Publier les mises à jour du canal](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer une hiérarchie de navigation du canal](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]