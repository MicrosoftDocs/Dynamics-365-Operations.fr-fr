---
title: Glossaire du modèle de page
description: Cette rubrique décrit les différents éléments utilisés dans les pages d’un site Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c5ec6dfd9147fd5e054303b4fd612caef78b7467d7f6f4850e46fcc9fb1346f2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758310"
---
# <a name="page-model-glossary"></a>Glossaire sur le modèle de page


[!include [banner](includes/banner.md)]

Cette rubrique décrit les différents éléments utilisés dans les pages d’un site Microsoft Dynamics 365 Commerce.

## <a name="page-element-definitions"></a>Définitions d’éléments de page

Le tableau suivant fournit un récapitulatif des termes avec lesquelles vous devez être familier lorsque vous modifiez l’aspect et le contenu du site. Pour des explications et des procédures plus complètes, suivez les liens.

| Terme | Description et remarques |
|------|-----------------------|
| [Module](work-with-modules.md) | <p>**Définition :** les modules sont le bloc élémentaire qui peut être créé et constitue le squelette d’une page web. Ils comprennent les modules d’en-tête, de bannière et de carrousel.</p><p>**Où il est sélectionné :** les modules déployés peuvent être sélectionnés et configurés à différentes phases du workflow de création du site, telles que les phases de création de modèle, de disposition, de page, et de fragment.</p><p>**Où il est modifié :** les modules personnalisés sont créés en code à l’aide du kit de développement logiciel (SDK). Ils sont alors chargés sur votre site, dans lequel ils deviennent disponibles pour sélection.</p> |
| Propriété du module | <p>**Définition :** les propriétés du module sont des paramètres spécifiques qui sont définis par le module. Elles peuvent être modifiées dans les outils de création de commerce électronique. Par exemple, les propriétés du module sont utilisées pour définir l’en-tête et l’image d’arrière-plan d’un module de bannière.</p><p>**Où il a configuré :** les propriétés de module sont sélectionnées et configurées dans le volet de propriété qui apparaît dans les environnements de création (éditeurs) pour les paramètres des modèles, des dispositions, des pages, des fragments, et d’application.</p> |
| [Modèle](templates-layouts-overview.md) | <p>**Définition :** les modèles définissent les combinaisons et les options de module qui doivent être utilisées pour une catégorie de pages (par exemple, les pages de marketing, les pages de catégorie, ainsi que mes pages de produit).</p><p>**Où il est sélectionné :** les modèles peuvent être sélectionnés lors des workflows de création de page ou de disposition.</p><p>**Où il est modifié :** les modèles sont créés dans l’éditeur de modèle. Aucun code n’est requis pour créer ou modifier.</p> |
| [Disposition](templates-layouts-overview.md) | <p>**Définition :** les dispositions définissent la sélection et l’organisation finales des modules à partir du jeu d’options du modèle parent. Une disposition peut être configurée pour une seule page (*disposition personnalisée*), ou elle peut être partagée par plusieurs pages (*disposition prédéfinie*).</p><p>**Où elle est sélectionné :** les dispositions peuvent être sélectionnées lors de la création de la page ou lorsqu’une disposition différente pour une page existante.</p><p>**Où il est modifié :** les dispositions sont créés dans l’éditeur de disposition. Aucun code n’est requis pour créer ou modifier.</p> |
| [Instance de la page](modify-existing-page.md) | <p>**Définition :** les instances de page définissent le contenu localisé final et spécifique à une seule page. Ce contenu est dérivé des valeurs des propriétés du module.</p><p>**Où il est sélectionné :** les pages sont sélectionnées lorsque des URL sont affectés.</p><p>**Où il est modifié :** les pages sont modifiées dans l’éditeur de page. Aucun code n’est requis pour créer ou modifier.</p> |
| [Thème](select-site-theme.md) | <p>**Définition :** les thèmes définissent la feuille de style en cascade (CSS), et déterminent l’aspect des modules qui s’affichent sur une page.</p><p>**Où elle est sélectionné :** après qu’un thème est chargé dans votre site à l’aide Microsoft Dynamics Lifecycle Services (LCS), il peut être sélectionné comme propriétés du module de conteneur de page.</p><p>**Où il est modifié :** les thèmes sont actuellement créés et modifiés à l’aide du kit de développement logiciel (SDK). Ils sont alors chargés sur votre site à l’aide de LCS.</p> |
| [Fragment](work-with-fragments.md) | <p>**Définition :** les fragments sont des modules entièrement configurés qui ont localisé du contenu qui peut être réutilisé et mis à jour centralement sur plusieurs pages. Par exemple, un fragment créé à partir d’un module d’en-tête peut être utilisé dans tous les modèles et sur toutes les pages dans votre site, et être mis à jour centralement à un endroit.</p><p>**Où il est sélectionné :** les fragments peuvent être sélectionnés partout où les modules peuvent être sélectionnés. Ils peuvent être remplacés pour un module pour augmenter l’efficacité via une création réutilisable et centralisée.</p><p>**Où il est modifié :** les fragments sont modifiés dans l’éditeur de fragment. Aucun code n’est requis pour créer ou modifier.</p> |
| [URL](create-page-URL.md) | <p>**Définition :** les adresses URL sont des adresses qui indiquent des pages web ou d’autres URL.</p><p>**Où il est sélectionné :** les URL sont sélectionnées si des liens entre les pages sont requis.</p><p>**Où il est modifié :** les URL sont modifiées dans l’éditeur d’URL. Aucun code n’est requis pour créer ou modifier.</p> |
| Actif | <p>**Définition :** les actifs sont des binaires de fichier qui ont une extension comme .jpg, .docx, .pdf, ou .mpg.</p><p>**Où il est sélectionné :** les actifs sont sélectionnés comme propriétés du module pour les modules qui les nécessitent.</p><p>**Où il est modifié :** les actifs sont chargés, et les métadonnées associées sont modifiées dans le gestionnaire d’actifs.</p> |

## <a name="additional-resources"></a>Ressources supplémentaires

[Manières d’ajouter du contenu](add-manage-content.md)

[États et cycle de vie des documents](document-states-overview.md)

[Utilisation de groupes de publication](publish-groups.md)

[Activer et utiliser le partage intercanal](cross-channel-sharing.md)

[Utiliser des modules](work-with-modules.md)

[Utiliser des fragments](work-with-fragments.md)

[Vue d’ensemble des modèles et dispositions](templates-layouts-overview.md)

[Personnaliser la navigation dans le site](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]