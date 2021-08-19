---
title: FAQ sur les activités de fin d’exercice
description: Cette rubrique a été compilée pour faciliter les activités de clôture de fin d’exercice.
author: kweekley
ms.date: 01/25/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1b7606314b9cf7050a565822b5b9e23beb0cb4978b20e88596c5002d918cfcd9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725072"
---
# <a name="year-end-activities-faq"></a>FAQ sur les activités de fin d’exercice 

[!include [banner](../includes/banner.md)]

Cette rubrique a été compilée pour faciliter les activités de clôture de fin d’exercice. Les informations contenues dans cette rubrique se concentrent principalement sur les questions relatives aux activités de clôture de fin d’exercice en Comptabilité et en Comptabilité fournisseur.

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Comptabilité : Comment savoir si nous sommes bien en train d’exécuter la clôture de fin d’exercice et non de l’annuler ?
Il arrive que des organisations essayent d’exécuter la clôture de fin d’exercice, mais qu’au lieu de cela, elles l’annulent. Si la clôture de fin d’exercice se termine très rapidement ou si elle ne produit pas de soldes d’ouverture, validez le paramètre **Annuler la clôture précédente** dans **Clôture de fin d’exercice** (**Comptabilité > Clôture de période > Clôture de fin d’exercice > Exécuter la clôture fiscale**). 

