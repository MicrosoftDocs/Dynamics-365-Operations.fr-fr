---
title: "L&quot;espace de travail portable de stock disponibles pour Microsoft Dynamics 365 pour l&quot;application Opérations"
description: "Les applications mobiles de l&quot;espace de travail de stock disponible vous gagnez des analyses déplacement dans le stock réservé et disponible à tout moment et n&quot;importe où."
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

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>L'espace de travail portable de stock disponibles pour Microsoft Dynamics 365 pour l'application Opérations

Les applications mobiles de l'espace de travail de stock disponible vous gagnez des analyses déplacement dans le stock réservé et disponible à tout moment et n'importe où. 

<a name="prerequisites"></a>Conditions préalables
-------------

| Logiciel requis                                                         | description ;                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Disposer connaissances Microsoft Dynamics 365 pour la plateforme mobiles d'opérations | [Dynamics 365 pour plateforme mobile opérations] (/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 pour les opérations                                          | Un environnement avec Microsoft Dynamics 365 pour la version 1611 d'opérations et Microsoft Dynamics pour la mise à jour 3 de plateforme Opérations (novembre 2016) |
| Base de connaissances 3215650 de correctif                                                    | Installez le correctif pour activer des espaces de travail autorisés dans votre Microsoft Dynamics 365 pour les opérations.                                       |
| Appareil mobile qui a Dynamics 365 pour l'application Opérations installée | Téléchargez Dynamics 365 pour l'application Opérations de votre magasin portable d'application.                                                                           |

## <a name="introduction"></a>Introduction
Généralement, les sociétés ont plusieurs expéditions et les réceptions plusieurs du stock chaque jour. Ces mouvements modifient constamment le statut du stock disponible. L'espace de travail portable du stock disponible vous permet de consulter le statut de stock disponible de société croisée, vous permettant d'obtenir les dernières analyses dans les données de stock sous l'périphérique mobile de votre choix. Que si vous travaillez dans l'entrepôt, les achats, les ventes, la fabrication, ou de gestion, ou avoir d'autres rôles, vous pouvez accéder aux données de stock disponible à tout moment et n'importe où. L'espace de travail portable fournit une vue instantanée du statut disponible sur plusieurs établissements, et vous permet d'afficher le stock disponible dans les outils, les réservations actuelles matières, et le stock disponible franc. Vous pouvez également entrer les numéros d'article pour rechercher le stock disponible, puis effectuer une recherche filtrée des produits disponibles ou des variantes. Spécifiquement, l'espace de travail portable fournit ces fonctions :

-   Vous pouvez rechercher le numéro ou le nom du produit de sous-produit pour trouver des produits pour afficher le statut de stock disponible.
-   Pour les produits sélectionnés, vous pouvez afficher les informations suivantes :
    -   Stock disponible par site
    -   Stock disponible par entrepôt
    -   Stock disponible par emplacement
    -   Stock disponible par lots (pour les produits contrôlés par lots)
    -   Stock disponible par statut du stock

<!-- -->

-   Le stock disponible de produit est affiché comme suit :
    -   Par le stock physique (cette vue représente le montant total.)
    -   Par Physique réservé (cette vue représente le montant réservé.)
    -   Par Physique disponible (cette vue représente le montant disponible qui n'a pas de réservation.)

## <a name="get-started"></a>Mise en route
Pour obtenir commencé sur votre périphérique mobile :

1.  Dans votre magasin portable d'application, chargez et installez Microsoft Dynamics 365 pour l'application Opérations.
2.  Démarrez l'application de votre périphérique.
3.  Permet d'entrer l'URL de Dynamics 365.
4.  Entrez la société pour signer dans en. Par exemple, entrez ** USMF **.
5.  La première fois que vous vous connectez, vous êtes invité à entrer le nom d'utilisateur et le mot de passe pour votre Microsoft Dynamics 365 pour le compte d'opérations. Entrez vos informations d'identification. Après avoir signer électroniquement dans, vous voyez des espaces de travail disponibles pour votre société.

Pour afficher des espaces de travail de votre application mobile, vous devez d'abord envoyer des espaces de travail souhaités à Dynamics 365 pour l'application Opérations.

1.  Début Dynamics 365 pour les opérations.
2.  Allez ** Administration du système ** &gt; ** au paramétrage ** &gt; ** des paramètres système **.
3.  Sélectionnez ** de gérer l'application mobile **.
4.  Sélectionnez l'espace de travail pour publier à la plateforme portable.
5.  Sélectionnez ** publiez l'espace de travail **.
6.  Permet d'actualiser le périphérique pour voir des espaces de travail émis.

## <a name="view-the-onhand-inventory-for-a-product"></a>Affichez le stock de disponible pour un produit
1.  Dans votre périphérique mobile, sélectionnez ** stock disponible ** l'espace de travail.
2.  Sélectionnez ** vérifiez disponible pour un article **. Vous découvrez une liste des produits chargés dans votre application pour l'utilisation hors ligne. Par défaut, 50 articles sont validés, mais vous pouvez modifier ce numéro. Pour plus d'informations, voir le Manuel préalables à la fois.
3.  Si votre article ne figure pas dans la liste, sélectionnez ** recherchez plus ** pour effectuer une recherche en ligne dans Dynamics 365 pour les opérations. Recherchez le nombre de produits, ou le basculez vers un nom de sous-produit de recherche.
4.  Sélectionnez un produit. Si l'article est une image, l'image s'affiche.
5.  Sélectionnez l'une des options suivantes pour afficher le statut du stock disponible :
    -   Affichez disponible par site
    -   Affichez disponible par entrepôt
    -   Affichez disponible par emplacement
    -   Affichez disponible par lots (pour les produits contrôlés par lots)
    -   Affichez disponible par statut du stock

    Le stock disponible de produit est affiché comme suit :
    -   Par le stock physique (cette vue représente le montant total.)
    -   Par Physique réservé (cette vue représente le montant réservé.)
    -   Par Physique disponible (cette vue représente le montant disponible qui n'a pas de réservation.)




