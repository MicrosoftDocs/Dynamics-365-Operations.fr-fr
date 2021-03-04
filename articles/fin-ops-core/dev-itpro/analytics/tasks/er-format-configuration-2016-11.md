---
title: ER Créer une configuration de format (novembre 2016)
description: Cette rubrique explique comment un utilisateur ayant le rôle d’administrateur système ou de développeur d’états électroniques peut créer une configuration de format pour la génération d’états électronique (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4cd3960594ab37ca867792c655cfd28dc332fa9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684761"
---
# <a name="er-create-a-format-configuration-november-2016"></a>ER Créer une configuration de format (novembre 2016)

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment un utilisateur ayant le rôle d’administrateur système ou de développeur d’états électroniques peut créer une configuration de format pour la génération d’états électronique (ER). Cette configuration de formats définira le format des documents électroniques utilisés pour traiter les paiements. Dans cet exemple, vous allez créer une configuration de format pour la société témoin, Litware, Inc. Pour effectuer ces étapes, vous devez d’abord accomplir celles de la procédure « Mettre en relation le modèle aux sources de données sélectionnées ».


## <a name="create-a-new-format-configuration"></a>Créer une configuration de format
1. Accédez à **Administration d’organisation > Espaces de travail > États électroniques**.
2. Cliquez sur **Configurations des états**.
3. Dans l’arborescence, sélectionnez **Paiements (modèle simplifié)**.
4. Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.

 > [!NOTE]
 > Si vous ne voyez pas **Créer la configuration**, vous devez activer le mode Configuration de la page **Paramètres de gestion des états électroniques**. 
 
5. Dans le champ **Nouveau**, entrez **Format basé sur le PaymentModel du modèle du paiement**.
6. Dans le champ **Nom**, tapez **LE SYSTÈME BACS (R-U factice)**.
7. Dans le champ **Description**, entrez **Format de paiement fournisseur du SYSTÈME BACS (R-U factice)**.
    * Le fournisseur de configuration actif est automatiquement entré ici. Ce fournisseur pourra mettre à jour cette configuration. D’autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.  
    * Un format spécifique de document électronique peut être défini. Laissez ce champ vide si vous souhaitez sélectionner un format au moment de l’exécution.  
8. Dans le champ **Définition du modèle de données**, entrez ou sélectionnez une valeur.
9. Cliquez sur **Créer une configuration**. Une nouvelle configuration client a été créée. La version temporaire peut servir à enregistrer le format de conception pour gérer des documents électroniques.  

## <a name="design-the-format-of-an-electronic-document"></a>Créer le format d’un document électronique
1. Cliquez sur **Concepteur**.
2. Cliquez sur **Ajouter racine** pour ouvrir la boîte de dialogue.
3. Dans l’arborescence, sélectionnez **Common\File**.
4. Dans le champ **Nom**, tapez **Xml**.
5. Dans le champ **Encodage**, tapez **UTF-8**.
6. Cliquez sur **OK**.
7. Cliquez sur **Ajouter**.
8. Dans l’arborescence, sélectionnez **XML\Élément**.
9. Dans le champ **Nom**, tapez **Message**.
10. Cliquez sur **OK**.
11. Dans l’arborescence, sélectionnez **Xml\Message**.
12. Cliquez sur **Ajouter un élément**.
13. Dans le champ **Nom**, tapez **ProcessingDate**.
14. Cliquez sur **OK**.
15. Cliquez sur **Ajouter un élément**.
16. Dans le champ Nom, tapez **MessageId**.
17. Cliquez sur **OK**.
18. Cliquez sur **Ajouter un élément**.
19. Dans le champ **Nom**, tapez **Paiements**.
20. Cliquez sur **OK**.
21. Dans l’arborescence, sélectionnez **Xml\Message\Paiements**.
22. Cliquez sur **Ajouter un élément**.
23. Dans le champ **Nom**, tapez **Article**.
24. Cliquez sur **OK**.
25. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article**.
26. Cliquez sur **Ajouter**.
27. Dans l’arborescence, sélectionnez **XML\Attribut**.
28. Dans le champ Nom, tapez **Id**.
29. Cliquez sur **OK**.
30. Cliquez sur **Ajouter**.
31. Dans l’arborescence, sélectionnez **XML\Élément**.
32. Dans le champ Nom, tapez **Fournisseur**.
33. Cliquez sur **OK**.
34. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur**.
35. Cliquez sur **Ajouter un élément**.
36. Dans le champ Nom, tapez **Nom**.
37. Cliquez sur **OK**.
38. Cliquez sur **Ajouter un élément**.
39. Dans le champ **Nom**, tapez **Banque**.
40. Cliquez sur **OK**.
41. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Banque**.
42. Cliquez sur **Ajouter un élément**.
43. Dans le champ **Nom**, tapez **RoutingNumber**.
44. Cliquez sur **OK**.
45. Cliquez sur **Ajouter un élément**.
46. Dans le champ **Nom**, tapez **AccountNumber**.
47. Cliquez sur **OK**.
48. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur**.
49. Cliquez sur **Copier**.
50. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article**.
51. Cliquez sur **Coller**.
52. Dans le champ **Nom**, tapez **Payeur**.
53. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article**.
54. Cliquez sur **Ajouter un élément**.
55. Dans le champ **Nom**, tapez **Devise**.
56. Cliquez sur **OK**.
57. Cliquez sur **Ajouter un élément**.
58. Dans le champ **Nom**, tapez **Description**.
59. Cliquez sur **OK**.
60. Cliquez sur **Ajouter un élément**.
61. Dans le champ Nom, tapez **TransDate**.
62. Cliquez sur **OK**.
63. Cliquez sur **Ajouter un élément**.
64. Dans le champ Nom, tapez **Montant**.
65. Cliquez sur **OK**.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Préparer des composants de format pour la mise en correspondance aux éléments de modèle de données
1. Dans l’arborescence, sélectionnez **Xml\Message\ProcessingDate**.
2. Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.
3. Dans l’arborescence, sélectionnez **Texte\DateTime**.
4. Dans le champ **Format**, tapez **jj-MM-aaaa**.
5. Cliquez sur **OK**.
6. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\TransDate**.
7. Cliquez sur **Ajouter DateTime**.
8. Dans le champ **Format**, tapez **jj-MM-aaaa**.
9. Dans le champ de type **DateTime**, sélectionnez **Date**.
10. Cliquez sur **OK**.
11. Dans l’arborescence, sélectionnez **Xml\Message\MessageId**.
12. Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.
13. Dans l’arborescence, sélectionnez **Texte\Chaîne**.
14. Cliquez sur **OK**.
15. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Nom**.
16. Cliquez sur **Ajouter une chaîne**.
17. Cliquez sur **OK**.
18. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Banque\RoutingNumber**.
19. Cliquez sur **Ajouter une chaîne**.
20. Cliquez sur **OK**.
21. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Banque\AccountNumber**.
22. Cliquez sur **Ajouter une chaîne**.
23. Cliquez sur **OK**.
24. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Payeur\Nom**.
25. Cliquez sur **Ajouter une chaîne**.
26. Cliquez sur **OK**.
27. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Payeur\Banque\RoutingNumber**.
28. Cliquez sur **Ajouter une chaîne**.
29. Cliquez sur **OK**.
30. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Payeur\Banque\AccountNumber**.
31. Cliquez sur **Ajouter une chaîne**.
32. Cliquez sur **OK**.
33. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Devise**.
34. Cliquez sur **Ajouter une chaîne**.
35. Cliquez sur **OK**.
36. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Description**.
37. Cliquez sur **Ajouter une chaîne**.
38. Cliquez sur **OK**.
39. Dans l’arborescence, sélectionnez **Xml\Message\Paiements\Article\Montant**.
40. Cliquez sur **Ajouter une chaîne**.
41. Cliquez sur **OK**.
42. Cliquez sur **Enregistrer**.
43. Fermez la page.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]