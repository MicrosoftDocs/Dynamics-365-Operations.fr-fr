---
title: Créer un modèle de facture financière
description: Cette procédure décrit comment créer un modèle de facture financière.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91f2ec2f8ab21616c6a1b886ee89d6faf84023e4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "310781"
---
# <a name="create-a-free-text-invoice-template"></a>Créer un modèle de facture financière

[!include [banner](../includes/banner.md)]

Pour cette procédure, utilisez la société fictive USMF. Cette procédure est destinée à l'utilisateur chargé de gérer et de traiter des factures de comptes clients.

## <a name="create-a-template"></a>Créer un modèle

1. Accédez à Comptabilité client > Factures > Factures récurrentes > Modèles de facture financière.
    * Cet écran permet de créer des modèles de facture financière pouvant inclure des lignes de facture, des frais, un modèle de répartition comptable ainsi que des informations de compte général.  
2. Cliquez sur Nouveau pour créer un modèle de facture financière.
3. Tapez une valeur dans le champ Nom de modèle.
    * « Nom de modèle » identifie un modèle de facture financière de façon unique. Deux modèles ne peuvent pas avoir le même « Nom de modèle ».  
4. Dans le champ Description, entrez la description du groupe de modèles.
5. Développez l'onglet Lignes de facture.
6. Dans le champ Description, entrez la description de la ligne de facture.
7. Dans le champ Compte principal, sélectionnez un compte de produit.
    * Vous pouvez sélectionner le compte de transactions de contrepartie d'un crédit client pour le montant total de la facture dans la page Profils de validation client.  
8. Dans le champ Groupe de taxe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le groupe de taxe pour la ligne de facture actuelle correspond au groupe de taxe par défaut associé au compte client.  
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
10. Dans le champ Groupe de taxe d'article, sélectionnez le groupe de taxe d'article à utiliser pour la ligne de facture actuelle.
11. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
12. Dans le champ Prix unitaire, entrez ou affichez le prix par unité pour la ligne de facture.
    * Ce montant est automatiquement multiplié par la valeur indiquée dans le champ Quantité afin de déterminer le montant de la ligne de facture.  
13. Ajoutez une nouvelle ligne au modèle de facture financière.
14. Dans le champ Description, entrez la description de la ligne de facture.
15. Dans le champ Compte principal, sélectionnez un compte de produit.
    * Vous pouvez sélectionner le compte de transactions de contrepartie d'un crédit client pour le montant total de la facture dans la page Profils de validation client.  
16. Dans le champ Groupe de taxe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le groupe de taxe pour la ligne de facture actuelle correspond au groupe de taxe par défaut associé au compte client.  
17. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
18. Dans le champ Groupes de taxe d'article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Groupe de taxe d'article pour la ligne de facture actuelle.  
19. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
20. Entrez ou affichez le nombre d'unités pour la ligne de facture.
    * Ce nombre est multiplié par la valeur indiquée dans le champ Prix unitaire afin de déterminer le montant de la ligne de facture.  
21. Permet d'entrer ou d'afficher le prix par unité pour la ligne de facture. 
    * Ce montant est multiplié par la valeur indiquée dans le champ Quantité afin de déterminer le montant de la ligne de facture.  
22. Affichez et modifiez les répartitions comptables pour une ligne individuelle et toutes les lignes enfants.
    * Les répartitions comptables définissent la façon dont un montant sera pris en compte, par exemple, la manière dont le produit, la taxe ou les frais seront reportés sur une facture financière.  
23. Mettez à jour les répartitions comptables pour la ligne de facture sélectionnée.
24. Cliquez sur Fermer.

## <a name="save-a-free-text-invoice-as-a-template"></a>Enregistrer une facture financière comme modèle
Vous pouvez également enregistrer une facture financière existante comme modèle. Lorsque vous sélectionnez Enregistrer dans le modèle sous l'onglet Facture, entrez un nom et une description pour le modèle. Si un modèle portant le nom existe déjà, une notification s'affiche pour indiquer qu'un modèle portant ce nom existe déjà. Vous pouvez toujours cliquer sur OK pour le remplacer. 
