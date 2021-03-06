---
title: Réaffectation de la prise en compte de revenu
description: Cette rubrique fournit des informations sur la réaffectation, qui permet aux organisations de recalculer les prix de produit lorsque les conditions d’une vente contractuelle sont modifiées. Elle comprend des liens vers d’autres rubriques décrivant comment reconnaître les revenus dans plusieurs scénarios.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2d961cb4eedda6265b4acd8dbd6f82e8026373fa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820567"
---
# <a name="revenue-recognition-reallocation"></a>Réaffectation de la prise en compte de revenu

[!include [banner](../includes/banner.md)]

La réaffectation permet aux organisations de recalculer les prix de produit lorsque les conditions d’une vente contractuelle sont modifiées. Dans le cadre de la prise en compte de revenu, les documents de commande client sont considérés comme le contrat.

Votre organisation doit déterminer elle-même si une réaffectation est nécessaire. L’ajout d’une nouvelle ligne à une commande client ou l’ajout d’une nouvelle commande client pour un client peut ne pas constituer une modification du contrat. Les scénarios suivants peuvent nécessiter une réallocation :

- Un client a ajouté des articles à une commande client (ou a supprimé des articles de la commande client), après que la commande a été entièrement ou partiellement facturée.
- Plusieurs commandes client, soit dans un état confirmé, soit dans un état facturé, ont été saisies pour le même contrat négocié.
- Un client a retourné un article ou reçu un avoir pour celui-ci après que la commande client originale a été entièrement ou partiellement facturée.

Il existe quelques limitations importantes sur le processus de réaffectation :

- Le processus ne peut être exécuté qu’une seule fois. Par conséquent, il est important de l’exécuter uniquement une fois que toutes les modifications sont finalisées.
- Le processus ne peut pas être exécuté sur les commandes client du projet.
- Si plusieurs commandes client sont impliquées, elles doivent concerner le même compte client.
- Toutes les commandes client doivent être réallouées dans la même devise de transaction.
- Le processus ne peut pas être contrepassé ou annulé après son exécution.

## <a name="set-up-reallocation"></a>Configurer la réaffectation

Un paramètre affecte le processus de réaffectation.

Étant donné que la réallocation peut être effectuée sur une commande client qui est partiellement ou entièrement facturée, toutes les écritures comptables précédentes de la facture doivent être corrigées à l’aide des nouveaux prix de revenus réalloués. Cette correction est effectuée en contrepassant l’écriture comptable de la facture d’origine et en validant une nouvelle écriture comptable basée sur les prix des produits réalloués.

