--- 
title: "Établir le mode de paiement client"
description: "Créez un mode de paiement pour les paiements client."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 0ba359567126efaa8274644444a8a261e24c6621
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="establish-customer-method-of-payment"></a>Établir le mode de paiement client

[!include [task guide banner](../../includes/task-guide-banner.md)]

Créez un mode de paiement pour les paiements client. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.
2. Cliquez sur Nouveau.
3. Dans le champ Mode de paiement, entrez un ID pour le mode de paiement.
    * L'ID du mode de paiement est indiqué sur les factures et les règlements, rendez-le assez descriptif pour comprendre quel type de paiement est enregistré, et pour quel compte bancaire.  
4. Entrez une description dans le champ Description.
5. Sélectionnez le statut de paiement requis pour valider les paiements.
    * Lorsque vous créez un paiement client, il peut seulement être validé lorsque le statut de paiement correspond au statut de paiement que vous définissez ici.  
6. Sélectionnez la manière dont les paiements de clients doivent être créés pour les factures.
    * Cette option est uniquement utilisée lors de l'exécution d'une proposition de paiement. Une proposition de paiement peut être utilisée pour les paiements client lorsque vous effectuez des débits directs et extrayez les fonds des comptes bancaires des clients.  
7. Sélectionnez le type de paiement.
    * Le type de paiement aidera à déterminer si le paiement est validé ou non.  
8. Sélectionnez le type de compte dans lequel les paiements seront validés.
    * Généralement, Banque est sélectionné pour cette option.  
9. Sélectionnez le compte bancaire dans lequel ce paiement sera enregistré.
10. Entrez le type de transaction bancaire pour identifier le type de paiement utilisé par votre banque.
    * Le type de transaction bancaire est utilisé lors du processus de rapprochement bancaire, et peut faciliter le rapprochement.  
11. Indiquez si ce paiement sera temporairement validé dans un compte de transition.
    * Si vous souhaitez essayer l'heure flottante pour un paiement pour rapprocher la banque, utilisez la fonctionnalité Transition. Le paiement sera temporairement validé dans un compte général jusqu'à ce qu'il soit compensé par la banque, le paiement sera alors déplacé dans un compte bancaire que vous avez défini ici.  
12. Entrez le compte principal utilisé pour la validation d'attente.
    * Il s'agit du compte principal dans lequel le paiement est temporairement validé si vous utilisez la transition.  
13. Utilisez l'onglet Format de fichier pour définir le paramètre pour les paiements électroniques.
14. Utilisez l'onglet Contrôle des paiements pour définir les champs qui sont obligatoires.
    * Par exemple, si tous les paiements doivent être déposés avec ce mode de paiement, vous pouvez sélectionner cette option sous cet onglet.  
15. Utilisez l'onglet Attributs de paiement pour indiquer les attributs de paiement que vous souhaitez utiliser pour ce mode de paiement.
16. Cliquez sur Enregistrer.


