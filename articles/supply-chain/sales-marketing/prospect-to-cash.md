---
title: Prospect en disponibilités
description: Cette rubrique fournit une vue d'ensemble de la solution Prospect en disponibilités entre Dynamics 365 Supply Chain Management et Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 1a96b7cfa57ec72b25f21d94fadb2fbf9bc6ea3b
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251353"
---
# <a name="prospect-to-cash"></a>Prospect en disponibilités

[!include [banner](../includes/banner.md)]

La solution Prospect en disponibilités offre la synchronisation directe entre Dynamics 365 Supply Chain Management et Dynamics 365 Sales. Les modèles Prospect en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données pour les comptes, contacts, produits, devis de vente, commandes client et factures client. Bien que les données transitent entre Finance and Operations et Sales, vous pouvez effectuer des activités de vente et de marketing dans Sales, et vous pouvez gérer l'exécution de commande à l'aide de la gestion des stocks de Supply Chain Management. 

Pour en savoir plus sur l'intégration de la solution Prospect en disponibilités, visionnez la brève vidéo YouTube [Intégration de la solution Prospect en disponibilités](https://www.youtube.com/watch?v=AVV9x5x-XCg).

Dans la version actuelle, la solution Prospect en disponibilités fournit les types suivants de synchronisation directe :

- [Tenir à jour les comptes dans Sales et les synchroniser directement avec Supply Chain Management](accounts-template-mapping-direct.md)
- [Tenir à jour les produits dans Supply Chain Management et les synchroniser directement avec Sales](products-template-mapping-direct.md)
- [Tenir à jour les contacts dans Sales et les synchroniser directement avec les contacts ou les clients dans Supply Chain Management](contacts-template-mapping-direct.md)
- [Synchroniser directement le devis de vente provenant de Sales avec Supply Chain Management](sales-quotation-template-mapping-sales-fin.md)
- [Synchroniser les commandes client directement entre Sales et Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)
- [Synchroniser directement la facture provenant de Supply Chain Management vers Sales](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a>Configuration système pour Supply Chain Management
L'intégration de la solution Prospect en disponibilités est prise en charge dans les versions suivantes :

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (décembre 2017)

- Dynamics 365 for Finance and Operations, Enterprise Edition (décembre 2017) - Version de l'application 7.3.11971.56116 avec Platform Update 12 (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise Edition (juillet 2017)

- Dynamics 365 for Finance and Operations, Enterprise Edition (juillet 2017) - avec Platform Update 8 (version de l'application 7.2.11792.56024 avec version de la plateforme 7.0.4565.16212).
- Les correctifs suivants sont requis :

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Ce correctif permet la synchronisation des commandes client entre Sales et Supply Chain Management via la fonctionnalité d'intégration de données. Il fournit également plusieurs autres améliorations.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ce correctif permet la synchronisation de la ligne de commande client entre Supply Chain Management et Sales via la fonctionnalité d'intégration de données.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ce correctif permet la synchronisation des commandes client entre Supply Chain Management et Sales via la fonctionnalité d'intégration de données.

    > [!NOTE]
    > Vous devez uniquement installer KB4045570 car l'installation inclut les modifications issues des autres correctifs. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations version 1611 (novembre 2016)

- Dynamics 365 for Finance and Operations version 1611 (novembre 2016) avec Platform Update 8 ou version ultérieure

- Les correctifs suivants sont requis :

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Permet la synchronisation des commandes client avec l'intégrateur de données entre Supply Chain Management et Sales. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Permet la synchronisation de la ligne et de l'en-tête de la commande client avec l'intégrateur de données entre Supply Chain Management et Sales.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - La prise en charge de l'intégration de la solution Prospect en disponibilités via les entités de données est requise.
    
    > [!NOTE]
    > Après avoir installé les correctifs, vous devez déclencher le traitement par lots suivant à partir de l'écran **SalesPopulateProspectToCash**. Cet écran est masqué, car vous n'en avez besoin qu'une seule fois. Pour accéder à l'écran, connectez-vous à l'environnement et ajoutez ce qui suit à l'URL dans le champ d'adresse du navigateur, *&mi=action:SalesPopulateProspectToCash*, par exemple, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. Lorsque l'écran s'ouvre, cliquez sur OK. Un nouveau champ **LineCreationSequnceNumber** dans les tables **SalesLine**, **SalesQuotationLine** et **CustInvoiceTrans** est renseigné avec des valeurs uniques et la liste des produits est actualisée. Cela est nécessaire pour assurer l'intégration de la solution Prospect en disponibilités.


## <a name="system-requirements-for-sales"></a>Configuration requise pour Sales

Pour utiliser la solution Prospect en disponibilités, vous devez installer les composants suivants :

- Dynamics 365 Sales version 1612 (8.2.1.207) (DB 8.2.1.207) en ligne ou ultérieure
- Solution Prospect en disponibilités pour Dynamics 365 Sales, version 1.15.0.0 or ultérieure. La solution est disponible pour le téléchargement depuis AppSource. [Télécharger Dynamics 365, Prospect en disponibilités](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
