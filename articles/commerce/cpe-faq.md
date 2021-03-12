---
title: FAQ des environnements d'évaluation Dynamics 365 Commerce
description: Cette rubrique fournit des réponses aux questions fréquemment posées sur l'environnement d'évaluation Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b8d7d7364087dacf3b4479ab008609ecffeaacb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000973"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>FAQ des environnements d'évaluation Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cette rubrique fournit des réponses aux questions fréquemment posées sur l'environnement d'évaluation Microsoft Dynamics 365 Commerce.

**Pouvons-nous utiliser l'environnement d'évaluation Commerce comme vitrine de commerce électronique pour les clients qui implémentent actuellement Retail ?**

N° L'environnement d'évaluation Commerce est uniquement destiné à l'évaluation. Si vous avez besoin d'un environnement pour un client qui implémente Retail, contactez Microsoft.

**L'environnement d'évaluation Commerce peut-il être utilisé pour fournir les fonctionnalités de commerce électronique s'appuyant sur une application/un environnement existant qui implémente Retail ?**

Non (généralement). Les composants de la version d'évaluation Commerce sont disponibles uniquement pour les environnements qui correspondent aux configurations spécifiées dans le guide des conditions préalables et de la mise en service. En outre, les données de démonstration de base requises ne seront pas disponibles dans les environnements qui ont été déployés avec une version initiale antérieure à la version 10.0.8. 

**Quels sont les coûts impliqués dans le déploiement de l'environnement d'évaluation Commerce sur Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS) ?**

Un environnement de démonstration du siège Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce traditionnel (machine virtuelle \[VM\]) sera hébergé dans votre abonnement Azure. Vous pouvez utiliser le [Calculateur de tarification Azure](https://azure.microsoft.com/pricing/calculator/) pour estimer ce coût.

D'autres composants tels que Commerce Scale Unit, le générateur de site Commerce et votre site de commerce électronique seront disponibles sous forme de logiciel en tant que service (SaaS) et seront hébergés par Microsoft.

**Quelles zones géographiques Azure sont actuellement prises en charge pour l'environnement d'évaluation de Commerce ?**

L'environnement d'évaluation de Commerce ne peut être déployé que dans la zone géographique de l'Amérique du Nord.

**Existe-t-il un disque dur virtuel téléchargeable doté de l'option complète de machine virtuelle OneBox ?**

Dynamics 365 Commerce et Commerce Scale Unit sont entièrement des logiciels en tant que service (SaaS) et doivent être hébergés dans le cloud.

**Pendant combien de temps l'environnement d'évaluation de Commerce peut-il être utilisé ?**

L'environnement d'évaluation de Commerce est assorti d'une limite d'utilisation de 30 jours à compter de la date à laquelle les composants SaaS tels que Commerce Scale Unit, le générateur de site Commerce et votre site de commerce électronique sont fournis.

**Puis-je prolonger la durée limite de mon environnement d'évaluation Commerce ?**

La prolongation du délai est une exception à la norme et est envisagée au cas par cas. Contactez votre partenaire Microsoft pour obtenir de l'aide.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble d'un environnement d'évaluation Dynamics 365 Commerce](cpe-overview.md)

[Mettre en service un environnement d'évaluation Dynamics 365 Commerce](provisioning-guide.md)

[Configurer un environnement d'évaluation Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurer le BOPIS dans un environnement d'évaluation Dynamics 365 Commerce](cpe-bopis.md)

[Configurer des fonctionnalités facultatives pour un environnement d'évaluation Dynamics 365 Commerce](cpe-optional-features.md)
