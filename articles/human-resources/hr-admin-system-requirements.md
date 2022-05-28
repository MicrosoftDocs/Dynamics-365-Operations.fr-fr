---
title: Configuration requise
description: Cette rubrique répertorie la configuration système requise pour Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e88006ebf174f1a416fa6d8572d439a0395f0e44
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690860"
---
# <a name="system-requirements"></a>Configuration requise

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique répertorie la configuration système requise pour Microsoft Dynamics 365 Human Resources. Elle décrit également les pays et régions où Human Resources est disponible, et fournit des informations sur les langues et la localisation des données pour Human Resources.

## <a name="supported-web-browsers"></a>Navigateurs Web pris en charge

Les utilisateurs peuvent accéder à Microsoft Dynamics 365 Human Resources à l’aide de n’importe lequel des navigateurs Web suivants qui s’exécutent sur les systèmes d’exploitation spécifiés : 

*   Microsoft Edge (dernière version publique disponible) sur Windows 10
*   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
*   Google Chrome (dernière version publique disponible)
*   Apple Safari (dernière version publique disponible)

Pour trouver la dernière version pour chaque navigateur Web, accédez au site Internet du fournisseur logiciel. 

## <a name="special-considerations"></a>Considérations particulières

* Pour permettre à l’enregistreur de tâches d’effectuer des captures d’écran et de les inclure dans les documents Microsoft Word générés, vous devez installer une extension Chrome préliminaire.
* L’éditeur de workflow démarre en tant qu’application ClickOnce. Seuls Microsoft Edge et Internet Explorer (sur une version prise en charge Microsoft Windows) prennent en charge les applications de ClickOnce. L’application ClickOnce d’éditeur de workflow nécessite un système d’exploitation compatible 64 bits.
* Pour afficher un aperçu des fichiers PDF, nous vous recommandons d’utiliser des navigateurs tels que Microsoft Edge (dernière version disponible) sous Windows 10, ou Google Chrome (dernière version disponible) sous Windows 10, Windows 8,1, Windows 8, Windows 7, ou sur la tablette Google Nexus 10.

## <a name="network-requirements"></a>Exigences réseau

* Human Resources est conçu pour les réseaux ayant une latence inférieure à 250 à 300 millisecondes (ms) ou moins. Cette latence est la latence entre un client de navigateur et le centre de données Microsoft Azure qui héberge Human Resources. Nous vous recommandons de tester la latence du réseau à l’adresse [www.azurespeed.com](https://www.azurespeed.com "Test de latence Azure").
* La bande passante requise pour Human Resources dépend de votre scénario. Les scénarios habituels nécessitent une bande passante de plus de 50 kilo-octets par seconde (KBps).
 
> [!WARNING]
> Ne calculez pas la bande passante d’un emplacement client nécessaire en multipliant le nombre d’utilisateurs par la bande passante minimale requise. Il est très difficile de calculer l’utilisation simultanée d’un emplacement donné. Pour les clients qui s’inquiètent des besoins de bande passante, utilisez une version d’évaluation de Human Resources.

## <a name="supported-microsoft-office-applications"></a>Applications Microsoft Office prises en charge

* Pour exécuter les compléments Microsoft Excel et Word, vous devez disposer de Microsoft Office 2016 pour Windows ou Mac. Pour plus de détails sur les exigences en matière de versions, voir [Dépannage de l’intégration d’Office](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md "Résolution des problèmes d’intégration d’Office").
* Pour afficher les documents qui sont générés par la fonctionnalité Exporter vers Excel ou Exporter vers Word, vous devez disposer de Microsoft Office 2007 ou version ultérieure.

## <a name="regional-availability-languages-and-localization"></a>Disponibilité, langues et localisation régionales

Vous pouvez télécharger un fichier PDF des pays, régions et langues pris en charge par Human Resources dans [Disponibilité internationale de Microsoft Dynamics 365](/dynamics365/get-started/availability). 

> [!NOTE]
> Bien que l’interface utilisateur soit localisée dans d’autres langues, toutes les données d’utilisateur sont stockées dans la langue dans laquelle elles ont été entrées. Vous pouvez créer des e-mails et des modèles dans d’autres langues, mais les données telles que les informations de planification sont uniquement disponibles en anglais à ce stade.

Si vous êtes développeur et intéressé à créer des personnalisations spécifiques à un pays ou une région, ou à créer une solution pour un pays ou une région actuellement non pris en charge par Microsoft, voir [Globalisation](/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
