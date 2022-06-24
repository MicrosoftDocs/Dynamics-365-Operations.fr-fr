---
title: Limite de seuil et limite de seuil d’exception
description: Cet article décrit le seuil et les limites d’exception pour la taxe déduite à la source (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: aceebad08b5454b64059e7ef374b9634bad35c37
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877934"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a>Limite de seuil et limite de seuil d’exception

[!include [banner](../includes/banner.md)]

Cet article décrit le seuil et les limites d’exception pour la taxe déduite à la source (TDS). Le TDS sur les factures et les paiements est toujours calculé en tenant compte de la limite de seuil et de la limite de seuil d’exception définis pour les composants de la taxe TDS dans la page **Composants de retenue à la source**. Les composants de taxe TDS sont associés aux codes de taxe TDS, qui sont inclus dans les groupes de taxe TDS. Les groupes de taxes TDS sont associés aux fournisseurs et aux clients pour calculer TDS au niveau de la facture ou du paiement.

TDS est calculé si le montant d’une transaction ou les transactions cumulées validées avec un groupe TDS spécifique pour un fournisseur dépasse la limite de seuil spécifiée sur la page **Composants de retenue à la source**. Le TDS ne sera pas calculé tant que le montant cumulé de la transaction ne dépassera pas la limite de seuil spécifiée.

Si une limite de seuil d’exception est spécifiée avec la limite de seuil pour un composant TDS, TDS est calculé lorsqu’un montant de transaction spécifique dépasse la limite de seuil d’exception, même si le montant de transaction cumulé ne dépasse pas la limite de seuil spécifiée.

### <a name="example"></a>Exemple
Un composant de taxe appelé TDS est configuré et attaché au groupe de taxe TDS appelé entrepreneur. Le seuil a été défini à 50 000 et le seuil d’exception à 20 000 pour la composant fiscale TDS. L’entrepreneur du groupe TDS est défini comme le groupe TDS par défaut pour le fournisseur 1.

Une facture d’achat 001 est validée pour le fournisseur 1 pour 10000. TDS n’est pas calculé pour la facture car le montant de la facture n’a pas dépassé la limite de seuil ou la limite de seuil d’exception. Une facture d’achat 002 est validée pour le fournisseur 1 pour 25 000. TDS n’est pas calculé pour la facture car le montant de la facture n’a pas dépassé la limite de seuil d’exception. Une facture d’achat 003 est validée pour le fournisseur 1 pour 20 000. TDS est calculé pour la facture car le montant total de la facture des trois factures émises pour le fournisseur a dépassé le seuil. Le TDS est calculé sur toutes les factures émises pour le fournisseur sur lesquelles le TDS n’a pas été calculé auparavant. Par conséquent, TDS est calculé sur 30 000, soit le montant total de la facture des factures 001 et 003.

La limite de seuil et la limite de seuil d’exception ne sont pas prises en compte pour le calcul TDS si la case **Seuil de surplomb** est cochée pour les codes de taxe TDS dans le groupe TDS associé à la transaction. La limite de seuil ne sera pas utilisée dans les codes de taxe TDS du groupe TDS dont la case à cocher **Seuil de surplomb** correspondant.

Si la case **Seuil de surplomb** est cochée pour un groupe TDS spécifique pour certaines factures, mais non sélectionnée pour d’autres factures qui ont été créées pour un fournisseur/client spécifique, le calcul de TDS sans oublier le seuil limite pour quelques factures peut avoir lieu compte tenu du montant cumulé sur tous factures sur lesquelles TDS n’a pas été calculé auparavant.

Par exemple, la limite de seuil est de 25 000. Les factures suivantes sont créées pour le fournisseur A.

- Facture 1 - 2 0000 - (la case **Seuil de surplomb** n’est pas cochée) : TDS n’est pas calculé.

- Facture 2 - 4 000 - (la case **Seuil de surplomb** n’est pas cochée) : TDS n’est pas calculé sur la base de 4 000.

- Facture 2 - 3 000 - (la case **Seuil de surplomb** n’est pas cochée) : TDS est calculé comme le montant de la facture cumulée, c’est-à-dire 27 000 (20 000 + 4000 + 3000) a dépassé la limite de seuil. TDS est calculé sur le montant cumulé des factures sur lesquelles le TDS n’a pas été calculé auparavant, c’est-à-dire 23 000 (20 000 + 3 000).
