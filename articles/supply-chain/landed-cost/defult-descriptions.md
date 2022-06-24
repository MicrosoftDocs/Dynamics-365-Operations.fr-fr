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
ms.openlocfilehash: 7020c39dd599be047e07caa391d6d4c69c426328
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889546"
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
