--- 
title: "Configurer les collaborateurs de vente au détail"
description: "Cette procédure illustre comment configurer un collaborateur de vente au détail comme commercial qui peut bénéficier d'une commission sur les ventes dans POS."
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: f583c421c2f6dfd019d9586cb7d14f3298127d94
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="configure-retail-workers"></a>Configurer les collaborateurs de vente au détail

[!include [task guide banner](../includes/task-guide-banner.md)]

Cette procédure illustre comment configurer un collaborateur de vente au détail comme commercial qui peut bénéficier d'une commission sur les ventes dans POS. La société fictive USRT sert d'exemple dans cette procédure.


## <a name="create-a-commission-sales-group-for-the-worker"></a>Créer un groupe de vente avec commission pour le collaborateur
1. Accédez à Ventes et marketing > Commissions > Groupes de ventes.
    * Les collaborateurs peuvent être affectés à un ou plusieurs groupes de vente. Dans POS, vous pouvez choisir n'importe quel groupe de vente contenant des collaborateurs issus du carnet d'adresses du magasin.  
2. Cliquez sur Nouveau.
3. Dans le champ Groupe, tapez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Cliquez sur Enregistrer.
6. Cliquez sur Général dans le volet Actions.
7. Cliquez sur Commercial.
    * Un groupe de vente peut contenir plusieurs collaborateurs. Les commissions peuvent être fractionnées entre les collaborateurs selon la façon dont vous définissez la part de commission.  
8. Saisissez ou sélectionnez une valeur dans le champ Nom.
9. Dans le champ Part de commission, entrez un nombre.
10. Cliquez sur Enregistrer.
11. Fermez la page.
12. Fermez la page.

## <a name="assign-the-workers-default-sales-group"></a>Affecter le groupe de vente par défaut des collaborateurs
1. Accédez à Commerce et vente au détail > Employés > Collaborateurs.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur l'onglet Vente au détail.
    * Un collaborateur peut être affecté à un groupe de vente par défaut. Le groupe de vente par défaut est automatiquement ajouté aux lignes de vente dans POS si l'option est activée dans le profil de la fonctionnalité pour le magasin.  
5. Cliquez sur Modifier.
6. Dans le champ Groupe par défaut, entrez ou sélectionnez une valeur.
7. Cliquez sur Enregistrer.


