---
title: Descriptions par défaut pour la comptabilité générale
description: Les descriptions par défaut peuvent être utilisées pour mettre à jour le champ Description dans les écritures de pièce justificative dans le grand livre.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 25dd72c86b22b50eccef22a5d2cbcfcf04280684
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021610"
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
