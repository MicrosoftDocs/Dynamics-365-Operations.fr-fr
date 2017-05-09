---
title: "Espace de travail mobile Stock disponible pour l&quot;application Microsoft Dynamics 365 for Operations"
description: "Les applications mobiles de l&quot;espace de travail Stock disponible vous permet d&quot;acquérir des connaissances mobiles sur les stocks réservés et disponibles à tout moment et n&quot;importe où."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espace de travail mobile Stock disponible pour l'application Microsoft Dynamics 365 for Operations

Les applications mobiles de l'espace de travail Stock disponible vous permet d'acquérir des connaissances mobiles sur les stocks réservés et disponibles à tout moment et n'importe où. 

<a name="prerequisites"></a>Conditions préalables
-------------

| Logiciel requis                                                         | description ;                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| En savoir plus sur la plateforme mobile Microsoft Dynamics 365 for Operations | [Plateforme mobile Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 for Operations                                          | Un environnement disposant de la version 1611 de Microsoft Dynamics 365 for Operations et de la mise à jour 3 de Microsoft Dynamics for Operations (novembre 2016). |
| Correctif de la Base de connaissances 3215650                                                    | Installez le correctif pour activer les espaces de travail fournis dans votre Microsoft Dynamics 365 for Operations.                                       |
| Appareil mobile sur lequel l'application Dynamics 365 for Operations est installée | Téléchargez l'application Dynamics 365 for Operations à partir de votre magasin d'application mobile.                                                                           |

## <a name="introduction"></a>Introduction
Généralement, les sociétés ont plusieurs expéditions et plusieurs réceptions de stock chaque jour. Ces mouvements modifient constamment le statut du stock disponible. L'espace de travail Stock disponible vous permet de voir l'état du stock en ligne afin d'obtenir les dernières informations sur les données de stock sur votre appareil mobile. Que vous travailliez dans l'entrepôt, les achats, les ventes, la fabrication ou la gestion, ou que vous ayez d'autres rôles, vous pouvez accéder aux données de stock en temps réel à tout moment et n'importe où. L'espace de travail mobile fournit une vue instantanée de l'état de la main-d'œuvre dans toutes les installations et vous permet de voir le stock disponible dans les installations, les réservations matérielles actuelles et le stock non réservé. Vous pouvez également entrer les numéros d'article pour rechercher le stock disponible, puis effectuer une recherche filtrée des produits ou des variantes disponibles. Spécifiquement, l'espace de travail mobile fournit ces fonctions :

-   Vous pouvez rechercher le numéro ou le nom du produit pour trouver des produits et afficher le statut du stock disponible.
-   Vous pouvez afficher les informations suivantes pour les produits sélectionnés :
    -   Stock disponible par site
    -   Stock disponible par entrepôt
    -   Stock disponible par emplacement
    -   Stock disponible par lots (pour les produits contrôlés par lots)
    -   Stock disponible par statut de stock

<!-- -->

-   Le stock de produits disponible est affiché comme suit :
    -   Par stock physique (cette vue représente la quantité totale.)
    -   Par quantité physique réservée (cette vue représente la quantité réservée.)
    -   Par quantité physique disponible (cette vue représente la quantité disponible qui n'est pas réservée.)

## <a name="get-started"></a>Mise en route
Pour démarrer sur votre périphérique mobile :

1.  Dans votre magasin d'application mobile, téléchargez et installez l'application Microsoft Dynamics 365 for Operations.
2.  Démarrez l'application sur votre appareil.
3.  Entrez votre URL Dynamics 365.
4.  Entrez la société à laquelle vous vous connectez. Par exemple, entrez **USMF**.
5.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer le nom d'utilisateur et le mot de passe de votre compte Microsoft Dynamics 365 for Operations. Entrez vos informations d'identification. Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent.

Pour afficher les espaces de travail sur votre application mobile, vous devez d'abord publier les espaces de travail souhaités sur l'application Dynamics 365 for Operations.

1.  Démarrez Dynamics 365 for Operations.
2.  Accédez à **Administration système** &gt; **Paramétrage** &gt; **Paramètres système**.
3.  Sélectionnez **Gérer l'application mobile**.
4.  Sélectionnez l'espace de travail pour le publier sur la plateforme mobile.
5.  Sélectionnez **Publier l'espace de travail**.
6.  Actualisez votre appareil pour afficher les espaces de travail publiés.

## <a name="view-the-onhand-inventory-for-a-product"></a>Afficher le stock disponible pour un produit
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Stock disponible**.
2.  Sélectionnez **Vérifier la disponibilité d'un article**. Vous découvrez une liste des produits chargés dans votre application pour l'utilisation hors ligne. Par défaut, 50 articles sont validés, mais vous pouvez modifier ce nombre. Pour plus d'informations, voir le manuel pré-lu.
3.  Si votre article ne figure pas dans la liste, sélectionnez **Rechercher plus** pour effectuer une recherche en ligne dans Dynamics 365 for Operations. Recherchez le nombre de produits ou basculez vers une recherche par nom de produit.
4.  Sélectionnez un produit. Si l'article est une image, l'image s'affiche.
5.  Sélectionnez l'une des options suivantes pour afficher le statut du stock disponible :
    -   Afficher la disponibilité par site
    -   Afficher la disponibilité par entrepôt
    -   Afficher la disponibilité par emplacement
    -   Afficher la disponibilité par lots (pour les produits contrôlés par lots)
    -   Afficher la disponibilité par statut du stock

    Le stock de produits disponible est affiché comme suit :
    -   Par stock physique (cette vue représente la quantité totale.)
    -   Par quantité physique réservée (cette vue représente la quantité réservée.)
    -   Par quantité physique disponible (cette vue représente la quantité disponible qui n'est pas réservée.)




