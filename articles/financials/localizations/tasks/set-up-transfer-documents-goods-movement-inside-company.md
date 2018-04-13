--- 
title: "Paramétrer les documents de transfert pour le mouvement de marchandises dans une société"
description: "Cette procédure indique comment créer des documents de transfert pour le mouvement de marchandises dans une société."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2f10f627f33108b8750a1d71d24a99763178e2ef
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a>Paramétrer les documents de transfert pour le mouvement de marchandises dans une société

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment créer des documents de transfert pour le mouvement de marchandises dans une société. Cette procédure est uniquement disponible pour les entités juridiques dont l'adresse principale se situe en Lituanie. La procédure a été créée avec les données de démonstration de la société fictive DEMF, avec une adresse principale en Lituanie. Avant d'exécuter cette procédure, vous devez exécuter la procédure « Paramétrer les documents de transfert pour le mouvement de marchandises dans une société ». Cette procédure est destinée aux comptables de stock. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="create-a-transfer-order"></a>Création d'un ordre de transfert
1. Accédez à Gestion des stocks > Commandes entrantes > Ordre de transfert.
2. Cliquez sur Nouveau.
3. Dans le champ Entrepôt d'origine, saisissez ou sélectionnez une valeur.
4. Dans le champ Entrepôt de destination, saisissez ou sélectionnez une valeur.
5. Cliquez sur Ajouter.
6. Dans la liste, marquez la ligne sélectionnée.
7. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.

## <a name="enter-transportation-details-for-the-transfer-order"></a>Entrer les détails du transport pour l'ordre de transfert
1. Cliquez sur Enregistrer.
2. Dans le volet Actions, cliquez sur Expédier.
3. Cliquez sur Détails du transport.
4. Sélectionnez Oui dans le champ Imprimer les détails du transport.
5. Dans le champ Marchandises émises par, entrez ou sélectionnez une valeur.
6. Dans le champ Colis, tapez une valeur.
7. Dans le champ Niveau de risque de la charge, tapez une valeur.
8. Dans le champ Transporteur, entrez ou sélectionnez une valeur.
9. Dans le champ Modèle, entrez ou sélectionnez une valeur.
10. Dans le champ Numéro d'enregistrement, tapez une valeur.
11. Dans le champ Numéro d'enregistrement de la remorque, entrez une valeur.
12. Dans le champ Chauffeur, entrez ou sélectionnez une valeur.
13. Dans le champ Nom du chauffeur, tapez une valeur.
14. Cliquez sur Enregistrer.
15. Fermez la page.

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a>Afficher le bon de livraison pour l'ordre de transfert non validé
1. Cliquez sur Bon de livraison.
2. Cliquez sur OK.
3. Fermez la page.

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a>Afficher le bon de livraison pour l'ordre de transfert validé
1. Dans le volet Actions, cliquez sur Ordre de transfert.
2. Dans le volet Actions, cliquez sur Expédier.
3. Cliquez sur Expédier l'ordre de transfert.
4. Cliquez sur l'onglet Général.
5. Dans le champ Mettre à jour, sélectionnez une option.
6. Cliquez sur l'onglet Vue d'ensemble.
7. Tapez une valeur dans le champ Bon de livraison.
8. Cliquez sur OK.
9. Dans le volet Actions, cliquez sur Expédier.
10. Cliquez sur Bon de livraison.
11. Cliquez sur OK.


