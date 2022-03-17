---
title: Configurer les environnements de service et les applications connectées
description: Cette rubrique fournit des informations sur la configuration de vos environnements de service et des applications connectées.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c3366e75b4a6d3f33a1aac9e444236d9ae57c829
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371611"
---
# <a name="configure-service-environments-and-connected-applications"></a>Configurer les environnements de service et les applications connectées

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur la configuration de vos environnements de service et des applications connectées. Il y a trois étapes à ce processus. L’étape 1 est obligatoire et les étapes 2 et 3 sont facultatives.

## <a name="step-1-create-a-service-environment"></a>Étape 1 : Créer un environnement de service

Lorsque vous créez votre environnement de service, définissez la liste des utilisateurs qui peuvent y déployer les fonctionnalités de globalisation. Facultativement, pour certains scénarios, définissez la liste des applications externes pouvant communiquer avec le service de facturation électronique. Configurez des séquences de nombres si vous comptez les utiliser dans vos scénarios.

Pour terminer cette étape, voir la rubrique [Environnements de services](e-invoicing-service-environments.md).

## <a name="step-2-add-certificates-and-secrets"></a>Étape 2 : Ajouter des certificats et clés secrètes

Ajouter une référence au coffre de clés et clés secrètes Microsoft Azure pour les utiliser dans vos scénarios. Cette étape est obligatoire si les actions dans les pipelines de traitement utilisent des certificats et des clés secrètes pour la signature numérique ou la communication avec des services Web externes.

Pour terminer cette étape, voir la rubrique [Certificats et clés secrètes client](e-invoicing-customer-certificates-secrets.md).

## <a name="step-3-configure-connected-applications"></a>Étape 3 : Configurer les applications connectées

Pour établir la communication entre les applications Dynamics 365 Finance ou Dynamics 365 Supply Chain Management et le service Facturation électronique, vous devez configurer Finance ou Supply Chain Management pour générer l’appel au service Facturation électronique et préparer les données commerciales dans une structure unifiée pouvant être transformée au format électronique requis. Les applications doivent également traiter correctement les réponses du service. Vous pouvez compléter cette configuration directement dans votre environnement Finance ou Supply Chain Management, ou vous pouvez la compléter dans Regulatory Configuration Service (RCS). Si vous terminez la configuration dans RCS, vous pouvez ensuite la déployer dans votre environnement Finance ou Supply Chain Management. Dans cette étape, vous enregistrerez l’application connectée pour le déploiement des paramètres.

Pour terminer cette étape, voir la rubrique [Applications connectées](e-invoicing-connected-applications.md).
