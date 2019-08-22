---
title: Déposer les paiements client
description: Déposez des paiements client.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: afbf74d1cf3dc87e97dda0873115b5c7fa49ca3d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834461"
---
# <a name="deposit-customer-payments"></a>Déposer les paiements client

[!include [task guide banner](../../includes/task-guide-banner.md)]

Déposez des paiements client. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Comptabilité client > Paiements > Journal des paiements.
2. Cliquez sur Nouveau.
3. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Sélectionnez le journal de paiement. 
5. Cliquez sur Lignes.
6. Dans le champ Compte, sélectionnez le client pour lequel vous enregistrez le paiement.
7. Dans le champ Crédit, entrez le montant du paiement.
    * Vous pouvez choisir de laisser le montant de ce champ vide, et laisser le système le calculer en sélectionnant les factures qui ont été payées.  
8. Tapez une valeur dans le champ Référence de paiement.
    * La référence de paiement peut être le numéro de chèque pour le paiement que vous entrez. La référence de paiement est requise pour inclure le paiement sur un bordereau de remise.  
9. Cochez la case Utiliser un bordereau de remise.
    * Si le paiement doit être inclus dans le dépôt, définissez ce paramètre sur Oui.  
10. Cliquez sur Nouveau.
11. Dans le champ Compte, sélectionnez le client pour le paiement suivant.
12. Dans le champ Crédit, entrez le montant du paiement.
13. Tapez une valeur dans le champ Référence de paiement.
14. Cochez la case Utiliser un bordereau de remise.
15. Cliquez sur Valider.
    * Les paiements doivent être validés avant que le bordereau de remise puisse être généré. Cela permet de garantir que les paiements ne changent pas une fois le bordereau de remise généré.  
16. Cliquez sur Fonctions.
17. Cliquez sur Bordereau de remise.
18. Cliquez sur OK.
    * La première page permet de créer le bordereau de remise.  
19. Cliquez sur OK.
    * La deuxième étape consiste à imprimer le bordereau de remise, mais cette étape n'est pas nécessaire.  

