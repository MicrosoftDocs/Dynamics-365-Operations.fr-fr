---
title: Réaffectation de la prise en compte de revenu - Scénario 1
description: Cette rubrique décrit un scénario de réaffectation dans lequel deux commandes client sont saisies, mais ne sont que confirmées. Le même scénario produira des résultats similaires si plus de deux commandes client sont dans un état confirmé.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a0add2d4bc01127c1f359736398123a6a3df9fe
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969650"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a>Réaffectation de la prise en compte de revenu - Scénario 1

[!include [banner](../includes/banner.md)]

Cette rubrique décrit un scénario de réaffectation dans lequel deux commandes client sont saisies, mais ne sont que confirmées. Le même scénario produira des résultats similaires si plus de deux commandes client sont dans un état confirmé.

Pour ce scénario, l’option **Valider les corrections des factures dans la Comptabilité client** est définie sur **Non** sur l’onglet **Prise en compte de revenu** de la page **Paramètres de comptabilité** (**Prise en compte de revenu \> Paramétrage \> Paramètres de Comptabilité**).

[![Option Valider les corrections des factures dans la Comptabilité client définie sur Non](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)

Une commande client est créée pour le client US\_SI\_0003. Le client achète un ordinateur portable (numéro d’article S0012) et un plan de support (numéro d’article S0008, « Service d’ingénierie continu »). Le produit de l’ordinateur portable est immédiatement reconnu (il n’y a pas d’échéancier de prise en compte de revenu). Le produit du plan de support est différé et reconnu sur 12 mois, comme défini par la plage de dates dans le contrat.

[![Lignes de commande client pour l’ordinateur portable et plan de support](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)

La commande client est confirmée. Étant donné que les deux articles sont configurés pour la répartition du prix du produit, celui-ci est calculé lorsque la commande client est confirmée. Vous pouvez afficher les produits qui seront reconnus sur la page **Répartition de prix du produit** (sur la page **Commande client**, dans le volet Actions, sur l’onglet **Gérer**, dans le groupe **Prise en compte de revenu**, sélectionnez **Répartition de prix du produit**). Le produit de l’ordinateur portable sera imputé au compte Produit pour un montant de 1 008,01 $. Le produit du plan de support sera imputé au compte Produit différé pour un montant de 190,99 $. La somme des prix doit être égale à la somme des lignes qui ont été configurées pour capturer la répartition de prix du produit (1 199,00 $).

[![Page Répartition de prix du produit](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)

Le client a choisi de ne pas acheter de services d’installation (numéro d’article S0001) au moment de l’achat, mais a changé d’avis par la suite. Par conséquent, une deuxième commande client est saisie pour le même client.

[![Ligne de commande client pour les services d’installation](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)

La deuxième commande client est confirmée. Étant donné que cette commande client ne contient qu’une seule ligne, la répartition de prix du produit n’est pas effectuée lorsque la commande client est confirmée. La répartition de prix du produit se produit uniquement s’il y a au moins deux articles uniques et s’ils sont configurés pour la répartition de prix du produit.

Si cette nouvelle commande client est la seule modification apportée au contrat du client, le processus de réaffectation peut maintenant être exécuté. Dans l’une des deux commandes client, sélectionnez **Redistribuer le prix avec les nouvelles lignes de commande** pour ouvrir la page **Redistribuer le prix avec les nouvelles lignes de commande**. Sinon, allez dans **Prise en compte de revenu \> Tâches périodiques \> Redistribuer le prix avec les nouvelles lignes de commande**. Sélectionnez les deux commandes client et les lignes de commande client correspondantes, puis sélectionnez **Mettre à jour la réaffectation**. La colonne **Montant réaffecté** affiche le nouveau prix des revenus pour chaque ligne de commande client.

[![Nouveaux prix de produit sur la page Redistribuer le prix avec les nouvelles lignes de commande](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)

Si vous sélectionnez **Justificatif attendu**, rien n’est affiché, car aucune facture n’a été enregistrée.

Pour terminer la réaffectation, sélectionnez **Processus**. Vous êtes invité à indiquer une date de validation, même si rien n’est validé. Une fois la réaffectation terminée, la page **Répartition de prix du produit** pour chaque commande client affiche la répartition des prix pour tous les articles des deux commandes client. En d’autres termes, la page **Répartition de prix du produit** pour chaque commande client comprendra un article qui n’existe pas sur cette commande client, car il fait partie du même contrat mais sur une commande client différente.

> [!TIP]
> Pour expliquer pourquoi ces éléments supplémentaires sont affichés, vous pouvez ajouter d’autres colonnes à la grille, telles que **ID de réaffectation** et **Commande client**.
> 
> [![Colonnes supplémentaires sur la page Répartition de prix du produit](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]