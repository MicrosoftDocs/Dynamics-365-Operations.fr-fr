---
title: Configuration de la facturation électronique
description: Cet article fournit une vue d’ensemble du processus de configuration de la facturation électronique.
author: gionoder
ms.date: 02/28/2022
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
ms.openlocfilehash: de94843c1e98a8788375bd41def587a64baea07d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272177"
---
# <a name="electronic-invoicing-setup"></a>Configuration de la facturation électronique

[!include [banner](../includes/banner.md)]

L’article fournit une vue d’ensemble du processus de configuration de la facturation électronique. Vous devez effectuer les étapes de configuration dans l’ordre spécifié ici. Si une étape est obligatoire, mais que vous l’ignorez, la fonctionnalité ne fonctionnera pas correctement et plusieurs échecs se produiront au moment des étapes suivantes ou quand vous utiliserez la fonctionnalité. 

Avant de commencer, assurez-vous que tous les composants principaux sont correctement configurés, que vous vous êtes inscrit à Regulatory Configuration Service (RCS) et que vous disposez d’une instance de RCS, et que le complément de facturation électronique est installé pour votre environnement Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management. Pour plus d’informations, voir [Se connecter et installer la facturation électronique](e-invoicing-install-add-in-microservices-lcs.md).

Ensuite, configurez les ressources Azure dont la facturation électronique a besoin pour faire son travail. Pour en savoir plus, voir [Configurer les ressources Azure pour la facturation électronique](e-invoicing-set-up-azure-resources.md).

Une fois les principaux composants configurés, utilisez RCS pour configurer les principaux composants logiques de la facturation électronique. Tout d’abord, définissez le nombre d’environnements de service que vous allez gérer. De cette façon, vous définissez les données logiques et le partitionnement de la configuration pour vous assurer d’avoir une frontière entre un environnement de développement ou de test et les environnements de production. Pour configurer votre processus de développement de manière flexible, vous pouvez avoir besoin de plusieurs environnements de développement et de test distincts. En plus de définir des environnements de service, établissez un lien vers vos applications métiers, telles que Finance ou Supply Chain Management, directement depuis RCS pour configurer les paramètres nécessaires au bon fonctionnement avec la facturation électronique. Pour plus d’informations sur les environnements, voir [Environnements de service](e-invoicing-service-environments.md).

Une fois que tout est configuré, vous pouvez créer vos propres fonctionnalités de globalisation qui définissent différents scénarios pour le traitement des documents électroniques et la transformation des données, ou pour l’importation des documents depuis le référentiel global. Pour plus d’informations sur l’utilisation des fonctionnalités de globalisation, voir [Utiliser les fonctionnalités de globalisation](e-invoicing-working-globalization-features.md).

Si vos scénarios nécessitent une intégration avec le courrier électronique ou SharePoint pour traiter les documents électroniques entrants, voir [Traitement des documents électroniques entrants](e-invoicing-process-incoming-electronic-documents.md) pour plus d’informations sur la configuration et l’utilisation de ces canaux.
