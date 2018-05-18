--- 
title: "Paramétrer le rapprochement automatique des frais de transport"
description: "Cette procédure indique comment paramétrer des données pour le rapprochement automatique des frais de transport."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 97f0c4d8fe06ab2fc252b9543cb688306214c79f
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-automatic-freight-reconciliation"></a>Paramétrer le rapprochement automatique des frais de transport

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment paramétrer des données pour le rapprochement automatique des frais de transport. Elle est généralement effectuée par un gestionnaire d'entrepôt. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.


## <a name="set-up-the-freight-bill-type"></a>Paramétrer le type de facture de frais de transport
1. Allez dans Gestion du transport > Paramétrage > Rapprochement des frais de transport > Type de facture des frais de transport.
    * Le type de facture des frais de transport définit comment les factures de frais de transport et les factures du transporteur doivent être mises en correspondance.  
2. Cliquez sur Nouveau.
3. Dans le champ Type de facture des frais de transport, tapez une valeur.
4. Dans le champ Assembly de moteur, tapez « Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer ».
    * Il s'agit de la gestion de transport standard correspondant à la bibliothèque de code du moteur.  
5. Dans le champ Classe de moteur, tapez « Microsoft.Dynamics.Ax.Tms.dll ».
    * Il s'agit de la gestion de transport standard correspondant à la classe du moteur.  
6. Cliquez sur Nouveau.
7. Dans le champ Description, sélectionnez la valeur qui doit correspondre sur la facture des frais de transport et la facture du transporteur.  
8. Dans le champ Correspondance nécessaire, sélectionnez « Oui ».
    * Si vous définissez ce champ sur Oui, cela implique que la valeur sélectionnée dans le champ Description doit correspondre sur la facture des frais de transport et la facture du transporteur. S'il est défini sur Non, le champ peut être vide sur l'un de ces éléments.  
9. Cliquez sur Enregistrer.

## <a name="set-up-the-freight-bill-type-assignment"></a>Paramétrer l'affectation du type de facture de frais de transport
1. Fermez la page.
2. Allez dans Gestion du transport > Paramétrage > Rapprochement des frais de transport > Affectations du type de facture des frais de transport.
    * L'affectation du type de facture de frais de transport permet de spécifier le type de facture de frais de transport utilisé pour un transporteur particulier.   
3. Cliquez sur Nouveau.
4. Dans le champ Mode, entrez ou sélectionnez une valeur.
5. Dans le champ Transporteur, entrez ou sélectionnez une valeur.
6. Dans le champ Type de facture des frais de transport, sélectionnez le type de facture des frais de transport que vous avez créé précédemment.
7. Fermez la page.

## <a name="set-up-the-audit-master"></a>Paramétrer les données principales d'audit
1. Allez dans Gestion du transport > Paramétrage > Rapprochement des frais de transport > Données principales d'audit.
    * La table maître d'audit définit les limites de tolérance pour le rapprochement automatique des frais de transport. Elle spécifie dans quelle mesure les montants en devises sur la facture des frais de transport et la facture de transporteur peuvent différer tout en autorisant le rapprochement. Elle définit également comment gérer les différences.  
2. Cliquez sur Nouveau.
3. Dans le champ ID données principales d'audit, tapez une valeur.
4. Dans le champ Transporteur, sélectionnez le même transporteur que celui sélectionné précédemment.
5. Dans le champ Type de facture des frais de transport, sélectionnez le type de facture des frais de transport que vous avez créé précédemment.
6. Développez la section Tolérance.
7. Dans le champ Niveau de tolérance minimal, entrez un nombre.
8. Dans le champ Niveau de tolérance maximal, entrez un nombre.
9. Développez la section Résultat.
10. Dans le champ Code motif du trop-perçu, entrez ou sélectionnez une valeur.
    * Si les montants en devises diffèrent sur la facture des frais de transport et la facture du transporteur, les codes motif du trop-perçu/moins-perçu spécifient les comptes sur lesquels la différence doit être enregistrée, tant qu'elle entre dans les niveaux de tolérance.  
11. Dans le champ Code motif du moins-perçu, entrez ou sélectionnez une valeur.
12. Fermez la page.


