---
title: Contrepasser la validation du journal
description: Cette rubrique décrit les fonctionnalités qui vous permettent de contrepasser les documents provenant de la liste de transaction de documents ou provenant des journaux financiers.
author: kweekley
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb1615312e9fd1786a5a0050dda3e9e9b20fe710
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753776"
---
# <a name="reverse-journal-posting"></a>Contrepasser la validation du journal

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctionnalités Microsoft Dynamics 365 Finance qui vous permettent de contrepasser un journal entier, ou de contrepasser un ou plusieurs documents provenant de la liste de transactions de documents, peu importe leur origine. 

Avant de pouvoir utiliser une des fonctionnalités décrites dans cette rubrique, vous devez l’activer dans votre système. Les administrateurs peuvent utiliser l’espace de travail **gestion des fonctionnalités** pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :
 - Module : Comptabilité
 - Nom de la fonctionnalité : **Contrepassation en masse pour plusieurs documents**

## <a name="reversing-journals"></a>Contrepassation des journaux

Vous pouvez contrepasser des lignes de journal individuellement. Avec la contrepassation de la validation du journal, vous pouvez également contrepasser tout un journal financier. Pour contrepasser un journal : 

- Filtrez sur les journaux publiés et ouvrez la vue **Lignes** sur le journal.
- Sélectionnez le menu **Contrepasser** en haut de la page.
- Vous verrez le nombre total de documents et les lignes de documents ainsi que le volume total des lignes contrepassées.
- Sélectionnez **Oui** pour utiliser les dates de transaction existantes ou **Non** pour en saisir de nouvelles. Dans certains cas, la période de la transaction d’origine peut être clôturée et vous devez saisir une nouvelle date de transaction pour la contrepassation.
- Si vous sélectionnez **Non**, entrez une date de transaction pour la contrepassation. 
- Saisissez un commentaire que vous souhaitez ajouter à la transaction de contrepassation.
- Sélectionnez le bouton **Contrepasser**.

Les transactions seront contrepassées. 

Si le document contient plus de 100 lignes, le processus de contrepassation sera exécuté avec le processus de traitement par lots. Vous pouvez examiner les résultats en affichant les commentaires dans le traitement par lots. Toutes les transactions qui ne peuvent pas être contrepassées sont répertoriées dans l’historique du traitement par lots.

Si le document contient 100 lignes ou moins, le processus de contrepassation s’exécute immédiatement. Les résultats seront présentés dans une boîte de dialogue qui indique tout document qui n’a pas pu être contrepassé et la raison de cet échec. Sélectionnez **OK** pour fermer la boîte de dialogue.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Contrepassation des documents provenant de la liste de transaction de documents. 

Vous pouvez également contrepasser les documents provenant de la **Liste des transactions des documents** parmi toutes les comptabilités auxiliaires. En outre, vous pouvez contrepasser plusieurs documents à la fois. 

Pour ce faire, procédez comme suit : 

- Sélectionnez le menu déroulant **Contrepasser l’intégralité du journal** en haut de la page.
- Le nombre total de documents et les lignes de documents sont affichés, ainsi que le volume total des lignes contrepassées.
- Sélectionnez **Oui** pour utiliser les dates de transaction existantes ou **Non** pour en saisir de nouvelles. Dans certains cas, la période de la transaction d’origine peut être clôturée et vous devez saisir une nouvelle date de transaction pour la contrepasser.
- Si vous sélectionnez **Non**, entrez une date de transaction pour la contrepassation. 
- Entrez un commentaire décrivant la transaction de contrepassation.
- Sélectionnez le bouton **Contrepasser**.

Les transactions seront contrepassées. 

Si le document contient plus de 100 lignes document, le processus de contrepassation sera exécuté avec le processus de traitement par lots. Vous pouvez examiner les résultats en affichant les commentaires dans le traitement par lots. Toutes les transactions qui ne peuvent pas être contrepassées sont notées dans l’historique du traitement par lots.

Si le nombre de lignes de documents est inférieur ou égal à cent, le processus de contrepassation s’exécute immédiatement. Les résultats seront affichés dans une boîte de dialogue qui indique tout document qui n’a pas pu être contrepassé et la raison de cet échec. Sélectionnez **OK** pour fermer la boîte de dialogue.

Les transactions peuvent être contrepassées que si elles sont conformes aux règles métier pour les contrepasser. Les paiements fournisseur ne peuvent pas être contrepassés en utilisant une capacité décrite dans cette rubrique. Les paiements fournisseur doivent être contrepassés en suivant les étapes indiquées dans [Contrepasser un paiement fournisseur](../accounts-payable/reverse-vendor-payment.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
