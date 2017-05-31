---
title: "Paramétrer des options de traitement des commandes"
description: "Cette rubrique fournit des informations sur le traitement des commandes pour les centres d&quot;appels à l&quot;aide de Microsoft Dynamics 365 for Operations - Vente au détail.."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 52b56274c8b72c67bc0a50f23114cebc510f1667
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-order-processing-options"></a>Paramétrer des options de traitement des commandes

[!include[banner](includes/banner.md)]


Cette rubrique fournit des informations sur le traitement des commandes pour les centres d'appels à l'aide de Microsoft Dynamics 365 for Operations - Vente au détail.. 

Le module Commerce et vente au détail de Dynamics 365 for Operations prend en charge plusieurs canaux de vente au détail, tels que les magasins en ligne, les magasins traditionnels et les centres d'appels. Dans les centre d'appels, les collaborateurs prennent les commandes des clients par téléphone et créent des commandes client. Cette rubrique décrit la procédure de création d'un centre d'appels et de configuration de ses options. Chaque centre d'appels peut avoir ses propres utilisateurs, modes de paiement, groupes de prix, dimensions financières, et modes de livraison. Vous pouvez configurer ces options lorsque vous créez les centres d'appels. **Important :** avant que les workflows de centre d'appels puissent être utilisés lorsque l'utilisateur actuel de Dynamics AX crée des commandes client, l'utilisateur doit être affecté au centre d'appels en tant qu'utilisateur du centre d'appels. Vous pouvez utiliser la page **Centre d'appels** pour activer ou désactiver les groupes de fonctions qui sont uniques aux centres d'appels. Les groupes de fonctions suivants peuvent être activés :

-   **Achèvement de commande** – Ce groupe inclut les fonctionnalités liées aux paiements et à l'achèvement des commandes sur la page **Commande client**.
-   **Vente directe** – Ce groupe inclut les fonctionnalités associées aux codes sources, aux scripts, et aux demandes de catalogue.

Lorsque vous activez ces fonctions dans les paramètres du centre d'appels, elles sont disponibles sur la page **Commande client** pour les utilisateurs associés au centre d'appels. La plupart de ces fonctions requièrent un paramétrage supplémentaire avant d'être utilisées. Des images et des scripts sont activés dans le cadre du paramètre de vente directe pour le centre d'appels spécifique. Si ces fonctionnalités sont activées, les scripts et les images de produit sont affichés dans le volet Récapitulatif de la page **Commande client**. L'image par défaut définie pour un produit est indiquée. Les scripts peuvent être configurés pour un article, un catalogue, un client ou un article dans le contexte d'un catalogue. Les commandes de centre d'appels peuvent afficher des informations supplémentaires sur la manière dont le prix pour une ligne de commande spécifique a été dérivé. Par exemple, les commandes indiquent quelles remises ont été appliquées. Vous activez cette fonctionnalité dans **Comptabilité client** &gt; **Paramétrage** &gt; **Paramètres de la comptabilité client** &gt; **Prix** &gt; **Détails des prix**. Vous pouvez accéder à la page **Détails des prix** à partir de la liste déroulante **Ligne de commande client**. Vous pouvez utiliser le suivi des événements de commande à des fins d'audit, pour réviser les actions effectuées sur une commande pendant son cycle de vie, ou pour suivre les actions d'un utilisateur spécifique. Par exemple, vous pouvez enregistrer l'action chaque fois qu'un utilisateur crée une commande client, bloque une commande, remplace des frais, ou met à jour une ligne de commande. Vous pouvez paramétrer des événements de commande pour suivre les actions d'utilisateurs spécifiques, de groupes d'utilisateurs, ou de tous les utilisateurs au cours d'une période spécifique. Vous pouvez afficher les actions effectuées sur un document en ouvrant la page **Événements de commande** à partir du volet Actions dans la page de ce document. Vous pouvez configurer des événements de commande dans **Ventes et marketing** &gt; **Paramétrage** &gt; **Événements** &gt; **Événements de commande**. Lorsque la commande d'un client ne peut pas être expédiée à temps, une société peut automatiquement envoyer des notifications par e-mail pour expliquer le statut de la commande et offrir au client la possibilité d'annuler la commande. Si le retard est supérieur au seuil spécifié, la commande peut être annulée automatiquement. Jusqu'à trois e-mails peuvent être envoyés à des intervalles spécifiés :

1.  **Première notification d'annulation** – Le client peut choisir d'annuler la commande.
2.  **Deuxième notification d'annulation** – Le client peut choisir d'annuler la commande.
3.  **Notification d'annulation finale** – Le système annule la commande, et le client est informé de l'annulation.

Vous pouvez exonérer les clients et produits individuels du processus de notification et d'annulation automatiques. Une alerte de marge est déclenchée lorsque vous ajoutez un article à une commande. L'alerte contient des informations importantes sur l'article, comme la marge de prix et la rentabilité de l'article. Vous pouvez utiliser ces informations pour décider si un remplacement de prix est approprié lorsque vous ajoutez un article à la commande client. Par exemple, vous pouvez paramétrer des seuils pour les marges commerciales, afin de spécifier qu'un seuil supérieur de 40 % ou plus par rapport au coût est acceptable pour un article, et qu'un seuil supérieur de 20 à 39 % par rapport au coût est discutable. Dans ce cas, tout article avec un seuil entre 20 et 39 % déclenche un avertissement. Aucun article dont le seuil est supérieur de moins de 20 % par rapport au coût ne peut pas être vendu, et le prix de l'article ne peut pas être ajusté. Vous pouvez configurer des alertes de marge dans **Comptabilité client** &gt; **Paramétrage** &gt; **Paramètres de la comptabilité client** &gt; **Alertes de marge**. Lorsque vous paramétrez l'affectation de taxe sur la base des règles par défaut, vous pouvez déterminer une priorité de correspondance pour les éléments d'adresse. Par exemple, vous pouvez spécifier que mettre en correspondance un groupe de taxe par code postal a une priorité plus élevée que mettre en correspondance un groupe de taxe par état. Lorsque vous entrez de nouveaux enregistrements d'adresse du client, le groupe de taxe est automatiquement affecté selon la mesure dans laquelle l'adresse du client correspond aux règles par défaut et à la priorité que vous avez définies. Vous pouvez configurer cette fonction dans la page **Paramètres de comptabilité**.




