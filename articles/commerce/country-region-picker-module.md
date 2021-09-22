---
title: Module de sélection de pays/région
description: Cette rubrique décrit le module de sélection de pays/région et explique comment le configurer dans Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 3134e10c096525ec2d82365a25eff16a3c5d5e11
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472609"
---
# <a name="countryregion-picker-module"></a>Module de sélection de pays/région

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit le module de sélection de pays/région et explique comment le configurer dans Microsoft Dynamics 365 Commerce.

Le module de sélection de pays/région utilise la fonction de [géodétection et redirection](geo-detection-redirection.md) de Dynamics 365 Commerce pour afficher les URL recommandées aux clients qui demandent une URL de site de commerce électronique qui n'est pas associée à leur pays ou à leur région.

Par exemple, un client au Canada demande une URL de site qui n'est pas associée au Canada. Dans ce cas, le module de sélection de pays/région affiche une boîte de dialogue qui recommande les URL de site associées au Canada. L’illustration suivante présente un exemple de la boîte de dialogue Sélecteur de pays/région.

![Exemple de boîte de dialogue de sélection de pays/région sur une page d'accueil.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Propriétés du module de sélection de pays/région

| Nom de la propriété              | Valeur       | Description |
| -------------------------- | ----------- | ----------- |
| Titre                    | Détails        | L'en-tête qui apparaît en haut de la boîte de dialogue. |
| Sous-titre                 | Détails        | Le sous-en-tête qui apparaît sous l'en-tête. |
| Pays : chaîne d'affichage    | Détails        | Nom d'affichage d'une option d'URL (par exemple, « Canada »). |
| Pays : sous-chaîne d'affichage | Détails        | Une sous-chaîne d'affichage facultative pour une option d'URL (par exemple, « Anglais » ou « Français »). |
| Pays : Image du pays     | Actif média | Une image facultative associée à une option d'URL (par exemple, une image du drapeau canadien). |
| Pays : URL du pays       | Détails        | L'URL qui correspond au canal et aux paramètres régionaux configurés pour le pays ou la région sur la page **Canaux** du générateur de site de Commerce (**Paramètres du site \> Canaux**). Cette URL doit correspondre exactement à l'URL configurée sur la page **Canaux**. |
| Lien action                | Lien action | Un lien facultatif qui apparaît au bas de la boîte de dialogue. Par exemple, ce lien peut pointer vers une page interne qui fournit une liste de tous les pays et régions pris en charge par le site. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Ajouter un module de sélection de pays/région à une page

Le module de sélection de pays/région peut être ajouté au module d'en-tête soit directement, soit via un fragment partagé. Pour plus d’informations sur les modules d’en-tête, voir [Module En-tête](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Configurer le module de sélection de pays/région dans le générateur de site Commerce

> [!NOTE]
> Les URL que vous recommandez à vos clients doivent être configurées en tant qu'objets de pays dans le module de sélection de pays/région.

Pour chaque URL que vous souhaitez afficher et recommander aux clients, suivez ces étapes dans le générateur de site de Commerce.

1. Sélectionnez l'emplacement du module de sélection de pays/région.
1. Dans le volet des propriétés, sous **Liste des pays**, sélectionnez **Ajouter un pays**.
1. Sélectionnez la nouvelle zone **Pays**.
1. Dans le champ **Chaîne d'affichage**, saisissez un nom d'affichage (par exemple, **Canada**).
1. Facultatif : dans le champ **Sous-chaîne d'affichage**, saisissez une sous-chaîne d'affichage (par exemple, **Français**, ou **fr-ca**).
1. Facultatif : sélectionnez une image dans la bibliothèque multimédia.
1. Dans le champ **URL du pays**, saisissez l'URL. Cette URL doit correspondre exactement à l'URL qui apparaît sur la page **Canaux** et est mappée sur le canal, y compris les paramètres régionaux associés au pays ou à la région.
1. Cliquez sur **OK**.
1. Répétez ces étapes pour toutes les autres URL de pays que vous souhaitez que le module de sélection de pays/région affiche.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer la géodétection et la redirection](geo-detection-redirection.md)

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module d’en-tête](author-header-module.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
