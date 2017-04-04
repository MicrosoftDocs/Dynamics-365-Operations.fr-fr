---
title: "Définir les communications de canal de vente au détail (Commerce Data Exchange)"
description: "Cet article fournit une vue d&quot;ensemble Commerce Data Exchange et de ses composants. Elle décrit le rôle que chaque composant joue dans le transfert des données entre Microsoft Dynamics 365 pour les opérations et des canaux de vente au détail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 29938d962db42a521dd8dc03b8e45e0e34410e4d
ms.openlocfilehash: d3b36ec2a3f859215d93dd7ebf1f1ecfb2731c59
ms.lasthandoff: 03/31/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Définir les communications de canal de vente au détail (Commerce Data Exchange)

Cet article fournit une vue d'ensemble Commerce Data Exchange et de ses composants. Elle décrit le rôle que chaque composant joue dans le transfert des données entre Microsoft Dynamics 365 pour les opérations et des canaux de vente au détail.

<a name="overview"></a>Vue d'ensemble
--------

Commerce échange de données est un système qui transfère des données entre Dynamics 365 pour les opérations et des canaux de vente au détail, tels que des magasins en ligne et les magasins de brique-et- physiques. La base de données contenant des données pour un canal de vente au détail n'utilisent pas de Dynamics 365 pour la base de données d'opérations. La base de données de canal contient uniquement les données requises pour les transactions de vente au détail. Les données principales sont configurées dans Dynamics 365 pour les opérations et réparties les canaux. Les données transactionnelles sont créées dans le système de (POS) de point de vente ou le magasin en ligne, puis téléchargées à Dynamics 365 pour les opérations. La distribution de données est asynchrone. Autrement dit, le processus de rassemblement et de groupement des données à la source se produit de manière distincte du processus de réception et d'application des données à la destination. Pour certains scénarios, comme les recherches de prix et de stock, les données doivent être extraites en temps réel. Pour prendre en charge ces scénarios, le commerce échange de données inclut également un service qui active la communication en temps réel entre Dynamics 365 pour les opérations et un canal. 

[mettre à jour au détail graphique![] (. /media/updated-retail-graphic.png)](. /media/updated-retail-graphic.png)  

## <a name="async-service"></a>Service Async
La modification de Microsoft SQL Server suivant dans Dynamics 365 pour la base de données d'opérations est utilisée pour déterminer les modifications de données qui doivent être envoyées aux canaux. Selon un programme de distribution, Dynamics 365 pour les modules d'opérations qui les données et les enregistre de stockage central (stockage azuré d'objet blob). Un processus de traitement par lots distinct utilise la bibliothèque client Commerce Data Exchange: Async pour insérer ce paquet de données dans la base de données du canal. 

[![Async Service](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Retail Planification

Les tâches du planificateur sont le mécanisme de distribution des données en provenance et à destination des emplacements. Les tâches sont composées de sous-tâches, qui indiquent les tables et les champs des tables contenant les données à distribuer. Dynamics 365 pour les opérations inclut les tâches prédéfinies et des sous-tâches du planificateur satisfont les exigences de réplication de la plupart des organisations. Les types de tâches prédéfinies sont créés :

-   ** Les tâches de téléchargement ** – Les tâches de téléchargement envoient les données modifiées de Dynamics 365 pour les opérations aux bases de données des canaux. Les modifications apportées aux enregistrements sont suivies via le suivi de modification SQL Server.
-   ** Tâches de chargement (Tâches P) ** – Les tâches de chargement extraient des transactions de vente d'un canal dans Dynamics 365 pour la base de données d'opérations. Les tâches P téléchargent les données de manière incrémentielle. Quand une tâche P s'exécute, la bibliothèque client Async vérifie le compteur de réplication pour les enregistrements qui ont déjà été reçus d'un emplacement. Un enregistrement est téléchargé uniquement si son compteur de réplication est supérieur à la plus grande valeur trouvée. Les tâches P ne mettent pas à jour les données qui ont été précédemment téléchargées.

Le programme de distribution est utilisé pour exécuter le transfert de données, manuellement ou en planifiant un traitement par lots dans Dynamics 365 pour les opérations. Un programme de distribution peut contenir un ou plusieurs regroupements de données de canal, et une ou plusieurs tâches du planificateur.

## <a name="realtime-service"></a>Real-time Service
Commerce échange de données : Le service en temps réel est un service intégré qui fournit la communication en temps réel entre Dynamics 365 pour les opérations et des canaux de vente au détail. Le service en temps réel permet à des ordinateurs différents et magasins en ligne du PDV pour extraire des données de Dynamics 365 pour les opérations dans le {{réel:in}}. Bien que la plupart des principales opérations puissent être exécutées dans la base de données des canaux locale, les scénarios suivants nécessitent l'accès direct aux données stockées dans Dynamics 365 pour les opérations :

-   émission et validation de cartes-cadeau ;
-   remboursement de points de fidélité ;
-   émission et validation d'avoirs ;
-   création et mise à jour des enregistrements client ;
-   création, mise à jour, puis exécution de commandes client ;
-   réception du stock avec une commande fournisseur ou un ordre de transfert ;
-   réalisation des comptages de stock ;
-   extraction des transactions de vente entre magasins et réalisation des transactions de retour.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Un profil en temps réel prédéfini de service est créé.


