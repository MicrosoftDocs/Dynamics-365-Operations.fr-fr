--- 
title: "Mapper un modèle de données aux sources de données sélectionnées pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur bénéficiant du rôle Administrateur système ou Développeur d'états électroniques peut mapper un modèle de données de génération d'états électronique (ER) vers des sources de donnés Dynamics 365 for Finance and Operations, Enterprise edition (novembre 2016) sélectionnées."
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 13b7fe7f7bfe24bd275428e931993aa46ecb9945
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---
# <a name="map-a-data-model-to-selected-data-sources-for-electronic-reporting-er"></a>Mapper un modèle de données aux sources de données sélectionnées pour la gestion des états électroniques (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur bénéficiant du rôle Administrateur système ou Développeur d'états électroniques peut mapper un modèle de données de génération d'états électronique (ER) vers des sources de donnés Dynamics 365 for Finance and Operations sélectionnées. Cette mise en correspondance de modèles sera utilisée ultérieurement comme source de données dans la configuration du format à utiliser pour gérer des documents de paiement électronique. Dans cet exemple, vous mettez en correspondance un modèle de données pour la société témoin, Litware, Inc. avec des sources de données. Pour effectuer ces étapes,, vous devez tout d'abord appliquer la procédure « Sélectionner des sources de données pour la mise en correspondance de modèles ».


## <a name="open-er-configurations-tree"></a>Ouvrir l'arborescence de configurations d'ER
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations.

## <a name="select-created-model-mapping"></a>Sélectionner une mise en correspondance de modèles créée
1. Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) ».
    * Vérifiez que la configuration du modèle « paiements (modèle simplifié) » a été créée à l'avance. Dans le cas contraire, arrêtez dès à présent et revenez après avoir effectué la section « Créer une configuration avec le modèle de données du domaine sélectionné » du Guide de tâche.  
2. Cliquez sur Concepteur de modèles.
3. Cliquez sur Mettre en correspondance le modèle à la source de données.
4. Sélectionnez l'enregistrement « Mise en correspondance de CT ».
    * Mise en correspondance VMT  

