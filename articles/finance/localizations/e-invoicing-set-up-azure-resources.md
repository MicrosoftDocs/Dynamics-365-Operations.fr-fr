---
title: Paramétrer les ressources Azure pour la facturation électronique
description: Cet article fournit une vue d’ensemble du processus de configuration des ressources Microsoft Azure pour la facturation électronique.
author: gionoder
ms.date: 01/26/2022
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
ms.openlocfilehash: f11e4eac831d54a6cac765a5adc4e4ffddbe0a22
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283083"
---
# <a name="set-up-azure-resources-for-electronic-invoicing"></a>Paramétrer les ressources Azure pour la facturation électronique

[!include [banner](../includes/banner.md)]

Le processus de configuration des ressources Microsoft Azure pour la facturation électronique comporte trois étapes. Les deux premières étapes, « Créer un coffre de clés Azure dans le portail Azure » et « Créer un compte de stockage Azure dans le portail Azure », sont obligatoires. La troisième étape, « Configurer une connexion SharePoint », est facultative.

## <a name="create-an-azure-key-vault-in-the-azure-portal"></a>Créer un coffre de clés Azure dans le portail Azure

Créez un coffre de clés dans votre abonnement Azure. Nous vous recommandons de créer un coffre de clés distinct pour la facturation électronique et de ne pas combiner les clés secrètes avec d’autres applications. Créez autant de clés secrètes et de certificats que nécessaire pour vos scénarios dans des documents électroniques. Vous devez créer au moins une clé secrète pour stocker le jeton de signature d’accès partagé (SAS) du compte de stockage Azure que vous allez créer à l’étape suivante.

Pour plus d’informations sur la façon d’effectuer cette étape, voir [Créer un coffre de clés Azure dans le portail Azure](e-invoicing-create-azure-key-vault-azure-portal.md).

## <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Créer un compte de stockage Azure dans le portail Azure

Vous êtes propriétaire de tous les documents et fichiers électroniques générés par le service de facturation électronique ou entrez dans le service. Ces documents et fichiers sont stockés dans un compte de stockage Azure que vous créez dans votre abonnement Azure. Le service accédera à votre compte de stockage à l’aide du jeton SAS extrait de votre clé secrète Key Vault.

Pour plus d’informations sur la façon d’effectuer cette étape, voir [Créer un compte de stockage Azure dans le portail Azure](e-invoicing-create-azure-storage-account-azure-portal.md).

## <a name="configure-a-sharepoint-connection"></a>Configurer une connexion SharePoint

Dans certains cas, vous devrez peut-être enregistrer des fichiers électroniques sur SharePoint et les récupérer depuis SharePoint. Afin que le service Facturation électronique puisse accéder à vos dossiers SharePoint, configurez l’accès à SharePoint.

Pour plus d’informations sur la façon d’effectuer cette étape, voir [Configurer une connexion SharePoint](e-invoicing-create-sharepoint-connection.md).
