---
title: "Prospect en disponibilités"
description: "Cette rubrique fournit une vue d'ensemble de la solution Prospect en disponibilités entre Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition et Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 602873e8af976c57f27ce53b76391516351755e3
ms.openlocfilehash: 29d33d3ecf97c15fed0247d172ff6fb3bbdaa018
ms.contentlocale: fr-fr
ms.lasthandoff: 01/25/2018

---

# <a name="prospect-to-cash"></a>Prospect en disponibilités

[!include[banner](../includes/banner.md)]

La solution Prospect en disponibilités fournit une synchronisation directe entre Dynamics 365 for Finance and Operations, Enterprise Edition et Dynamics 365 for Sales. Les modèles Prospect en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données pour les comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales. Bien que les données transitent entre Finance and Operations et Sales, vous pouvez effectuer des activités de vente et de marketing dans Sales, et vous pouvez gérer l'exécution de commande à l'aide de la gestion des stocks de Finance and Operations. 

Pour plus d'informations sur l'intégration de la solution Prospect en disponibilités, consultez la courte vidéo YouTube :

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

Dans la version actuelle, la solution Prospect en disponibilités fournit les types suivants de synchronisation directe :

- [Tenir à jour les comptes dans Sales et les synchroniser directement avec Finance and Operations](accounts-template-mapping-direct.md)
- [Tenir à jour des produits dans Finance and Operations et les synchroniser directement avec Sales](products-template-mapping-direct.md)
- [Tenir à jour les contacts dans Sales et les synchroniser directement avec les contacts ou les clients dans Finance and Operations](contacts-template-mapping-direct.md)
- [Synchroniser le devis de vente directement entre Sales et Finance and Operations (modèle en attente de lancement)](sales-quotation-template-mapping-sales-fin.md)
- [Synchroniser les commandes client directement à partir de Finance and Operations avec Sales](sales-order-template-mapping-direct.md)
- [Synchroniser les commandes client directement entre Sales et Finance and Operations (modèle en attente de lancement)](sales-order-template-mapping-direct-two-ways.md)
- [Synchroniser les factures client directement à partir de Finance and Operations avec Sales](sales-invoice-template-mapping-direct.md)

Dans les versions antérieures, la solution Prospect en disponibilités fournit les types suivants de synchronisation non directe :

- [Tenir à jour les comptes dans Sales et les synchroniser avec Finance and Operations](accounts-template-mapping.md)
- [Tenir à jour des contacts dans Sales et les synchroniser sur Finance and Operations](contacts-template-mapping.md)
- [Tenir à jour des produits dans Finance and Operations et les synchroniser avec Sales](products-template-mapping.md)
- [Créer des devis dans Sales et les synchroniser avec Finance and Operations](sales-quotation-template-mapping.md)
- [Créer des commandes client dans Finance and Operations et les synchroniser avec Sales](sales-order-template-mapping.md)
- [Créer des factures client dans Finance and Operations et les synchroniser avec Sales](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a>Configuration requise pour Finance and Operations

L'intégration de la solution Prospect en disponibilités est prise en charge dans les versions suivantes :

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (décembre 2017)

- Dynamics 365 for Finance and Operations, Enterprise Edition (décembre 2017) - Version d'application 7.3.11971.56116 avec mise à jour 12 de la plateforme (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise Edition (juillet 2017)

- Dynamics 365 for Finance and Operations, Enterprise Edition (juillet 2017) avec mise à jour 8 de la plateforme (version d'application 7.2.11792.56024 avec version de plateforme 7.0.4565.16212).
- Les correctifs suivants sont requis :

    - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Ce correctif permet la synchronisation des commandes client entre Sales et Finance and Operations via la fonctionnalité d'intégration de données. Il fournit également plusieurs autres améliorations.
    - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ce correctif permet la synchronisation des lignes de commande client entre Finance and Operations et Sales via la fonctionnalité d'intégration de données.
    - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ce correctif permet la synchronisation des commandes client entre Finance and Operations et Sales via la fonctionnalité d'intégration de données.

    > [!NOTE]
    > Vous devez uniquement installer KB4045570 car l'installation inclut les modifications issues des autres correctifs. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations, version 1611 (novembre 2016)

- Dynamics 365 for Finance and Operations, version 1611 (novembre 2016) avec mise à jour 8 ou plus de la plateforme

- Les correctifs suivants sont requis :

    - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Permet la synchronisation des commandes client avec l'intégrateur de données entre Finance and Operations et Sales. 
    - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Permet la synchronisation des en-têtes et lignes de commande client avec l'intégrateur de données entre Finance and Operations et Sales.
    - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - La prise en charge de l'intégration de la solution Prospect en disponibilités via les entités de données est requise.
    
    > [!NOTE]
    > Après avoir installé les correctifs, vous devez déclencher le traitement par lots suivant à partir de l'écran **SalesPopulateProspectToCash**. Cet écran est masqué, car vous n'en avez besoin qu'une seule fois. Pour accéder à l'écran, connectez-vous à l'environnement et ajoutez ce qui suit à l'URL dans l'adresse du navigateur : &mi=action:SalesPopulateProspectToCash, par exemple, https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash. Lorsque l'écran s'ouvre, cliquez sur OK. Un nouveau champ **LineCreationSequnceNumber** dans les tables **SalesLine**, **SalesQuotationLine** et **CustInvoiceTrans** est renseigné avec des valeurs uniques et la liste des produits est actualisée. Cela est nécessaire pour assurer l'intégration de la solution Prospect en disponibilités.


## <a name="system-requirements-for-sales"></a>Configuration requise pour Sales

Pour utiliser la solution Prospect en disponibilités, vous devez installer les composants suivants :

- Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) en ligne
- Solution Prospect en disponibilités pour Dynamics 365 for Sales, version 1.15.0.0 (v15). 

   > [!NOTE]
   >
   > Les modèles avec la version 1.0.0.0 et 1.0.0.1 sont pris en charge dans la solution Prospect en disponibilités pour Dynamics 365 for Sales, version 1.14.1.0
   >
   > Les modèles avec la version 2.0.0.0 et 2.1.0.0 sont pris en charge dans la solution Prospect en disponibilités pour Dynamics 365 for Sales, version 1.15.0.0

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Installer le Prospect pour une solution de disponibilités pour Sales

1. Téléchargez le [fichier zip du package de la solution Prospect en disponibilités pour Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) à partir de CustomerSource.
2. Vérifiez que le fichier zip est débloqué. Sinon, lorsque vous tentez d'installer le package de solution, vous pouvez recevoir le message d'erreur suivant : « Aucun package d'importation n'a été trouvé ». Pour débloquer le fichier zip, cliquez dessus avec le bouton droit, puis sélectionnez **Propriétés**. Sélectionnez **Débloquer**.
3. Décompressez et exécutez **PackageDeployer.exe**.
4. Installez la solution Prospect en disponibilités dans votre instance de Sales :

    1. Sélectionnez **Office 365** comme type de déploiement.
    2. Sélectionnez **Show advanced**.
    3. Pour une installation rapide, sélectionnez une région. Si vous sélectionnez **Don't know**, le système recherchera toutes les régions et le temps d'installation sera plus long.
    4. Entrez le nom d'utilisateur et le mot de passe d'un utilisateur administrateur disposant de droits d'installation.



