---
title: Validation du certificat personnalisé NF-e
description: Cette rubrique fournit des informations sur l’activation et l’utilisation du certificat personnalisé NF-e.
author: gionoder
ms.date: 10/06/2020
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
ms.openlocfilehash: 895513f51798a797ebf59f8a5be4f5cde006726d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813966"
---
# <a name="nf-e-custom-certificate-validation"></a>Validation du certificat personnalisé NF-e

[!include [banner](../includes/banner.md)]

Lorsque vous activez la fonction de vérification du certificat personnalisé NF-e, la validation personnalisée autorise une connexion aux services Web. Cette connexion est nécessaire pour transmettre le certificat NF-e et recevoir l’autorisation de SEFAZ.

La propriété **Objectif de l’authentification du serveur** du certificat V5 est émise par l’autorité de certification racine brésilienne. Cette propriété est désactivée par défaut et doit être activée manuellement. Dans certaines circonstances, la mise à jour automatique du certificat peut faire en sorte que cette propriété ne soit plus activée. Si cela se produit, la connexion TLS est affectée et n’est plus fiable. La capacité d’émettre NF-e sur les environnements de production pour les États du Minas Gerais (MG) et du Paraná (PR) est également affectée.

Cette mise à jour permet une solution alternative pour la validation des certificats, ce qui signifie qu’il est possible d’établir une communication sécurisée.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]