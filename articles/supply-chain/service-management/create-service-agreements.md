---
title: Création d’accords de service
description: Cet article décrit l’utilisation des fonctionnalités des modules de comptabilité Gestion des services et Gestion de projets pour la création d’accords de service.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d18d279cd437e98cad6495def953978cb78e723e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901761"
---
# <a name="create-service-agreements"></a>Création d’accords de service

[!include [banner](../includes/banner.md)]

Cet article décrit l’utilisation des fonctionnalités des modules de comptabilité Gestion des services et Gestion de projets pour la création d’accords de service.

## <a name="create-a-service-agreement-from-service-management"></a>Création d’un accord de service à partir du module Gestion des services

1. Accédez à **Gestion des services**.
2. Sélectionnez **Accords de service** pour créer une ligne d’accord de service dans l’en-tête de la page. 
3. Sélectionnez **Nouveau**. Entrez une description, sélectionnez une référence à un projet dans le champ **ID Projet**, puis remplissez les champs et les lignes restants de l’accord de service. Sélectionnez **Enregistrer**.
4. Sous l’onglet **Relations**, sélectionnez **Objets du service** ou **Tâches de service** pour créer des relations d’objets de service ou des relations de tâches de service pour l’accord de service. Les objets et tâches de service pour lesquels vous avez créé des relations peuvent être associés aux lignes de l’accord de service.
5. Dans la partie inférieure de la page, créez des lignes d’accord de service en copiant les lignes d’un modèle de service ou d’un autre accord de service ou en les créant manuellement.

> [!NOTE]
> Si vous copiez les lignes d’un autre accord de service, vous pouvez indiquer si vous souhaitez également copier les relations d’objets ou de tâches de service. Si vous copiez ces relations, elles sont ajoutées aux relations existantes de l’accord de service. Si vous copiez les lignes d’accord de service d’un modèle de service, les relations d’objets et de tâches de service sont automatiquement copiées comme telles dans les nouvelles lignes d’accord de service.

## <a name="create-service-agreement-lines-manually"></a>Création manuelle des lignes d’accord de service

1. Dans la page **Accords de service**, ajoutez une ligne d’accord de service dans la grille de lignes. 
2. Entrez les informations appropriées pour la ligne d’accord de service. 
3. Sélectionnez **CTRL+S** pour enregistrer la ligne, puis fermez la page.

## <a name="create-a-service-agreement-from-project"></a>Création d’un accord de service à partir du module Projet

1. Sélectionnez **Gestion et comptabilité des projets**.
2. Sélectionnez **Tous les projets**.
3. Sélectionnez le projet dans la liste.
4. Dans le volet **Actions**, sélectionnez **Gérer**. Dans le groupe d’actions **Nouveau**, sélectionnez **Service** et **Accord de service**.
5. Suivez les étapes de la section intitulée **Création d’un accord de service** comme décrit précédemment dans cet article pour accéder à la référence du projet.


## <a name="related-articles"></a>Articles connexes

[Vue d’ensemble de développement et d’établissement d’accords de service](service-agreements.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]