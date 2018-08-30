--- 
title: "Mapper les composants des formats à des éléments de modèle de données"
description: "La procédure suivante explique comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut mettre en correspondance des éléments de modèle de données aux composants de la configuration de la gestion des états électroniques, qui définit un format de document électronique pour le domaine de paiements de l'entreprise."
author: NickSelin
manager: AnnBe
ms.date: 02/27/2017
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
ms.openlocfilehash: e065cfbfc645bb7ac48134fe43d87bec013e8c81
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="map-the-components-of-formats-to-data-model-elements"></a>Mapper les composants des formats à des éléments de modèle de données

[!include [task guide banner](../../includes/task-guide-banner.md)]

La procédure suivante explique comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut mettre en correspondance des éléments de modèle de données aux composants de la configuration de la gestion des états électroniques, qui définit un format de document électronique pour le domaine de paiements de l'entreprise. Ce format sera utilisé ultérieurement pour générer des documents électroniques pour traiter les paiements. Dans cet exemple, vous créerez une configuration de format pour la société fictive, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les fournisseurs de configurations ER sont partagés pour toutes les sociétés. Pour mener à bien ces étapes, vous devez d'abord effectuer les étapes du Guide de tâche « Créer une configuration de format ».


## <a name="select-a-format-configuration"></a>Sélectionner une configuration de format
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations des états.
3. Dans l'arborescence, développez « Paiements (modèle simplifié) ».
4. Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) »\BACS (nom fictif britannique) ».
5. Cliquez sur Concepteur.

## <a name="map-format-components-to-data-model-elements"></a>Mettre en correspondance des composants de format aux éléments de modèle de données
1. Cliquez sur Développer/réduire.
2. Cliquez sur l'onglet Mise en relation.
3. Dans l'arborescence , développez « model ».
4. Dans l'arborescence, sélectionnez « Xml\Message\ProcessingDate\DateTime ».
5. Dans l'arborescence, sélectionnez « modèle\ProcessingDateTime »
6. Cliquez sur Lier.
7. Dans l'arborescence, sélectionnez « Xml\Message\MessageId\Chaîne ».
8. Dans l'arborescence, sélectionnez « modèle\MessageIdentification ».
9. Cliquez sur Lier.
10. Dans l'arborescence, développez model\Payments.
11. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Montant\Chaîne ».
12. Dans l'arborescence, sélectionnez « modèle\Paiements\InstructedAmount ».
13. Cliquez sur Lier.
14. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\TransDate\DateTime ».
15. Dans l'arborescence, sélectionnez « modèle\Paiements\TransactionDate ».
16. Cliquez sur Lier.
17. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Description\Chaîne ».
18. Dans l'arborescence, sélectionnez « modèle\Paiements\Description ».
19. Cliquez sur Lier.
20. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Devise\Chaîne ».
21. Dans l'arborescence, sélectionnez modèle\Paiements\Devise.
22. Cliquez sur Lier.
23. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\ID ».
24. Dans l'arborescence, sélectionnez « modèle\Paiements\End2EndID ».
25. Cliquez sur Lier.
26. Dans l'arborescence , développez « modèle\Paiements\Créditeur ».
27. Dans l'arborescence , développez « modèle\Paiements\Créditeur\Compte ».
28. Dans l'arborescence , développez « modèle\Paiements\Créditeur\Agent ».
29. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Nom\Chaîne ».
30. Dans l'arborescence, sélectionnez « modèle\Paiements\Créditeur\Nom ».
31. Cliquez sur Lier.
32. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\RoutingNumber\Chaîne ».
33. Dans l'arborescence, sélectionnez « Modèle\Paiements\Créditeur\Agent\RoutingNumber ».
34. Cliquez sur Lier.
35. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\AccountNumber\Chaîne ».
36. Dans l'arborescence, sélectionnez « modèle\Paiements\Créditeur\Compte\Numéro ».
37. Cliquez sur Lier.
38. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Nom\Chaîne ».
39. Dans l'arborescence , développez « modèle\Paiements\Débiteur ».
40. Dans l'arborescence , développez « modèle\Paiements\Débiteur\Compte ».
41. Dans l'arborescence , développez « modèle\Paiements\Débiteur\Agent ».
42. Dans l'arborescence, sélectionnez « modèle\Paiements\Débiteur\Nom ».
43. Cliquez sur Lier.
44. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\RoutingNumber\Chaîne ».
45. Dans l'arborescence, sélectionnez « modèle\Paiements\Débiteur\Agent\RoutingNumber ».
46. Cliquez sur Lier.
47. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\AccountNumber\Chaîne ».
48. Dans l'arborescence, sélectionnez « modèle\Paiements\Débiteur\Compte\Numéro ».
49. Cliquez sur Lier.
50. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».
51. Dans l'arborescence, sélectionnez model\Payments.
52. Cliquez sur Lier.
53. Cliquez sur Enregistrer.

## <a name="validate-format-mapping"></a>Valider une mise en correspondance de format
1. Cliquez sur Valider.
    * Validez la nouvelle mise en correspondance pour vous assurer que toutes les liaisons sont correctes.  
2. Fermez la page.

## <a name="change-status-of-the-current-version-of-format-configuration"></a>Modifier le statut de la version actuelle de la configuration du format
    * Dans les étapes suivantes, vous modifierez le statut de la configuration de format de Brouillon sur Terminé pour la rendre disponible pour la génération de documents de paiement.  
1. Cliquez sur Modifier le statut.
2. Cliquez sur Terminé.
3. Dans le champ Description, entrez une valeur.
    * Par exemple, « version 1 ».  
4. Cliquez sur OK.
5. Sélectionnez une version terminée de la configuration actuelle.
    * Notez que la configuration est enregistrée comme version terminée 1.1 : version 1 du format selon la version 1 du modèle de données.  

## <a name="define-effective-date-for-completed-version-of-format"></a>Définir la date d'effet de la version du format terminée
    * Chaque version de format peut être configurée comme disponible pour l'utilisation à partir d'une certaine date. Lorsque plusieurs versions de format sont actives à une certaine date, le format le plus récent (selon le numéro de version) est activé pour l'utilisation. La valeur de date de session est utilisée pour la sélection de la version appropriée.  

## <a name="restrict-access-to-created-format-from-companies"></a>Limiter l'accès au format créé des sociétés
1. Développez la section Codes pays/région ISO.
    * Chaque accès au format peut être limité en identifiant les pays/régions particuliers dans lesquels un format s'applique. Lorsque la liste de pays/régions pour le format spécifique est vide, ce format peut être utilisé dans n'importe quelle société. Lorsque certains codes pays/région ISO sont insérés dans la liste de pays/régions, le format ne peut être utilisé que pour des sociétés pour lesquelles l'adresse principale se trouve dans le pays/la région.  