Chaque organisation doit décider si la correction doit mettre à jour uniquement la Comptabilité ou si elle doit également mettre à jour la Comptabilité client. La décision détermine le paramètre approprié de l’option **Valider les corrections des factures dans la comptabilité client lors de la réaffectation** de l’onglet **Prise en compte de revenu** de la page **Paramètres de comptabilité** (**Prise en compte de revenu \> Paramétrage \> Paramètres de Comptabilité**). Le paramètre approprié dépend du scénario spécifique. Pour plus d’informations sur les scénarios possibles, consultez les liens de la section [Scénarios de réaffectation](#scenarios-for-reallocation) plus loin dans cette rubrique.

[![Onglet Prise en compte de revenu sur la page Paramètres de Comptabilité](./media/01_RevRecScenarios.png)](./media/01_RevRecScenarios.png)

Si l’option **Valider les corrections des factures dans la Comptabilité client** est définie sur **Oui**, le processus de réaffectation produit le résultat suivant :

- Un document de crédit est créé dans Comptes clients pour contrepasser la facture qui doit être corrigée.

    - Le document de crédit réutilise le numéro de facture d’origine, mais « -1 » y est ajouté.
    - Le document de crédit est automatiquement imputé à la facture d’origine. Si la facture d’origine a déjà été réglée avec un autre document de crédit ou paiement, ce règlement est automatiquement annulé.
    - Le document de crédit est imputé en Comptabilité pour contrepasser l’écriture comptable qui a été validée sur la facture d’origine. Cependant, les écritures de transaction Stock et Coût des marchandises vendues (COGS) ne sont pas contrepassées.

- Une nouvelle facture basée sur les nouveaux montants de prix réaffectés est créée en Comptabilité clients.

    - La nouvelle facture réutilise le numéro de facture d’origine, mais « -2 » y est ajouté.
    - La nouvelle facture est automatiquement imputée à tout document de crédit ou à tout paiement précédemment réglé avec la facture d’origine.
    - La nouvelle facture est imputée en Comptabilité en utilisant les nouveaux montants de prix des produits réalloués. Elle n’est pas imputée à nouveau dans les comptes d’inventaire et COGS, car ces écritures sont conservées sur l’écriture comptable de la facture d’origine.

Si l’option **Valider les corrections des factures dans la Comptabilité client** est définie sur **Non**, le processus de réaffectation produit le résultat suivant :

- Une écriture comptable de contrepassation est enregistrée uniquement en Comptabilité. Toute la comptabilité de la facture originale est contrepassée, à l’exception des écritures de compte d’inventaire et COGS.
- Une nouvelle écriture comptable est imputée uniquement en Comptabilité, en fonction des nouveaux prix des produits réalloués. Elle n’est pas imputée à nouveau dans les comptes d’inventaire et COGS, car ces écritures sont conservées sur l’écriture comptable de la facture d’origine.
- La facture de la page **Transactions clients** n’est pas affectée ou modifiée, mais reflète toujours l’écriture comptable d’origine. Il n’y a aucune référence aux écritures de contrepassation ou aux nouvelles écritures.

Comme cela a été mentionné, vous ne pouvez mettre à jour que Comptabilité ou à la fois Comptabilité et Comptabilité client. Les deux approches ont des avantages et des inconvénients. Nous vous recommandons d’évaluer les exigences de votre organisation pour déterminer quelle option vous devez utiliser. Si vous mettez à jour la Comptabilité et la Comptabilité client, les écritures comptables correctes seront affichées sur la nouvelle facture et peuvent être consultées à partir du document sur la page **Transactions du client**. En outre, le processus de règlement utilisera les écritures comptables mises à jour pour comptabiliser les escomptes de trésorerie et les gains ou pertes. D’autre part, le document de crédit et la nouvelle facture apparaîtront sur les relevés clients et les balances âgées, tout comme le font d’autres documents de crédit et factures clients. La description de ces documents indiquera qu’ils ont été créés par une correction comptable.

## <a name="run-the-reallocation-process"></a>Exécuter le processus de réaffectation

Pour démarrer le processus de réaffectation, sélectionnez **Redistribuer le prix avec les nouvelles lignes de commande** dans une commande client que vous devez réaffecter. Sinon, allez dans **Prise en compte de revenu \> Tâches périodiques \> Redistribuer le prix avec les nouvelles lignes de commande**, puis entrez les filtres appropriés, tels que le compte client.

[![Page Redistribuer le prix avec les nouvelles lignes de commande](./media/02_RevRecScenarios.png)](./media/02_RevRecScenarios.png)

La grille supérieure de la page **Redistribuer le prix avec les nouvelles lignes de commande** s’intitule **Ventes**. Elle répertorie les commandes du client. Sélectionnez les commandes client qui doivent être réaffectées. Vous ne pouvez pas sélectionner des commandes client de projet, car elles ne peuvent pas être réaffectées. Vous ne pouvez pas non plus sélectionner de commandes client qui ont déjà un ID de réaffectation, car les commandes client hors projet ne peuvent être réaffectées qu’une seule fois. Si une commande client a un ID de réaffectation, elle a déjà été marquée pour une réaffectation par un autre utilisateur.

La grille inférieure de la page s’intitule **Lignes**. Après avoir sélectionné une ou plusieurs commandes client dans la grille **Ventes**, la grille **Lignes** affiche les lignes de commande client. Sélectionnez les lignes de la commande client qui doivent être réaffectées. Si vous avez sélectionné une seule commande client, les lignes de cette même commande client doivent être réaffectées. Cette situation peut se produire lorsqu’une des lignes de commande client a été précédemment facturée, puis une nouvelle ligne a été ajoutée, ou une ligne existante a été supprimée ou annulée. Si une ligne a été supprimée, elle n’apparaîtra pas dans la grille. Par conséquent, elle ne peut pas être sélectionnée. Cependant, elle sera toujours prise en compte lors de l’exécution du processus de réaffectation.

Après avoir sélectionné les lignes de commande client requises, utilisez les boutons du volet Actions comme décrit ici :

- **Mettre à jour la réaffectation** : Calculez les nouveaux montants de prix de revenu pour les lignes de commande client sélectionnées. Si une ligne a été supprimée ou annulée, la réaffectation sera effectuée uniquement pour les lignes existantes que vous avez sélectionnées. L’illustration suivante montre un exemple de lignes de commande client avant la mise à jour de la réaffectation.

    [![Lignes de commande client avant la mise à jour de la réaffectation](./media/03_RevRecScenarios.png)](./media/03_RevRecScenarios.png)

    Les nouveaux montants de prix de revenu sont indiqués dans la colonne **Montant réaffecté** dans la grille **Lignes**. À ce stade, la réaffectation a été traitée, mais elle n’a pas encore été calculée. L’illustration suivante montre un exemple de lignes de commande client après la mise à jour de la réaffectation.

    [![Lignes de commande client après la mise à jour de la réaffectation](./media/04_RevRecScenarios.png)](./media/04_RevRecScenarios.png)

- **Processus** : Traiter ou afficher les prix des revenus réaffectés. Une fois que vous avez cliqué sur ce bouton, il n’y a aucun moyen d’annuler la réaffectation. Si vous n’avez pas sélectionné **Mettre à jour la réaffectation** avant de sélectionner **Processus**, la réaffectation est exécutée automatiquement.

    - Si aucune ligne de commande client n’a été facturée, les montants des prix de vente sont mis à jour sur toutes les commandes client sélectionnées pour une réaffectation.
    - Si une ou plusieurs lignes de commande client ont été facturées, les écritures comptables de correction sont validées et tous les détails du calendrier de produits qui ont été créés pour la ligne de commande client facturée sont corrigés.

- **Justificatif attendu** : Affichez un aperçu des écritures comptables qui ont été créées pour toutes les lignes de commande client qui ont été facturées. Si aucune ligne n’a été facturée, rien n’est affiché. Si vous n’avez pas sélectionné **Mettre à jour la réaffectation** avant de sélectionner **Justificatif attendu**, la réaffectation est exécutée automatiquement.
- **Réaffectation des revenus** : Ouvrez une page qui affiche la répartition du prix des revenus pour toutes les lignes sélectionnées. Vous ne pouvez modifier aucune des informations de la page. Elle indique les montants de ligne qui ont été utilisés pour effectuer la réaffectation.

    [![Montants de ligne qui ont été utilisés pour la réaffectation](./media/05_RevRecScenarios.png)](./media/05_RevRecScenarios.png)

- **Réinitialiser les données pour le client sélectionné** : Si le processus de réaffectation a été lancé mais ne s’est pas terminé, effacez les données du tableau de réaffectation pour le client sélectionné uniquement. Par exemple, si vous marquez plusieurs lignes de commande client pour réaffectation et que vous laissez la page ouverte sans sélectionner **Processus**, la page se ferme. Dans ce cas, les lignes de commande client resteront marquées et ne seront pas disponibles pour qu’un autre utilisateur puisse terminer le processus de réaffectation. La page peut même être vide lorsqu’elle est ouverte. Dans cette situation, le bouton **Réinitialiser les données pour le client sélectionné** peut être utilisé pour effacer les commandes client non traitées afin qu’un autre utilisateur puisse terminer le processus de réaffectation.

## <a name="scenarios-for-reallocation"></a>Scénarios de réaffectation

Les rubriques suivantes traitent de différents scénarios de prise en compte de revenu :

- [Réaffectation de la prise en compte de revenu - Scénario 1](rev-rec-reallocation-scenario-1.md) : Deux commandes clients sont saisies, mais elles ne sont que confirmées. Le même scénario produira des résultats similaires si plus de deux commandes client sont dans un état confirmé.
- [Réaffectation de la prise en compte de revenu - Scénario 2](rev-rec-reallocation-scenario-2.md) : Deux commandes client sont saisies, puis le client ajoute un article au contrat après la facturation de la première commande client.
- [Réaffectation de la prise en compte de revenu - Scénario 3](rev-rec-reallocation-scenario-3.md) : Une nouvelle ligne est ajoutée à une commande client existante, facturée.
- [Réaffectation de la prise en compte de revenu - Scénario 4](rev-rec-reallocation-scenario-4.md) : Une nouvelle ligne est supprimée d’une commande client existante partiellement facturée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]