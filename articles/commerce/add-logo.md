---
title: Ajouter un logo
description: Cette rubrique décrit comment ajouter un logo à votre site dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f15680deb0eab763ba68f2897139c915d1f8a6a3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412216"
---
# <a name="add-a-logo"></a>Ajouter un logo

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment ajouter un logo à votre site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Lorsque vous créez votre site, l'une des premières choses que vous ferez probablement est d'ajouter le logo de votre entreprise ou de votre marque à l'en-tête du site. La bibliothèque de modules en ligne Dynamics 365 Commerce fournit un module qui facilite cette tâche.

Vous pouvez ajouter un logo directement à un modèle, une disposition ou une page. De cette façon, vous pouvez facilement changer le logo qui apparaît sur des pages ou des groupes de pages spécifiques. Cependant, cette rubrique couvre le scénario le plus fréquent, où vous ajoutez votre logo à un fragment d'en-tête qui peut être réutilisé sur toutes les pages de votre site.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir ajouter un logo à toutes les pages de votre site, vous devez effectuer ces tâches.

1. Téléchargez votre logo dans la bibliothèque multimédia.
1. Créez un fragment d'en-tête. Pour plus d'informations sur la création et l'utilisation de fragments, consultez [Utilisation des fragments](work-with-fragments.md).
1. Incluez le fragment d'en-tête dans le modèle que les pages de votre site utilisent pour leurs options de disposition et de module. Pour plus d'informations sur les modèles, voir [Utilisation des modèles](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Ajouter un logo à un fragment d'en-tête

Pour ajouter un logo au fragment d'en-tête de votre site, procédez comme suit.

1. Dans le volet de navigation sur la gauche, sélectionnez **Fragments**.
1. Sélectionnez le fragment d'en-tête créé précédemment, puis sélectionnez **Modifier**.
1. Développez le module d'en-tête.
1. Dans le volet des propriétés du module d'en-tête, fournissez une image et un lien pour le logo. 
1. Enregistrez le fragment d'en-tête, terminez de le modifier et publiez-le.

Après avoir publié le fragment d'en-tête mis à jour, toutes les pages de site qui utilisent le modèle qui contient le fragment d'en-tête afficheront votre logo.

## <a name="additional-resources"></a>Ressources supplémentaires

[Sélectionner un thème pour le site](select-site-theme.md)

[Utilisation de fichiers de remplacement CSS](css-override-files.md)

[Ajouter une icône de favori](add-favicon.md)

[Ajouter un message de bienvenue](add-welcome-message.md)

[Ajouter un avis de droits d’auteur](add-copyright-notice.md)

[Ajouter des langues à votre site](add-languages-to-site.md)

[Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]