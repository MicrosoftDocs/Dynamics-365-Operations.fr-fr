---
title: Configuration de la facturation électronique
description: Cette rubrique fournit une vue d’ensemble du processus de configuration de la facturation électronique.
author: dkalyuzh
ms.date: 02/28/2022
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
ms.openlocfilehash: 8138c63e9eff1d2ca934f9d4467e4e3b73dae941
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371647"
---
# <a name="electronic-invoicing-setup"></a>Configuration de la facturation électronique

[!include [banner](../includes/banner.md)]

La rubrique fournit une vue d’ensemble du processus de configuration de la facturation électronique. Vous devez effectuer les étapes de configuration dans l’ordre spécifié ici. Si une étape est obligatoire, mais que vous l’ignorez, la fonctionnalité ne fonctionnera pas correctement et plusieurs échecs se produiront lors des étapes suivantes ou lorsque vous utiliserez la fonctionnalité. 

Avant de commencer, assurez-vous que tous les composants principaux sont correctement configurés, que vous vous êtes inscrit à Regulatory Configuration Service (RCS) et que vous disposez d’une instance de RCS, et que le complément de facturation électronique est installé pour votre environnement Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management. Pour plus d’informations, voir [Se connecter et installer la facturation électronique](e-invoicing-install-add-in-microservices-lcs.md).

Ensuite, configurez les ressources Azure dont la facturation électronique a besoin pour faire son travail. Pour en savoir plus, voir [Configurer les ressources Azure pour la facturation électronique](e-invoicing-set-up-azure-resources.md).

Une fois les principaux composants configurés, utilisez RCS pour configurer les principaux composants logiques de la facturation électronique. Tout d’abord, définissez le nombre d’environnements de service que vous allez gérer. De cette façon, vous définissez les données logiques et le partitionnement de la configuration pour vous assurer d’avoir une frontière entre un environnement de développement ou de test et les environnements de production. Pour configurer votre processus de développement de manière flexible, vous pouvez avoir besoin de plusieurs environnements de développement et de test distincts. En plus de définir des environnements de service, établissez un lien vers vos applications métiers, telles que Finance ou Supply Chain Management, directement depuis RCS pour configurer les paramètres nécessaires au bon fonctionnement avec la facturation électronique. Pour plus d’informations sur les environnements, voir [Environnements de service](e-invoicing-service-environments.md).

Une fois que tout est configuré, vous pouvez créer vos propres fonctionnalités de globalisation qui définissent différents scénarios pour le traitement des documents électroniques et la transformation des données, ou pour l’importation des documents depuis le référentiel global. Pour plus d’informations sur l’utilisation des fonctionnalités de globalisation, voir [Utiliser les fonctionnalités de globalisation](e-invoicing-working-globalization-features.md).

Pour plus d’informations sur les actions dans les pipelines de traitement qui composent le processus que vous allez créer dans les fonctionnalités de globalisation, consultez **[TERMINÉ ! : Actions de traitement de documents]**.

Si vos scénarios nécessitent une intégration avec le courrier électronique ou SharePoint pour traiter les documents électroniques entrants, voir [Traitement des documents électroniques entrants](e-invoicing-process-incoming-electronic-documents.md) pour plus d’informations sur la configuration et l’utilisation de ces canaux.
