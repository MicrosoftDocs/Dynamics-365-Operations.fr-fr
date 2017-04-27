---
title: "Espace de travail mobile Commandes client pour l&quot;application Microsoft Dynamics 365 for Operations"
description: "Avec l&quot;espace de travail mobile des commandes client, vous pouvez être informé de vos commandes client n&quot;importe où et à tout moment."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: dbc6dc39-b535-42d3-9fbd-4724597388ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 851c53e1c53fb37488ed86e25e3ede83ca0541db
ms.lasthandoff: 03/31/2017


---

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espace de travail mobile Commandes client pour l'application Microsoft Dynamics 365 for Operations

Avec l'espace de travail mobile des commandes client, vous pouvez être informé de vos commandes client n'importe où et à tout moment. 

<a name="prerequisites"></a>Conditions préalables
-------------

| Logiciel requis                                                         | description ;                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| En savoir plus sur la plateforme mobile Microsoft Dynamics 365 for Operations | [Plateforme mobile Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Assurez-vous d'utiliser un environnement disposant de la version 1611 de Microsoft Dynamics 365 for Operations et de la mise à jour 3 de Microsoft Dynamics for Operations (novembre 2016). |
| Correctif de la Base de connaissances 3215650                                                    | Installez le correctif pour activer les espaces de travail fournis dans Microsoft Dynamics 365 for Operations.                                                                       |
| Appareil mobile sur lequel l'application Dynamics 365 for Operations est installée | Téléchargez l'application Dynamics 365 for Operations à partir de votre magasin d'application mobile.                                                                                                      |

## <a name="overview"></a>Vue d'ensemble
Cet espace de travail mobile accède à l'application Dynamics 365 for Operations et vous permet d'afficher des informations détaillées sur chaque commande client, comme le statut de la commande, les coordonnées du client et les coordonnées de la personne qui a pris la commande. L'espace de travail mobile fournit une vue instantanée des commandes client. Vous pouvez afficher les commandes client par client, afficher toutes les commandes client, ou afficher des informations sur une commande client spécifique. L'espace de travail mobile fournit deux vues pour vous aider à analyser les commandes client en profondeur.

### <a name="view-all-sales-orders"></a>Afficher toutes les commandes client

Cette vue répertorie toutes les commandes client.

-   Utilisez l'un des filtres suivants pour sélectionner les commandes client que vous souhaitez afficher.
    -   Recherche par commande client
    -   Rechercher par compte client
    -   Recherche par nom de client
    -   Rechercher par statut
    -   Rechercher par statut de lancement
    -   Recherche par date et heure de création

<!-- -->

-   Après avoir sélectionné les commandes client, vous pouvez afficher les détails de commandes spécifiques. En particulier, vous pouvez afficher :
    -   le nom du client et les informations d'adresse
    -   les différentes dates de la commande client, telles que la date d'expédition demandée et la date d'expédition confirmée
    -   les coordonnées de la personne qui a pris la commande
    -   les coordonnées du client
    -   Lignes de commande
    -   Expéditions qui affichent quand et comment une commande client a été expédiée

### <a name="view-orders-for-a-customer-"></a>Afficher les commandes pour un client ** **

Cette vue répertorie les commandes client par client.

-   Utilisez l'un des filtres suivants pour afficher les commandes pour un client.
    -   Rechercher par nom
    -   Rechercher par compte

<!-- -->

-   Après avoir sélectionné un client, vous pouvez afficher :
    -   le nom et le groupe du client
    -   les coordonnées du client
    -   les commandes du client et les détails qui les concernent :
        -   le nom du client et les informations d'adresse
        -   les différentes dates de commande client
        -   les coordonnées de la personne qui a pris la commande
        -   les coordonnées du client
        -   Lignes de commande
        -   Expéditions qui affichent quand et comment une commande client a été expédiée

## <a name="get-started"></a>Mise en route
Suivez les étapes ci-après pour commencer à utiliser l'espace de travail mobile des commandes client sur votre appareil mobile.

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

## <a name="view-information-about-sales-orders-for-a-customer"></a>Afficher des informations sur les commandes client pour un client
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Commandes client**.
2.  Sélectionnez **Afficher les commandes pour un client**.
3.  Utilisez les informations **Compte** ou **Nom du client** pour trouver le client souhaité.
4.  Sélectionnez le client
5.  Sélectionnez **Informations de contact** ou **Commandes client**.
6.  Si **Commandes client** est sélectionné, une liste des commandes client du client s'affiche.
7.  Sélectionnez **Commandes client**.
8.  Vous pouvez ici afficher des informations sur les lignes de commande client, les expéditions, les informations de contact du client et les informations de contact de la personne qui a pris la commande.




