---
title: Définir les schémas de fidélité
description: Cette procédure décrit comment définir un plan de fidélité.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb1afb0ebce742fa2f6accd65e553df6607107a4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972278"
---
# <a name="define-loyalty-schemes"></a>Définir les schémas de fidélité

[!include [banner](../includes/banner.md)]

Cette procédure décrit comment définir un plan de fidélité. Les plans de fidélité sont des règles de gain ou de remboursement pour un programme de fidélité. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > Clients > Fidélité > Programmes de fidélité.
2. Cliquez sur Nouveau.
3. Dans le champ ID programme, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Vous pouvez définir plusieurs plans de fidélité pour un programme de fidélité. Les plans de fidélité peuvent s'appliquer à tous les canaux ou uniquement à un sous-ensemble de canaux.  
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Cliquez sur Enregistrer.
9. Cliquez sur Ajouter une ligne.
10. Dans le champ Type d'activité, sélectionnez une option.
    * Sélectionnez Acheter des produits par montant si vous souhaitez que les clients obtiennent des récompenses en fonction du montant dépensé. Sélectionnez Acheter des produits par quantité si vous souhaitez que les clients obtiennent des récompenses en fonction du nombre de produits achetés.  Sélectionnez Nombre de transactions de vente si vous souhaitez que les clients obtiennent des récompenses pour chaque transaction de vente, indépendamment de ce qu'il ont acheté ou du montant dépensé.  
    * Permet de sélectionner une catégorie. La catégorie limite les produits auxquels cette règle de gain s'applique.  
    * Si vous souhaitez que la règle de gain s'applique à tous les produits, laissez ce champ vide.  
11. Dans le champ Montant/quantité de l'activité, saisissez un nombre.
    *  Pour le type d'activité Nombre de transactions de vente, vous devez toujours utiliser la valeur « 1,0 ». Pour les types d'activités Acheter des produits par montant ou Acheter des produits par quantité, toute transaction inférieure à la valeur saisie ne déclenche pas la règle de gain. Par exemple, si le type d'activité est Acheter des produits par montant et que vous saisissez « 10.00 », une transaction de vente pour « 9.00 » ne génère pas de récompenses pour cette règle de gain.  
12. Dans le champ Devise de l'activité, tapez une valeur.
13. Dans le champ ID de point de récompense, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
14. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
15. Dans le champ Points de récompense, saisissez un nombre.
    * Les points de récompense de type Montant enregistrent les montants obtenus avec les décimales. Par exemple, si la règle de gain indique 1 point de récompense obtenu pour chaque dollar canadien dépensé et que le client dépense 1,25 dollar canadien, il obtiendra 1,25 point de récompense. Les points de récompense de type Quantité enregistrent les montants obtenus en tant qu'entiers. Si on prend l'exemple où la règle de gain indique 1 point de récompense obtenu pour chaque dollar canadien dépensé et que le client dépense 1,25 dollar canadien, il obtiendra 1,0 point de récompense.  
16. Cliquez sur Enregistrer.
17. Cliquez sur Ajouter une ligne.
    * Les règles de remboursement sont utilisées lorsque le mode de paiement de fidélité est utilisé.  
18. Dans le champ ID de point de récompense, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Seuls les points de récompense remboursables sont affichés.  
19. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
20. Dans le champ Points de récompense, saisissez un nombre.
21. Dans le champ Type de remboursement, sélectionnez une option.
    * Lorsque vous sélectionnez l'option Montant du paiement, le champ Montant ou Quantité est considéré comme une valeur de devise. Dans ce cas, la quantité de points de récompense utilisés par devise de paiement est un taux fixe. Lorsque vous sélectionnez l'option Paiement en fonction de la quantité, le champ Montant ou Quantité est considéré comme une valeur de quantité. Dans ce cas, la quantité de points de récompense utilisés par quantité d'article est un taux fixe. Toutefois, le montant exprimé dans la devise peut varier si le prix des articles payés avec des points de récompense de fidélité varie pour la même quantité. Le type de remboursement Remise sous forme de points de fidélité est valide uniquement si la clé de configuration des fonctions spécifiques à un pays ou une région est activée pour la Russie et si les profils de fonctionnalité de PDV présentent le code ISO « RU ».  
    * Permet de sélectionner une catégorie. La catégorie limite les produits auxquels cette règle de remboursement s'applique.  
    * Si vous souhaitez que la règle de remboursement s'applique à tous les produits, laissez ce champ vide.  
22. Dans le champ Montant ou quantité, entrez un nombre.
23. Tapez une valeur dans le champ Devise.
24. Cliquez sur Enregistrer.
25. Cliquez sur Ajouter une ligne.
    * Sélectionnez un ou plusieurs nœuds dans la liste Nœuds d'organisation disponibles et déplacez-les vers la liste Nœuds d'organisation sélectionnés en cliquant sur la flèche entre les deux listes.  
26. Cliquez sur OK.
27. Cliquez sur Enregistrer.
    * Lorsque vous modifiez les canaux d'un programme de fidélité, vous devez exécuter l'option Traiter les programmes de fidélité. Ainsi, les programmes de fidélité des canaux seront mis à jour.  

