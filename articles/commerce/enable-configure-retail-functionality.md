---
title: Initialisation des données d'origine dans de nouveaux environnements Commerce
description: Cet article décrit les données créées dans le cadre du processus d'initialisation de Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 24d4d49c51738203bb89a9844d57f644b8afd4b7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412178"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a>Initialisation des données d'origine dans de nouveaux environnements Commerce

[!include [banner](includes/banner.md)]

Cet article décrit les données créées dans le cadre du processus d'initialisation de Dynamics 365 Commerce.

Une fois la solution Commerce déployée via Microsoft Dynamics Lifecycle Services (LCS), vous devez initialiser la configuration de Commerce pour créer les données de configuration de base.

> [!IMPORTANT]
> Avant d'initialiser la configuration de Commerce, vérifiez que vous avez spécifié une langue et une adresse postale pour chaque entité juridique dans laquelle vous paramétrez des magasins. Cette étape doit être exécutée pour chaque entité juridique que vous utilisez pour Commerce.

Pour initialiser la configuration, procédez comme suit.

1. Démarrez le client Commerce.
2. Cliquez sur **Commerce et vente au détail** &gt; **Configuration du siège** &gt; **Paramètres** &gt; **Paramètres des ventes au détail**.
3. Cliquez sur **Initialiser**.

L'initialisation crée les données de configuration par défaut suivantes :

- Tâches et sous-tâches de Planificateur de commerce
- Schéma de canal commercial
- Programmes de distribution Commerce
- Structures d'écran par défaut, qui incluent des grilles de boutons, des images et des rubriques
- Informations sur le fuseau horaire
- Opérations de point de vente (PDV)
- Autorisations PDV
- Rapports sur les canaux
- Métadonnées d'attribut
- Modèles de validation de l'entité
- Traitement par lots pour vider l'historique des sessions Commerce Data Exchange

En outre, l'enregistrement qui est lié à PCI (Payment Card Industry) est activé pour la base de données Commerce.

> [!NOTE]
> Il existe une option pour configurer séparément le Planificateur de commerce. Cette option permet de rétablir les paramètres par défaut de la configuration du Planificateur de commerce.

Une fois l'initialisation terminée, vous devez configurer les données de Commerce supplémentaires. Voici quelques exemples :

- Paramètres commerciaux
- Paramètres de planification commerciale
- Canaux de Commerce
- Registres et périphériques
- Assortiments


[!INCLUDE[footer-include](../includes/footer-banner.md)]