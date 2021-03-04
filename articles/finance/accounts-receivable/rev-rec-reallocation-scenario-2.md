---
title: Réaffectation de la prise en compte de revenu - Scénario 2
description: Cette rubrique passe par un scénario de réaffectation dans lequel deux commandes client sont saisies, puis le client ajoute un article au contrat après la facturation de la première commande client. Lorsqu’un nouvel article est ajouté à un contrat, il peut être ajouté soit à une nouvelle commande client, soit à la commande client existante.
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
ms.openlocfilehash: 30b4c55a82237b5c8b6b41032243da337a5ec969
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003394"
---
# <a name="revenue-recognition-reallocation--scenario-2"></a>Réaffectation de la prise en compte de revenu - Scénario 2

[!include [banner](../includes/banner.md)]

Cette rubrique passe par un scénario de réaffectation dans lequel deux commandes client sont saisies, puis le client ajoute un article au contrat après la facturation de la première commande client. Lorsqu’un nouvel article est ajouté à un contrat, il peut être ajouté soit à une nouvelle commande client, soit à la commande client existante.

Pour ce scénario, l’option **Valider les corrections des factures dans la Comptabilité client** est définie sur **Non** sur l’onglet **Prise en compte de revenu** de la page **Paramètres de comptabilité** (**Prise en compte de revenu \> Paramétrage \> Paramètres de Comptabilité**).

[![Option Valider les corrections des factures dans la Comptabilité client définie sur Non](./media/12_rev-rec-scenarios.png)](./media/12_rev-rec-scenarios.png)

Une commande client est créée pour le client US\_SI\_0003. Le client achète des services d’installation (numéro d’article S0001) et un plan de support (numéro d’article S0008) pour un ordinateur portable, mais il n’a pas encore sélectionné l’ordinateur portable. Le produit des services d’installation sera différé jusqu’à la date d’achat de l’ordinateur portable. Le produit du plan de support est différé et reconnu sur 12 mois, comme défini par la plage de dates dans le contrat.

[![Lignes de commande client pour les services d’installation et le plan de support](./media/13_rev-rec-scenarios.png)](./media/13_rev-rec-scenarios.png)

La commande client est confirmée. Étant donné que les deux articles sont configurés pour la répartition du prix du produit, celui-ci est calculé lorsque la commande client est confirmée. Vous pouvez afficher les produits qui seront reconnus sur la page **Répartition de prix du produit** (sur la page **Commande client**, dans le volet Actions, sur l’onglet **Gérer**, dans le groupe **Prise en compte de revenu**, sélectionnez **Répartition de prix du produit**). Le produit pour les services d’installation sera imputé au compte Produit différé pour un montant de 250 $. Le produit du plan de support sera aussi imputé au compte Produit différé pour un montant de 150 $. La somme des prix doit être égale à la somme des lignes qui ont été configurées pour capturer la répartition de prix du produit (400 $).

[![Page Répartition de prix du produit](./media/14_rev-rec-scenarios.png)](./media/14_rev-rec-scenarios.png)

La commande client est entièrement facturée. L’illustration suivante montre l’écriture comptable validée pour la facture.

[![Écriture comptable de la commande client entièrement facturée](./media/15_rev-rec-scenarios.png)](./media/15_rev-rec-scenarios.png)

L’échéancier de prise en compte de revenu est également créé, mais aucun produit n’est encore pris en compte.

[![Page Échéancier de prise en compte de revenu](./media/16_rev-rec-scenarios.png)](./media/16_rev-rec-scenarios.png)

Quelques jours plus tard, le client sélectionne un ordinateur portable. Une deuxième commande client est saisie pour le client.

[![Ligne de commande client pour l’ordinateur portable](./media/17_rev-rec-scenarios.png)](./media/17_rev-rec-scenarios.png)

La deuxième commande client est confirmée. Étant donné que cette commande client ne contient qu’une seule ligne, la répartition de prix du produit n’est pas effectuée lorsque la commande client est confirmée. La répartition de prix du produit se produit uniquement s’il y a au moins deux articles uniques et s’ils sont configurés pour la répartition de prix du produit.

Si cette nouvelle commande client est la seule modification apportée au contrat du client, le processus de réaffectation peut maintenant être exécuté. Dans l’une des deux commandes client, sélectionnez **Redistribuer le prix avec les nouvelles lignes de commande** pour ouvrir la page **Redistribuer le prix avec les nouvelles lignes de commande**. Sinon, allez dans **Prise en compte de revenu \> Tâches périodiques \> Redistribuer le prix avec les nouvelles lignes de commande**. Sélectionnez les deux commandes client et les lignes de commande client correspondantes, puis sélectionnez **Mettre à jour la réaffectation**. La colonne **Montant réaffecté** affiche le nouveau prix des revenus pour chaque ligne de commande client.

[![Nouveaux prix de produit sur la page Redistribuer le prix avec les nouvelles lignes de commande](./media/18_rev-rec-scenarios.png)](./media/18_rev-rec-scenarios.png)

