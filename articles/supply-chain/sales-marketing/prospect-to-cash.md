---
title: "Prospect en disponibilités"
description: "La rubrique fournit une vue d'ensemble de la solution de prospect en disponibilités entre Dynamics 365 for Finance and Operations, Enterprise edition et Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: a5f1ecd5f8b46287839439a963e571531ae161a7
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="prospect-to-cash"></a>Prospect en disponibilités  

[!include[banner](../includes/banner.md)]

La solution de prospect en disponibilités utilise l'[Intégration de données](/common-data-service/entity-reference/dynamics-365-integration) pour synchroniser les données entre les instances de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Dynamics 365 for Sales via Common Data Service. Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis client, commandes client et factures client entre Finance and Operations et Sales. Bien que les données transitent entre Finance and Operations et Sales, vous pouvez effectuer des ventes et des activités marketing dans Sales et gérer l'exécution de commande avec la gestion des stocks de Finance and Operations. 

Cette solution fournit l'intégration dans les sections suivantes : 

-   [Tenir à jour les comptes dans Sales et les synchroniser avec Finance and Operations](accounts-template-mapping.md)
-   [Tenir à jour les contacts dans Sales et les synchroniser avec Finance and Operations](contacts-template-mapping.md)
-   [Tenir à jour des produits dans Finance and Operations et les synchroniser avec Sales](products-template-mapping.md)
-   [Créer des devis dans Sales et les synchroniser avec Finance and Operations](sales-quotation-template-mapping.md)
-   [Créer des commandes client dans Finance and Operations et les synchroniser avec Sales](sales-order-template-mapping.md)
-   [Créer des factures client dans Finance and Operations et les synchroniser avec Sales](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Configuration système pour Dynamics 365 for Finance and Operations, Enterprise edition

Pour utiliser le prospect pour une solution de disponibilités, vous devez installer les éléments suivants :

- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Juillet 2017) avec Mise à jour 8 de la plateforme (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)

- Deux correctifs pour Dynamics 365 for Finance and Operations, Enterprise edition (juillet 2017).

    -  [KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Ce correctif permet la synchronisation des lignes de commande client avec la fonctionnalité d'intégration de données de Finance and Operations avec Sales.
        
    -  [KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Ce correctif permet la synchronisation des commandes client avec la fonctionnalité d'intégration de données de Finance and Operations avec Sales.
    
**Remarque** : Vous devez uniquement installer KB4036524 car l'installation inclut les modifications issues de KB4036461.
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a>Configuration requise pour Dynamics 365 pour Sales

Pour utiliser le prospect pour une solution de disponibilités, vous devez installer les éléments suivants :

- Dynamics 365 pour la version de Sales 1612 (8.2.1.207) (DB 8.2.1.207) en ligne ou ultérieure.
- Prospect pour une solution de disponibilités pour Dynamics 365 for Sales, version 1.14.0.0 (v14) or ultérieure.

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Installer le Prospect pour une solution de disponibilités pour Sales

- Téléchargez [le fichier zip du package de solution Prospect pour une solution de disponibilités pour Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) depuis le CustomerSource.

- Assurez-vous que le fichier zip est débloqué de sorte que vous n'obteniez pas le message d'erreur « No import packages were found » lorsque vous installez le package de solution. Pour débloquer le fichier, procédez comme suit :

    -  Cliquez avec le bouton droit sur le fichier zip.
    -  Sélectionnez **Properties**, puis sélectionnez **Unblock**. 

- Décompressez et exécutez PackageDeployer.exe.

- Installez le Prospect pour une solution de disponibilités dans votre instance de Sales.

    - Sélectionnez le type de déploiement **Office 365**.
    - Sélectionnez **Show advanced**.
    - Pour une installation rapide, sélectionnez **Region**. Si vous sélectionnez **Don’t know**, le système recherchera toutes les régions et le temps d'installation sera plus long.
    - Entrez un **Nom d'utilisateur** et un **Mot de passe** d'utilisateur Admin disposant des droits d'utilisateur nécessaires pour effectuer l'installation.

