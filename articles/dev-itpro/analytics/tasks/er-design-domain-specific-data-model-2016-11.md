--- 
title: "Concevoir un modèle de données spécifique au domaine pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle de données pour les documents de paiement électronique."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fadc5bc54654faf9e91e0831bdd0ff087cea3164
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="design-a-domain-specific-data-model-for-electronic-reporting-er"></a>Concevoir un modèle de données spécifique au domaine pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle de données pour les documents de paiement électronique. Ce modèle de données sera utilisé ultérieurement comme source de données quand vous créerez le format des documents de paiement.



Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés. Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Sélectionnez le fournisseur de configuration pour la société fictive, « Litware, Inc ». Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».  
2. Cliquez sur Configurations des états.
    * Vous allez créer une configuration qui contient un modèle de données pour les documents de paiement électronique. Ce modèle de données sera utilisé ultérieurement comme source de données quand vous allez créer le format pour les documents de paiement.  

## <a name="create-a-new-data-model-configuration"></a>Créer une configuration de modèle de données
1. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
2. Tapez « Paiements (modèle simplifié) » dans le champ Nom.
    * Paiements (modèle simplifié)  
3. Tapez « Configuration du modèle de paiement » dans le champ Description.
    * Configuration du modèle de paiement  
    * Le fournisseur de configuration actif est automatiquement entré ici. Ce fournisseur pourra mettre à jour cette configuration. D'autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.  
4. Cliquez sur le bouton « Créer la configuration » pour terminer la tâche de création de la configuration.

## <a name="create-a-data-model"></a>Créer un modèle de données
    * Vous créez un modèle de données pour la configuration sélectionnée. Cette version de configuration aura un statut de brouillon.  
1. Cliquez sur Concepteur.

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a>Définir la structure d'une partie qui participe à un processus de paiement
1. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
2. Dans le champ Nom, tapez « Partie ».
    * Partie  
3. Cliquez sur Ajouter.
4. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
5. Tapez « Nom » dans le champ Nom.
    * Nom  
6. Sélectionnez « Chaîne » dans le champ Type d'article.
7. Cliquez sur Ajouter.
8. Dans le champ Rechercher, tapez « Partie ».
    * Partie  
9. Cliquez sur Précédent

## <a name="define-the-bank-structure-for-this-model"></a>Définir la structure de la banque pour ce modèle
1. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
2. Tapez « Agent » dans le champ Nom.
    * Agent ;  
3. Sélectionnez « Enregistrement » dans le champ Type d'article.
4. Cliquez sur Ajouter.
5. Dans le champ Description, entrez « Institution financière (une banque, par exemple) chargée d'un compte de la partie (débiteur/créditeur) ».
    * Institution financière (une banque, par exemple) chargée d'un compte de la partie (débiteur/créditeur).  
6. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
7. Tapez « Nom » dans le champ Nom.
    * Nom  
8. Sélectionnez « Chaîne » dans le champ Type d'article.
9. Cliquez sur Ajouter.
10. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
11. Tapez SWIFT dans le champ Nom.
    * SWIFT  
12. Cliquez sur Ajouter.
13. Dans le champ Description, entrez « Code d'identification de la banque ».
    * Code d'identification de la banque  
14. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
15. Tapez « RoutingNumber » dans le champ Nom.
    * RoutingNumber  
16. Cliquez sur Ajouter.
17. Dans le champ Description, entrez « Numéro d'acheminement ».
    * Numéro d'acheminement  
18. Cliquez sur Précédent

## <a name="define-the-bank-account-structure-for-this-model"></a>Définir la structure de compte de la banque pour ce modèle
1. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
2. Tapez « Compte » dans le champ Nom.
    * Compte  
3. Sélectionnez « Enregistrement » dans le champ Type d'article.
4. Cliquez sur Ajouter.
5. Dans le champ Description, entrez « Identification d'un compte d'une partie dans une institution financière (une banque, par exemple) ».
    * Identification d'un compte d'une partie dans une institution financière (une banque, par exemple).  
6. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
7. Tapez « Devise » dans le champ Nom.
    * Devise  
8. Sélectionnez « Chaîne » dans le champ Type d'article.
9. Cliquez sur Ajouter.
10. Dans le champ Description, entrez « Code devise ».
    * Code devise  
11. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
12. Tapez « Numéro » dans le champ Nom.
    * Numéro  
13. Cliquez sur Ajouter.
14. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
15. Tapez « IBAN » dans le champ Nom.
    * IBAN  
16. Cliquez sur Ajouter.
17. Dans le champ Description, entrez « Numéro de compte bancaire international ».
    * Numéro de compte bancaire international  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a>Définir la structure du message de paiement pour le type de virement.
1. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
2. Dans le nœud Nouveau sous forme de champ, entrez « Racine du modèle ».
3. Tapez « CustomerCreditTransferInitiation » dans le champ Nom.
    * CustomerCreditTransferInitiation  
4. Cliquez sur Ajouter.
5. Dans le champ Rechercher, tapez « CustomerCreditTransferInitiation ».
    * CustomerCreditTransferInitiation  
6. Cliquez sur Précédent
7. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
8. Tapez « MessageIdentification » dans le champ Nom.
    * MessageIdentification  
9. Cliquez sur Ajouter.
10. Dans le champ Description, entrez « Référence point à point affectée par le donneur d'ordre (et envoyée à la partie suivante) afin d'identifier le message ».
    * Référence point à point affectée par le donneur d'ordre et envoyée à la partie suivante dans la chaîne afin d'identifier le message.  
11. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
12. Tapez « ProcessingDateTime » dans le champ Nom.
    * ProcessingDateTime  
13. Sélectionnez « DateTime » dans le champ Type d'article.
14. Cliquez sur Ajouter.
15. Dans le champ Description, entrez « Date et heure de création du message de paiement ».
    * Date et heure de création du message de paiement  
16. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
    * Définir la structure de transaction de paiement pour ce modèle.  
17. Tapez « Paiements » dans le champ Nom.
    * Paiements  
18. Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.
19. Cliquez sur Ajouter.
20. Dans le champ Description, entrez « Lignes de paiement du message actuel ».
    * Lignes de paiement du message actuel  
21. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
22. Tapez « Créancier » dans le champ Nom.
    * Créancier  
23. Sélectionnez « Enregistrement » dans le champ Type d'article.
24. Cliquez sur Ajouter.
25. Dans le champ Description, entrez « Partie à laquelle un montant est dû ».
    * Partie à laquelle un montant est dû.  
26. Cliquez sur Basculer la référence d'élément.
27. Dans le champ Rechercher, tapez « Partie ».
    * Partie  
28. Cliquez sur Suivant
29. Cliquez sur OK.
30. Dans le champ Rechercher, tapez « Paiements ».
    * Paiements  
31. Cliquez sur Suivant
32. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
33. Tapez « Débiteur » dans le champ Nom.
    * Débiteur  
34. Cliquez sur Ajouter.
35. Dans le champ Description, entrez « Partie qui doit une somme d'argent au créancier (final) ».
    * Partie qui doit une somme d'argent au créancier (final).  
36. Cliquez sur Basculer la référence d'élément.
37. Dans le champ Rechercher, tapez « Partie ».
    * Partie  
38. Cliquez sur Suivant
39. Cliquez sur OK.
40. Cliquez sur Suivant
41. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
42. Tapez « Description » dans le champ Nom.
    * Description  
43. Sélectionnez « Chaîne » dans le champ Type d'article.
44. Cliquez sur Ajouter.
45. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
46. Tapez « Devise » dans le champ Nom.
    * Devise  
47. Cliquez sur Ajouter.
48. Dans le champ Description, entrez « Code devise ».
    * Code devise  
49. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
50. Tapez « TransactionDate » dans le champ Nom.
    * TransactionDate  
51. Sélectionnez « Date » dans le champ Type d'article.
52. Cliquez sur Ajouter.
53. Dans le champ Description, entrez « Date de transaction ».
    * Date de transaction  
54. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
55. Tapez « InstructedAmount » dans le champ Nom.
    * InstructedAmount  
56. Sélectionnez « Réel » dans le champ Type d'article.
57. Cliquez sur Ajouter.
58. Dans le champ Description, entrez « Montant à transférer entre le débiteur et le créancier, avant déduction des frais. Le montant doit être exprimé dans la devise choisie par la partie qui prend l'initiative.
    * Montant à transférer entre le débiteur et le créancier, avant déduction des frais. Le montant doit être exprimé dans la devise choisie par la partie qui prend l'initiative.  
59. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
60. Tapez « End2EndID » dans le champ Nom.
    * End2EndID  
61. Sélectionnez « Chaîne » dans le champ Type d'article.
62. Cliquez sur Ajouter.
63. Dans le champ Description, entrez « Identification unique affectée par la partie qui prend l'initiative. Cette identification est transmise telle quelle tout au long de la chaîne de bout en bout. »
    * Identification unique affectée par la partie qui prend l'initiative. Cette identification est transmise telle quelle tout au long de la chaîne de bout en bout.  
64. Tapez « PaymentModel » dans le champ Nom.
    * Le nom PaymentModel s'aligne avec les interfaces prédéfinies des écrans de paiement.  
65. Cliquez sur Enregistrer.
66. Fermez la page.


