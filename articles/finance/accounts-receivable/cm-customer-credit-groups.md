---
title: Groupes de créditer du client
description: Cette rubrique fournit des informations sur les groupes de crédits client.
author: mikefalkner
manager: AnnBe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 90d75493b928bfa4edafeef7730bc272c9146192
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261255"
---
# <a name="customer-credit-groups"></a>Groupes de créditer du client

[!include [banner](../includes/banner.md)]

Vous pouvez définir des groupes de clients qui ont une limite de crédit partagée. La limite de crédit individuelle définie sur le compte de facture client est également prise en compte.

Les membres d'un groupe de crédits client peuvent être sélectionnés parmi différentes entités juridiques. Lorsque vous ajoutez un client à la liste des clients du groupe de crédits client, la date d'expiration de la limite de crédit pour chaque client est remplacée par la date d'expiration affectée au groupe.

Vous pouvez configurer des groupes de crédits client sur la page **Groupes de crédit client** (**Gestion de crédit \> Groupes de crédits client \> Groupes de crédits client**).

1. Dans les champs **Numéro du groupe** et **Description**, entrez un identificateur et une description pour le groupe.
2. Dans les champs **Limite de crédit** et **Devise**, entrez la limite de crédit et la devise à utiliser lorsque le système vérifie la limite de crédit pour tout membre du groupe.
3. Dans le champ **Limite de crédit à ce jour**, entrez la date d'expiration de la limite de crédit. Les groupes de crédit client doivent avoir une date d'expiration.

Une fois la configuration d'un groupe de crédits client terminée, vous pouvez y ajouter des clients en spécifiant leur entité juridique et leur ID de compte client. Lorsque vous ajoutez un nouveau client à un groupe de crédits client, le système recherche le même compte client dans toutes les entités juridiques et vous invite à l'ajouter au groupe de crédits client.

Utilisez le menu **Soldes échus** pour afficher les détails de balance âgée pour tous les clients facturés dans un groupe de crédits client. La page **Balance âgée** affiche un récapitulatif des soldes échus pour les comptes clients de facturation.
