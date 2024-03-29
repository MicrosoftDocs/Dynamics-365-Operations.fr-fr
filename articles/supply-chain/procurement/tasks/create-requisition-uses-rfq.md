---
title: Créer une demande qui emploie un appel d’offre
description: Cet article explique comment ajouter le prix et les informations sur le fournisseur à une demande d’achat à partir d’un processus d’appel d’offre.
author: GalynaFedorova
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ecde250e3517464611b68fe3c960bfbfdf06319
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846009"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Créer une demande qui emploie un appel d’offre

[!include [banner](../../includes/banner.md)]

Cet article explique comment ajouter le prix et les informations sur le fournisseur à une demande d’achat à partir d’un processus d’appel d’offre. L’exemple indiqué dans ce guide peut être utilisé dans la société fictive USMF, et vous devez être connecté en tant qu’Admin pour accomplir toutes les étapes. Les tâches de ce guide seraient généralement effectuées par des professionnels de l’approvisionnement.


## <a name="create-a-requisition"></a>Créer une demande
1. Dans le volet de navigation allez dans **Modules > Approvisionnement > Demandes d’achat > Demandes d’achat préparées par moi**.
2. Sélectionnez **Nouveau**.
3. Tapez une valeur dans le champ **Nom**.
4. Dans le champ **Date demandée**, entrez une date.
5. Dans le champ **Date comptable**, entrez une date.
6. Cliquez sur **OK**.
7. Saisissez ou sélectionnez une valeur dans le champ **Motif**.
8. Sélectionnez **Ajouter la ligne**.
9. Dans le champ **Catégorie d’approvisionnement**, choisissez une catégorie dans l’arborescence, puis cliquez sur **OK**.
10. Dans le champ **Nom du produit**, saisissez une valeur.
11. Entrez un nombre dans le champ **Quantité**.
12. Saisissez ou sélectionnez une valeur dans le champ **Unité**.
13. Sélectionnez **Enregistrer**.
14. Sélectionnez **Workflow** pour ouvrir la boîte de dialogue.
15. Sélectionnez **Soumettre**.
16. Fermez la page.
17. Sélectionnez **Soumettre**.

## <a name="reassign-a-workflow-task"></a>Réaffecter une tâche de workflow
La prochaine tâche consiste à créer un appel d’offre pour obtenir des offres des fournisseurs pour le produit. Dans les données fictives de la société USMF, le workflow de demande est défini avec une règle de sorte que si un fournisseur n’est pas choisi, ou si le prix unitaire est 0 pour une ligne, une tâche est affectée à un travailleur spécifique pour créer un appel d’offre. Pour poursuivre avec ce guide, vous devez attribuer à nouveau cette tâche à un autre utilisateur (vous-même). Vous pouvez seulement le faire si vous êtes connecté en tant qu’Admin.  

1. Sélectionnez **Workflow** pour ouvrir la boîte de dialogue.
2. Sélectionnez **Afficher l’historique**.
3. Actualisez la page.
4. Développez la section **Détails du suivi**.
5. Dans l’arborescence, choisissez la ligne qui commence par « Workflow de ligne activé le ».
6. Sélectionnez **Afficher les détails du flux de travail**.
7. Développez la section **Éléments de travail**.
8. Sélectionnez **Réaffecter**.
9. Dans le champ **Utilisateur**, sélectionnez **Admin**.
10. Sélectionnez **Réaffecter**.
11. Fermez les deux pages.

## <a name="create-an-rfq"></a>Créer un appel d’offre

1. Actualisez la page.
2. Sélectionnez **Appel d’offre**.
3. Dans le champ **Entité juridique acheteuse**, sélectionnez **USMF**. Vous devez choisir la même entité juridique qui celle de la ligne de demande.  
4. Dans la liste, marquer la ligne sélectionnée. Si vous avez plusieurs lignes sur votre demande d’achat, choisissez toutes les lignes que vous voulez ajouter à l’appel d’offre.  
5. Cliquez sur **OK**.
6. Actualisez la page.
7. Vérifiez que le récapitulatif est ouvert, puis développez la section **Documents associés**.
8. Cliquez sur le lien dans le champ **Appel d’offre** pour ouvrir l’appel d’offre qui vient d’être créé.
9. Sélectionnez **En-tête**.
10. Sélectionnez **Ajouter**.
11. Dans le champ **Compte fournisseur**, saisissez ou sélectionnez une valeur.
12. Sélectionnez **Ajouter**.
13. Dans le champ **Compte fournisseur**, saisissez ou sélectionnez une valeur.
14. Sélectionnez **Envoyer**.
15. Cliquez sur **OK**.
16. Sélectionnez **Entrer une réponse**.
17. Dans le volet Actions, sélectionnez **Répondre**.
18. Sélectionnez **Copier des données dans la réponse**. Cette opération copie des données, telles que la quantité et les dates, de l’appel d’offre à la réponse.  
19. Entrez un nombre dans le champ **Prix unitaire**. C’est le prix que vous avez reçu du fournisseur. Vous pourriez également vouloir entrer des informations supplémentaires à partir du fournisseur.  
20. Sélectionner **Accepter**.
21. Cliquez sur **OK**.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Vérifiez que le prix et le fournisseur ont été transférés dans la demande.
1. Fermez la page.
2. Sélectionnez **Lignes**.
3. Sélectionnez **Informations associées**.
4. Sélectionnez **Demande d’achat**.
5. Choisissez la ligne qui a été transférée à l’appel d’offre. Vérifiez que le prix et le fournisseur ont été copiés dans la demande.  
6. Sélectionnez **Workflow** pour ouvrir la boîte de dialogue.
7. Sélectionnez Terminer.
8. Sélectionnez la page.
9. Sélectionnez Terminer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]