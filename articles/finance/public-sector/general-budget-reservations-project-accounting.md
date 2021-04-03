---
title: Comptabilité de projet avec des réservations budgétaires générales
description: Cette rubrique fournit des informations sur la comptabilité de projet qui utilise les réservations budgétaires générales pour le secteur public.
author: AlexRenney
manager: AnnBe
ms.date: 04/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetReservation_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: cf55723007580ec2e6e19deb23fff5b9795b54c6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258140"
---
# <a name="project-accounting-with-general-budget-reservations"></a>Comptabilité de projet avec des réservations budgétaires générales

[!include [banner](../includes/banner.md)]

Si votre organisation utilise la comptabilité de projet, vous pouvez inclure dans votre projet des références aux réservations budgétaires générales. Ces références peuvent affecter la budgétisation, les coûts engagés, ainsi que la réservation et la consommation des sources de financement.

Certaines dépenses sont planifiées pour être imputées aux projets. Lorsque vous créez une réservation budgétaire générale, vous pouvez spécifier le projet et la catégorie de projet pour lesquels un achat est prévu. Vous pouvez également spécifier d’autres informations relatives au projet, telles que le prix de vente attendu. (Pour les entités du secteur public, le prix de vente attendu est généralement le prix de revient.) Toutes ces informations sont incluses dans les documents d’achat qui sont générés pour les projets ultérieurement.

Si la réservation budgétaire générale contient une répartition de projet, la commande fournisseur, la demande d’achat, ou la facture fournisseur qui référence la réservation doivent inclure la répartition de projet et toutes les informations de projet. Ces informations sont automatiquement copiées sur le document source de la réservation budgétaire générale.

## <a name="turn-on-tracking-of-committed-costs-for-general-budget-reservations"></a>Activer le suivi des coûts engagés pour les réservations budgétaires générales

Les coûts engagés du projet sont créés lorsque les documents d’achat sont approuvés, confirmées, ou validés. Les coûts représentent les montants qui seront dépensés sur un projet. Les chefs de projet peuvent afficher les coûts en attente pour un projet afin de suivre précisément les coûts de leur projet.

1. Accédez à **Gestion de projets et comptabilité \> Paramétrage \> Paramètres de gestion de projets et de comptabilité**.
2. Dans l’onglet **Contrôle des coûts**, sous l’organisateur **Engagements en termes de coûts**, définissez l’option **Réservation budgétaire générale** sur **Oui**.

    - Les options **Demande d’achat**, **Commande fournisseur** et **Facture fournisseur** sont automatiquement définies sur **Oui**.
    - Lorsque la réservation budgétaire générale est validée, elle est comptabilisée dans les coûts engagés du projet.

## <a name="specify-project-information-in-a-general-budget-reservation"></a>Spécifier les informations de projet dans une réservation budgétaire générale

1. Accédez à **Budgétisation \> Réservations budgétaires générales**.
2. Créez une réservation budgétaire générale.
3. Dans l’organisateur **Lignes de réservation budgétaire générale**, ajoutez un ID projet et une catégorie de projet pour chaque ligne de réservation applicable. Les informations du projet sont automatiquement copiées dans la réservation.
4. Facultatif : Pour afficher les détails du projet, dans l’organisateur **Détails de la ligne**, sélectionnez l’onglet **Projet**.

## <a name="view-project-committed-costs-for-a-general-budget-reservation"></a>Afficher les coûts engagés du projet pour une réservation budgétaire générale

Lorsque vous validez une réservation budgétaire générale pour un projet, un coût engagé est créé pour le montant de réservation par rapport à ce projet. Le coût engagé représente le montant total des distributions de ce projet.

1. Accédez à **Budgétisation \> Réservations budgétaires générales**.
2. Ouvrez la réservation budgétaire générale validée, et sélectionnez une ligne de réservation.
3. Sélectionnez **Coûts engagés**. La page **Coûts engagés** s’affiche et indique les coûts engagés associés à la ligne sélectionnée.

    Les coûts engagés pour les réservations budgétaires générales sont basés sur le montant, peu importe si le coût engagé inclut une quantité et un coût unitaire distincts. La quantité du coût engagé est toujours 1.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]