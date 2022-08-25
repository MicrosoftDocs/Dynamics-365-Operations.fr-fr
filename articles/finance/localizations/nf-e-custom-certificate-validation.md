---
title: Validation de certificat personnalisé NF-e
description: Cet article fournit des informations sur l’activation et l’utilisation du certificat personnalisé NF-e.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: f78fdbd133aecaf9dbf8abe0006abd6deb1b1b15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288542"
---
# <a name="nf-e-custom-certificate-validation"></a>Validation de certificat personnalisé NF-e

[!include [banner](../includes/banner.md)]

La propriété **Objectif de l’authentification du serveur** des certificats émis par l’autorité de certification racine brésilienne est désactivée par défaut et doit être activée manuellement. Dans certaines circonstances, la mise à jour automatique du certificat peut faire en sorte que cette propriété ne soit plus activée. Si cela se produit, la connexion TLS est affectée et n’est plus fiable. La capacité d’émettre le modèle 55 de document fiscal électronique brésilien (NF-e) sur les environnements de production pour les États du Minas Gerais (MG) et du Paraná (PR) est affectée.

Pour activer le correctif pour **Validation de certificat personnalisé NF-e**, accédez à **Gestion des fonctionnalités**. Cette fonctionnalité fournit une solution alternative pour les validations de certificats V5 et V10 et permet une connexion sécurisée avec les services web, ce qui est nécessaire pour la transmission sécurisée du NF-e et la réception de l’autorisation de SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
