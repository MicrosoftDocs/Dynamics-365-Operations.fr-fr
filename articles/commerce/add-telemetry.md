---
title: Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie
description: Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a5f82426d87cd2e0faa0195a841899bb03f9df08
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697334"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.

## <a name="overview"></a>Vue d'ensemble

Les analyses web sont un outil essentiel lorsque vous souhaitez inclure la manière dont vos clients peuvent interagir avec votre site et prendre des décisions qui aideront à optimiser l'expérience pour la conversion maximale. De nombreux packages d'analyses web sont disponibles pour vous aider à atteindre ces objectifs, comme Google Analytics, Clicky, Moz Analytics, et KISSMetrics. La plupart des packages d'analyses web nécessitent que vous ajoutiez un code du script côté client dans l'élément **\<en-tête\>** du fichier HTML pour toutes les pages du site.

> [!NOTE]
> Les instructions de cette rubrique s'appliquent également à l'autre fonctionnalité côté client personnalisée que Microsoft Dynamics 365 Commerce n'offre pas en mode natif.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Créer un fragment réutilisable pour votre code de script

Après avoir créé un fragment pour votre code du script, il peut être réutilisé dans l'ensemble des pages sur votre site.

1. Accédez à **Fragments \> Nouveau fragment de page**.
2. Sélectionnez **Script externe**, entrez un nom pour le fragment, puis sélectionnez **OK**.
3. Dans la hiérarchie du fragment, sélectionnez l'enfant du module **injecteur de script** du fragment que vous venez de créer.
4. Dans le volet de propriétés de droite, ajoutez le script côté client, et définissez d'autres options de configuration comme vous le souhaitez.

## <a name="add-the-fragment-to-templates"></a>Ajouter le fragment aux modèles

1. Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.
2. Dans le volet gauche, développez la hiérarchie de modèle pour afficher l'emplacement **En-tête HTML**.
3. Sélectionnez le bouton représentant des points de suspension (**...**) en regard de l'emplacement **Pied de page HTML**, et sélectionnez **Ajouter un fragment**.
4. Sélectionnez le fragment créé pour votre code de script.
5. Enregistrez le modèle, et archivez-le.

> [!NOTE]
> Après avoir terminé, vous devez publier fragment et le modèle principal. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter un logo](add-logo.md)

[Sélectionner un thème pour le site](select-site-theme.md)

[Ajouter une icône de favori](add-favicon.md)

[Ajouter un message de bienvenue](add-welcome-message.md)

[Ajouter un avis de droits d'auteur](add-copyright-notice.md)

[Ajouter des langues à votre site](add-languages-to-site.md)

