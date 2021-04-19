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
# <a name="nf-e-custom-certificate-validation"></a><span data-ttu-id="84e37-103">Validation du certificat personnalisé NF-e</span><span class="sxs-lookup"><span data-stu-id="84e37-103">NF-e custom certificate validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84e37-104">Lorsque vous activez la fonction de vérification du certificat personnalisé NF-e, la validation personnalisée autorise une connexion aux services Web.</span><span class="sxs-lookup"><span data-stu-id="84e37-104">When you turn the NF-e custom certificate verification feature, custom validation allows a connection with the web services.</span></span> <span data-ttu-id="84e37-105">Cette connexion est nécessaire pour transmettre le certificat NF-e et recevoir l’autorisation de SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="84e37-105">This connection is required to transmit NF-e and receive authorization from SEFAZ.</span></span>

<span data-ttu-id="84e37-106">La propriété **Objectif de l’authentification du serveur** du certificat V5 est émise par l’autorité de certification racine brésilienne.</span><span class="sxs-lookup"><span data-stu-id="84e37-106">The **Server authentication purpose** property from the certificate V5 is issued by the Brazilian Root Certificate Authority.</span></span> <span data-ttu-id="84e37-107">Cette propriété est désactivée par défaut et doit être activée manuellement.</span><span class="sxs-lookup"><span data-stu-id="84e37-107">This property is turned off by default and must be manually enabled.</span></span> <span data-ttu-id="84e37-108">Dans certaines circonstances, la mise à jour automatique du certificat peut faire en sorte que cette propriété ne soit plus activée.</span><span class="sxs-lookup"><span data-stu-id="84e37-108">In some circumstances, the automatic certificate update can switch this property to no longer be enabled.</span></span> <span data-ttu-id="84e37-109">Si cela se produit, la connexion TLS est affectée et n’est plus fiable.</span><span class="sxs-lookup"><span data-stu-id="84e37-109">If this happens, the TLS connection is affected and is no longer trusted.</span></span> <span data-ttu-id="84e37-110">La capacité d’émettre NF-e sur les environnements de production pour les États du Minas Gerais (MG) et du Paraná (PR) est également affectée.</span><span class="sxs-lookup"><span data-stu-id="84e37-110">The ability to issue NF-e on production environments for states of Minas Gerais (MG) and Paraná (PR) states is also impacted.</span></span>

<span data-ttu-id="84e37-111">Cette mise à jour permet une solution alternative pour la validation des certificats, ce qui signifie qu’il est possible d’établir une communication sécurisée.</span><span class="sxs-lookup"><span data-stu-id="84e37-111">This update allows for an alternative solution for certificate validation, which means that it’s possible to establish a secure communication.</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]