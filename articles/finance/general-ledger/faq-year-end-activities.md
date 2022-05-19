---
title: FAQ sur les activités de fin d’exercice
description: Cette rubrique répertorie les questions qui peuvent se poser lors de la clôture d’un exercice et les réponses qui peuvent faciliter les activités de clôture de fin d’exercice.
author: moaamer
ms.date: 12/21/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 19d23c2c5a8fabd6799c6240c25f3ede4064c001
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725594"
---
# <a name="year-end-activities-faq"></a>FAQ sur les activités de fin d’exercice 

[!include [banner](../includes/banner.md)]

Cette rubrique répertorie les questions qui peuvent se poser lors de la clôture d’un exercice et les réponses qui peuvent faciliter les activités de clôture de fin d’exercice. Les informations contenues dans cette rubrique traitent principalement des questions relatives aux activités de clôture de fin d’exercice en comptabilité et en comptabilité fournisseur.

## <a name="general-ledger-year-end-enhancements"></a>Améliorations apportées à la fin de l’exercice en comptabilité 
La version 10.0.20 améliore la clôture de fin d’exercice activée par défaut à partir de la version 10.0.25. Si votre organisation utilise une version antérieure à la version 10.0.25, nous vous recommandons d’activer cette fonctionnalité avant de commencer le processus de clôture de fin d’exercice. Pour pouvoir utiliser cette fonctionnalité, vous devez l’activer dans le système. Les administrateurs peuvent utiliser l’espace de travail Gestion des fonctionnalités pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. À cet emplacement, la fonctionnalité est répertoriée de la manière suivante :

 - Module : Comptabilité
 - Nom de la fonctionnalité : Améliorations apportées à la fin de l’exercice en comptabilité

La configuration des modèles de clôture de fin d’exercice a été déplacée vers une nouvelle page de configuration, **Configuration du modèle de clôture de fin d’exercice**. La page de clôture de fin d’exercice existante va changer pour ressembler à ce qui se passe dans la réévaluation des comptes en devises en comptabilité où une liste s’affiche à chaque exécution ou contrepassation de la clôture de fin d’exercice. Un chef comptable peut initier la clôture de fin d’exercice à partir de la nouvelle page. 

Pour contrepasser la clôture de fin d’exercice, sélectionnez l’exercice le plus récent pour l’entité juridique appropriée et cliquez sur le bouton **Contrepasser la clôture de fin d’exercice**. Cette contrepassation supprime les écritures comptables de la clôture de fin de l’exercice précédent et réexécute la clôture de fin d’exercice automatiquement. 

Vous pouvez réexécuter la clôture de fin d’exercice en redémarrant le processus pour l’exercice et l’entité juridique. Le processus continue d’utiliser les paramètres de comptabilité pour déterminer si la réexécution de clôture de fin d’exercice ne prendra en compte que les transactions nouvelles ou modifiées, ou si elle contrepassera totalement la clôture précédente, en réexécutant le processus pour toutes les transactions.  

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

## <a name="degenerate-dimensions"></a>Dimensions dégénérées

Une dimension dégénérée ne peut pas être réutilisée seule et en association avec d’autres dimensions ou très peu. Il existe deux types de dimensions dégénérées. Premier type : une dimension individuellement dégénérée. En général, ce type de dimension dégénérée n’apparaît que sur une seule transaction ou sur de petits ensembles de transactions. Deuxième type : dimension qui devient dégénérée en association avec une ou plusieurs dimensions supplémentaires qui présentent le même potentiel en fonction des permutations possibles qui peuvent être générées. Une dimension dégénérée peut avoir un impact significatif sur la performance du processus de clôture de fin d’exercice. Pour limiter les problèmes de performance, définissez toutes les dimensions dégénérées sur **Clôturer individuellement** dans la configuration de la clôture de fin d’exercice, comme indiqué dans la section précédente.

## <a name="general-ledger-what-does-the-period-close-year-end-close-do"></a>Comptabilité : En quoi consiste la clôture de période, la clôture de fin d’exercice ?
 
