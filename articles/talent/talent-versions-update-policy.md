---
title: Configuration du système Talent et politique de mise à jour
description: Cette rubrique répertorie les besoins pour Dynamics 365 for Talent. Elle décrit également la stratégie de mise à jour.
author: andreabichsel
manager: AnnBe
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6c881bf25e7145228ccf7ef73a7ef3637c115a49
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741773"
---
# <a name="talent-system-requirements-and-update-policy"></a>Configuration du système Talent et politique de mise à jour

[!include [banner](includes/banner.md)]

Cette rubrique décrit les besoins pour Microsoft Dynamics 365 for Talent, y compris Attract, Onboard et Core HR. Elle décrit également les pays et régions où Talent est disponible, et fournit des informations sur les langues et la localisation des données pour Talent. En outre, cette rubrique fournit la stratégie de mise à jour de Talent.

## <a name="supported-web-browsers"></a>Navigateurs Web pris en charge

L'application Web Microsoft Dynamics 365 for Talent peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés : 

*   Microsoft Edge (dernière version publique disponible) sur Windows 10
*   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
*   Google Chrome (dernière version publique disponible)
*   Apple Safari (dernière version publique disponible)

Pour trouver la dernière version pour chaque navigateur Web, accédez au site Internet du fournisseur logiciel. 

> [!NOTE]
> * Pour capturer des images générées à partir de l'enregistreur de tâches et les inclure dans les documents Microsoft Word, vous devez avoir une extension Chrome installée. 
> * L'éditeur de workflow démarre en tant qu'application ClickOnce. Seuls Microsoft Edge et Internet Explorer (sur une version prise en charge Microsoft Windows) prennent en charge les applications de ClickOnce. L'application ClickOnce d'éditeur de workflow nécessite un système d'exploitation compatible 64 bits.
> * Pour afficher un aperçu des fichiers PDF, nous vous recommandons d'utiliser des navigateurs tels que Microsoft Edge (dernière version disponible) sous Windows 10, ou Google Chrome (dernière version disponible) sous Windows 10, Windows 8,1, Windows 8, Windows 7, ou sur la tablette Google Nexus 10.
>   Exigences réseau
> * Dynamics 365 for Talent est conçu pour les réseaux ayant une latence inférieure à 250 à 300 millisecondes (ms) ou moins. Cette latence est la latence entre un client de navigateur et le centre de données Microsoft Azure qui héberge Dynamics 365 for Talent. Nous vous recommandons de tester la latence du réseau à l'adresse [www.azurespeed.com](https://www.azurespeed.com "Test de latence Azure").
> * La bande passante requise pour Dynamics 365 for Talent dépend de votre scénario. La plupart des scénarios habituels nécessitent une bande passante de plus de 50 kilo-octets par seconde (KBps).
> 
> [!WARNING]
> Ne calculez pas la bande passante d'un emplacement client nécessaire en multipliant le nombre d'utilisateurs par la bande passante minimale requise. Il est très difficile de calculer l'utilisation simultanée d'un emplacement donné. Pour les clients qui s'inquiètent des besoins de bande passante, utilisez une version d'évaluation de Dynamics 365 for Talent.

## <a name="supported-microsoft-office-applications"></a>Applications Microsoft Office prises en charge

* Pour exécuter les compléments Microsoft Excel et Word, vous devez disposer de Microsoft Office 2016 pour Windows ou Mac. Pour plus de détails sur les exigences en matière de versions, voir [Dépannage de l'intégration d'Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Dépannage de l'intégration d'Office").
* Pour afficher les documents qui sont générés par la fonctionnalité Exporter vers Excel ou Exporter vers Word, vous devez disposer de Microsoft Office 2007 ou version ultérieure.

## <a name="regional-availability-languages-and-localization"></a>Disponibilité, langues et localisation régionales

Vous pouvez télécharger un fichier PDF des pays, régions et langues pris en charge par Talent dans [Disponibilité internationale de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability). 

> [!NOTE]
> Bien que l'interface utilisateur soit localisée dans d'autres langues, toutes les données d'utilisateur sont stockées dans la langue dans laquelle elles ont été entrées. Vous pouvez créer des e-mails et des modèles dans d'autres langues, mais les données telles que les informations de planification sont uniquement disponibles en anglais à ce stade.

Si vous êtes développeur et intéressé à créer des personnalisations spécifiques à un pays ou une région, ou à créer une solution pour un pays ou une région actuellement non pris en charge par Microsoft, voir [Globalisation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

## <a name="update-policy"></a>Stratégie de mise à jour

Microsoft Dynamics 365 for Talent fait l'objet d'une maintenance dans le cadre d'une offre Cloud. Les mises à jour de Dynamics 365 for Talent sont continues et appliquées automatiquement par Microsoft.

Les mises à jour sont publiées régulièrement et s'appliqueront à tous les environnements. Dynamics 365 for Talent est pris en charge conformément à la [Stratégie Microsoft Support Lifecycle](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), qui fournit des instructions cohérentes et prévisibles pour la disponibilité du support produit.
