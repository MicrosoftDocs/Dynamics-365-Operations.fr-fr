---
title: "Paramétrage de l'exécution des commandes en magasin"
description: "Cette rubrique fournit une vue d'ensemble de la procédure de paramétrage de l'exécution des commandes en magasin."
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: ccff6533257379c0305f7414dd36e17d1c323c21
ms.contentlocale: fr-fr
ms.lasthandoff: 03/07/2018

---


# <a name="set-up-order-fulfillment-for-stores"></a>Paramétrer l'exécution des commandes pour les magasins

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Vue d'ensemble
De nombreuses détaillants souhaitent optimiser l'exécution des commandes en autorisant les magasins à exécuter les commandes. L'exécution des commandes au niveau du magasin permet de faciliter les scénarios de surstock pour un magasin spécifique, ou peut être nécessaire d'un point de vue logistique dans les cas où un magasin a des capacités supplémentaires ou est situé à une distance d'expédition proche du client. Pour répondre à ce besoin, une opération d'exécution de commandes unifiée est disponible dans le point de vente.

Pour les commandes à exécuter dans un magasin spécifique, l'entrepôt du magasin est indiqué sur l'en-tête ou les lignes de la commande. 

L'opération d'exécution des commandes dans le point de vente fournit une zone de travail unique dans le point de vente qui peut être utilisée pour traiter les commandes. Cela va de l'acceptation de la commande à son marquage comme expédiée en passant par l'activation du prélèvement en magasin. 

## <a name="set-up-the-order-fulfillment-operation"></a>Paramétrer l'opération d'exécution des commandes

L'opération d'exécution des commandes, [ID opération 928](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-operations) peut être utilisée pour accéder à la zone de travail d'exécution des commandes dans le point de vente. 

