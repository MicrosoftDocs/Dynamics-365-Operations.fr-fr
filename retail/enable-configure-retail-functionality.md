---
title: "Initialiser les données de départ dans un nouvel environnement de vente au détail"
description: "Cet article décrit les données créées dans le cadre du processus d&quot;initialisation de Microsoft Dynamics 365 for Operations - Vente au détail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 534c9ab0f4d95f42d09f35d3197a2258c8d39526
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Initialiser les données de départ dans un nouvel environnement de vente au détail

[!include[banner](includes/banner.md)]


Cet article décrit les données créées dans le cadre du processus d'initialisation de Microsoft Dynamics 365 for Operations - Vente au détail.

Une fois la solution Retail déployée via les Microsoft Dynamics Lifecycle Services (LCS), vous devez initialiser la configuration de vente au détail pour créer les données de configuration de base. **Important :** avant d'initialiser la configuration de vente au détail, vérifiez que vous avez spécifié une langue et une adresse postale pour chaque entité juridique dans laquelle vous paramètrez des magasins de vente au détail. Cette étape doit être exécutée pour chaque entité juridique que vous utilisez pour la vente au détail. Pour initialiser la configuration de vente au détail, procédez comme suit.

1.  Démarrez le client Dynamics 365 for Operations.
2.  Cliquez sur **Commerce et vente au détail** &gt; **Configuration du siège** &gt; **Paramètres** &gt; **Paramètres des ventes au détail**.
3.  Cliquez sur **Initialiser**.

L'initialisation crée les données de configuration par défaut suivantes :

-   Tâches et sous-tâches de Retail Planification
-   Schéma de canal de vente au détail
-   Programmes de distribution de vente au détail
-   Structures d'écran par défaut, qui incluent des grilles de boutons, des images et des rubriques
-   Informations sur le fuseau horaire
-   Opérations de point de vente (PDV)
-   Autorisations PDV
-   Rapports sur les canaux
-   Métadonnées d'attribut
-   Modèles de validation de l'entité
-   Traitement par lots pour vider l'historique des sessions Commerce Data Exchange

En outre, l'enregistrement qui est liée à PCI (Payment Card Industry) est activé pour la base de données Dynamics 365 for Operations. **Remarque :** il existe une option pour configurer séparément le Retail Planification. Cette option permet de rétablir les paramètres par défaut de la configuration de Retail Planification. Une fois l'initialisation terminée, vous devez configurer les données de vente au détail supplémentaires. Voici quelques exemples :

-   Paramètres des ventes au détail
-   Paramètres de Retail scheduler
-   Canaux de vente au détail
-   Registres et périphériques
-   Assortiments





