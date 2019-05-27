---
title: Recouvrement de la TVA dans le module Gestion des dépenses
description: Cette rubrique explique comment recevoir des remboursements sur les transactions de taxe sur la valeur ajoutée (TVA) admissibles.
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bc9e533de40aa8fe8ddfe422cfe0f4078a360c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568938"
---
# <a name="vat-recovery-in-expense-management"></a>Recouvrement de la TVA dans le module Gestion des dépenses

[!include [banner](../includes/banner.md)]

Pour recevoir des remboursement sur des transactions de taxe sur la valeur ajoutée (TVA) admissibles, une société ou organisation doit identifier, collecter, vérifier et soumettre des informations précises. Ce processus inclut plusieurs tâches, et selon la taille de votre société, peut inclure plusieurs employés ou rôles.

Pour récupérer la TVA à l'aide de Gestion des dépenses, les conditions préalables suivantes doivent être réunies :

- Les codes taxe doivent être créés pour les pays/régions affectés aux catégories de dépenses.
- Un groupe de taxe doit être créé pour chaque code taxe.
- Un code taxe d'article doit être créé pour chaque groupe de taxe.

Une fois les conditions préalables réunies, les employés doivent suivre les étapes requises pour demander des remboursements sur les transactions de TVA.

1. Sur l'état de dépenses, entrez les informations de taxe sur les transactions de carte de crédit pour identifier les remboursements de TVA admissibles.
2. Assurez-vous que toutes les informations de taxe sont complètes, puis validez l'état de dépenses.
3. Traitez les dépenses qui sont admissibles pour la récupération de la TVA internationale.
4. Envoyez les données de récupération de la TVA à un fournisseur tiers pour remplir les déclarations de récupération de la TVA internationale.
5. Traitez les dépenses pour la récupération de la TVA locale.

Les sections suivantes offrent des exemples sur la manière dont les employés de Contoso effectuent chaque étape.

## <a name="on-an-expense-report-enter-tax-information-about-credit-card-transactions-to-identify-eligible-vat-refunds"></a>Sur un état de dépenses, entrez les informations de taxe sur les transactions de carte de crédit pour identifier les remboursements de TVA admissibles

Nancy, une commerciale Contoso basée aux États-Unis, est récemment revenue d'un voyage d'affaires à but commercial au Royaume-Uni. Lors de son déplacement, elle a payé ses repas avec sa carte de crédit personnelle. Elle doit à présent créer un état de dépenses pour rapprocher ses propres dépenses.

Lorsque Nancy entre les informations dans son état de dépenses, elle sélectionne **Royaume-Uni** dans le champ **Pays/région** sur la page **Modifier l'état de dépenses**. La liste de groupes de taxe est ensuite filtrée afin qu'elle affiche uniquement les groupes s'appliquant au Royaume-Uni. Nancy sélectionne le groupe de taxe **Royaume-Uni 001**, puis et le groupe de taxe d'article **Restauration**. Elle ajoute ensuite une nouvelle transaction pour son hébergement. Comme il n'existe qu'un seul groupe de taxe et qu'un seul groupe de taxe d'article pour l'hébergement au Royaume-Uni, ces informations sont automatiquement renseignées dans l'état de dépenses de Nancy.

Conformément à la stratégie de Contoso, toutes les dépenses doivent avoir un reçu correspondant. Par conséquent, lorsque Nancy enregistre son état de dépenses, elle reçoit un message qui indique qu'elle doit joindre un reçu pour chaque transaction qu'elle a répertoriée dans son état de dépenses. Nancy vérifie qu'elle a joint une image numérique de chaque reçu de transaction à son état de dépenses, puis envoie celui-ci pour approbation. Elle envoie ensuite les reçus papier à l'équipe de traitement administratif. Cette équipe enverra les données de récupération de la TVA au fournisseur tiers qui remplit les retours avec recouvrement de la TVA internationale pour Contoso.

