---
title: Contrepasser la validation du journal
description: Cette rubrique décrit les fonctionnalités qui vous permettent de contrepasser les documents provenant de la liste de transaction de documents ou provenant des journaux financiers.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248583"
---
# <a name="reverse-journal-posting"></a>Contrepasser la validation du journal

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctionnalités Microsoft Dynamics 365 Finance qui vous permettent de contrepasser un journal entier ou de contrepasser un ou plusieurs documents provenant de la liste de transactions de documents, peu importe leur origine. 

## <a name="reversing-journals"></a>Contrepassation des journaux

Vous pouvez contrepasser des lignes de journal individuellement. Avec la contrepassation de la validation du journal, vous pouvez également contrepasser tout un journal financier. Pour contrepasser un journal : 
- Ouvrez le journal financier et filtrez selon les journaux validés.
- Cliquez sur le menu Contrepasser en haut de la page.
- Vous verrez le nombre total de documents et les lignes de documents ainsi que le volume total des lignes contrepassées.
- Sélectionnez Oui pour utiliser les dates de transaction existantes ou Non pour en saisir de nouvelles. Dans certains cas, la période de la transaction d'origine peut être clôturée et vous pouvez saisir une nouvelle date de transaction pour la contrepassation.
- Si vous choisissez Non, entrez une date de transaction pour la contrepassation. 
- Saisissez un commentaire que vous souhaitez ajouter à la transaction de contrepassation.
- Cliquez sur le bouton Contrepasser.

Les transactions seront contrepassées. 

Si le nombre de lignes de documents dépasse la centaine, le processus de contrepassation sera exécuté avec le processus de traitement par lots. Vous pouvez examiner les résultats de la contrepassation en affichant les commentaires dans le traitement par lots qui a été exécuté. Tous les échecs sont mentionnés dans l'historique des traitement par lots.

Si le nombre de lignes de documents est inférieur ou égal à cent, le processus de contrepassation s'exécute immédiatement. Les résultats seront présentés dans une boîte de dialogue qui indique tout document qui n'a pas pu être contrepassé et la raison de cet échec. Cliquez sur OK pour fermer la boîte de dialogue.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Contrepassation des documents provenant de la liste de transaction de documents. 

Vous pouvez également contrepasser les documents provenant de la **Liste des transactions des documents** parmi toutes les comptabilités auxiliaires. En outre, vous pouvez contrepasser plusieurs documents à la fois. 

Pour ce faire, procédez comme suit : 
- Cliquez sur le menu Contrepasser en haut de la page.
- Vous verrez le nombre total de documents et les lignes de documents ainsi que le volume total des lignes contrepassées.
- Sélectionnez Oui pour utiliser les dates de transaction existantes ou Non pour en saisir de nouvelles. Dans certains cas, la période de la transaction d'origine peut être clôturée et vous pouvez saisir une nouvelle date de transaction pour la contrepassation.
- Si vous choisissez Non, entrez une date de transaction pour la contrepassation. 
- Saisissez un commentaire que vous souhaitez ajouter à la transaction de contrepassation.
- Cliquez sur le bouton Contrepasser.

Les transactions seront contrepassées. 

Si le nombre de lignes de documents dépasse la centaine, le processus de contrepassation sera exécuté avec le processus de traitement par lots. Vous pouvez examiner les résultats de la contrepassation en affichant les commentaires dans le traitement par lots qui a été exécuté. Tous les échecs sont mentionnés dans l'historique des traitement par lots.

Si le nombre de lignes de documents est inférieur ou égal à cent, le processus de contrepassation s'exécute immédiatement. Les résultats seront présentés dans une boîte de dialogue qui indique tout document qui n'a pas pu être contrepassé et la raison de cet échec. Cliquez sur OK pour fermer la boîte de dialogue.

