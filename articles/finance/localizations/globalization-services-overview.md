---
title: Services de globalisation Dynamics 365
description: Cette rubrique fournit une vue d’ensemble des services de globalisation de Microsoft Dynamics 365.
author: JaneA07
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2ef942f7f6dac2c321a51800ade0bf25f2162304
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018805"
---
# <a name="dynamics-365-globalization-services"></a>Services de globalisation Dynamics 365

[!include [banner](../includes/banner.md)]

Les services de globalisation suivants peuvent être configurés pour étendre les capacités qui existent dans certains services en ligne de Microsoft Dynamics 365 :

- **Regulatory Configuration Service (RCS)** prend en charge la configuration de différents types de documents et d'états électroniques. RCS fournit une version améliorée du concepteur d'états électroniques (ER) où le référentiel de configuration est un service autonome. Pour plus d’informations, voir [Regulatory Configuration Service](rcs-overview.md).
- LA **Facturation électronique** rassemble des formats configurables pour les transformations, des signatures numériques et des intégrations configurables pour la connectivité avec des services web externes, y compris la certification et la gestion des réponses. Pour plus d’informations, voir [Facturation électronique](e-invoicing-service-overview.md).
- Le **Calcul des taxes** offre une flexibilité accrue en prenant en charge plusieurs ID taxe, la détermination du code taxe, le concepteur de calcul des taxes et un moteur d'exécution pour se conformer aux réglementations fiscales complexes du monde entier. Pour plus d’informations, voir [Calcul des taxes](global-tax-calcuation-service-overview.md).

Ces services de globalisation fournissent une intégration prête à l'emploi avec les services en ligne de Dynamics 365 suivants.

| Service en ligne | RCS | Facturation électronique | Calcul de la taxe (version préliminaire) |
|----------------|-----|----------------------|---------------------------|
| Dynamics 365 Finance | Oui | Oui | Oui | 
| Dynamics 365 Supply Chain Management | Oui | Oui | Oui | 
| Dynamics 365 Project Operations | Oui | Oui | Non applicable | 
| Dynamics 365 Commerce | Oui | Non applicable | Non applicable | 

> [!NOTE]
> En raison des différences de disponibilité des emplacements géographiques Azure pour RCS, la configuration de ce service peut entraîner le transfert des données client en dehors de la zone géographique sélectionnée pour le service en ligne Dynamics 365 concerné. Pour plus d'informations, voir [Dynamics 365 et Power Platform : disponibilité, emplacement des données, langue et localisation](https://aka.ms/rcs/D365Productavailabilityguide).