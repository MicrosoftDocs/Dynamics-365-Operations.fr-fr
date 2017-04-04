---
title: "Vue d&quot;ensemble des règlements des paiements centralisés"
description: "Les organisations qui comprennent plusieurs entités juridiques peuvent créer et gérer des paiements à l&quot;aide d&quot;une entité juridique qui assure la gestion de tous les paiements. Cela élimine le besoin d&quot;entrer la même transaction dans plusieurs entités juridiques et permet de gagner du temps en rationalisant le processus de proposition de paiement, le processus de règlement, la modification des transactions en cours et la modification des transactions clôturées pour les paiements centralisés."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 222414
ms.assetid: 610f6858-0f37-4d0f-8c68-bab5a971ef4a
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 08c0af5eabc31dca0b36a2dc62ce2f739b808cde
ms.lasthandoff: 03/31/2017


---

# <a name="settlement-overview-for-centralized-payments"></a>Vue d'ensemble des règlements des paiements centralisés

Les organisations qui comprennent plusieurs entités juridiques peuvent créer et gérer des paiements à l'aide d'une entité juridique qui assure la gestion de tous les paiements. Cela élimine le besoin d'entrer la même transaction dans plusieurs entités juridiques et permet de gagner du temps en rationalisant le processus de proposition de paiement, le processus de règlement, la modification des transactions en cours et la modification des transactions clôturées pour les paiements centralisés. 

Lorsqu'un paiement client ou fournisseur est entré dans une entité juridique et est réglé avec une facture entrée dans une autre entité juridique, le règlement applicable et les transactions d’échéance sont automatiquement générés pour chaque entité juridique. Un enregistrement de règlement est créé pour chaque combinaison de facture et de paiement dans la transaction. Un nouveau numéro document est affecté à chaque enregistrement de règlement, basé sur la série de numéros de souche de document de paiement spécifiée sur la page **Paramètres de la comptabilité client** pour les clients et sur la page **Paramètres de la comptabilité fournisseur** pour les fournisseurs. 

Si d'autres enregistrements de règlement sont générés pour les escomptes de règlement, les réévaluations de devises étrangères, les différences minimes, les trop-perçus ou les moins-perçus, ils se voient affecter la date ultérieure de la transaction de paiement ou de facturation. Si le règlement s'effectue après la validation du paiement, les enregistrements de règlement utilisent la date de validation du règlement spécifiée sur la page **Régler les transactions en cours**.
Types de validation, types de transaction et description par défaut
----------------------------------------------------------

Les transactions N° de document de règlement intersociétés utilisent les types de validation de règlement intersociétés, de règlement client intersociétés, et de transaction de règlement fournisseur intersociétés. Vous pouvez paramétrer les informations pour le type de transaction sur la page **Descriptions par défaut**. 

Les types de transaction suivants sont disponibles pour les règlements de société unique et de société croisée :

-   Règlement
-   Escompte de règlement
-   Réévaluations de devises étrangères (y compris les réévaluations de devises étrangères réalisées et non réalisées)
-   Différence minime
-   Trop-perçu/moins-perçu

Vous pouvez également définir des descriptions par défaut pour les N° document de règlement intersociétés.

<a name="currency-exchange-gains-or-losses"></a>Bénéfice ou perte de taux de change
---------------------------------

Le taux de change utilisé pour les transactions client ou fournisseur est stocké avec la transaction. Les profits ou pertes réalisés pour les changes sont validés dans l'entité juridique de la facture ou celle de paiement, en fonction de l'option sélectionnée pour le champ **Valider le bénéfice ou la perte du taux de change** sur la page **Comptabilité intersociétés** de l'entité juridique de paiement. Les exemples suivants utilisent ces devises :
-   Devise comptable de paiement : EUR
-   Devise comptable de la facture : USD
-   Devise de la transaction de paiement : DKK
-   Devise de la transaction de la facture : CAD

#### <a name="currency-calculations"></a>Calculs en devise

Lors du règlement d'une facture entrée dans une entité juridique avec un paiement entré dans une autre entité juridique, la devise de transaction du paiement (DKK) est convertie en trois étapes :
1.  conversion dans la devise comptable du paiement (EUR), en utilisant les taux de change de l'entité juridique de paiement ;
2.  conversion dans la devise comptable de la facture (USD) ;
3.  conversion dans la devise de la transaction de la facture (CAD), en utilisant les taux de change de l'entité juridique de la facture.

Le processus de conversion utilise les taux de change à la date du paiement. Si le montant du paiement résultant dans la devise de la transaction de la facture (CAD) est égal au montant de la facture (CAD), la facture est considérée comme intégralement payée. 

Lorsque la page **Régler les transactions en cours** est ouverte à partir d'un journal des paiements dans lequel le montant du paiement n'a pas été entré, le montant à régler est calculé en fonction des factures sélectionnées pour le règlement sur la page **Régler les transactions en cours**. Le montant à régler est converti en trois étapes :
1.  conversion dans la devise comptable de la facture (USD), en utilisant les taux de change de l'entité juridique de la facture à compter de la date de paiement ;
2.  conversion dans la devise comptable du paiement (EUR), en utilisant les taux de change de l'entité juridique de la facture à compter de la date de paiement ;
3.  conversion dans la devise de la transaction du paiement (DKK).

