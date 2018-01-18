---
title: "Étendre les fonctionnalités de Microsoft Dynamics 365 for Talent"
description: "Si vous avez créé des applications Microsoft PowerApps, vous pouvez démarrer ces applications à partir des liens contenus dans Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Talent
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cfd3b475b113fdab4ceeb3e636fea6c9134ab982
ms.openlocfilehash: 0ab829803634871c9060daa381bd02d7d2bbdf42
ms.contentlocale: fr-fr
ms.lasthandoff: 12/01/2017

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a>Étendre les fonctionnalités de Microsoft Dynamics 365 for Talent
Si vous avez créé des applications Microsoft PowerApps, vous pouvez démarrer ces applications à partir des liens contenus dans Microsoft Dynamics 365 for Talent. Pour paramétrer l'accès à vos applications, vous devrez configurer certaines informations de Talent sur une page de configuration que vous pouvez ouvrir à partir de l'espace de travail **Administration du système**.

## <a name="configuring-embedded-powerapps-within-talent"></a>Configuration des applications PowerApps incorporées dans Talent
Utilisez la page **Définir les applications Microsoft PowerApps incorporées** pour configurer les pages Talent pour démarrer les applications PowerApps. Pour ouvrir la page **Définir les applications Microsoft PowerApps incorporées**, ouvrez l'espace de travail **Administration du système**, puis ouvrez l'onglet **Liens**. Sélectionnez **Microsoft PowerApps** dans le groupe **Paramétrage**. 

Les informations suivantes sont saisies ou définies sur cette page : 

> - Nom descriptif ou identificateur de chaque application PowerApps.
> - Identificateur unique (GUID) de chaque application que vous ajoutez à une page Talent. L'ID d'application est disponible sur le site PowerApps [powerapps.com](http://powerapps.com/). 
> - Page à partir de laquelle les utilisateurs peuvent ouvrir une application ou un état. Certaines pages Talent prennent en charge les applications PowerApps incorporées et les états Power BI. 

 > [!NOTE]
 >  Entrez le nom interne de la page au lieu du nom complet qui apparaît en haut de la page. Pour rechercher le nom interne, ouvrez la page dont vous avez besoin du nom interne, puis cliquez avec le bouton droit n'importe où sur la page. Lorsque le menu s'ouvre, placez votre pointeur sur l'élément **Informations sur l'écran**. Le nom d'écran interne s'affiche en regard de l'élément **Informations sur l'écran** dans le menu.
 
> - Spécifiez le contrôle d'écran à partir duquel l'application peut extraire les données de contexte. Par exemple, une application peut utiliser les données concernant un collaborateur. Si vous ouvrez la page **Collaborateur** dans le champ **Contexte**, la page **Collaborateur** s'ouvre lorsque vous démarrez l'application. La saisie de données dans le champ **Contexte** est facultative. 
> - Définissez la taille de la boîte de dialogue dans laquelle l'application PowerApps s'exécute. Les boîtes de dialogue sont conçues comme « petites » ou « grandes » afin d'optimiser l'interface utilisateur lorsque votre application s'exécute sur un téléphone ou un appareil plus grand, respectivement. 

Vous pouvez également spécifier les entités juridiques pour lesquelles une application est disponible, ou vous pouvez la rendre accessible à toutes vos entités juridiques. Par défaut, vos applications PowerApps sont accessibles à toutes les entités juridiques.

## <a name="opening-an-application"></a>Ouverture d'une application
Lorsque vous avez configuré les applications PowerApps incorporées, les liens vers les applications que vous avez spécifiées sont ajoutés aux pages dans Talent. Cliquez sur un lien pour ouvrir une application. 