## <a name="bind-created-data-sources-to-data-model-elements"></a>Lier des sources de données créées à des éléments de modèles de données
1. Cliquez sur Concepteur.
2. Dans l'arborescence, sélectionnez « Date et heure de traitement(ProcessingDateTime) ».
3. Dans l'arborescence, sélectionnez « Date de traitement(ProcessingDateTime) ».
4. Cliquez sur Lier.
5. Dans l'arborescence, sélectionnez « Identification de message de paiement (MessageIdentification) ».
6. Dans l'arborescence , développer « Transactions ».
7. Dans l'arborescence, sélectionnez « Transactions\Numéro de lot du journal(JournalNum) ».
8. Cliquez sur Lier.
9. Dans l'arborescence, sélectionnez « Paiements ».
10. Dans l'arborescence, sélectionnez « Transactions ».
11. Cliquez sur Lier.
12. Dans l'arborescence , développez « Paiements=Transactions ».
13. Dans l'arborescence , développez « Paiements=Transactions\Créditeur ».
14. Dans l'arborescence , développez « Paiements=Transactions\Créditeur\Compte ».
15. Dans l'arborescence, sélectionnez « Paiements=Transactions\Créditeur\Compte\Code devise(Currency) ».
16. Dans l'arborescence , développez « Transactions\vendBankAccountInTransactionCompany() ».
17. Dans l'arborescence, sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode) ».
18. Cliquez sur Lier.
19. Dans l'arborescence, sélectionnez « Paiements=Transactions\Créditeur\Compte\Code IBAN(IBAN) ».
20. Dans l'arborescence , sélectionnez « Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN) ».
21. Cliquez sur Lier.
22. Dans l'arborescence, sélectionnez « Paiements=Transactions\Créditeur\Compte\Numéro ».
23. Dans l'arborescence , sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Numéro de compte bancaire(AccountNum) ».
24. Cliquez sur Lier.
25. Dans l'arborescence , développez « Paiements=Transactions\Créditeur\Agent ».
26. Dans l'arborescence, sélectionnez « Paiements=Transactions\Créditeur\Agent\Nom ».
27. Dans l'arborescence , sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Nom ».
28. Cliquez sur Lier.
29. Dans l'arborescence, sélectionnez « Paiements=Transactions\Créditeur\Agent\Numéro de routage(RoutingNumber) ».
30. Dans l'arborescence , sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Numéro de routage(RegistrationNum) ».
31. Cliquez sur Lier.
32. Dans l'arborescence, sélectionnez « Paiements=Transactions\Créditeur\Agent\Code SWIFT(SWIFT) ».
33. Dans l'arborescence, sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Code SWIFT(SWIFTNo) ».
34. Cliquez sur Lier.
35. Dans l'arborescence, sélectionnez « Paiements=Transactions\Créditeur\Nom ».
36. Dans l'arborescence , développez « Transactions\findVendTable() ».
37. Dans l'arborescence , sélectionnez « Transactions\findVendTable()name() ».
38. Cliquez sur Lier.
39. Dans l'arborescence, sélectionnez « Paiements=Transactions\Code devise(Currency) ».
40. Dans l'arborescence, développez « Transactions\>Relations ».
41. Dans l'arborescence, développez « Transactions\>Relations\Table des devises(Currency) ».
42. Dans l'arborescence, sélectionnez « Transactions\>Relations\Table des devises(Currency)\Code devis (CurrencyCodeISO) ».
43. Cliquez sur Lier.
44. Dans l'arborescence , développez « Paiements=Transactions\Débiteur ».
45. Dans l'arborescence , développez « Paiements=Transactions\Débiteur\Compte ».
46. Dans l'arborescence, sélectionnez « Paiements=Transactions\Débiteur\Compte\Code devise(Currency) ».
47. Dans l'arborescence, sélectionnez « Compte bancaire(BankAccount) ».
48. Dans l'arborescence, développez « Compte bancaire(BankAccount) ».
49. Dans l'arborescence, sélectionnez « Compte bancaire(BankAccount)\Devise(CurrencyCode) ».
50. Cliquez sur Lier.
51. Dans l'arborescence, sélectionnez « Compte bancaire(BankAccount)\IBAN ».
52. Dans l'arborescence, sélectionnez « Paiements=Transactions\Débiteur\Compte\Code IBAN(IBAN) ».
53. Cliquez sur Lier.
54. Dans l'arborescence, sélectionnez « Paiements=Transactions\Débiteur\Compte\Numéro ».
55. Dans l'arborescence, sélectionnez « Compte bancaire(BankAccount\Numéro de compte bancaire(AccountNum) ».
56. Cliquez sur Lier.
57. Dans l'arborescence , développez « Paiements=Transactions\Débiteur\Agent ».
58. Dans l'arborescence, sélectionnez « Paiements=Transactions\Débiteur\Agent\Nom ».
59. Dans l'arborescence, sélectionnez « Compte bancaire(BankAccount)\Nom ».
60. Cliquez sur Lier.
61. Dans l'arborescence, sélectionnez « Paiements=Transactions\Débiteur\Agent\Numéro de routage(RoutingNumber) ».
62. Dans l'arborescence, sélectionnez « Compte bancaire(BankAccount\Numéro de routage(RegistrationNum) ».
63. Cliquez sur Lier.
64. Dans l'arborescence, sélectionnez « Paiements=Transactions\Débiteur\Agent\Code SWIFT(SWIFT) ».
65. Dans l'arborescence, sélectionnez « Compte bancaire(BankAccount)\Code SWIFT(SWIFTNo) ».
66. Cliquez sur Lier.
67. Dans l'arborescence, sélectionnez « Paiements=Transactions\Débiteur\Nom ».
68. Dans l'arborescence, sélectionnez « Informations sur la société(Company) ».
69. Dans l'arborescence, développez « Informations sur la société(Company) ».
70. Dans l'arborescence, sélectionnez « Informations sur la société(Company)\Nom ».
71. Cliquez sur Lier.
72. Dans l'arborescence, sélectionnez « Paiements=Transactions\Description ».
73. Dans l'arborescence, sélectionnez « Transactions\Description(Txt) ».
74. Cliquez sur Lier.
75. Dans l'arborescence, sélectionnez « Transactions \Code d'identification de bout en bout(End2EndID) ».
76. Dans l'arborescence, sélectionnez « Transactions\$EndToEndID ».
77. Cliquez sur Lier.
78. Dans l'arborescence, sélectionnez « Transactions\Montant instruit(InstructedAmount) ».
79. Dans l'arborescence, sélectionnez « Transactions\$Amount ».
80. Cliquez sur Lier.
81. Dans l'arborescence, sélectionnez « Transactions\Date de transaction(TransactionDate) ».
82. Dans l'arborescence, sélectionnez « Transactions\Date(TransDate) ».
83. Cliquez sur Lier.

## <a name="validate-created-mapping"></a>Valider une mise en correspondance créée
1. Cliquez sur Valider.
    * Validez la nouvelle mise en correspondance pour vous assurer que toutes les liaisons sont correctes.  
2. Cliquez sur la flèche pour développer ou réduire la section Liste des erreurs.
3. Cliquez sur Enregistrer.
4. Fermez la page.
5. Fermez la page.
6. Fermez la page.

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a>Modifier le statut de la version actuelle de la configuration du modèle
1. Cliquez sur Modifier le statut.
    * Modifiez le statut de la configuration du modèle conçue : remplacez Brouillon par Terminé pour le rendre disponible pour la conception de format de paiement.  
2. Cliquez sur Terminé.
    * Sélectionnez Terminer.  
3. Dans le champ Description, entrez une valeur.
    * Par exemple, « version 1 ».  
4. Cliquez sur OK.
5. Sélectionnez la version terminée de la configuration actuelle.
    * Notez que la configuration créée est enregistrée comme version 1 terminée.  