Le montant du paiement résultant est transféré dans la ligne de journal des paiements à la fermeture de la page **Régler les transactions en cours**.

#### <a name="posting-for-gain-or-loss-because-of-different-accounting-currencies"></a>Validation des bénéfices ou pertes dus aux différentes devises comptables

En cas de bénéfice ou de perte de taux de change, le bénéfice ou la perte est validé dans l'entité juridique spécifiée dans le champ **Valider le bénéfice ou la perte du taux de change** sur la page **Comptabilité intersociétés** pour l'entité juridique de paiement. Le montant du bénéfice ou de la perte est converti dans la devise comptable de l'entité juridique où il est validé, en utilisant le taux de change défini pour cette entité juridique.

<a name="cash-discounts"></a>Escomptes de règlement
--------------

Les escomptes de règlement générés pendant le processus de règlement de société croisée sont validés dans l'entité juridique de la facture ou dans celle de paiement, selon l'option sélectionnée dans le champ **Valider l'escompte de règlement** sur la page **Comptabilité intersociétés** pour l'entité juridique de paiement. Une transaction de règlement correspondante est générée dans l'entité juridique de la facture.

<a name="overpayments-and-underpayments"></a>Trop-perçus et moins-perçus
------------------------------

Les tolérances concernant les trop-perçus, les moins-perçus et les différences minimes sont déterminées en fonction de l'entité juridique de paiement des trop-perçus et de celle des moins-perçus. Le compte de validation utilisé est déterminé par le paramètre du champ **Administration d'escompte de règlement** de la page **Paramètres de la Comptabilité client** pour les clients, et le champ **Administration d'escompte de règlement** de la page **Paramètres de la Comptabilité fournisseur** pour les fournisseurs.

-   Si le paramètre d'administration d'escompte de règlement est Spécifique ou Non spécifique et que l'escompte de règlement applicable est validé dans une autre entité juridique que celle du trop-perçu, le compte automatique pour Client - Escompte de règlement, Fournisseur - Escompte de règlement ou Différence minime dans la devise comptable est utilisé. Vous pouvez spécifier ces comptes sur la page **Comptes pour transactions automatiques**.
-   Si le paramètre d'administration d'escompte de règlement est Non spécifique et que l'escompte de règlement est validé dans la même entité juridique que celle du trop-perçu (l'entité juridique de paiement et l'entité juridique de la facture sont identiques), le compte d'escompte de règlement est ajusté. Par exemple, si une facture de 100,00 avec un escompte de règlement disponible de 3,00 est réglée avec un paiement pour 98,00, le compte d'escompte de règlement est ajusté pour 1,00. Le montant net de l'escompte est 2,00.
-   Si le paramètre d'administration d'escompte de règlement est Non spécifique, l'escompte de règlement est validé dans la même entité juridique que celle du trop-perçu, le trop-perçu ou le moins-perçu est réglé avec plusieurs factures comportant des escomptes de règlement et le compte d'escompte de règlement de la dernière facture est ajusté.

Si la sélection d'administration d'escompte de règlement est Non spécifique, les règles du règlement de paiement non spécifique s'appliquent uniquement dans les cas suivants :
-   existence d'un trop-perçu ;
-   trop-perçu réglé avec une ou plusieurs factures comportant un escompte de règlement ;
-   escompte de règlement validé dans la même entité juridique que celle du trop-perçu.

Dans tous les autres cas, les trop-perçus ou les moins-perçus sont validés dans le compte automatique pour Client - Escompte de règlement, Fournisseur - Escompte de règlement ou Différence minime dans la devise comptable.

## <a name="sales-tax"></a>Taxe
Les transactions de taxe restent dans l'entité juridique dans laquelle elles ont été validées à l'origine. 

Si la taxe a été validée pour un acompte, le règlement de société croisée contrepasse la taxe sur l'acompte dans l'entité juridique de l'acompte. Les taxes dans l'entité juridique de la facture restent dans l'entité juridique de la facture.

## <a name="financial-dimensions"></a>Dimensions financières
Pour les paiements clients, les transactions d'échéance dans l'entité juridique de paiement utilisent les dimensions financières spécifiées pour le compte collectif des ventes à partir de paiement en cours de règlement. Dans l'entité juridique de la facture, les transactions d'échéance utilisent les dimensions financières spécifiées pour le compte collectif des ventes à partir de la facture en cours de règlement. 

Pour les paiements fournisseur, les transactions d'échéance dans l'entité juridique de paiement utilisent les dimensions financières spécifiées pour le compte collectif des achats à partir de paiement en cours de règlement. Dans l'entité juridique de la facture, les transactions d'échéance utilisent les dimensions financières spécifiées pour le compte collectif des achats à partir de la facture en cours de règlement.

## <a name="withholding-tax"></a>Retenue à la source
Le compte fournisseur associé à la facture est utilisé pour déterminer si la retenue à la source doit être calculée. Si la retenue à la source s'applique, elle est calculée dans l'entité juridique associée à la facture. Si les entités juridiques utilisent différentes monnaies, c'est le taux de change de l'entité juridique associée à la facture qui est utilisé.