Ensuite, sélectionnez **Justificatif attendu** pour afficher les écritures comptables qui ne seront validées qu’en Comptabilité. Comme l’option **Valider les corrections des factures dans la Comptabilité client** est définie sur **Non** sur la page **Paramètres de Comptabilité**, rien ne sera changé dans les comptes clients lorsque la réaffectation sera traitée.

[![Écritures comptables sur la page Justificatif attendu](./media/19_rev-rec-scenarios.png)](./media/19_rev-rec-scenarios.png)

Sur la page **Justificatif attendu**, les trois dernières lignes contrepassent l’écriture comptable d’origine de la facture validée. Les quatre premières lignes constituent la nouvelle écriture comptable qui est validée pour la facture. Il est important de comprendre qu’une nouvelle facture n’est pas présentée au client. Après la réaffectation, le client doit toujours 426 $, qui est le montant qui doit être imputé aux comptes clients dans la nouvelle écriture comptable. Le total de la taxe compensatoire et des revenus différés est égal à 188,69 $ + 314,48 $ + 26,00 $ = 529,17 $. Le montant des revenus reportés a changé en raison de la réaffectation. La différence de 103,17 $ est enregistrée dans un compte de compensation des revenus de facturation partielle. Ce solde sera supprimé une fois la facture validée pour la deuxième commande client qui a été incluse dans la réaffectation.

Pour terminer la réaffectation, sélectionnez **Processus**. Vous êtes invité à indiquer une date de validation, même si rien n’est validé. Une fois la réaffectation terminée, la page **Répartition de prix du produit** pour chaque commande client affiche la répartition des prix pour tous les articles des deux commandes client. En d’autres termes, la page **Répartition de prix du produit** pour chaque commande client comprendra un article qui n’existe pas sur cette commande client, car il fait partie du même contrat mais sur une commande client différente.

> [!TIP]
> Pour expliquer pourquoi ces éléments supplémentaires sont affichés, vous pouvez ajouter d’autres colonnes à la grille, telles que **ID de réaffectation** et **Commande client**.
> 
> [![Colonnes supplémentaires sur la page Répartition de prix du produit](./media/20_rev-rec-scenarios.png)](./media/20_rev-rec-scenarios.png)

Dans la commande client 00036, l’échéancier de prise en compte de revenu a également été mis à jour, en fonction du nouveau prix de réaffectation du produit. À partir de cette commande client, ouvrez la page **Échéancier de prise en compte de revenu**. Auparavant, il y avait 13 lignes pour l’article S0008 (un échéancier de 12 mois était attribué à cet article). Il y a maintenant 39 lignes : les 13 échéances d’origine, 13 échéances de contrepassation et 13 lignes basées sur le nouveau prix du produit.

[![Page Échéancier de prise en compte de revenu mis à jour avec 39 lignes pour l’article S0008](./media/21_rev-rec-scenarios.png)](./media/21_rev-rec-scenarios.png)

De même, il y avait auparavant deux lignes pour l’article S0001, mais il y en a maintenant six.

[![Page Échéancier de prise en compte de revenu mis à jour avec six lignes pour l’article S0001](./media/22_rev-rec-scenarios.png)](./media/22_rev-rec-scenarios.png)

Lorsque vous sélectionnez **Justificatif** dans la commande client 000036, le journal des factures affiche l’écriture comptable d’origine. Pour afficher l’écriture de contrepassation et la nouvelle écriture comptable à partir de la commande client, sélectionnez **Ajustements de produit** dans le volet Actions, puis sélectionnez **Justificatif**.

[![Commande client 000036](./media/23_rev-rec-scenarios.png)](./media/23_rev-rec-scenarios.png)

Ensuite, ouvrez la page **Tous les clients** (**Comptabilité client \> Clients \> Tous les clients**), sélectionnez le client **US\_SI\_0003**, puis sélectionnez **Transactions**. La facture ouverte de la commande client 000036 s’affiche. Si vous sélectionnez le justificatif, vous verrez l’écriture comptable d’origine, et non la nouvelle écriture comptable de la réaffectation. L’écriture de contrepassation et la nouvelle écriture comptable ne peuvent pas être affichées à partir de Comptabilité client.

La deuxième commande client est désormais facturée. La facture totale présentée au client est de 1 099,00 $ + 71,44 $ de taxe = 1 170,44 $. L’illustration suivante montre l’écriture comptable validée.

[![Page Justificatif de transaction avec l’écriture comptable validée](./media/24_rev-rec-scenarios.png)](./media/24_rev-rec-scenarios.png)

Étant donné que la somme des revenus et des ventes est supérieure à 1 170,44 $, la différence est validée pour -130,17 $. Ce montant efface le solde du compte de compensation des revenus de la facture partielle. Ce solde est validé dans la nouvelle écriture comptable après la réaffectation.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]