[![Exécution de la clôture de fin d’exercice et annulation de la clôture de fin d’exercice.](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Si le paramètre **Annuler la clôture précédente** est défini sur **Oui**, la clôture de fin d’exercice précédente est annulée. Lors d’une annulation, toutes les écritures de solde de clôture et de solde d’ouverture sont supprimées, comme si la clôture de fin d’exercice n’avait jamais été exécutée. Les justificatifs sont supprimés. La clôture de fin d’exercice ne s’exécutera pas à nouveau automatiquement. Vous devez recommencer le processus, cette fois en définissant le paramètre **Annuler la clôture précédente** sur **Non**. 

> [!NOTE]
> Il est possible que l’écriture du solde de clôture soit créée dans l’exercice en cours de clôture. Cela se produit uniquement si le paramètre de Comptabilité **Création de transactions de clôture lors du transfert** est défini sur **Oui**. L’écriture de solde d’ouverture est toujours créée, car il s’agit du solde d’ouverture de l’exercice suivant.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Comptabilité : Quelle est la différence entre le paramètre Annuler et Supprimer comptabilité pour la clôture de l’exercice ?
Une confusion peut exister sur la différence entre le paramètre **Annuler la clôture précédente** de la boîte de dialogue **Clôture de fin d’exercice** et le paramètre **Suppression des transactions de clôture d’exercice lors du transfert** dans Comptabilité (**Comptabilité > Clôture de période > Clôture de fin d’exercice > Exécuter la clôture fiscale**).  

[![Différence entre le paramètre Annuler et Supprimer comptabilité pour la clôture de l’exercice.](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Sélectionnez **Annuler la clôture précédente** dans le menu déroulant de la boîte de dialogue lors de l’exécution du processus de clôture de fin d’exercice pour supprimer toutes les écritures du solde de clôture et du solde d’ouverture, comme si la clôture de fin d’exercice n’avait jamais été exécutée. Les justificatifs seront supprimés. La clôture de fin d’exercice ne s’exécutera pas à nouveau automatiquement. Pour exécuter la clôture de fin d’exercice, vous devez relancer ce processus, en définissant cette fois le paramètre **Annuler la clôture précédente** sur **Non** (**Comptabilité > Paramètre comptable > Paramètres de Comptabilité**). 

[![Paramètres de Comptabilité.](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

Le paramètre **Suppression des transactions de clôture d’exercice lors du transfert** en Comptabilité est utilisé uniquement lors de l’exécution (et non de l’annulation) de la clôture de fin d’exercice (le paramètre **Annuler la clôture précédente** est défini sur **Non**). Si ce paramètre est défini sur **Oui**, toutes les écritures de solde de clôture et de solde d’ouverture seront supprimées et la clôture de fin d’exercice recommencera. Ce processus est utilisé lorsque l’organisation souhaite que toutes les transactions, y compris les ajustements depuis la dernière clôture de l’exercice, soient comptabilisées dans une seule écriture comptable pour les écritures du solde de clôture et du solde d’ouverture. 

Si cette option est définie sur **Non**, toutes les écritures du solde de clôture et du solde d’ouverture sont conservées. Elles ne sont pas supprimées. Au lieu de cela, un nouveau solde de clôture et une nouvelle écriture de solde d’ouverture seront créés uniquement pour le delta ou pour les nouvelles transactions validées depuis la dernière clôture pour cet exercice.  

> [!NOTE]
> L’écriture du solde de clôture est créée dans l’exercice en cours de clôture. Cela se produit uniquement si le paramètre de comptabilité **Création de transactions de clôture lors du transfert** est défini sur **Oui** en Comptabilité. L’écriture de solde d’ouverture est toujours créée, car il s’agit du solde d’ouverture de l’exercice suivant. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Comptabilité : Comment faire pour améliorer les performances du processus de fin d’exercice ? 
Vous pouvez apporter un certain nombre de modifications pour améliorer les performances de la clôture de fin d’exercice. Nous vous recommandons d’évaluer ces propositions pour déterminer si la modification est appropriée pour votre organisation.  

### <a name="dimension-sets"></a>Ensembles de dimensions
Lors de la clôture de fin d’exercice, chaque solde d’ensemble de dimensions est reconstitué, ce qui a un impact direct sur les performances. Certaines organisations créent des ensembles de dimensions inutilement car ils ont été utilisés à un moment donné ou sont susceptibles de l’être.  Ces ensembles de dimensions inutiles sont toujours reconstruits lors de la clôture de l’exercice, ce qui allonge le processus. Prenez le temps d’évaluer vos ensembles de dimensions et supprimez ceux qui sont inutiles.

Les ensembles de dimensions inutiles ont également un impact sur le traitement par lots **BudgetDimensionFocusInitializeBalance** (**Comptabilité > Plan comptable > Dimensions > Ensembles de dimensions financières**).

[![Ensembles de dimensions financières.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configuration du modèle de clôture de fin d’exercice
Le modèle de clôture de fin d’exercice permet aux organisations de sélectionner le niveau de dimension financière à maintenir lors du transfert des soldes de profits et pertes vers les bénéfices non répartis. Les paramètres permettent à une organisation de conserver les dimensions financières détaillées (**Clôturer tout**) lors du transfert des soldes vers les bénéfices non répartis ou de choisir de récapituler les montants en une seule valeur de dimension (**Clôturer individuellement**). Cela peut être défini pour chaque dimension financière. Pour plus d’informations sur ces paramètres, consultez la rubrique [Clôture de fin d’exercice](year-end-close.md).

Nous vous recommandons d’évaluer les exigences de votre organisation et, si possible, de clôturer autant de dimensions que possible à l’aide de l’option de fin d’exercice **Clôturer individuellement** pour améliorer les performances. En clôturant sur une seule valeur de dimension (qui peut également être une valeur vide), le système calcule moins de détails lors de la détermination des soldes pour les écritures de compte de bénéfices non répartis.

### <a name="10013-update-or-later"></a>Mise à jour 10.0.13 ou ultérieure
Si vous avez effectué une mise à jour vers la version 10.0.13 ou ultérieure depuis la clôture de fin d’exercice de votre organisation, ce processus de clôture peut prendre plus de temps en raison de l’[implémentation de la fonctionnalité HashV2](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/verify-hash-function-changes-after-update-to-dynamics-365-finance-2020-release-wave-2). (Le terme *code de hachage* fait référence à un champ calculé à partir d’autres champs de chaîne. L’API pour calculer la valeur GUID de code de hachage a été mise à jour pour améliorer la sécurité.) Pour accélérer le processus de clôture de fin d’exercice, nous vous recommandons de reconstruire les soldes des ensembles de dimensions avant d’exécuter cette clôture. Si vous avez déjà effectué une reconstruction des soldes d’ensemble de dimensions après avoir effectué la mise à jour 10.0.13, il n’est pas nécessaire de réexécuter le processus de reconstruction.
 
## <a name="general-ledger--what-does-the-period-close--year-end-close-do"></a>Comptabilité - En quoi consiste Clôture de période - Clôture de fin d’exercice ?
 
[![Clôture de période, Clôture de fin d’exercice.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets-new-feature"></a>Améliorations des performances pour la reconstruction des ensembles de dimensions financières (nouvelle fonctionnalité)
Une nouvelle fonctionnalité ajoutée dans la version 10.0.16 améliore les performances des processus de clôture et de consolidation de fin d’exercice. Cette fonctionnalité s’intitule Améliorations des performances pour la reconstruction des ensembles de dimensions financières. Elle modifie la reconstruction des ensembles de dimensions afin qu’ils ne soient reconstruits que pour une période pertinente. Dans les versions précédentes, les ensembles de dimensions étaient reconstruits pour toutes les dates. Par exemple, si vous clôturez l’année 2020, le système ne reconstruira que les soldes des transactions de l’exercice 2020. Si vous exécutez la consolidation pour une plage de dates allant du 1er novembre 2020 au 30 novembre 2020, le système ne reconstruira que les soldes pour cette plage de dates.

Cette fonctionnalité étant considérée comme importante, vous devrez l’activer à l’aide de l’espace de travail **Gestion des fonctionnalités**.
 
[![Clôture de fin d’exercice.](./media/faq-2020-yr-end-06.png)](./media/faq-2020-yr-end-06.png)

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2020"></a>Comptabilité fournisseur : Quels changements ont été apportés pour prendre en charge la génération d’états de fin d’exercice pour le formulaire 1099 pour 2020 ?

Deux nouvelles fonctionnalités réglementaires ont été ajoutées pour les changements de fin d’exercice du formulaire 1099 en 2020. La première fonctionnalité, **Appliquer les modifications aux formulaires 1099-NEC et 1099-MISC pour 2020**, a été publié en milieu d’année comme une fonctionnalité obligatoire. Son objectif est de s’assurer que données transactionnelles du formulaire 1099 pour l’année 2020 peuvent faire l’objet d’un suivi pour le nouveau formulaire 1099-NEC. Cette fonctionnalité a ajouté les champs du formulaire 1099 nécessaires pour prendre en charge le nouveau formulaire 1099-NEC et mis à jour les champs du formulaire 1099-MISC. Cette mise à jour a également mis à niveau les données d’enregistrement du fournisseur pour les informations de la zone de déclaration des honoraires. 

La deuxième caractéristique réglementaire,**Relevés 1099 mis à jour pour la loi fiscale 2020**, contient les modifications suivantes.

- 1099-OID - L’IRS a converti le formulaire pour une utilisation continue.
   - Les 3è et 4è chiffres de l’exercice de déclaration doivent être renseignés lors de l’impression. Utilisez les 3ème et 4ème chiffres du champ **Année de déclaration** des **Options d’impression de la taxe sur les honoraires**. 

- 1099-NEC - Un nouveau formulaire pour 2020. Ce formulaire enregistre les revenus des travailleurs indépendants. 

-   1099-MISC - En raison de la création du formulaire 1099-NEC, l’IRS a révisé le formulaire 1099-MISC et réorganisé les numéros de case pour déclarer certains revenus.
Les changements dans la déclaration des revenus et les numéros de case du formulaire sont indiqués ci-dessous.
   - Le payeur a réalisé des ventes directes de 5 000 $ ou plus (case à cocher) dans la case 7.
   - Le produit de l’assurance-récolte est indiqué dans la case 9.
   - Le produit brut versé à un avocat est indiqué dans la case 10.
   - Les reports de l’article 409A sont déclarés dans la case 12.
   - Les revenus de rémunération différée non qualifiés sont déclarés à la case 14.
   - Les cases 15, 16 et 17 indiquent respectivement la taxe régionale retenue, le numéro d’identification de taxe régionale et le montant des revenus régionaux gagnés.

- Aucun changement à 1099-DIV ou 1099-INT en 2020.

- Transmission électronique - Le format a changé pour tenir compte du nouveau formulaire NEC, et des modifications de la case MISC décrites ci-dessus. Pour obtenir des informations spécifiques sur les exigences de transmission électronique, voir [Publication IRS 1220](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Comptes fournisseurs : 1099 - Comment puis-je modifier la zone de déclaration des honoraires et les valeurs pour un fournisseur dont les informations n’ont pas fait l’objet d’un suivi tout au long de l’année ?
Utilisez la fonctionnalité Mise à jour 1099 (onglet **Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs > Sélectionner un fournisseur> Fournisseur dans le ruban > Mise à jour 1099**) pour passer par les transactions de facture précédemment payées pour réaffecter les données relatives à la déclaration des honoraires de manière appropriée en fonction des paramètres sur l’onglet **Taxe sur les honoraires** sur la page **Fournisseur**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>Puis-je exécuter la fonctionnalité Mise à jour 1099 pour tous les fournisseurs à la fois ?
Non. La routine de la fonctionnalité Mise à jour 1099 est effectuée sur un seul fournisseur à la fois. Si cette exigence est requise par votre organisation, veuillez noter l’idée intitulée [Processus de traitement par lots pour la mise à jour des données relatives à la déclaration des honoraires du fournisseur](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-vs-update-all-in-the-update-1099-utility"></a>Comptabilité fournisseur : 1099 - « Recalculer les montants des honoraires existants » vs « Tout mettre à jour » dans l’utilitaire Mise à jour 1099.
La case à cocher **Recalculer les montants des honoraires existants** réinitialisera le montant des honoraires aux valeurs totales payées, en cas d’utilisation conjointement avec la case à cocher **Tout mettre à jour**. 

[![Transactions 1099 fiscales : Avant d’exécuter la routine de mise à jour.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

La case à cocher **Recalculer les montants des honoraires existants** n’entre en jeu que lorsqu’il y a des valeurs de déclaration d’honoraire partielles sur la facture ou si elle a été modifiée sur le formulaire de taxe sur les honoraires. Par exemple, supposons que vous ayez une facture évaluée à 1000 $, mais que l’utilisateur tape manuellement un montant d’honoraires de 500 $ sur la facture.

[![Transactions 1099 fiscales : Marquer à la fois Tout mettre à jour et Recalculer les montants des honoraires existants.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Lorsque cela est payé, le montant des honoraires payés sera de 500 $. Si vous effectuez la routine de recalcul, le système remplacera le montant des honoraires par 1000 $, c’est-à-dire le montant total qui a été payé.

[![Transactions 1099 fiscales : Après l’exécution de la routine 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Comptabilité fournisseur : 1099 - Créer manuellement des transactions de déclaration d’honoraires
Une organisation peut avoir besoin de créer manuellement des transactions de déclaration d’honoraires qui ne sont pas associées à une facture. Vous pouvez ajouter des transactions manuelles de déclaration d’honoraires en accédant à **Comptabilité fournisseur > Tâches périodiques> Taxe sur les honoraires > Règlement fournisseur pour les déclarations d’honoraires**. Cliquez sur le bouton **Transactions manuelles de déclaration d’honoraires**. 

Les transactions de déclaration d’honoraires créées manuellement ne sont pas mises à jour avec le processus **Tout mettre à jour** ou le processus **Recalculer les montants des honoraires existants** dans l’utilitaire **Mise à jour 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Comptabilité fournisseur : 1099 - Est-ce que Dynamics 365 Finance prend en charge le formulaire 1096 ? 

Dynamics 365 Finance n’imprime pas le formulaire 1096 Résumé annuel et transmission des déclarations de renseignements aux États-Unis.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Comptes fournisseurs : 1099 - Existe-t-il de nouvelles fonctionnalités prenant en charge la génération d’état 1099 pour le secteur public ? 
Une nouvelle fonctionnalité du secteur public,**Mettre à jour les informations par compte principal 1099**, a été ajoutée. Vous pouvez l’activer dans l’espace de travail **Gestion des fonctionnalités**. Cette fonction vous permet d’associer les valeurs de déclaration d’honoraire pour un fournisseur par le compte principal dans la répartition comptable, plutôt que le compte par défaut sur l’enregistrement du fournisseur.

Pour plus d’informations, voir [Paramétrer des fournisseurs pour la génération d’état 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
