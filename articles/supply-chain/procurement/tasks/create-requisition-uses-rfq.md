--- 
title: "Créer une demande qui emploie un appel d'offre"
description: "Ce guide montre comment ajouter le prix et les informations sur le fournisseur à une demande d'achat à partir d'un processus d'appel d'offre."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 14eed7982041b7af7dad5453b10f07f063ba1855
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Créer une demande qui emploie un appel d'offre

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide montre comment ajouter le prix et les informations sur le fournisseur à une demande d'achat à partir d'un processus d'appel d'offre. L'exemple indiqué dans ce guide peut être utilisé dans la société fictive USMF, et vous devez être connecté en tant qu'Admin pour accomplir toutes les étapes. Les tâches de ce guide seraient généralement effectuées par des professionnels de l'approvisionnement.


## <a name="create-a-requisition"></a>Créer une demande
1. Accédez à Approvisionnement > Demandes d'achat > Demandes d'achat préparées par moi.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Date demandée, entrez une date.
5. Dans le champ Comptabilité, entrez une date.
6. Cliquez sur OK.
7. Dans le champ Motif, saisissez ou sélectionnez une valeur.
8. Cliquez sur Ajouter une ligne.
9. Dans le champ Catégorie d'approvisionnement, choisissez une catégorie dans l'arborescence, puis cliquez sur OK.
10. Dans le champ Produit, saisissez une valeur.
11. Dans le champ Quantité, entrer un numéro.
12. Saisissez ou sélectionnez une valeur dans le champ Unité.
13. Cliquez sur Enregistrer.
14. Cliquer sur Workflow pour ouvrir la boîte de dialogue.
15. Cliquez sur Soumettre.
16. Fermez la page.
17. Cliquez sur Soumettre.

## <a name="reassign-a-workflow-task"></a>Réaffecter une tâche de workflow
    * La prochaine tâche consiste à créer un appel d'offre pour obtenir des offres des fournisseurs pour le produit. Dans les données fictives de la société USMF, le workflow de demande est défini avec une règle de sorte que si un fournisseur n'est pas choisi, ou si le prix unitaire est 0 pour une ligne, une tâche est affectée à un travailleur spécifique pour créer un appel d'offre. Pour poursuivre avec ce guide, vous devez attribuer à nouveau cette tâche à un autre utilisateur (vous-même). Vous pouvez seulement le faire si vous êtes connecté en tant qu'Admin.  
1. Cliquer sur Workflow pour ouvrir la boîte de dialogue.
2. Cliquez sur Afficher l'historique.
3. Actualisez la page.
4. Développez la section Détails du suivi.
5. Dans l'arborescence, choisissez la ligne qui commence par « Workflow de ligne activé le ».
6. Cliquez sur Afficher les détails du workflow.
7. Développez la section Éléments de travail.
8. Cliquez sur Réaffecter.
9. Dans le champ Utilisateur, sélectionnez Admin.
10. Cliquez sur Réaffecter.
11. Fermez la page.
12. Fermez la page.

## <a name="create-an-rfq"></a>Créer un appel d'offre
1. Actualisez la page.
2. Cliquez sur Réponse de l'appel d'offre.
3. Sélectionnez USMF dans le champ Entité juridique acheteuse.
    * Vous devez choisir la même entité juridique qui celle de la ligne de demande.  
4. Dans la liste, marquez la ligne sélectionnée.
    * Si vous avez plusieurs lignes sur votre demande d'achat, choisissez toutes les lignes que vous voulez ajouter à l'appel d'offre.  
5. Cliquez sur OK.
6. Actualisez la page.
7. Ouvrez le Récapitulatif, puis augmentez la section Documents associés.
    * Le Récapitulatif est peut-être déjà ouvert. Recherchez l'icône dotée d'une flèche, à droite des boutons à bascule Lignes/En-tête. Si la flèche pointe vers la droite, le récapitulatif est déjà ouvert. Si la flèche pointe vers la gauche, cliquez sur le récapitulatif pour l'ouvrir.  
8. Cliquez sur le lien dans le champ Appel d'offre pour ouvrir l'appel d'offre qui vient d'être créé.
9. Cliquez sur En-tête.
10. Cliquez sur Ajouter.
11. Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.
12. Cliquez sur Ajouter.
13. Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.
14. Cliquez sur Envoyer.
15. Cliquez sur OK.
16. Cliquez sur Entrer une réponse.
17. Cliquez sur Répondre dans le volet Actions.
18. Cliquez sur Copier des données dans la réponse.
    * Cette opération copie des données, telles que la quantité et les dates, de l'appel d'offre à la réponse.  
19. Entrez un nombre dans le champ Prix unitaire.
    * C'est le prix que vous avez reçu du fournisseur. Vous pourriez également vouloir entrer des informations supplémentaires à partir du fournisseur.  
20. Cliquez sur Accepter.
21. Cliquez sur OK.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Vérifiez que le prix et le fournisseur ont été transférés dans la demande.
1. Fermez la page.
2. Cliquez sur Lignes.
3. Cliquez sur Informations associées.
4. Cliquez sur Demande d'achat.
5. Choisissez la ligne qui a été transférée à l'appel d'offre.
    * Vérifiez que le prix et le fournisseur ont été copiés dans la demande.  
6. Cliquer sur Workflow pour ouvrir la boîte de dialogue.
7. Cliquez sur Terminé.
8. Fermez la page.
9. Cliquez sur Terminé.


