--- 
title: "Créer des configurations de format pour la gestion des états électroniques"
description: "es étapes suivantes expliquent comment un utilisateur dans l'administrateur système ou le rôle Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 8c11f64fd899b8be4e6c3179913787eb2c32c6c6
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="create-electronic-reporting-er-format-configurations"></a>Créer des configurations de format pour la gestion des états électroniques

[!include [task guide banner](../../includes/task-guide-banner.md)]

es étapes suivantes expliquent comment un utilisateur dans l'administrateur système ou le rôle Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER). Cette configuration de formats définira le format des documents électroniques utilisés pour traiter les paiements. Dans cet exemple, vous allez créer une configuration de format pour la société témoin, Litware, Inc. Pour effectuer ces étapes, vous devez d'abord accomplir celles de la procédure « Mettre en relation le modèle aux sources de données sélectionnées ».


## <a name="create-a-new-format-configuration"></a>Créer une configuration de format
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations des états.
3. Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) ».
4. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
5. Dans le champ Nouveau, entrez « Format basé sur le PaymentModel du modèle du paiement ».
6. Dans le champ Nom, tapez « LE SYSTÈME BACS (R-U factice) ».
    * LE SYSTÈME BACS (R-U factice)  
7. Dans le champ Description, entrez « Format de paiement fournisseur du SYSTÈME BACS (R-U factice) ».
    * Format de paiement fournisseur du SYSTÈME BACS (R-U factice)  
    * Le fournisseur de configuration actif est automatiquement entré ici. Ce fournisseur pourra mettre à jour cette configuration. D'autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.  
    * Un format spécifique de document électronique peut être défini. Laissez ce champ vide si vous souhaitez sélectionner un format au moment de l'exécution.  
8. Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.
9. Cliquez sur Créer une configuration.
    * Une nouvelle configuration client a été créée. La version temporaire peut servir à enregistrer le format de conception pour gérer des documents électroniques.  

## <a name="design-format-of-electronic-document"></a>Créer le format du document électronique
1. Cliquez sur Concepteur.
2. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
3. Dans l'arborescence, sélectionnez « Common\File ».
4. Dans le champ Nom, tapez « Xml ».
    * XML  
5. Dans le champ Encodage, tapez « UTF-8 ».
    * UTF-8  
6. Cliquez sur OK.
7. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
8. Dans l'arborescence , sélectionnez « XML\Élément ».
9. Dans le champ Nom, tapez « Message ».
    * Message  
10. Cliquez sur OK.
11. Dans l'arborescence, sélectionnez « Xml\Message ».
12. Cliquez sur Ajouter un élément.
13. Dans le champ Nom, tapez « ProcessingDate ».
    * ProcessingDate  
14. Cliquez sur OK.
15. Cliquez sur Ajouter un élément.
16. Dans le champ Nom, tapez « MessageId ».
    * MessageId  
17. Cliquez sur OK.
18. Cliquez sur Ajouter un élément.
19. Tapez « Paiements » dans le champ Nom.
    * Paiements  
20. Cliquez sur OK.
21. Dans l'arborescence, sélectionnez « Xml\Message\Paiements ».
22. Cliquez sur Ajouter un élément.
23. Dans le champ Nom, tapez « Article ».
    * Article  
24. Cliquez sur OK.
25. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».
26. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
27. Dans l'arborescence, sélectionnez « XML\Attribut ».
28. Dans le champ Nom, tapez « Id ».
    * ID  
29. Cliquez sur OK.
30. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
31. Dans l'arborescence , sélectionnez « XML\Élément ».
32. Dans le champ Nom, tapez « Fournisseur ».
    * Fournisseur  
33. Cliquez sur OK.
34. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur ».
35. Cliquez sur Ajouter un élément.
36. Tapez « Nom » dans le champ Nom.
    * Nom  
37. Cliquez sur OK.
38. Cliquez sur Ajouter un élément.
39. Dans le champ Nom, tapez « Banque ».
    * Banque  
40. Cliquez sur OK.
41. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque ».
42. Cliquez sur Ajouter un élément.
43. Tapez « RoutingNumber » dans le champ Nom.
    * RoutingNumber  
44. Cliquez sur OK.
45. Cliquez sur Ajouter un élément.
46. Dans le champ Nom, tapez « AccountNumber ».
    * Numéro de compte,  
47. Cliquez sur OK.
48. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur ».
49. Cliquez sur Copier.
50. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».
51. Cliquez sur Coller.
52. Dans le champ Nom, tapez « Payeur ».
    * Payeur  
53. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».
54. Cliquez sur Ajouter un élément.
55. Tapez « Devise » dans le champ Nom.
    * Devise  
56. Cliquez sur OK.
57. Cliquez sur Ajouter un élément.
58. Tapez « Description » dans le champ Nom.
    * Description  
59. Cliquez sur OK.
60. Cliquez sur Ajouter un élément.
61. Dans le champ Nom, tapez « TransDate ».
    * Date de transaction  
62. Cliquez sur OK.
63. Cliquez sur Ajouter un élément.
64. Dans le champ Nom, tapez « Montant ».
    * Montant  
65. Cliquez sur OK.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Préparer des composants de format pour la mise en correspondance aux éléments de modèle de données
1. Dans l'arborescence, sélectionnez « Xml\Message\ProcessingDate ».
2. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
3. Dans l'arborescence, sélectionnez « Texte\DateTime ».
4. Dans le champ Format, tapez « jj-mm-aaaa ».
    * aaaa/MM/jj  
5. Cliquez sur OK.
6. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\TransDate ».
7. Cliquez sur Ajouter DateTime.
8. Dans le champ Format, tapez « jj-mm-aaaa ».
    * aaaa/MM/jj  
9. Dans le champ de type DateTime, sélectionnez « Date »
10. Cliquez sur OK.
11. Dans l'arborescence, sélectionnez « Xml\Message\MessageId ».
12. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
13. Dans l'arborescence, sélectionnez « Texte\Chaîne ».
14. Cliquez sur OK.
15. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Nom ».
16. Cliquez sur Ajouter une chaîne.
17. Cliquez sur OK.
18. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\RoutingNumber ».
19. Cliquez sur Ajouter une chaîne.
20. Cliquez sur OK.
21. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\AccountNumber ».
22. Cliquez sur Ajouter une chaîne.
23. Cliquez sur OK.
24. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Nom ».
25. Cliquez sur Ajouter une chaîne.
26. Cliquez sur OK.
27. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\RoutingNumber ».
28. Cliquez sur Ajouter une chaîne.
29. Cliquez sur OK.
30. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\AccountNumber ».
31. Cliquez sur Ajouter une chaîne.
32. Cliquez sur OK.
33. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Devise ».
34. Cliquez sur Ajouter une chaîne.
35. Cliquez sur OK.
36. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Description ».
37. Cliquez sur Ajouter une chaîne.
38. Cliquez sur OK.
39. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Montant ».
40. Cliquez sur Ajouter une chaîne.
41. Cliquez sur OK.
42. Cliquez sur Enregistrer.
43. Fermez la page.