[![Clôture de période, clôture de fin d’exercice.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets"></a>Améliorations des performances pour la reconstruction des ensembles de dimensions financières
Une nouvelle fonctionnalité, ajoutée dans la version 10.0.16, améliore les performances des processus de consolidation et de clôture de fin d’exercice. Cette fonctionnalité s’intitule Améliorations des performances pour la reconstruction des ensembles de dimensions financières. Elle modifie la reconstruction des ensembles de dimensions afin qu’ils ne soient reconstruits que pour une période pertinente. Dans les versions précédentes, les ensembles de dimensions étaient reconstruits pour toutes les dates. Par exemple, si vous clôturez l’année 2020, le système ne reconstruira que les soldes des transactions de l’exercice 2020. Si vous exécutez la consolidation pour une plage de dates allant du 1er novembre 2020 au 30 novembre 2020, le système ne reconstruit que les soldes pour cette plage de dates.

Pour pouvoir utiliser cette fonctionnalité, vous devez l’activer dans le système. Les administrateurs peuvent utiliser l’espace de travail Gestion des fonctionnalités pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. À cet emplacement, la fonctionnalité est répertoriée de la manière suivante :
 
- Module : Comptabilité
- Nom de la fonctionnalité : Améliorations des performances pour la reconstruction des ensembles de dimensions financières

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2021"></a>Comptabilité fournisseur : Quels changements ont été apportés pour prendre en charge la génération d’états de fin d’exercice pour le formulaire 1099 pour 2021 ?

En 2021, les formulaires DIV, NEC et MISC ont été légèrement modifiés et quelques cases supplémentaires sont apparues.

#### <a name="div-new-box2e-2f"></a>DIV : nouvelles cases 2e, 2f
 
- Case 2e. Indique la partie du montant de la case 1a qui correspond au gain de la section 897 attribuable aux intérêts des biens immobiliers des États-Unis (USRPI).  
- Case 2f. Indique la partie du montant de la case 2a qui correspond au gain de la section 897 attribuable à l’USRPI. Remarquez que les cases 2e et 2f s’appliquent uniquement aux personnes et entités étrangères dont les revenus conservent leur caractère lorsqu’ils sont transmis ou distribués à ses propriétaires ou bénéficiaires étrangers directs ou indirects. Il est généralement considéré comme effectivement lié à un commerce ou à une entreprise aux États-Unis. Consultez les instructions pour votre déclaration de revenus. 
 
#### <a name="nec-new-box-2"></a>NEC : nouvelle case 2 
 
Si la case 2 est cochée, déclarez les produits de consommation totalisant 5 000 $ ou plus qui vous ont été vendus pour la revente, sur une base d’achat-vente, de provision-commission ou autre. En général, vous déclarez tout revenu provenant de la vente de ces produits dans le programme C (formulaire 1040). 
 
En attendant, la taille du formulaire NEC est modifiée. Lors de l’impression, il y a trois formulaires par page. 
 
#### <a name="misc-new-box-11"></a>MISC : nouvelle case 11 
 
La case 11 indique le montant payé pour l’achat de poisson destiné à la revente à tout professionnel de la pêche. Consultez les instructions de votre déclaration de revenus pour déclarer ces revenus. 
 
#### <a name="electronic-filing"></a>Transmission électronique 
Pour plus d’informations sur la transmission électronique, voir [Publication sur les exigences de la transmission électronique](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

Mettre à jour les spécifications de format et les dispositions d’enregistrement pour le rapport électronique 2021 
- Enregistrement « A » de l’émetteur de la section 2. 
- Codes de montant : position du champ 28-45 améliorée, longueur à 18. 
 
#### <a name="sec-2-issuer-a-record-for-reporting-payments-on-form-1099-div"></a>Enregistrement « A » de l’émetteur de la section 2, pour la déclaration des paiements sur le formulaire 1099-DIV : 
- Type de montant : ajout de la section 897 Dividendes ordinaires et ajout du code de montant H. 
- Type de montant : ajout de la section 897 Gains en capital et ajout du code de montant J. 
 
#### <a name="sec-3-payee-b-record"></a>Enregistrement « B » du bénéficiaire de la section 3 
- Enregistrements des informations générales : troisième puce mise à jour de 16 à 18 champs Montant du paiement. 
- Titre du champ Paiement H : position du champ 247-258 mise à jour, titre du champ, longueur et description générale du champ. 
- Titre du champ Paiement J : position du champ 259-270 mise à jour, titre du champ, longueur et description générale du champ. 
- Champ vide mis à jour sur la position du champ 271-286. 
- Indicateur de pays étranger mis à jour sur la position du champ 287. 
- Champ de la ligne du nom du premier bénéficiaire mis à jour sur la position du champ 288-327. 
- Champ de la ligne du nom du deuxième bénéficiaire mis à jour sur la position du champ 328-367. 
- Positions de la disposition d’enregistrement, formulaire 1099-MISC : position du champ 548 et indicateur des exigences de transmission FATCA du titre de champ supprimés. 
- Positions de la disposition d’enregistrement, formulaire 1099-NEC : champ 545-546 vers vide, champ 547 vers indicateur de vente directe, longueur et description et remarques du champ 548-722 vers vide mis à jour. 
 
#### <a name="sec-4-end-of-issuer-c-record"></a>Enregistrement « C » de la fin de l’émetteur de la section 4 
- Titre du champ Paiement H : position du champ 304-321 mise à jour, titre du champ, longueur et description générale du champ. 
- Titre du champ Paiement J : position du champ 322-339 mise à jour, titre du champ, longueur et description générale du champ. 
- Titre du champ 340-499 : longueur mise à jour sur 160. 
 
#### <a name="sec-5-state-totals-k-record"></a>Enregistrement « K » des totaux d’état de la section 5 
- Titre du champ Paiement H : position du champ 304-321 mise à jour, titre du champ, longueur et description générale du champ. 
- Titre du champ Paiement J : position du champ 322-339 mise à jour, titre du champ, longueur et description générale du champ. 
- Titre du champ 340-499 : longueur mise à jour sur 160.  

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Comptabilité fournisseur : 1099 - Comment puis-je modifier la zone de déclaration des honoraires et les valeurs pour un fournisseur dont les informations n’ont pas fait l’objet d’un suivi tout au long de l’année ?
Utilisez la fonctionnalité Mise à jour 1099 (onglet **Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs > Sélectionner un fournisseur> Fournisseur dans le ruban > Mise à jour 1099**) pour passer par les transactions de facture précédemment payées pour réaffecter les données relatives à la déclaration des honoraires de manière appropriée en fonction des paramètres sur l’onglet **Taxe sur les honoraires** sur la page **Fournisseur**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>Puis-je exécuter la fonctionnalité Mise à jour 1099 pour tous les fournisseurs à la fois ?
Non. La routine de la fonctionnalité Mise à jour 1099 est effectuée sur un seul fournisseur à la fois. Si cette exigence est requise par votre organisation, votez pour l’idée intitulée [Processus de traitement par lots pour la mise à jour des données 1099 du fournisseur](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Comptabilité fournisseur : 1099 - Recalculer les montants du formulaire 1099 existants et Tout mettre à jour dans l’utilitaire Mise à jour 1099.
La case à cocher **Recalculer les montants du formulaire 1099 existants** réinitialise le montant des honoraires sur les valeurs totales payées si elle est cochée en même temps que la case **Tout mettre à jour**. 

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

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Comptabilité fournisseur : 1099 - Existe-t-il de nouvelles fonctionnalités prenant en charge la génération d’état 1099 pour le secteur public ? 
Une nouvelle fonctionnalité du secteur public,**Mettre à jour les informations par compte principal 1099**, a été ajoutée. Vous pouvez l’activer dans l’espace de travail **Gestion des fonctionnalités**. Cette fonction vous permet d’associer les valeurs de déclaration d’honoraire pour un fournisseur par le compte principal dans la répartition comptable, plutôt que le compte par défaut sur l’enregistrement du fournisseur.

Pour plus d’informations, voir [Paramétrer des fournisseurs pour la génération d’état 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
