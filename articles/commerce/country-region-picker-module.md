---
title: Module de sélection de pays/région
description: Cet article décrit le module de sélection de pays/région et explique comment le configurer dans Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: d20b3be008a37b1c86e6fefe0ccc90c581e18340
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861990"
---
# <a name="countryregion-picker-module"></a>Module de sélection de pays/région

[!include [banner](includes/banner.md)]

Cet article décrit le module de sélection de pays/région et explique comment le configurer dans Microsoft Dynamics 365 Commerce.

Le module de sélection de pays/région utilise la fonction de [géodétection et redirection](geo-detection-redirection.md) de Dynamics 365 Commerce pour afficher les sites recommandés aux clients qui demandent une URL de site de commerce électronique qui n'est pas associée à leur pays ou à leur région.

Par exemple, un client au Canada demande une URL de site qui est associée à un pays autre que le Canada. Dans ce cas, le module de sélection de pays/région affiche une boîte de dialogue qui recommande les URL de site associées au Canada. 

## <a name="how-it-works"></a>Comment ça fonctionne

Lorsque la détection géographique et la redirection sont activées pour un site et qu'un client demande une URL de site, le pays détecté pour le client et l'URL qu'il a demandée sont utilisés pour déterminer si cette URL correspond au pays où se trouve le client. Le mappage entre les URL et les pays est défini sur la page **Canaux** sous **Paramètres du site** dans le générateur de sites de Commerce. 

Si l'URL de la requête ne correspond à aucune URL mappée au pays du client, la liste d'une ou plusieurs URL mappées à ce pays est renvoyée dans la réponse. Le sélecteur de pays / région compare chaque URL de cette liste aux URL qui ont été configurées dans le module pays / région. Pour chaque correspondance exacte trouvée, le sélecteur de pays / région affiche le titre d'affichage, le sous-titre et l'image pour cette URL, et crée des hyperliens vers ces éléments à l'aide de l'URL.

Lorsqu'un client sélectionne une option dans le sélecteur de pays/région, il est redirigé vers l'URL du lien hypertexte. Cette URL est écrite dans le cookie **\_msdyn365\_\_\_site\_** afin d'être utilisé comme préférence du client pour le site. Ensuite, la prochaine fois que le client demandera l'URL qui n'est pas associée à son pays ou sa région, il sera automatiquement redirigé vers son pays préféré. Par conséquent, nous vous recommandons d'utiliser également le [module de sélection de site](site-selector.md) sur votre site de commerce électronique, afin que les clients aient un moyen de remplacer ou de mettre à jour leur préférence de site. 

Si un client ferme la boîte de dialogue du sélecteur de pays/région, aucun cookie n'est écrit et le client reste sur le site actuel. 

L’illustration suivante présente un exemple de la boîte de dialogue Sélecteur de pays/région.

![Exemple de boîte de dialogue de sélection de pays/région sur une page d'accueil.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Propriétés du module de sélection de pays/région

| Nom de la propriété              | Valeur       | Description                                                  |
| -------------------------- | ----------- | ------------------------------------------------------------ |
| Titre                    | Détails        | L'en-tête qui apparaît en haut de la boîte de dialogue.       |
| Sous-titre                 | Détails        | Le sous-en-tête qui apparaît sous l'en-tête.               |
| Pays : chaîne d'affichage    | Détails        | Nom d'affichage d'une option d'URL (par exemple, « Canada »).   |
| Pays : sous-chaîne d'affichage | Détails        | Une sous-chaîne d'affichage facultative pour une option d'URL (par exemple, « Anglais » ou « Français »). |
| Pays : Image du pays     | Actif média | Une image facultative associée à une option d'URL (par exemple, une image du drapeau canadien). |
| Pays : URL du pays       | Texte        | L'URL du site pour le pays/la région en cours de configuration. Cette URL doit correspondre exactement à l'URL que vous avez spécifiée pour ce pays/région sur la page **Canaux** sous **Paramètres du site** dans le générateur de sites de Commerce. De plus, le domaine de l'URL doit être le domaine personnalisé spécifié dans le champ **Faire correspondre le domaine** de la page **Canaux**, et non l'adresse de travail du site que Commerce fournit lorsque vous créez votre environnement de commerce électronique (par exemple, l'URL `https://<yourcompany>.commerce.dynamics.com/`). |
| Lien action                | Lien action | Un lien facultatif qui apparaît au bas de la boîte de dialogue. Par exemple, ce lien peut pointer vers une page interne qui fournit une liste de tous les pays et régions pris en charge par le site. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Ajouter un module de sélection de pays/région à une page

Le module de sélection de pays/région peut être ajouté au module d'en-tête soit directement, soit via un fragment partagé. Pour plus d’informations sur les modules d’en-tête, voir [Module En-tête](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Configurer le module de sélection de pays/région dans le générateur de site Commerce

> [!NOTE]
> Les URL que vous recommandez à vos clients doivent être configurées en tant qu'objets de pays dans le module de sélection de pays/région.

Pour chaque URL de site que vous souhaitez afficher et recommander aux clients, suivez ces étapes dans le générateur de site de Commerce.

1. Sélectionnez l'emplacement du module de sélection de pays/région.
1. Dans le volet des propriétés, sous **Liste des pays**, sélectionnez **Ajouter un pays**.
1. Sélectionnez la nouvelle zone **Pays**.
1. Dans le champ **Chaîne d'affichage**, saisissez un nom d'affichage (par exemple, **Canada**).
1. Facultatif : dans le champ **Sous-chaîne d'affichage**, saisissez une sous-chaîne d'affichage (par exemple, **Français**, ou **fr-ca**).
1. Facultatif : sélectionnez une image dans la bibliothèque multimédia.
1. Dans le champ **URL du pays**, saisissez l'URL. Cette URL doit correspondre exactement à l'URL qui apparaît sur la page **Canaux** et qui est mappée sur le canal, y compris les paramètres régionaux associés au pays ou à la région. 
1. Cliquez sur **OK**.
1. Répétez ces étapes pour toutes les autres URL de pays que vous souhaitez que le module de sélection de pays/région affiche.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer la géodétection et la redirection](geo-detection-redirection.md)

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module d’en-tête](author-header-module.md)

[Module de sélection de site](site-selector.md)

[Module de barre de navigation](add-breadcrumb.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
