---
title: Création en masse de devis de vente
description: Cette procédure illustre comment créer efficacement des devis offrant un ensemble de produits ou de services à envoyer à plusieurs clients.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 227ff0dd03f8917f4551ce08067ef26c6204b059
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980716"
---
# <a name="mass-create-sales-quotations"></a>Création en masse de devis de vente

[!include [banner](../../includes/banner.md)]

Cette procédure illustre comment créer efficacement des devis offrant un ensemble de produits ou de services à envoyer à plusieurs clients. Cette création de devis en masse est basée sur des modèles de devis. Vous pouvez exécuter cette procédure avec vos propres données ou avec la société fictive de démonstration USMF.


## <a name="create-a-quotation-template"></a>Créer un modèle de devis
1. Accédez à Ventes et marketing > Configuration > Devis > Groupes de modèles.
2. Cliquez sur Nouveau.
3. Dans le champ ID groupe, tapez un ID de votre choix.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Enregistrer.
6. Fermez la page.
7. Accédez à Ventes et marketing > Devis de vente > Tous les devis.
8. Cliquez sur Nouveau.
9. Sélectionnez « Client » dans le champ Type de compte.
10. Entrez ou sélectionnez une valeur dans le champ Compte client.
11. Cliquez sur OK.
    * Pour qu'un devis devienne un modèle, vous devez effectuer des étapes de paramétrage dans l'en-tête du devis. Cela doit être effectué avant d'ajouter des lignes au devis.   
12. Dans le volet Actions, cliquez sur Options.
13. Cliquez sur Changer de vue.
14. Cliquez sur Vue de l'en-tête.
15. Développez la section Paramétrage.
16. Saisissez ou sélectionnez une valeur dans le champ ID groupe.
17. Tapez une valeur dans le champ Nom de modèle.
18. Sélectionnez Oui dans le champ Actif.
    * Seuls les modèles actifs peuvent être utilisés lorsque vous appliquez un modèle à un nouveau devis de vente.  
19. Dans le volet Actions, cliquez sur Options.
20. Cliquez sur Changer de vue.
21. Cliquez sur Affichage des lignes.
22. Dans le champ Article, saisissez ou sélectionnez une valeur.
23. Dans le champ Article, tapez une valeur.
24. Fermez la page.
25. Entrez un nombre dans le champ Pourcentage de remise.
26. Cliquez sur Ajouter une ligne.
27. Dans le champ Article, saisissez ou sélectionnez une valeur.
28. Dans le champ Article, tapez une valeur.
29. Fermez la page.
30. Dans le champ Prix unitaire, entrez un nouveau prix ou modifiez le prix actuel.
31. Cliquez sur Ajouter une ligne.
32. Dans le champ Article, saisissez ou sélectionnez une valeur.
33. Dans le champ Article, tapez une valeur.
34. Fermez la page.
35. Dans le champ Quantité, entrer un numéro.
36. Entrez un nombre dans le champ Remise.
37. Cliquez sur Enregistrer.

## <a name="apply-the-template-to-create-a-single-quotation"></a>Appliquer le modèle pour créer un devis unique
1. Accédez à Ventes et marketing > Devis de vente > Tous les devis.
    * Notez que le devis que vous venez de créer est marqué comme modèle.  
2. Cliquez sur Nouveau.
3. Sélectionnez « Client » dans le champ Type de compte.
4. Entrez ou sélectionnez une valeur dans le champ Compte client.
5. Développez la section Modèle.
6. Saisissez ou sélectionnez une valeur dans le champ ID groupe.
7. Saisissez ou sélectionnez une valeur dans le champ Nom du modèle.
8. Dans le champ Mode de calcul, sélectionnez « En fonction des valeurs du modèle ».
9. Cliquez sur OK.
    * Le nouveau devis a maintenant été créé, en fonction des données et des conditions du modèle.  
10. Fermez la page.
11. Fermez la page.

## <a name="apply-the-template-to-mass-create-quotations"></a>Appliquer le modèle à la création en masse de devis
1. Accédez à Ventes et marketing > Devis de vente > Mise à jour du devis > Création en masse de devis.
2. Sélectionnez « Client » dans le champ Type de compte.
3. Saisissez ou sélectionnez une valeur dans le champ ID groupe.
4. Saisissez ou sélectionnez une valeur dans le champ Nom du modèle.
5. Dans le champ Mode de calcul, sélectionnez « En fonction des valeurs du modèle ».
6. Développez les enregistrements pour inclure la section.
7. Cliquez sur Filtre.
8. Dans le champ Critères définissez le filtre de sorte à couvrir une gamme de clients à inclure dans cette création en masse de devis. Utilisez le format suivant : "Client1..ClientN.
    * Par exemple, vous pouvez définir le filtre sur : US-001...US-004  
9. Cliquez sur OK.
10. Cliquez sur OK.
11. Accédez à Ventes et marketing > Devis de vente > Tous les devis.
    * Vérifiez que des devis ont été créés pour tous les clients spécifiés dans la routine de mise à jour collective, comme l'indique le modèle sélectionné.  

