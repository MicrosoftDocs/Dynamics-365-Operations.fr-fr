---
title: Ouvrir une URL en PDV
description: Cet article fournit une vue d’ensemble des améliorations apportées à la fonctionnalité de recherche de produits et de clients dans  Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.custom: 141393
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: ad82cf1039515e58d1717453ee3fb4e3dafd84fe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276425"
---
# <a name="open-url-in-pos"></a>Ouvrir une URL en PDV

[!include [banner](includes/banner.md)]

Cet article décrit comment configurer un bouton dans le point de vente (PDV) Dynamics 365 Commerce pour ouvrir une URL. Cette fonctionnalité ne nécessite pas de personnalisation du code, et peut être configurée par une personne avec un rôle non développeur. 

Cette fonctionnalité permet la configuration d’un bouton dans PDV, à l’aide du concepteur de grille de boutons pour ouvrir une URL. Actuellement, cette opération est prise en charge dans les configurations suivantes :

- Ouvrir dans une nouvelle fenêtre.
- Ouvrir dans PDV.
- Ouvrir une application native.

## <a name="open-in-new-window"></a>Ouvrir dans une nouvelle fenêtre

Cette configuration détermine si l’URL doit s’ouvrir dans une nouvelle fenêtre ou de l’application. Si elle est configurée pour ouvrir une URL web dans l’application, le volet de navigation latéral et la barre supérieure du PDV sont visibles et disponibles pour une intervention de l’utilisateur. Si elle est configurée pour s’ouvrir dans une nouvelle fenêtre, l’URL s’ouvre dans une nouvelle fenêtre d’application sur Modern POS pour Windows, et dans un nouvel onglet du navigateur dans tous les autres clients du PDV. Pour ce faire, vous devez configurer l’URL avec l’option **Ouvrir dans une nouvelle fenêtre** sélectionnée.

## <a name="open-within-pos"></a>Ouvrir dans le PDV

L’ouverture d’une URL Web dans le PDV n’est pris en charge actuellement que pour Modern POS sous Windows. Sous d’autres clients, cette capacité est en cours de développement et son lancement est planifié dans les futures mises à jour. Pour ce faire, vous devez configurer l’URL avec l’option **Ouvrir dans une nouvelle fenêtre** non sélectionnée.

## <a name="open-a-native-app"></a>Ouvrir une application native

Cette fonction vous permet également de spécifier les URL non Web pour ouvrir une application native. Par exemple, vous pouvez spécifier des protocoles d’URL tels que MailTo, SIP, IM ou MSTEAMS, qui peuvent ensuite être gérés par les applications natives respectives dans le périphérique de serveur. Pour ce faire, vous devez configurer l’URL avec l’option **Ouvrir dans une nouvelle fenêtre** sélectionnée.

- Pour les ordinateurs Windows, voir [Exporter ou importer les associations d’applications par défaut](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) pour définir les associations de protocoles par défaut si vous paramétrez votre ordinateur à l’aide de DISM (Deployment Image Servicing and Management).
- Si vous utilisez MDM, tel qu’Intune, pour gérer vos ordinateurs Windows, voir [Stratégie CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults).
- Si vous êtes développeur et que vous générez un site Web personnalisé, voir [Lancer l’application par défaut pour une URI](/windows/uwp/launch-resume/launch-default-app).

## <a name="open-a-native-app-seamlessly"></a>Ouvrir une application native en toute transparence

Windows, iOS et Android permettent également l’ouverture des applications de façon plus transparente, selon l’association du protocole d’application. Si votre application n’est pas déjà configurée pour gérer l’ouverture d’un navigateur Web, vous pouvez nécessiter un développeur pour la configurer.

- Pour Windows, voir [Activer les applications pour les sites Web avec des gestionnaires d’URI d’application](/windows/uwp/launch-resume/web-to-app-linking).
- Pour iOS, voir [Liens universels pour les développeurs](https://developer.apple.com/ios/universal-links/).
- Pour Android, voir [Gestion des liens d’applications Android](https://developer.android.com/training/app-links/).

| Client                | Ouvrir dans une nouvelle fenêtre | Ouvrir une application native | Ouvrir dans le PDV | Détails                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| Modern POS sous Windows | ✓\*                | ✓               | ✓              | \* S’ouvre dans une nouvelle fenêtre Modern POS |
| PDV Cloud             | ✓\*                | ✓               | O              | \* S’ouvre dans un nouvel onglet du navigateur        |
| Modern POS sous iOS     | ✓\*                | ✓               | O              | \* S’ouvre dans un nouvel onglet du navigateur        |
| Modern POS sous Android | ✓\*                | ✓               | O              | \* S’ouvre dans un nouvel onglet du navigateur        |

## <a name="before-you-begin"></a>Avant de commencer

Avant de commencer, examinez la procédure de configuration des [Mises en page de l’écran pour le point de vente (PDV)](pos-screen-layouts.md).

## <a name="open-url-in-pos"></a>Ouvrir une URL dans PDV

Pour configurer l’ouverture d’une URL dans le PDV, procédez comme suit.

1. Au niveau du siège social, accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Mises en page de l’écran**.
2. Sélectionnez **Grilles de boutons \> Concepteur**.
3. Créez un bouton.
4. Sélectionnez les propriétés du **Bouton**.
5. Sélectionnez **Ouvrir l’URL** comme action.
6. Entrez l’URL à utiliser.
7. Configurez si l’URL doit s’ouvrir dans une nouvelle fenêtre.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
