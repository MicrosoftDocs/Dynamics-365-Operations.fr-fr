---
title: Déposer les paiements client
description: Déposez des paiements client.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d903f557fbaeb720dd4a34dc1c772be0dcb56eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443165"
---
# <a name="deposit-customer-payments"></a>Déposer les paiements client

[!include [banner](../../includes/banner.md)]

Déposez des paiements client. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à **Volet de navigation > Modules > Comptabilité client > Paiements > Journal des paiements**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom**, sélectionnez **CustPay** dans le menu déroulant.
4. Sélectionnez **Lignes**.
5. Dans le champ **Compte**, sélectionnez le client pour lequel vous enregistrez le paiement.
6. Dans le champ **Crédit**, entrez le montant du paiement. Vous pouvez choisir de laisser le montant de ce champ vide, et laisser le système le calculer en sélectionnant les factures qui ont été payées.  
7. Tapez une valeur dans le champ **Référence de paiement**. La référence de paiement peut être le numéro de chèque pour le paiement que vous entrez. La référence de paiement est requise pour inclure le paiement sur un bordereau de remise.  
8. Cochez la case Utiliser un bordereau de remise. Si le paiement doit être inclus dans le dépôt, définissez ce paramètre sur Oui.  
9. Sélectionnez **Nouveau**.
10. Dans le champ **Compte**, sélectionnez le client pour le paiement suivant.
11. Dans le champ **Crédit**, entrez le montant du paiement.
12. Tapez une valeur dans le champ **Référence de paiement**.
13. Cochez la case **Utiliser un bordereau de remise**.
14. Sélectionnez **Valider**. Les paiements doivent être validés avant que le bordereau de remise puisse être généré. Cela permet de garantir que les paiements ne changent pas une fois le bordereau de remise généré.  
15. Sélectionnez **Fonctions**.
16. Sélectionnez **Bordereau de remise**.
17. Cliquez sur **OK**. La première page permet de créer le bordereau de remise.  
18. Cliquez sur **OK**. La deuxième étape consiste à imprimer le bordereau de remise, mais cette étape n’est pas nécessaire.  

