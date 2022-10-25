---
title: Plans basés sur des devis et des appels d’offre
description: Cet article décrit comment configurer la planification générale pour prendre en compte les devis et les appels d’offre lorsqu’elle génère des ordres planifiés.
author: t-benebo
ms.date: 09/20/2022
ms.topic: article
ms.search.form: SalesQuotationListPage, ReqPlanSched, SalesQuotationTable, smmOpportunityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-20
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: eaeb3c26a562c1daebe8296b26077ee5a3223e4d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690097"
---
# <a name="plan-based-on-quotations-and-rfqs"></a>Plan basé sur des devis et des appels d’offre

[!include [banner](../../includes/banner.md)]

Les devis et les appels d’offre représentent des commandes futures possibles ou même probables. Par conséquent, il est logique de les prendre en compte lors de la planification générale, afin que l’approvisionnement supplémentaire puisse être planifié en fonction des appels d’offres existants et de la probabilité que chaque devis devienne une commande réelle. Cet article décrit comment configurer la planification générale pour prendre en compte les devis et les appels d’offre lorsqu’elle génère des ordres planifiés.

## <a name="set-up-master-planning-to-consider-sales-quotations-andor-rfqs"></a>Configurer une planification générale pour tenir compte des devis de vente et/ou appels d’offres

Utilisez la procédure suivante pour configurer la planification générale afin de tenir compte des offres de vente et/ou appels d’offres.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez un plan existant dans le volet de liste ou sélectionnez **Nouveau** dans le volet Actions pour en créer un.
1. Dans l’organisateur **Général**, définissez les champs suivants :

    - **Inclure les devis de vente** : définissez cette option sur *Oui* pour tenir compte des offres de vente lors de l’exécution du plan en cours. Définissez-le sur *Non* pour les ignorer.
    - **% de probabilité** : définissez le niveau de confiance minimum requis pour qu’un devis soit inclus dans la planification générale. Le calcul de la planification générale inclut tous les devis qui ont été créés à partir d’opportunités ayant ce pourcentage de probabilité ou plus. Pour inclure tous les devis, y compris les devis auxquels aucune probabilité ou opportunité n’est associée, définissez ce champ sur *0* (zéro). Pour plus d’informations sur les probabilités de devis, consultez la section suivante.
    - **Inclure les demandes de devis** : définissez cette option sur *Oui* pour tenir compte des appels d’offre lors de l’exécution du plan en cours. Définissez-le sur *Non* pour les ignorer. Si vous choisissez de prendre en compte les appels d’offres, le système crée des bons de commande planifiés pour ceux-ci, mais il ne précise pas le fournisseur tant que l’appel d’offres n’est pas résolu. Les commandes fournisseur prévisionnelles créées pour les appels d’offres peuvent affecter les quantités d’autres commandes planifiées.

1. Continuez à mettre en place votre plan directeur de la manière habituelle.

## <a name="assign-and-view-probabilities-for-quotations"></a>Attribuer et afficher des probabilités pour les devis

Comme mentionné dans la section précédente, un plan directeur ne tient compte que des devis qui atteignent ou dépassent le seuil de probabilité défini pour le plan (si un seuil est défini). Cependant, la probabilité n’est pas définie directement sur chaque devis. Au lieu de cela, il est hérité de l’opportunité qui a été utilisée pour générer le devis. Par conséquent, les devis créés directement sur la page **Tous les devis** n’ont aucune probabilité attribuée ou aucune opportunité associée, et ils ne sont jamais pris en compte par la planification générale (à moins que le champ **% de probabilité** est défini sur *0* \[zéro\]). Pour qu’une probabilité lui soit affectée, un devis doit être généré à partir d’une opportunité.

### <a name="create-a-quotation-from-an-opportunity"></a>Créer un devis depuis une opportunité

Utilisez la procédure suivante pour affecter une probabilité à une opportunité, puis créer un devis à partir de cette opportunité.

1. Accédez à **Ventes et marketing \> Relations \> Opportunités \> Toutes les opportunités**.
1. Sélectionnez une opportunité existante ou sélectionnez **Nouveau** sur le volet Actions pour en créer une.
1. Remplissez la page d’opportunité pour identifier l’opportunité comme vous le souhaitez. Assurez-vous de définir le champ **Probabilité** sur une valeur appropriée. Seuls les schémas directeurs configurés pour rechercher des probabilités de cette valeur ou plus tiennent compte des devis générés à partir de cette opportunité.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sur l’onglet **Opportunité**, dans le groupe **Nouveau**, sélectionnez **Devis de vente** ou **Devis de projet**, selon le type de devis que vous souhaitez créer.
1. Dans la boîte de dialogue **Créer un devis**, définissez les champs nécessaires, puis les sélectionnez **OK**.
1. Un devis est créé et ouvert. Sur le raccourci **Lignes**, utilisez la barre d’outils pour ajouter des lignes de vente ou des lignes de projet selon les besoins pour définir le contenu du devis.
1. Dans le volet Actions, sélectionnez **Enregistrer**. Puis fermez le devis.

### <a name="view-the-probability-that-is-assigned-to-a-quotation"></a>Afficher la probabilité attribuée à un devis

La seule façon d’afficher la probabilité affectée à un devis est d’ouvrir l’opportunité qui a été utilisée pour créer ce devis, comme décrit dans la procédure suivante.

1. Accédez à **Ventes et marketing \> Devis de vente \> Tous les devis**.
1. Si la colonne **Identifiant de l’opportunité** n’est pas affichée (elle est masquée dans une installation par défaut), suivez ces étapes pour l’afficher temporairement. (Sinon, pour garder la colonne **Identifiant de l’opportunité** disponible, créez une [vue enregistrée](../../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json) qui l’inclut.)

    1. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) de la grille, puis sélectionnez **Insérer des colonnes**.
    1. Dans la boîte de dialogue **Insérer des colonnes**, recherchez la ligne où le champ **Champ** est défini sur *Opportunité*, et sélectionnez la case à cocher **Sélectionner** pour cette ligne.
    1. Sélectionnez **Mise à jour** pour ajouter la colonne sélectionnée à la page **Tous les devis**.

1. Dans la grille, recherchez la ligne du devis concerné. Puis, dans la colonne **Identifiant de l’opportunité**, sélectionnez la valeur de cette ligne.

    > [!NOTE]
    > Si vous recherchez un devis de projet, vous devrez peut-être sélectionner l’en-tête de colonne **Type de devis** et effacer son filtre. Dans une installation par défaut, ce filtre est défini de sorte que seuls les devis de vente soient affichés.

1. L’opportunité associée est ouverte. Vous pouvez maintenant afficher et modifier la valeur **Probabilité** selon vos besoins.
