---
title: Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie
description: Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.
author: bicyclingfool
manager: annbe
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: dfebc6616186a3a8859b00e90c178129feaa324b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980155"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.

## <a name="overview"></a>Vue d’ensemble

Les analyses web sont un outil essentiel lorsque vous souhaitez inclure la manière dont vos clients peuvent interagir avec votre site et prendre des décisions qui aideront à optimiser l’expérience pour la conversion maximale. De nombreux packages d’analyses web sont disponibles pour vous aider à atteindre ces objectifs, comme Google Analytics, Clicky, Moz Analytics, et KISSMetrics. La plupart des packages d’analyses web nécessitent que vous ajoutiez un code du script côté client dans l’élément **\<head\>** du fichier HTML pour toutes les pages du site.

> [!NOTE]
> Les instructions de cette rubrique s’appliquent également à l’autre fonctionnalité côté client personnalisée que Microsoft Dynamics 365 Commerce n’offre pas en mode natif.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Créer un fragment réutilisable pour votre code de script

Un fragment vous permet de réutiliser un code de script externe ou en ligne sur toutes les pages de votre site, peu importe le modèle qu’elles utilisent.

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a>Créer un fragment réutilisable pour votre code de script en ligne

Pour créer un fragment réutilisable pour votre code de script en ligne dans le générateur de site, procédez comme suit.

1. Accédez à **Fragments**, puis sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez **Script en ligne**.
1. Sous **Nom du fragment**, entrez un nom pour le fragment, puis sélectionnez **OK**.
1. Sous le fragment que vous avez créé, sélectionnez le module **Script en ligne par défaut**.
1. Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client. Puis configurez d’autres options selon vos besoins.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Sélectionnez **Publier**.

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a>Créer un fragment réutilisable pour votre code de script externe

Pour créer un fragment réutilisable pour votre code de script externe dans le générateur de site, procédez comme suit :

1. Accédez à **Fragments**, puis sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez **Script externe**.
1. Sous **Nom du fragment**, entrez un nom pour le fragment, puis sélectionnez **OK**.
1. Sous le fragment que vous avez créé, sélectionnez le module **Script externe par défaut**.
1. Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe. Puis configurez d’autres options selon vos besoins.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Sélectionnez **Publier**.

> [!NOTE]
> Si la stratégie de stratégie de sécurité (CSP) est activée pour votre site, assurez-vous que toutes les URL externes sont ajoutées à l'instruction CSP **script-src** dans le générateur de site Commerce. Pour plus d’informations, voir [Gérer la stratégie de sécurité du contenu (CSP)](manage-csp.md).

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a>Ajouter un fragment qui inclut le code de script à un modèle

Pour ajouter un fragment qui comprend un code de script à un modèle dans le générateur de site, procédez comme suit :

1. Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.
1. Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.
1. Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un fragment**.
1. Sélectionnez le fragment créé pour votre code de script.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Sélectionnez **Publier**.

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a>Ajouter un script externe ou en ligne directement à un modèle

Si vous souhaitez insérer un script en ligne ou externe directement dans un ensemble de pages contrôlées par un seul modèle, vous n’avez pas à créer de fragment tout d’abord.

### <a name="add-an-inline-script-directly-to-a-template"></a>Ajouter un script en ligne directement à un modèle

Pour ajouter un script en ligne directement à un modèle dans le générateur de site, procédez comme suit.

1. Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.
1. Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.
1. Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script en ligne**.
1. Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client. Puis configurez d’autres options selon vos besoins.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Sélectionnez **Publier**.

### <a name="add-an-external-script-directly-to-a-template"></a>Ajouter un script externe directement à un modèle

Pour ajouter un script externe à un modèle dans le générateur de site, procédez comme suit.

1. Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.
1. Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.
1. Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script externe**.
1. Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe. Puis configurez d’autres options selon vos besoins.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Sélectionnez **Publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter un logo](add-logo.md)

[Sélectionner un thème pour le site](select-site-theme.md)

[Utilisation de fichiers de remplacement CSS](css-override-files.md)

[Ajouter une icône de favori](add-favicon.md)

[Ajouter un message de bienvenue](add-welcome-message.md)

[Ajouter un avis de droits d’auteur](add-copyright-notice.md)

[Ajouter des langues à votre site](add-languages-to-site.md)
