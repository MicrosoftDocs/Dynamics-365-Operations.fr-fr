---
title: Données principales fournisseur intégrées
description: Cette rubrique décrit l'intégration des données fournisseur entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: da451c63c23444da564307505d38699faf9df19a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770981"
---
# <a name="integrated-vendor-master"></a>Données principales fournisseur intégrées

[!include [banner](../includes/banner.md)]

Le terme *fournisseur* fait référence à une organisation de fournisseur ou un propriétaire unique qui fait partie du processus de la chaîne d'approvisionnement, et qui fournit des marchandises pour l'entreprise. Bien que *fournisseur* est un concept établi dans les applications Finance and Operations, il n'existe pas de concept de fournisseur dans d'autres applications Dynamics 365. Au lieu de cela, certaines entreprises surchargent l'entité Compte pour enregistrer les informations client et fournisseur. D'autres sociétés utilisent un concept de fournisseur personnalisé. L'intégration de Common Data Service prend en charge ces deux conceptions. Par conséquent, vous pouvez activer l'une des conceptions, selon le scénario de l'entreprise.

L'intégration des données fournisseur entre les applications Finance and Operations et d'autres applications Dynamics 365 de multi-gérer les données. Indépendamment de l'origine des données fournisseur, elles sont intégrés en arrière-plan, au delà des limites de l'application et des différences de l'infrastructure. 

### <a name="vendor-data-flow"></a>Flux de données fournisseur

Si vous souhaitez utiliser d'autres applications Dynamics 365 pour la gestion des fournisseurs, et si vous souhaitez isoler les informations fournisseur des informations client, vous pouvez utiliser la nouvelle conception de fournisseur.

![Flux de données fournisseur](media/dual-write-vendor-data-flow.png)

Si vous souhaitez utiliser d'autres applications Dynamics 365 pour la gestion des fournisseurs, et que vous souhaitez continuer d'utiliser l'entité Compte pour stocker les informations fournisseur, vous pouvez utiliser la nouvelle conception de fournisseur étendue. Dans cette conception, les informations fournisseur étendues, telles que le groupe de fournisseurs et le profil de validation fournisseur, sont enregistrées dans les détails du fournisseur.

![Flux de données fournisseur étendues](media/dual-write-vendor-detail.jpg)

Les informations de contact fournisseur ressemblent aux informations de contact client. En arrière-plan, les informations de la personne à contacter sont stockées et extraites des mêmes entités.

## <a name="templates"></a>Modèles

Les données fournisseur incluent toutes les informations sur le fournisseur, telles que le groupe de fournisseurs, les adresses, les informations de contact, le profil de paiement et le profil de facture. Un ensemble de mappages d'entités fonctionne ensemble pendant l'interaction des données fournisseur, comme indiqué dans le tableau suivant.

Applications Finance and Operations | Autres applications Dynamics 365         | Description
----------------------------|---------------------------------|------------
Vendor V2               | Compte | Les sociétés qui utilisent l'entité Compte pour stocker les informations fournisseur peuvent continuer de l'utiliser de la même manière. Elles peuvent également bénéficier de la prochaine fonctionnalité de fournisseur explicite en raison de l'intégration des applications Finance and Operations.
Vendor V2               | Msdyn\_vendors | Les sociétés qui utilisent une solution personnalisée pour les fournisseurs peuvent profiter du concept de fournisseur prédéfini introduit dans Common Data Service en raison de l'intégration des applications Finance and Operations. 
Groupes de fournisseurs | msdyn_vendorgroups | Ce modèle synchronise les informations du groupe de fournisseurs.
Mode de paiement fournisseur | msdyn_vendorpaymentmethods | Ce modèle synchronise les informations de la méthode de paiement des fournisseurs.
Contacts CDS V2             | contacts                        | Le modèle [Contacts](dual-write-customer.md#cds-contacts-v2-to-contacts) synchronise toutes les informations principales, secondaires et tertiaires de contact, à la fois pour les clients et les fournisseurs.
Lignes d'échéancier de paiement      | msdyn_paymentschedulelines      | Le modèle [Lignes du programme de paiement](dual-write-customer.md#payment-schedule-lines-to-msdyn_paymentschedulelines) synchronise les données de référence pour les clients et les fournisseurs.
Echéancier de paiement            | msdyn_paymentschedules          | Le modèle [Lignes du programme de paiement](dual-write-customer.md#payment-schedule-to-msdyn_paymentschedules) synchronise les données de référence du programme de paiement pour les clients et les fournisseurs.
Lignes de jour de paiement CDS V2    | msdyn_paymentdaylines           | Le modèle [Lignes de jour de paiement](dual-write-customer.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) synchronise les données de référence des lignes de jour de paiement pour les clients et les fournisseurs.
Jours de paiement CDS            | msdyn_paymentdays               | Le modèle [Jours de paiement](dual-write-customer.md#payment-days-cds-to-msdyn_paymentdays) synchronise les données de référence des jours de paiement pour les clients et les fournisseurs.
Conditions de paiement            | msdyn_paymentterms              | Le modèle [Conditions de paiement](dual-write-customer.md#terms-of-payment-to-msdyn_paymentterms) synchronise les données de référence des conditions de paiement pour les clients et les fournisseurs.
Affixes de nom                | msdyn_nameaffixes               | Le modèle [Affixes de nom](dual-write-customer.md#name-affixes-to-msdyn_nameaffixes) synchronise les données de référence des affixes de nom pour les clients et les fournisseurs.

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [Vendors](dual-write/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](dual-write/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](dual-write/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