Suivez les étapes décrites dans la section [Ajouter l'opération à une grille de boutons](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) pour spécifier le paramètre à utiliser lors de l'appel des opérations d'exécution des commandes dans le point de vente. Par défaut, après avoir spécifié les opérations d'exécution des commandes, le paramètre **Toutes les commandes** est sélectionné. Lorsqu'elle est configurée avec ce paramètre, l'opération répertorie toutes les lignes de commande qui doivent être exécutées dans le magasin actuel. Le paramètre **Commandes à expédier** est également disponible. Il peut être affecté à un bouton et utilisé lorsque l'utilisateur souhaite uniquement afficher les commandes à expédier en dehors du magasin. Enfin, il existe le paramètre **Commandes pour prélèvement**. Lorsqu'il est appelé dans le point de vente, ce paramètre répertorie uniquement les commandes à prélever dans le magasin. Les différents paramètres peuvent être affectés à différents boutons pour fournir à l'utilisateur plusieurs options d'affichage des opérations d'exécution des commandes. 

### <a name="enable-users-to-access-order-fulfillment-at-the-point-of-sale"></a>Autoriser les utilisateurs à accéder aux opérations d'exécution des commandes dans le point de vente 

L'opération d'exécution des commandes ne dispose pas de sa propre autorisation prédéfinie, mais à l'avenir, les utilisateurs devront disposer de l'autorisation **Autoriser la récupération de commandes** pour appeler l'opération à partir du point de vente.

Au niveau du point de vente, un paramètre de configuration est disponible pour déterminer si une ligne de commande doit être acceptée manuellement à partir du point de vente. Si cette option de configuration n'est pas définie, les lignes de commande sont acceptées par défaut. Si cette option de configuration est activée, les utilisateurs du point de vente devront disposer de l'autorisation **Autorisation l'acceptation de commandes** pour accepter les commandes à partir du point de vente. 


### <a name="enable-manual-order-acceptance"></a>Activer l'acceptation manuelle des commandes

Par défaut, les lignes de commande affectées à un magasin sont marquées comme **Acceptées**. Cela signifie qu'elles sont censées être exécutées à partir du magasin affecté et ne sont pas soumises à d'autres affectations. Dans certains cas, les détaillants souhaitent accepter manuellement les commandes avant qu'elles puissent être exécutées. Par exemple, si un magasin manque de personnel et n'est pas en mesure d'exécuter les commandes, un directeur de magasin accepte uniquement le nombre de commandes à traiter qui, selon lui, peuvent être traitées correctement dans une journée donnée. Tant qu'une commande n'est pas acceptée, elle peut être réaffectée par l'arrière-guichet à un autre magasin. Ainsi, l'acceptation de commandes permet également d'indiquer qu'une commande a été reçue par un magasin et sera exécutée. 

Les lignes de commande pour prélèvement en magasin sont marquées comme **En attente** et ne sont pas soumises à acceptation.

Pour activer l'acceptation manuelle des lignes de commande, accédez à **Vente au détail** > **Canaux** > **Magasins de vente au détail** > **Tous les magasins de vente au détail**. Sélectionnez le magasin et cliquez sur l'ID magasin pour afficher les détails du magasin. Cliquez sur **Modifier**. Dans l'organisateur **Général**, localisez le sous en-tête **Exécution des commandes** et modifiez l'option **Acceptation manuelle** de **Non** en **Oui**. 

### <a name="enable-reject-order-line-capability"></a>Activer la fonction de rejet de ligne de commande

Les lignes de commande peuvent également être rejetées à partir du point de vente. Le rejet d'une ligne de commande signifie qu'elle n'est pas exécutée dans ce magasin et qu'elle est renvoyée pour réaffectation à un autre magasin ou entrepôt. L'autorisation de rejet d'une ligne de commande est accordée via l'autorisation **Autoriser le rejet de commandes** dans le groupe d'autorisations POS associé au collaborateur. Lors du rejet d'une ligne, les détaillants peuvent demander à leurs collaborateurs de fournir un motif de rejet. Pour ce faire, utilisez les codes info de type **Activité de code info** **Exécution des commandes** et affectez-les à l'action **Rejeter la ligne de commande** dans le profil de fonctionnalité associé au canal. 

>[!Note]
>Seuls les codes info de type **Activité de code info** **Exécution des commandes** peuvent être affectés à l'action **Rejeter la ligne de commande**.

### <a name="synchronize-changes-to-the-channel-database"></a>Synchroniser les modifications à la base de données des canaux

Une fois que l'opération a été affectée à une grille de boutons, les autorisations appropriées ont été affectées et le canal est configuré, les modifications doivent être synchronisées avec la base de données du canal. Pour ce faire, accédez à **Vente au détail** > **Informatique au détail** > **Programme de distribution**. Sélectionnez le programme « 1090-Caisses enregistreuses » pour synchroniser les modifications de la grille de boutons, puis cliquez sur **Exécuter maintenant**. Ensuite, synchronisez les modifications des autorisations en sélectionnant « 1060-Personnel » et en cliquant sur **Exécuter maintenant**. Ensuite, synchronisez les modifications des canaux en sélectionnant « 1070-Configuration des canaux » et en cliquant sur **Exécuter maintenant**. Enfin, synchronisez le nouveau code info créé pour le motif de rejet en sélectionnant « 1110-Configuration globale » et en cliquant sur **Exécuter maintenant**.

## <a name="use-order-fulfillment-at-the-point-of-sale"></a>Utiliser l'opération d'exécution des commandes dans le point de vente

Ouvrez le point de vente et sélectionnez l'opération d'exécution des commandes. Selon la façon dont elle est configurée, toutes les lignes, les lignes de commande pour prélèvement ou les lignes de commande à expédier sont répertoriées. 

### <a name="order-fulfillment-view"></a>Vue d'exécution des commandes 

La vue d'exécution des commandes répertorie les lignes de commande à exécuter dans le magasin et comporte les colonnes suivantes :

  - Numéro de commande
  - Numéro de produit
  - Description 
  - Quantité commandée
  - Date de livraison demandée
  - Nom du client
  - Statut de l'exécution
  
Des informations supplémentaires pour une ligne de commande spécifique peuvent être affichées en sélectionnant la ligne de commande et en ouvrant le menu volant situé en dessous des informations sur l'utilisateur/l'équipe de travail affichées dans l'en-tête du point de vente. Ce menu comporte 2 onglets : un pour les détails de la ligne et un autre pour les détails de la commande. L'onglet des détails de la ligne inclut les informations suivantes :

  - Quantité commandée
  - Quantité restante à expédier/prélever
  - Quantité prélevée
  - Quantité emballée
  - Quantité facturée (déjà prélevée ou expédiée)
  - Mode de livraison
  - Adresse de livraison
  
Le menu volant comporte également un onglet qui fournit d'autres détails au niveau de la commande, notamment :

  - Nom du client
  - ID de client
  - Numéro de commande
  - Total de la commande
  - Solde de la commande
  
En bas de la vue d'exécution des commandes se trouve un volet Actions. Il contient toutes les actions pouvant être effectuées sur une ligne de commande. Si une action n'est pas disponible sur la base du statut d'une ligne, cette action n'est pas disponible. 

Par défaut, les commandes ont le statut **Accepté**. Le statut des commandes peut être affiché sous forme de colonne dans la liste des lignes de commande. Si l'option **Acceptation manuelle** est configurée au niveau du canal, toutes les lignes à expédier ont le statut **En attente** et doivent être acceptées avant de pouvoir être exécutées. Les commandes pour prélèvement en magasin sont **En attente** par défaut et ne doivent pas être acceptées.

### <a name="order-fulfillment-line-actions"></a>Actions sur la ligne d'exécution des commandes

**Modifier** - Si le statut d'une commande est en attente, il peut être modifié dans le point de vente. Les commandes qui ont déjà été partiellement prélevées, emballées ou facturées ne peuvent pas être modifiées à partir de la vue d'exécution des commandes.

**Accepter** - Si l'option **Acceptation manuelle** est configurée au niveau du canal, les lignes doivent d'abord être acceptées pour pouvoir suivre le processus d'exécution des commandes.

**Prélever** - Cette option prend en charge plusieurs actions. Tout d'abord, l'option **Prélèvement** met à jour le statut de la ligne de commande afin que les autres personnes du magasin ne tentent pas de prélever la même ligne. Ensuite, l'option **Imprimer la liste des prélèvements** imprime la liste des prélèvements pour le(s) ligne(s) sélectionnée(s) et met à jour également leur statut sur **Prélèvement**. Les formats de liste de prélèvements sont contrôlés dans le cadre des formats de réception. Pour plus d'informations sur le paramétrage des formats de réception, voir [Modèles de réception et impression](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing). Enfin, l'option **Marquer comme prélevé** indique que la ligne a été prélevée. L'option **Marquer comme prélevé** active les transactions de stock correspondantes dans l'arrière-guichet. Les actions de prélèvement peuvent être exécutées simultanément pour plusieurs lignes de commande et pour tous les modes de livraison.

**Rejeter** - Les lignes ou les lignes partielles peuvent être rejetées. Elles peuvent ainsi être réaffectées de l'arrière-guichet vers un autre magasin ou entrepôt. Les lignes ne peuvent être rejetées que si elles n'ont pas encore été prélevées ou emballées. Pour rejeter une ligne qui a déjà été prélevée ou emballée, le prélèvement ou l'emballage de cette ligne doit être annulé. 

**Emballer** - Cette option prend en charge deux actions : **Imprimer le bon de livraison** imprime un bon de livraison pour les lignes sélectionnées et **Marquer comme emballé** marque les lignes comme emballées et livrées dans l'arrière-guichet. Seules les lignes de commande appartenant à la même commande et présentant le même mode de livraison peuvent être emballées en même temps. Les formats de bon de livraison sont contrôlés dans le cadre des formats de réception. Pour plus d'informations sur le paramétrage des formats de réception, voir [Modèles de réception et impression](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing).

**Expédier** - Cette action marque les lignes sélectionnées comme **Livrées** dans l'arrière-guichet. Une fois qu'une ligne a été entièrement expédiée, elle n'apparaît plus dans la vue d'exécution des commandes.

**Prélever** - Cette action ajoute les lignes à la vue des transactions pour le prélèvement. Si d'autres lignes de la commande ne sont pas en cours de prélèvement, elles sont ajoutées à la vue des transactions avec zéro comme quantité. Une fois qu'une ligne a été entièrement prélevée, elle n'apparaît plus dans la vue d'exécution des commandes. 

### <a name="order-fulfillment-filtering"></a>Filtrage de l'exécution des commandes

L'exécution des commandes dans le point de vente inclut le filtrage pour aider l'utilisateur à trouver facilement ce dont il a besoin. Les filtres peuvent être modifiés dans le volet Actions en bas de l'écran **Point de vente**. Par défaut, un filtre **Type de livraison** est appliqué, selon le paramétrage de l'opération. Si l'opération est configurée avec le paramètre **Toutes les commandes**, ce filtre est appliqué lors de l'accès à l'opération d'exécution des commandes. Ceci est également valable pour les paramètres **Prélèvement en magasin** et **Expédier à partir du magasin**. Les autres filtres qui peuvent être appliqués à la vue d'exécution des commandes sont les suivants :

  - Numéro de client
  - Nom du client
  - E-mail du client
  - Numéro de commande
  - Mode de livraison
  - Numéro d'accusé de réception
  - ID référence de canal
  - Numéro de magasin d'origine
  - Statut de ligne
  - Date de création
  - Date de livraison
  - Date de réception

