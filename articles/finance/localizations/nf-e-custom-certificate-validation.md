---
title: Validation du certificat personnalisé NF-e
description: Cette rubrique fournit des informations sur l’activation et l’utilisation du certificat personnalisé NF-e.
author: gionoder
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 26ffed1f49d9087ca767aab1b8cac41b099f73cb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443106"
---
# <a name="nf-e-custom-certificate-validation"></a>Validation du certificat personnalisé NF-e

[!include [banner](../includes/banner.md)]

Lorsque vous activez la fonction de vérification du certificat personnalisé NF-e, la validation personnalisée autorise une connexion aux services Web. Cette connexion est nécessaire pour transmettre le certificat NF-e et recevoir l’autorisation de SEFAZ.

La propriété **Objectif de l’authentification du serveur** du certificat V5 est émise par l’autorité de certification racine brésilienne. Cette propriété est désactivée par défaut et doit être activée manuellement. Dans certaines circonstances, la mise à jour automatique du certificat peut faire en sorte que cette propriété ne soit plus activée. Si cela se produit, la connexion TLS est affectée et n’est plus fiable. La capacité d’émettre NF-e sur les environnements de production pour les États du Minas Gerais (MG) et du Paraná (PR) est également affectée.

Cette mise à jour permet une solution alternative pour la validation des certificats, ce qui signifie qu’il est possible d’établir une communication sécurisée.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]