---
title: Fichiers reçus Invoice capture
description: Cet article explique comment collecter des fichiers de factures à partir de différentes sources dans Invoice capture.
author: sunfzam
ms.date: 10/13/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3c55540d11a67d4d4c4c8477d51cb6f1f5777767
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690135"
---
# <a name="invoice-capture-received-files"></a>Fichiers reçus Invoice capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Dans Invoice capture, la page **Fichiers reçus** est un endroit central où les fichiers de factures sont reçus de différentes sources.

## <a name="upload-invoice-files"></a>Télécharger les fichiers de facturation

Les assistants comptabilité fournisseur peuvent télécharger les images de facture en sélectionnant **Télécharger un fichier** pour ouvrir la boîte de dialogue **Télécharger**. Après qu’un assistant comptabilité fournisseur sélectionne un fichier, le bouton **Télécharger** devient disponible.

## <a name="include-or-obsolete-invoice-files"></a>Inclure ou abandonner des fichiers de factures

Les utilisateurs peuvent sélectionner les factures avec des erreurs ou des avertissements, puis incluent ou abandonnent les factures en sélectionnant le bouton correspondant sur le volet Actions. Une facture marquée comme abandonnée n’apparaît pas dans la vue **Fichiers reçus (obsolètes)**.

## <a name="view-captured-invoices"></a>Afficher les factures capturées

Une fois qu’un fichier reçu a été reconnu avec succès, les informations de la facture capturée sont renvoyées par le modèle d’IA et saisies dans Microsoft Dataverse. L’assistant comptabilité fournisseur peut vérifier les détails de facture en sélectionnant **Afficher la facture capturée**. Les utilisateurs peuvent télécharger le fichier de facture original au besoin.
