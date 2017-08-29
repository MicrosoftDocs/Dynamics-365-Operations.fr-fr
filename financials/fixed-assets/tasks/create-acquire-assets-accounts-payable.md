--- 
title: "Créer et acquérir des actifs à partir de la comptabilité fournisseur"
description: "Ce guide de tâche décrit la création et l'acquisition d'une immobilisation avec le processus d'achat."
author: saraschi2
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f814d20bc16bb3334ae4bc449cc0d45843487023
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Créer et acquérir des actifs à partir de la comptabilité fournisseur

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche décrit la création et l'acquisition d'une immobilisation avec le processus d'achat.  Il utilise les données de démonstration de la société fictive USMF et les fonctions de comptable et de commis à la comptabilité fournisseur.


## <a name="set-fixed-assets-parameters"></a>Définir les paramètres des immobilisations
1. Accédez à Immobilisations > Paramétrage > Paramètres des immobilisations.
2. Développez ou réduisez la section Commandes fournisseur.
3. Activez la case à cocher Autoriser l'acquisition d'actifs à partir d'Achats.
4. Activez la case à cocher Créer un actif lors de la validation de l'accusé de réception des marchandises ou de la facture.

## <a name="create-a-new-vendor-invoice"></a>Créer une facture fournisseur
1. Accédez à Comptabilité fournisseur > Espaces de travail > Saisie de facture fournisseur.
2. Cliquez sur Nouvelle facture fournisseur.
3. Dans le champ Compte de facturation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Tapez une valeur dans le champ Nombre.
6. Entrez une date dans le champ Date de validation.
7. Cliquez sur Ajouter une ligne.
8. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Les articles non stockés ou les catégories d'approvisionnement peuvent être utilisés pour l'acquisition d'immobilisation.  
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
10. Dans le champ Quantité, entrer un numéro.
    * Une ligne de facture crée une seule immobilisation, indépendamment de la quantité.  La valeur contenue dans le champ de quantité de la facture sera transférée vers la quantité d'immobilisation.  
11. Entrez un nombre dans le champ Prix unitaire.
12. Développez ou réduisez la section Détails de ligne.
13. Cliquez sur l'onglet Immobilisation.
14. Activez la case à cocher Créer une nouvelle immobilisation.
15. Dans le champ Groupe d'immobilisations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
16. Dans la liste, sélectionnez le groupe d'immobilisations à utiliser lors de la création de la nouvelle immobilisation.
17. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
18. Cliquez sur Valider.
    * L'immobilisation est créée et acquise lors de la validation de la facture.  


