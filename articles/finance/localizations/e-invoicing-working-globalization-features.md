---
title: Composants de fonctionnalité de globalisation
description: Cet article fournit une vue d’ensemble des composants de fonctionnalité de globalisation.
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 94e2d118c332a15f41f33184f5e44b0fdaccd000
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275224"
---
# <a name="globalization-feature-components"></a>Composants de fonctionnalité de globalisation

[!include [banner](../includes/banner.md)]

Une fonctionnalité de globalisation désigne un ensemble de composants qui définissent les règles de transformation des données dans les configurations de gestion des états électroniques. Ces composants comprennent des instructions pour traiter les documents électroniques, puis les envoyer ou les recevoir à partir de canaux externes. Ils incluent également des conditions qui définissent quand une fonctionnalité doit être exécutée pour les données métier entrantes.

Tous les composants dépendent les uns des autres. Les fonctionnalités de globalisation facilitent la création et la maintenance de cette dépendance, ainsi que la prise en charge de la gestion du cycle de vie et de la gestion des versions de l’ensemble de composants.

## <a name="access-electronic-invoicing-feature-components"></a>Accéder aux composants de fonctionnalité de facturation électronique 

1. Connectez-vous à votre compte RCS (Regulatory Configuration Service).
2. Dans l’espace de travail **Fonctionnalité de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.

    Les fonctionnalités de globalisation comportent plusieurs composants. La page **Fonctionnalités de facturation électronique** comprend un onglet distinct pour chaque composant.

    - **Version** – Ce composant prend en charge la gestion du cycle de vie de la fonctionnalité. Vous pouvez l’utiliser pour gérer le statut de différentes versions de la fonctionnalité.
    - **Configurations** – Ce composant vous permet de gérer, d’afficher et de modifier les configurations de gestion des états électroniques et de mappage de format associées qui sont utilisées dans le pipeline de traitement.
    - **Paramétrages** – Ce composant permet aux utilisateurs des services de globalisation, tels qu’un service de facturation électronique, de gérer les paramètres de la version de fonctionnalité associée. Par conséquent, il permet une construction flexible des règles de communication et de réaction.
    - **Environnements** – Ce composant permet aux utilisateurs des services de globalisation, tels qu’un service de facturation électronique, de gérer l’environnement dans lequel le paramétrage de la version de la fonctionnalité est utilisé et d’accorder une autorisation aux utilisateurs qui y auront accès. Il leur permet également d’accorder une autorisation aux utilisateurs qui auront accès à la configuration de la version de la fonctionnalité.
    - **Organisations** – Ce composant permet aux utilisateurs de partager la fonctionnalité avec des organisations externes.
    - **Mots clés** – Ce composant vous permet de baliser les fonctionnalités qui peuvent être utilisées dans le plan de globalisation pour la référence.
