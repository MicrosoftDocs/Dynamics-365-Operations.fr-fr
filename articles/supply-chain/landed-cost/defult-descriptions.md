---
title: Descriptions par défaut pour la comptabilité générale
description: Les descriptions par défaut peuvent être utilisées pour mettre à jour le champ Description dans les écritures de pièce justificative dans le grand livre.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f95dff3a77a552d5788d813b3d13dc30579be715
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695705"
---
# <a name="default-descriptions-for-the-general-ledger"></a>Descriptions par défaut pour la comptabilité générale

[!include [banner](../../includes/banner.md)]

Les descriptions par défaut peuvent être utilisées pour mettre à jour le champ **Description** dans les écritures de pièce justificative dans le grand livre. Cette fonctionnalité a été améliorée pour fonctionner avec le coût au débarquement.

Pour configurer les descriptions par défaut des écritures comptables, accédez à **Administration organisationnelle \> Installer \> Descriptions par défaut**.

Le tableau suivant répertorie les nouvelles valeurs qui ont été ajoutées pour le champ **Description** sur la page **Descriptions par défaut** pour prendre en charge le coût au débarquement.

| Type de description | Notes |
|---|---|
| Importation des coûts – Comptabilisation des coûts | Lorsqu’une facture de commande fournisseur est validée, une provision pour coûts est traitée pour l’estimation des coûts de voyage. Des descriptions par défaut peuvent être spécifiées pour ajouter le numéro de voyage à la description. Utilisez *%4* comme numéro d’expédition. |
| Évaluation des coûts d’importation – Ordre des marchandises en transit | Si vous utilisez le traitement en transit, la facture de la commande fournisseur est enregistrée et les marchandises sont enregistrées sur un compte de marchandises en transit. Des descriptions par défaut peuvent être spécifiées pour ajouter le numéro de commande en transit à la description. Utilisez *%4* pour le numéro de commande en transit. |
| Stock – Clôture – Ajustement | Lorsque la facture des comptes fournisseurs (CF) est traitée pour un coût de voyage, un ajustement d’inventaire est traité pour estimer les coûts de voyage. Des descriptions par défaut peuvent être spécifiées pour ajouter le numéro de voyage à la description. Utilisez *%4* comme numéro d’expédition. |

Pour plus d’informations sur l’utilisation de la page **Descriptions par défaut**, voir [Configurer des descriptions par défaut pour la publication automatique](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).
