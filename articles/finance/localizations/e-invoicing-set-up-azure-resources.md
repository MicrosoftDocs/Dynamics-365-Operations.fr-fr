---
title: Paramétrer les ressources Azure pour la facturation électronique
description: Cet article fournit une vue d’ensemble du processus de configuration des ressources Microsoft Azure pour la facturation électronique.
author: dkalyuzh
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: c5b7b2ca4d7733fb1c75ded8798655699284fe1a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907727"
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
