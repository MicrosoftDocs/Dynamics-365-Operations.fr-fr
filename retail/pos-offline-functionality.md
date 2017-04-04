---
title: "Fonctionnalité de PDV hors connexion"
description: "Cet article fournit des informations sur le mode hors connexion pour le PDV moderne Retail, dans lequel les périphériques de PDV basculent automatiquement de la base de données de canal à la base de données hors connexion si le serveur au détail n&quot;est pas disponible. Cet article inclut également des informations de paramétrage général pour le mode hors connexion et explique que la synchronisation des données se produit entre la base de données hors connexion et la base de données de canal."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27041
ms.assetid: 20b51874-8912-40cf-9296-864df707315a
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ef4d20b3302e4a420c7013b77a57ebdfa99fe6a3
ms.lasthandoff: 03/31/2017


---

# <a name="pos-offline-functionality"></a>Fonctionnalité de PDV hors connexion

Cet article fournit des informations sur le mode hors connexion pour le PDV moderne Retail, dans lequel les périphériques de PDV basculent automatiquement de la base de données de canal à la base de données hors connexion si le serveur au détail n'est pas disponible. Cet article inclut également des informations de paramétrage général pour le mode hors connexion et explique que la synchronisation des données se produit entre la base de données hors connexion et la base de données de canal.

<a name="overview"></a>Vue d'ensemble
--------

Dans le Retail Modern POS, un périphérique de (POS) de point de vente conclu le mode hors connexion à chaque fois que le serveur de vente au détail est pas disponible. Par conséquent, si la connexion avec le serveur de vente au détail est perdue, le Retail Modern POS passe automatiquement à la base de données hors ligne. Lors d'une transaction de vente, si une demande de données n'aboutit pas dans l'intervalle d'expiration configuré dans le profil hors ligne, Retail Modern POS bascule automatiquement sur la base de données hors connexion et continue la transaction de vente. Tandis que le périphérique de PDV est en mode hors ligne, Retail Modern POS tente de se reconnecter au serveur de vente au détail après l'intervalle de tentative de reconnexion configuré dans le profil hors connexion. Cette tentative de reconnexion se produit uniquement au début d'une transaction.

### <a name="determining-the-connection-mode-of-retail-modern-pos"></a>Détermination du mode de connexion de Retail Modern POS

L'en-tête de statut dans Retail Modern POS indique l'état actuel de la connexion, et la fenêtre **Statut de la connexion** indique le statut de la dernière tentative de synchronisation avec la base de données hors ligne. [![Connection status](./media/status.png)](./media/status.png)

### <a name="creating-a-button-to-manually-switch-between-online-and-offline-modes"></a>Création d'un bouton pour basculer manuellement entre les modes en ligne et hors connexion

Vous pouvez ajouter un bouton à Retail Modern POS pour basculer manuellement entre les modes en ligne et hors ligne. Créer un bouton pour l'opération de PDV **917 – Statut de la connexion à la base de données**. Le nom de ce bouton est **Déconnecter** quand Retail Modern POS est connecté au serveur de vente au détail et **Connecter** lorsqu'il est déconnecté. Vous pouvez utiliser ce bouton pour afficher la connexion, ainsi que pour réaliser la connexion ou la déconnexion au serveur de vente au détail. [bouton de débranchement d'![dans le Retail Modern POS] (. /media/details-1024x537.png)](. /media/details.png)

## <a name="setup"></a>Configuration
Pour activer le support technique hors connexion d'un périphérique du PDV (Registre), définissez ** support hors connexion ** l'option ** Oui ** sur ** registre ** la page. Une entité de base de données des canaux est créée et ajoutée au groupe de données du canal du magasin. Exécutez ensuite tous les programmes de répartition requis pour générer les paquets de données pour la base de données hors ligne. Ensuite, installez la version hors connexion du Retail Modern POS. Le processus d'installation crée la base de données hors ligne. En outre, installez Microsoft SQL Server 2014 Express si nécessaire. La synchronisation hors ligne des données démarre après la première connexion à Retail Modern POS.

## <a name="data-synchronization"></a>Synchronisation des données
Le programmateur Retail est utilisé pour envoyer les données principales à la base de données hors ligne. Par défaut, quand un programme de distribution est exécuté, des modifications des données sont envoyées à la base de données du canal et à la base de données hors ligne. Retail Modern POS inclut la bibliothèque de synchronisation Async, qui télécharge tous les paquets de données disponibles et les insère dans la base de données hors ligne. Si des transactions sont créées hors connexion, Retail Modern POS les télécharge vers le serveur de vente au détail, afin qu'elles puissent être insérées dans la base de données du canal. La synchronisation des données hors connexion peut se produire uniquement si Retail Modern POS est en cours d'exécution. [![Offline synchronization](./media/offline-sync-1024x521.png)](./media/offline-sync.png)


