---
title: Paramétrer un format de bordereau de paiement pour les factures de projet
description: Les entreprises associent généralement les bordereaux de paiement imprimés aux factures pour aider leurs clients et fournir une référence de paiement pour la validation et le règlement.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMLegalEntity, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4671e1df3bc86361736b5882d67e6b160b4c5644
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174863"
---
# <a name="set-up-payment-slip-format-for-project-invoices"></a>Paramétrer un format de bordereau de paiement pour les factures de projet

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les entreprises associent généralement les bordereaux de paiement imprimés aux factures pour aider leurs clients et fournir une référence de paiement pour la validation et le règlement. Les bordereaux de paiement peuvent être utilisés pour les factures de projet ou de service, les lettres de relance, les notes d'intérêt et les relevés de compte, en plus des factures client et des factures financières. Pour traiter les bordereaux de paiement, commencez par paramétrer votre ID créditeur et les formats de bordereau de paiement associé.

La société fictive DEMF sert d'exemple dans cette procédure. 

Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est au Danemark.


## <a name="set-up-a-creditor-id-number"></a>Paramétrage d'un ID créditeur
1. Accédez à Administration d'organisation > Organisations > Entités juridiques.
2. Développez ou réduisez la section la section Informations sur le compte en banque.
3. Cliquez sur Modifier.
4. Dans le champ ID créditeur financier, tapez une valeur.
5. Cliquez sur Enregistrer.
6. Fermez la page.

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a>Paramétrage d'un format de bordereau de paiement pour les factures, les notes, les lettres et les relevés
1. Accédez à Comptabilité client > Paramétrage > Écrans > Paramétrage d'écran.
2. Cliquez sur l'onglet Facture.
3. Dans le champ Document de paiement associé de facture client, sélectionnez une option.
    * Aucun(e) – N'imprimez pas de bordereau de paiement. Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).   FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.   FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.  
4. Cliquez sur Enregistrer.
5. Cliquez sur l'onglet Facture financière.
6. Dans le champ Document de paiement associé de facture financière, sélectionnez une option.
    * Aucun(e) – N'imprimez pas de bordereau de paiement. Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).   FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.   FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.  
7. Cliquez sur Enregistrer.
8. Cliquez sur l'onglet Note d'intérêt.
9. Dans le champ Document de paiement associé de note d'intérêt, sélectionnez une option.
    * Aucun(e) – N'imprimez pas de bordereau de paiement. Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).   FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.   FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.  
10. Cliquez sur Enregistrer.
11. Cliquez sur l'onglet Lettre de relance.
12. Dans le champ Document de paiement associé de lettre de relance, sélectionnez une option.
    * Aucun(e) – N'imprimez pas de bordereau de paiement. Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).   FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.   FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.  
13. Cliquez sur Enregistrer.
14. Cliquez sur l'onglet Relevé de compte.
15. Dans le champ Document de paiement associé de relevé d'échéances, sélectionnez une option.
    * Aucun(e) – N'imprimez pas de bordereau de paiement. Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).   FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.   FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.  
16. Cliquez sur Enregistrer.
17. Fermez la page.