## <a name="make-sure-that-all-tax-information-is-complete-and-then-post-the-expense-report"></a>Assurez-vous que toutes les informations de taxe sont complètes, puis validez l'état de dépenses

April, la coordinatrice des Achats chez Contoso, doit entrer toutes les informations de taxe manquantes d'un état de dépenses avant que celui-ci puisse être validé. Elle ouvre la page **Détails de l'état de dépenses** et voit l'état de dépenses approuvé de Nancy. Elle l'ouvre ensuite pour afficher les détails des transactions. Elle constate que Nancy n'a pas entré de groupe de taxe d'article pour l'une des transactions. Cette information étant manquante, April ne peut pas valider l'état de dépenses. Par conséquent, elle consulte la page **Configurations de taxe** dans Gestion des dépenses et trouve le groupe de taxe d'article pour le pays/la région et le type de transaction. Elle peut maintenant valider l'état de dépenses dans la comptabilité.

Lorsqu'elle valide l'état des dépenses, un élément de travail TVA récupérable est créé. Cet élément de travail est affecté à un membre de l'équipe de traitement administratif. April reçoit un message confirmant que cette validation a réussi. Ce message répertorie également le nombre de transactions de TVA ayant été identifiées pour la récupération.

## <a name="process-expenses-that-are-eligible-for-international-vat-recovery"></a>Traitez les dépenses qui sont admissibles pour la récupération de la TVA internationale

Arnie est membre de l'équipe administrative de Contoso. Il est chargé de confirmer que toutes les informations requises pour la récupération de la TVA sont fournies sur les états de dépenses. Il ouvre la page **Recouvrement fiscal des dépenses** et sélectionne l'état de dépenses envoyé par Nancy. Arnie vérifie que tous les reçus requis sont joints et que le groupe de taxe et les codes taxe corrects sont entrés.

Lorsqu'il reçoit les reçus papier de Nancy, il les compare aux reçus numériques, puis attribue le statut **Prêt pour la récupération** à l'état de dépenses.

## <a name="send-vat-recovery-data-to-the-third-party-vendor-to-file-international-recovery-returns"></a>Envoi des données de récupération de la TVA à un fournisseur tiers à des fins de renseignement des déclarations de récupération de la TVA internationale

Lorsqu'Arnie est prêt à envoyer les données de l'état de dépense au fournisseur tiers qui renseignera les déclarations de récupération de la TVA internationale, il ouvre la page **Recouvrement fiscal des dépenses**. Il filtre la page pour afficher uniquement les états de dépenses possédant le statut **Prêt pour la récupération**. Il sélectionne ensuite **Fichier** &gt; **Exporter vers Excel**. Les informations de TVA des états de dépenses sont exportées vers une feuille de calcul Microsoft Excel. Arnie envoie cette feuille de calcul au fournisseur tiers et inclut un message déclarant que les reçus papier ont été envoyés par courrier.

## <a name="process-expenses-for-domestic-vat-recovery"></a>Traitement des dépenses à des fins de récupération de la TVA locale

Arnie doit vérifier que les transactions d'état de dépenses sont admissibles pour la récupération de la TVA et que les reçus numériques sont joints aux états. Pour commencer à traiter les dépenses admissibles pour la récupération de la TVA locale, Arnie ouvre la page **Recouvrement fiscal des dépenses** et sélectionne l'état de dépenses à vérifier. Il vérifie que les reçus sont au nom de la société au lieu de l'employé. Pour une récupération de la TVA, les reçus doivent être au nom de la société. Il confirme ensuite que le groupe de taxe et les codes taxe corrects ont été appliqués.

Lorsqu'Arnie reçoit les reçus papier, il attribue le statut **Prêt pour la récupération** à l'état de dépenses. Il peut ensuite remplir la déclaration auprès de l'administration fiscale appropriée. Dans ce cas, il s'agit de l'IRS (Internal Revenue Service), située aux États-Unis.
