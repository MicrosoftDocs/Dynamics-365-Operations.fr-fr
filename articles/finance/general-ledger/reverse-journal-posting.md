---
title: Contrepasser la validation du journal
description: Cette rubrique décrit les fonctionnalités qui vous permettent de contrepasser les documents provenant de la liste de transaction de documents ou provenant des journaux financiers.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
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
ms.openlocfilehash: 08aec836ce4b7b6a59c445f138365f101a78c68e
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2020
ms.locfileid: "3030920"
---
# <a name="reverse-journal-posting"></a>Contrepasser la validation du journal

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctionnalités Microsoft Dynamics 365 Finance qui vous permettent de contrepasser un journal entier, ou de contrepasser un ou plusieurs documents provenant de la liste de transactions de documents, peu importe leur origine. 

## <a name="reversing-journals"></a>Contrepassation des journaux

Vous pouvez contrepasser des lignes de journal individuellement. Avec la contrepassation de la validation du journal, vous pouvez également contrepasser tout un journal financier. Pour contrepasser un journal : 

- Ouvrez le journal financier et filtrez selon les journaux validés.
- Sélectionnez le menu **Contrepasser** en haut de la page.
- Vous verrez le nombre total de documents et les lignes de documents ainsi que le volume total des lignes contrepassées.
- Sélectionnez **Oui** pour utiliser les dates de transaction existantes ou **Non** pour en saisir de nouvelles. Dans certains cas, la période de la transaction d'origine peut être clôturée et vous devez saisir une nouvelle date de transaction pour la contrepassation.
- Si vous sélectionnez **Non**, entrez une date de transaction pour la contrepassation. 
- Saisissez un commentaire que vous souhaitez ajouter à la transaction de contrepassation.
- Sélectionnez le bouton **Contrepasser**.

Les transactions seront contrepassées. 

Si le document contient plus de 100 lignes, le processus de contrepassation sera exécuté avec le processus de traitement par lots. Vous pouvez examiner les résultats en affichant les commentaires dans le traitement par lots. Toutes les transactions qui ne peuvent pas être contrepassées sont répertoriées dans l'historique du traitement par lots.

Si le document contient 100 lignes ou moins, le processus de contrepassation s'exécute immédiatement. Les résultats seront présentés dans une boîte de dialogue qui indique tout document qui n'a pas pu être contrepassé et la raison de cet échec. Sélectionnez **OK** pour fermer la boîte de dialogue.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Contrepassation des documents provenant de la liste de transaction de documents. 

Vous pouvez également contrepasser les documents provenant de la **Liste des transactions des documents** parmi toutes les comptabilités auxiliaires. En outre, vous pouvez contrepasser plusieurs documents à la fois. 

Pour ce faire, procédez comme suit : 

- Sélectionnez le menu **Contrepasser** en haut de la page
- Vous verrez le nombre total de documents et les lignes de documents ainsi que le volume total des lignes contrepassées.
- Sélectionnez **Oui** pour utiliser les dates de transaction existantes ou **Non** pour en saisir de nouvelles. Dans certains cas, la période de la transaction d'origine peut être clôturée et vous devez saisir une nouvelle date de transaction pour la contrepasser.
- Si vous sélectionnez **Non**, entrez une date de transaction pour la contrepassation. 
- Entrez un commentaire décrivant la transaction de contrepassation.
- Sélectionnez le bouton **Contrepasser**.

Les transactions seront contrepassées. 

Si le document contient plus de 100 lignes document, le processus de contrepassation sera exécuté avec le processus de traitement par lots. Vous pouvez examiner les résultats en affichant les commentaires dans le traitement par lots. Toutes les transactions qui ne peuvent pas être contrepassées sont notées dans l'historique du traitement par lots.

Si le nombre de lignes de documents est inférieur ou égal à cent, le processus de contrepassation s'exécute immédiatement. Les résultats seront affichés dans une boîte de dialogue qui indique tout document qui n'a pas pu être contrepassé et la raison de cet échec. Sélectionnez **OK** pour fermer la boîte de dialogue.

Les transactions peuvent être contrepassées que si elles sont conformes aux règles métier pour les contrepasser. Les paiements fournisseur ne peuvent pas être contrepassés en utilisant une capacité décrite dans cette rubrique. Les paiements fournisseur doivent être contrepassés en suivant les étapes indiquées dans [Contrepasser un paiement fournisseur](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).

