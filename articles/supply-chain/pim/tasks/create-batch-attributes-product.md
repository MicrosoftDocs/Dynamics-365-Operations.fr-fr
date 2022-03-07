---
title: Créer les attributs de lot pour un produit
description: Cette procédure décrit comment créer un attribut de lot, affecter des plages de valeur par défaut et inclure l’attribut à un groupe.
author: t-benebo
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PdsBatchAttrib
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 71779bf864b4dbe86d90131808014d1d08815155
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565604"
---
# <a name="create-batch-attributes-for-a-product"></a>Créer les attributs de lot pour un produit

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment créer un attribut de lot, affecter des plages de valeur par défaut et inclure l’attribut à un groupe. La société fictive de démonstration utilisée pour créer cette procédure s’appelle USP2.

1. Accédez à Gestion des stocks > Configuration > Lot > Attributs du lot.
2. Cliquez sur Nouveau.
3. Dans le champ Attribut, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Type d’attribut, sélectionnez « Fraction ».
    * Cette procédure utilise le type Fraction pour activer les valeurs décimales. Vous pouvez sélectionner d’autres types d’attributs. Si vous sélectionnez le type Énumération, vous devez entrer des valeurs contenues dans la liste d’énumération avant de pouvoir entrer une valeur dans le champ Cible.  
6. Dans le champ Minimum, entrez un nombre.
7. Dans le champ Maximum, entrez un nombre.
8. Dans le champ Incrémenter, entrez un nombre.
9. Dans le champ Cible, tapez une valeur.
10. Cliquez sur Enregistrer.
11. Fermez la page.
12. Accédez à Gestion des stocks > Configuration > Lot > Groupes d’attributs de lots.
13. Cliquez sur Nouveau.
14. Dans le champ Groupe d’attributs, tapez une valeur.
15. Dans le champ Description, entrez une valeur.
16. Cliquez sur Enregistrer.
17. Cliquez sur Attributs de groupe.
18. Cliquez sur Nouveau.
19. Dans le champ Attributs, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
20. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
21. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Un attribut peut être inclus dans n’importe quel groupe.  
22. Cliquez sur Enregistrer.
23. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]