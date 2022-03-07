---
title: Validation du certificat personnalisé NF-e
description: Cette rubrique fournit des informations sur l’activation et l’utilisation du certificat personnalisé NF-e.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8144e16b127bdbe954ef44f52c5ac71689a2036e6085e9a4ccc8bb17f91ae9b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755589"
---
# <a name="nf-e-custom-certificate-validation"></a>Validation de certificat personnalisé NF-e

[!include [banner](../includes/banner.md)]

La propriété **Objectif de l’authentification du serveur** des certificats émis par l’autorité de certification racine brésilienne est désactivée par défaut et doit être activée manuellement. Dans certaines circonstances, la mise à jour automatique du certificat peut faire en sorte que cette propriété ne soit plus activée. Si cela se produit, la connexion TLS est affectée et n’est plus fiable. La capacité d’émettre le modèle 55 de document fiscal électronique brésilien (NF-e) sur les environnements de production pour les États du Minas Gerais (MG) et du Paraná (PR) est affectée.

Pour activer le correctif pour **Validation de certificat personnalisé NF-e**, accédez à **Gestion des fonctionnalités**. Cette fonctionnalité fournit une solution alternative pour les validations de certificats V5 et V10 et permet une connexion sécurisée avec les services web, ce qui est nécessaire pour la transmission sécurisée du certificat NF-e et la réception de l’autorisation de SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
