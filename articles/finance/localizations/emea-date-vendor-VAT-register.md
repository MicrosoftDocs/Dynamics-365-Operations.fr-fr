---
title: Date du registre de TVA
description: Cette rubrique fournit des informations sur une fonctionnalité permettant d’activer la date du registre de TVA du fournisseur
author: anasyash
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: global
ms.author: anasyash
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 882d5a8718d819cff80bfa5b86e054a39e9db159
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7992061"
---
# <a name="date-of-vendor-vat-register"></a>Date du registre de TVA

Dans Microsoft Dynamics 365 Finance version 10.0.24, un nouveau champ **Date du registre de TVA du fournisseur** est disponible pour les factures fournisseur. Ce champ précise la date de la fourniture taxable d’un achat.

Pour activer le nouveau champ, accédez à l’espace de travail **Gestion des fonctionnalités**, recherchez et sélectionnez la fonction **Activer la date du registre de TVA du fournisseur sur les factures fournisseur**, puis sélectionnez **Activer maintenant**.

Les factures entrantes de vos fournisseurs peuvent avoir deux dates : la date à laquelle le fournisseur a émis la facture et la date de la fourniture taxable (c’est-à-dire la date à laquelle le fournisseur a facturé la taxe sur la valeur ajoutée [TVA] à payer). Dans certains scénarios, ces deux dates peuvent différer.

Vous pouvez déduire le montant de la TVA entrante pour une facture d’achat et inclure cette facture dans les déclarations de TVA ultérieurement, à une date différente des deux dates mentionnées précédemment. Cette date est contrôlée par la législation locale concernant le report de la déduction de la TVA entrante pour certains scénarios. Elle varie selon les pays et les régions.

Certaines déclarations de TVA, tels que la [Déclaration de contrôle de la TVA](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement) en République tchèque, exigent que la date de la livraison taxable soit indiquée sur un document d’achat. Cette date doit être déclarée afin que l’administration fiscale puisse rapprocher les déclarations de TVA entre les contreparties.

Dans Finance, vous pouvez définir des dates dans les champs suivants :

- **Date de facturation** – La date d’émission de la facture par le fournisseur.
- **Date du registre de TVA** – La date de la déduction du montant de la TVA pour la facture d’achat.
- **Date du registre de TVA du fournisseur** – La date de la fourniture taxable du fournisseur.
- **Date de réception du document** – La date à laquelle vous avez reçu la facture.

Ces champs sont inclus dans les pages suivantes :

- Facture fournisseur
- Registre des factures fournisseur
- Approbation de la facture fournisseur
- Journal des factures fournisseur

Une fois la facture fournisseur validée, vous pouvez consulter les dates sur les pages **Journal des factures** et **Transactions fournisseur**.
