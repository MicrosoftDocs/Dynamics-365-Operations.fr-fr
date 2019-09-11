---
title: Créer et acquérir des actifs à partir de la comptabilité fournisseur
description: Ce guide de tâche décrit la création et l'acquisition d'une immobilisation avec le processus d'achat.
author: saraschi2
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 025639e6e5bdc6b95e9c496f11f29ed8ec8d388c
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914674"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Créer et acquérir des actifs à partir de la comptabilité fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche décrit la création et l'acquisition d'une immobilisation avec le processus d'achat.  Il utilise les données de démonstration de la société fictive USMF et les fonctions de comptable et de commis à la comptabilité fournisseur.


## <a name="set-fixed-assets-parameters"></a>Définir les paramètres des immobilisations
1. Dans le **volet de navigation** accédez à **Modules > Immobilisations > Paramétrage > Paramètres des immobilisations**.
2. Développez l'organisateur **Commandes fournisseur**.
3. Activez la case à cocher **Autoriser l'acquisition d'actifs à partir d'Achats**.
4. Activez la case à cocher **Créer un actif lors de la validation de l'accusé de réception des marchandises ou de la facture**.

## <a name="create-a-new-vendor-invoice"></a>Créer une facture fournisseur
1. Dans le **Volet de navigation**, allez dans **Modules > Comptabilité fournisseur > Espaces de travail > Saisie de facture fournisseur**.
2. Cliquez sur **Nouvelle facture fournisseur**.
3. Dans le champ **Compte de facturation**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Dans le champ **Nombre**, tapez une valeur.
6. Entrez une date dans le champ **Date de validation**.
7. Cliquez sur **Ajouter une ligne**.
8. Dans le champ **Numéro d'article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. Les articles non stockés ou les catégories d'approvisionnement peuvent être utilisés pour l'acquisition d'immobilisation.  
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
10. Entrez un nombre dans le champ **Quantité**. Une ligne de facture crée une seule immobilisation, indépendamment de la quantité. La valeur contenue dans le champ de quantité de la facture sera transférée vers la quantité d'immobilisation.  
11. Entrez un nombre dans le champ **Prix unitaire**.
12. Développez le raccourci **Détails de ligne**.
13. Cliquez sur l'onglet **Immobilisation**.
14. Activez la case à cocher **Créer une nouvelle immobilisation**.
15. Dans le champ **Groupe d'immobilisations**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
16. Dans la liste, sélectionnez le groupe d'immobilisations à utiliser lors de la création de la nouvelle immobilisation.
17. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
18. Cliquez sur **Valider**. L'immobilisation est créée et acquise lors de la validation de la facture.  

