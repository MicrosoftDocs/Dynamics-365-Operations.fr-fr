---
title: "Définir les communications de canal de vente au détail (Commerce Data Exchange)"
description: "Cet article fournit une vue d&quot;ensemble Commerce Data Exchange et de ses composants. Il explique le rôle que joue chaque composant dans le transfert des données entre Microsoft Dynamics 365 for Operations et les canaux de vente au détail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: ba1bb54a29250a2bb59622ee4391b64ac455af33
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Définir les communications de canal de vente au détail (Commerce Data Exchange)

[!include[banner](../includes/banner.md)]


Cet article fournit une vue d'ensemble Commerce Data Exchange et de ses composants. Il explique le rôle que joue chaque composant dans le transfert des données entre Microsoft Dynamics 365 for Operations et les canaux de vente au détail.

<a name="overview"></a>Vue d'ensemble
--------

Commerce Data Exchange est un système qui transfère des données entre Dynamics 365 for Operations et les canaux de vente au détail, tels que des magasins en ligne ou des magasins traditionnels. La base de données qui enregistre les données pour un canal de vente au détail est distincte de la base de données Dynamics 365 for Operations. La base de données de canal contient uniquement les données requises pour les transactions de vente au détail. Des données principales sont configurées dans Dynamics 365 for Operations et distribuées aux canaux. Les données transactionnelles sont créées dans le système de point de vente (POS) ou dans le magasin en ligne, puis téléchargées vers Dynamics 365 for Operations. La distribution de données est asynchrone. Autrement dit, le processus de rassemblement et de groupement des données à la source se produit de manière distincte du processus de réception et d'application des données à la destination. Pour certains scénarios, comme les recherches de prix et de stock, les données doivent être extraites en temps réel. Pour prendre en charge ces scénarios, Commerce Data Exchange inclut également un service qui active la communication en temps réel entre Dynamics 365 for Operations et un canal. 

[![updated-retail-graphic](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Service Async
Le suivi de modification de Microsoft SQL Server sur la base de données Dynamics 365 for Operations permet de déterminer les modifications des données qui doivent être envoyées aux canaux. Selon un programme de distribution, Dynamics 365 for Operations regroupe ces données et les enregistre dans le stockage central (stockage en blob Azure). Un processus de traitement par lots distinct utilise la bibliothèque client Commerce Data Exchange: Async pour insérer ce paquet de données dans la base de données du canal. 

[![Service Async](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Retail Planification

Les tâches du planificateur sont le mécanisme de distribution des données en provenance et à destination des emplacements. Les tâches sont composées de sous-tâches, qui indiquent les tables et les champs des tables contenant les données à distribuer. Dynamics 365 for Operations inclut des tâches prédéfinies et des sous-tâches du planificateur qui correspondent aux exigences de réplication de la plupart des organisations. Les types de tâches prédéfinies sont créés :

-   **Tâches de téléchargement** – Les tâches de téléchargement envoient les données modifiées de Dynamics 365 for Operations vers les bases de données des canaux. Les modifications apportées aux enregistrements sont suivies via le suivi de modification SQL Server.
-   **Tâches de téléchargement amont (tâches P)** – Les tâches de téléchargement amont extraient les transactions de vente d'un canal à destination de la base de données Dynamics 365 for Operations. Les tâches P téléchargent les données de manière incrémentielle. Quand une tâche P s'exécute, la bibliothèque client Async vérifie le compteur de réplication pour les enregistrements qui ont déjà été reçus d'un emplacement. Un enregistrement est téléchargé uniquement si son compteur de réplication est supérieur à la plus grande valeur trouvée. Les tâches P ne mettent pas à jour les données qui ont été précédemment téléchargées.

Le programme de distribution est utilisé pour exécuter le transfert de données, manuellement ou en programmant un traitement par lots dans Dynamics 365 for Operations. Un programme de distribution peut contenir un ou plusieurs regroupements de données de canal, et une ou plusieurs tâches du planificateur.

## <a name="realtime-service"></a>Realtime Service
Commerce Data Exchange : Real-time Service est un service intégré qui offre une communication synchronisée en temps réel entre Dynamics 365 for Operations et les canaux de vente au détail. Real-time Service permet à différents ordinateurs de POS et magasins en ligne d'extraire des données spécifiques de Dynamics 365 for Operations, en temps réel. Bien que la plupart des opérations principales puissent être exécutées dans la base de données locale du canal, les scénarios suivants nécessitent un accès direct aux données stockées dans Dynamics 365 for Operations :

-   émission et validation de cartes-cadeau ;
-   remboursement de points de fidélité ;
-   émission et validation d'avoirs ;
-   création et mise à jour des enregistrements client ;
-   création, mise à jour, puis exécution de commandes client ;
-   réception du stock avec une commande fournisseur ou un ordre de transfert ;
-   réalisation des comptages de stock ;
-   extraction des transactions de vente entre magasins et réalisation des transactions de retour.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Un profil Real-time Service prédéfini est créé.




