---
title: FAQ sur les activités de fin d’exercice
description: Cet article répertorie les questions qui peuvent se poser lors de la clôture d’un exercice et les réponses qui peuvent faciliter les activités de clôture de fin d’exercice.
author: moaamer
ms.date: 12/01/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2e33c1dcbfa4da74f2e8acc6e29f04fda3abd185
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853038"
---
# <a name="year-end-activities-faq"></a>FAQ sur les activités de fin d’exercice 

[!include [banner](../includes/banner.md)]

Cet article répertorie les questions qui peuvent se poser lors de la clôture d’un exercice et les réponses qui peuvent faciliter les activités de clôture de fin d’exercice. Les informations contenues dans cet article traitent principalement des questions relatives aux activités de clôture de fin d’exercice en comptabilité et en comptabilité fournisseur.

## <a name="general-ledger-year-end-enhancements"></a>Améliorations apportées à la fin de l’exercice en comptabilité

La version 10.0.20 de Microsoft Dynamics 365 Finance a introduit une amélioration de la clôture de fin d’exercice. Cette amélioration est activée par défaut à partir de la version 10.0.25 et est obligatoire à partir de la version 10.0.29. Si votre organisation utilise une version antérieure à la version 10.0.25, nous vous recommandons d’activer cette fonctionnalité avant de commencer le processus de clôture de fin d’exercice. Pour pouvoir utiliser cette fonctionnalité, vous devez l’activer dans le système. Les administrateurs peuvent utiliser l’espace de travail **Gestion des fonctionnalités** pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. À cet emplacement, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** Comptabilité
- **Nom de la fonctionnalité :** Améliorations apportées à la fin de l’exercice en comptabilité

La configuration des modèles de clôture de fin d’exercice a été déplacée vers une nouvelle page de configuration, **Configuration du modèle de clôture de fin d’exercice**. La page de clôture de fin d’exercice existante va devenir une page du style **Réévaluation des comptes en devises dans la Comptabilité** où une liste s’affiche à chaque exécution ou contrepassation de la clôture de fin d’exercice. La page n’affichera pas d’informations historiques sur les clôtures de fin d’exercice effectuées avant l’activation de la fonctionnalité. Un chef comptable peut initier la clôture de fin d’exercice à partir de la nouvelle page.

Pour contrepasser la clôture de fin d’exercice, sélectionnez l’exercice le plus récent pour l’entité juridique appropriée, puis sélectionnez **Contrepasser la clôture de fin d’exercice**. Cette contrepassation supprime les écritures comptables de la clôture de fin de l’exercice précédent et ne réexécute pas automatiquement la clôture de fin d’exercice. Si vous activez la fonctionnalité **Améliorations apportées à la fin de l’exercice en comptabilité** après avoir effectué une clôture de fin d’exercice et que vous souhaitez contrepasser les résultats historiques de fin d’exercice, exécutez la la clôture historique de fin d’exercice après avoir activé le paramètre de Comptabilité **Supprimer les entrées de fin d’exercice existantes lors de la nouvelle clôture de l’exercice**.

Vous pouvez réexécuter la clôture de fin d’exercice en redémarrant le processus pour l’exercice et l’entité juridique. Le processus continue d’utiliser les paramètres de Comptabilité pour déterminer si la réexécution de clôture de fin d’exercice ne prendra en compte que les transactions nouvelles ou modifiées, ou si le processus est réexécuté pour toutes les transactions et contrepasse totalement la clôture précédente.

## <a name="general-ledger-the-general-ledger-year-end-enhancements-feature-is-enabled-why-cant-i-view-my-previous-year-closings-in-the-history-section-of-the-year-end-close-page"></a>Comptabilité : La fonctionnalité Améliorations apportées à la fin de l’exercice en comptabilité est activée. Pourquoi ne puis-je pas voir mes clôtures de l’exercice précédent dans la section Historique de la page Clôture de fin d’exercice ?

Avant l’activation de la fonctionnalité **Améliorations apportées à la fin de l’exercice en comptabilité**, la date et l’heure de la dernière exécution du processus de clôture de fin d’exercice sont suivies. Aucun suivi n’est assuré pour l’historique à chaque exécution de la clôture de fin d’exercice. C’est pourquoi les détails de chaque exécution de la clôture de fin d’exercice ne peuvent pas être affichés. Une fois la fonctionnalité activée, les informations sur le processus suivant de clôture de fin d’exercice sont conservées. Les justificatifs de tous les processus de clôture de fin d’exercice, même ceux exécutés avant l’activation de la fonctionnalité, peuvent être consultés sur la page **Transactions de N° document**. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-cant-be-run-because-one-or-more-ledger-transactions-posted-into-the-fiscal-year-that-you-are-closing-were-settled-to-a-ledger-transaction-in-a-different-fiscal-year-what-does-this-error-mean"></a>Comptabilité : Le processus de clôture de fin d’exercice échoue en raison de l’erreur suivante : « La clôture de fin d’exercice ne peut pas être exécutée, car au moins une écriture comptable validée dans l’exercice que vous clôturez a été réglée par une écriture comptable dans un autre exercice financier. » Que signifie cette erreur ?

Étant donné que la fonctionnalité **Reconnaissance entre un règlement comptable et la clôture de fin d’exercice** est activée, seules les écritures comptables réglées par l’exercice en cours de clôture sont exclues du solde d’ouverture. Ce comportement entraîne un déséquilibre des débits et des crédits. Pour plus d’informations, voir [Reconnaissance entre un règlement comptable et la clôture de fin d’exercice](awareness-between-ledger-settlement-year-end-close.md).

## <a name="general-ledger-reversal-of-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-for-112022-cant-be-reversed-because-beginning-balance-transaction-have-been-ledger-settled-in-fiscal-year-112023-what-does-this-error-mean"></a>Comptabilité : La contrepassation du processus de clôture de fin d’exercice échoue en raison de l’erreur suivante : « La clôture de fin d’exercice du 01/01/2022 ne peut pas être contrepassée, car la transaction du solde d’ouverture a été réglée en comptabilité au cours de l’exercice 01/01/2023. » Que signifie cette erreur ?

La fonctionnalité **Reconnaissance entre un règlement comptable et la clôture de fin d’exercice** étant activée, les contrepassations du traitement de fin d’exercice ne sont pas autorisées si les transactions d’ouverture ont été réglées dans le nouvel exercice. Contrepassez le règlement comptable dans le nouvel exercice 2023 avant de contrepasser la clôture de fin d’exercice du 1er janvier 2022. Vous pouvez également à nouveau clôturer l’exercice au 1er janvier 2022, mais uniquement pour les nouvelles écritures de régularisation. Pour à nouveau clôturer l’exercice pour les ajustements uniquement, désactivez le paramètre de Comptabilité **Supprimer les entrées de fin d’exercice existantes lors de la nouvelle clôture de l’exercice**.

## <a name="general-ledger-why-isnt-the-ledger-settlement-automation-processing-decembers-ledger-settlement-transactions"></a>Comptabilité : Pourquoi l’automatisation du règlement comptable ne traite-t-elle pas les transactions de règlement comptable de décembre ?

La fonctionnalité **Automatiser les règlements comptables** exécutera l’automatisation pour les transactions datées du premier jour de l’exercice jusqu’à la date actuelle lorsque l’occurrence s’exécute. Pour les exercices se terminant le 31 décembre, vous devrez peut-être ajuster la date d’exécution de votre occurrence pour vous assurer qu’elle est exécutée en décembre. Par exemple, l’automatisation est configurée pour s’exécuter le premier jour de chaque mois. Cette automatisation sera exécutée le 1er décembre 2022 et devrait s’exécuter le 1er janvier 2023. Nous vous recommandons de modifier l’occurrence du 1er janvier 2023 afin qu’elle s’exécute plutôt le 31 décembre 2022. Ce changement garantira que les transactions datées du 2 au 31 décembre seront prises en compte pour le règlement automatique.

## <a name="general-ledger-whats-the-difference-between-the-reverse-year-end-close-action-and-the-delete-existing-year-end-entries-when-reclosing-parameter-for-year-end-close"></a>Comptabilité : Quelle est la différence entre l’action Contrepasser la clôture de fin d’exercice et le paramètre Supprimer les entrées de fin d’exercice existantes lors de la nouvelle clôture pour la clôture de fin d’exercice ?

Une confusion peut exister quant à la différence entre l’action **Contrepasser la clôture de fin d’exercice** et le paramètre de Comptabilité **Supprimer les entrées de fin d’exercice existantes lors de la nouvelle clôture** (**Comptabilité \> Paramétrage de la comptabilité \> Paramètres de comptabilité**).

Sélectionnez l’action **Contrepasser la clôture de fin d’exercice** lors de l’exécution du processus de clôture de fin d’exercice pour supprimer toutes les écritures du solde de clôture et du solde d’ouverture, comme si la clôture de fin d’exercice n’avait jamais été exécutée. Dans ce cas, les justificatifs seront supprimés. La clôture de fin d’exercice ne s’exécutera pas à nouveau automatiquement. Pour exécuter la clôture de fin d’exercice, sélectionnez l’action **Exécuter la clôture de fin d’exercice**.

Le paramètre de Comptabilité **Supprimer les entrées de fin d’exercice existantes lors de la nouvelle clôture de l’exercice** est utilisé uniquement lorsque vous exécutez (et non contrepassez) la clôture de fin d’exercice. Si le paramètre est défini sur **Oui**, toutes les écritures de solde de clôture et de solde d’ouverture seront supprimées et la clôture de fin d’exercice recommencera. Cette option est utilisée lorsqu’une organisation souhaite que toutes les transactions, y compris les ajustements depuis la dernière clôture de fin d’exercice, soient comptabilisées dans une seule écriture comptable pour les écritures du solde de clôture et du solde d’ouverture. Si le paramètre est défini sur **Non**, toutes les écritures du solde de clôture et du solde d’ouverture sont conservées. Elles ne sont pas supprimées. Au lieu de cela, une nouvelle écriture de solde de clôture et une nouvelle écriture de solde d’ouverture seront créées uniquement pour le delta ou pour les nouvelles transactions validées depuis la dernière clôture de fin d’exercice pour cet exercice.

> [!NOTE]
> L’écriture du solde de clôture est créée dans l’exercice en cours de clôture. Cela se produit uniquement si le paramètre de comptabilité **Création de transactions de clôture lors du transfert** est défini sur **Oui** en Comptabilité. L’écriture de solde d’ouverture est toujours créée, car il s’agit du solde d’ouverture de l’exercice suivant.

## <a name="general-ledger-what-is-the-difference-between-close-all-and-close-single-options-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process"></a>Comptabilité : Quelle est la différence entre les options « Fermer tout » et « Fermer individuellement » dans la section Transférer les dimensions du résultat du processus de clôture de fin d’exercice ?

**Fermer tout** conserve les valeurs d’origine de dimension financière des transactions validées et les utilise pour créer les soldes d’ouverture pour le compte de bénéfices non répartis. Des soldes de départ distincts des bénéfices non répartis seront créés pour chaque combinaison unique de valeurs de dimension financière. Si **Fermer individuellement** est sélectionné, toutes les transactions validées avec cette dimension financière sont résumées dans un solde d’ouverture de bénéfices non répartis pour la valeur de dimension entrée dans le champ qui s’affiche après **Fermer individuellement**. 

Par exemple, toutes les transactions pour l’exercice ont été validées avec la structure de compte Compte principal – Département. Pour la dimension financière Département du modèle, **Fermer individuellement** est sélectionné et la valeur 100 est entrée comme valeur de dimension. Si le revenu total de toutes les transactions validées dans les départements 200, 300 et 400 est de 100 000 $, un solde d’ouverture est créé pour les Bénéfices non répartis – 100. Si vous sélectionnez **Fermer individuellement**, mais laissez vierge la valeur de dimension financière, toutes les transactions seront validées dans les bénéfices non répartis et la valeur de dimension demeurera vierge.

## <a name="general-ledger-when-i-select-close-single-option-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process-will-my-detailed-transactional-information-be-lost"></a>Comptabilité : Lorsque je sélectionne l’option « Fermer individuellement » dans la section Transférer les dimensions du résultat du processus de clôture de fin d’exercice, mes informations transactionnelles détaillées sont-elles perdues ?

Les options **Fermer tout** et **Fermer individuellement** permettent de spécifier les dimensions financières des transactions validées au compte de résultat qui seront transférées au compte principal des bénéfices non répartis. La validation historique et détaillée au compte de résultat n’est pas impactée et restera détaillée. L’option a une incidence sur le niveau de détail qui est transféré aux comptes de bénéfices non répartis en tant que solde d’ouverture au cours du nouvel exercice. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-the-reporting-currency-for-the-year-does-not-balance-what-does-this-mean"></a>Comptabilité : le processus de clôture de fin d’exercice échoue, car la devise de déclaration pour l’exercice est déséquilibrée. Que signifie ceci ?

Cette erreur peut se produire après l’activation de la fonctionnalité **Reconnaissance entre un règlement comptable et la clôture de fin d’exercice** (la fonctionnalité Reconnaissance). Lorsque la fonctionnalité est activée, les écritures comptables qui ont été réglées ne sont plus incluses dans le solde d’ouverture de l’exercice suivant lors de l’exécution de la clôture de fin d’exercice de comptabilité. L’exclusion des écritures comptables qui sont réglées peut présenter un défi pour les clients lors de la clôture de fin d’exercice si la comptabilité est définie avec une devise de déclaration.   
Le règlement comptable est effectué uniquement pour la devise comptable.  Lorsque les écritures comptables sont réglées, le contrôle garantit uniquement que les débits en devise comptable sont égaux aux crédits en devise comptable. Les montants en devise de déclaration pour ces écritures comptables ne sont pas validés et peuvent ne pas avoir de débits = crédits.  De plus, le règlement comptable ne calcule pas et ne valide pas automatiquement un gain/une perte dans la devise de déclaration.  En raison de ces limitations, une transaction de gain/perte doit exister dans la devise de déclaration lors de l’exécution du règlement comptable.  Si le gain/la perte n’est pas inclus dans le règlement comptable, la clôture de fin d’exercice générera un message de déséquilibre.  Pour plus d’informations, voir [La reconnaissance entre la fonctionnalité de règlement comptable et la devise de déclaration est déséquilibrée](reporting-currency-yec.md).

## <a name="general-ledger-what-can-be-changed-to-help-enhance-the-performance-of-year-end-processing"></a>Comptabilité : Comment faire pour contribuer à l’amélioration des performances du processus de fin d’exercice ?

Vous pouvez apporter plusieurs modifications pour contribuer à l’amélioration des performances de la clôture de fin d’exercice. Nous vous recommandons d’évaluer ces propositions pour déterminer si elles sont appropriées pour votre organisation.

### <a name="optimize-year-end-close-service"></a>Service Optimiser la clôture de fin d’exercice

Le service **Optimiser la clôture de fin d’exercice** permet aux clients Microsoft Dynamics 365 Finance d’accélérer leur clôture de fin d’exercice en déplaçant le traitement lourd de fin d’exercice vers un microservice. Le temps gagné grâce à une clôture de fin d’exercice efficace permet à chaque équipe de Finance de réagir en temps voulu aux ajustements requis, aboutissant à la génération des états financiers. Le traitement de la clôture de fin d’exercice sur un microservice permet de libérer des ressources précieuses. L’élévation du traitement minimise la charge sur SQL Server et donne aux clients la possibilité d’accélérer le traitement de la clôture de fin d’exercice.

Le service **Optimiser la clôture de fin d’exercice** est disponible dans la version 10.0.31, afin que davantage de clients puissent utiliser le nouveau service pour la saison de fin d’exercice 2022. De plus, le service a été rétroporté vers les versions 10.0.30 et 10.0.29. Pour plus d’informations, voir [Optimiser la clôture de fin d’exercice](optimize-year-end-close.md).

### <a name="dimension-sets"></a>Ensembles de dimensions

Lorsque vous exécutez la clôture de fin d’exercice, chaque solde d’ensemble de dimensions est reconstruit. Ce comportement a un impact direct sur les performances. Certaines organisations créent des ensembles de dimensions inutilement, car ils ont été utilisés à un moment donné ou sont susceptibles de l’être. Ces ensembles de dimensions inutiles étant toujours reconstruits lors de la clôture de fin d’exercice, le processus est allongé. Prenez le temps d’évaluer vos ensembles de dimensions et supprimez ceux qui sont inutiles.

Les ensembles de dimensions inutiles ont également un impact sur le traitement par lots **BudgetDimensionFocusInitializeBalance** (**Comptabilité \> Plan comptable \> Dimensions \> Ensembles de dimensions financières**).

[![Ensembles de dimensions financières.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configuration du modèle de clôture de fin d’exercice

Le modèle de clôture de fin d’exercice permet aux organisations de sélectionner le niveau de dimension financière à maintenir lors du transfert des soldes de profits et pertes vers les bénéfices non répartis. Les paramètres permettent à une organisation de conserver les dimensions financières détaillées (**Clôturer tout**) lors du transfert des soldes vers les bénéfices non répartis ou de choisir de récapituler les montants en une seule valeur de dimension (**Clôturer individuellement**). Cela peut être défini pour chaque dimension financière. Pour plus d’informations sur ces paramètres, consultez l’article [Clôture de fin d’exercice](year-end-close.md).

Nous vous recommandons d’évaluer les exigences de votre organisation et, si possible, de clôturer autant de dimensions que possible à l’aide de l’option de fin d’exercice **Clôturer individuellement** pour améliorer les performances. En clôturant sur une seule valeur de dimension (qui peut également être une valeur vide), le système calcule moins de détails lors de la détermination des soldes pour les écritures de compte de bénéfices non répartis.

### <a name="degenerate-dimensions"></a>Dimensions dégénérées

Une dimension dégénérée ne peut pas être réutilisée seule et en association avec d’autres dimensions ou très peu. Il existe deux types de dimensions dégénérées. Premier type : une dimension individuellement dégénérée. En général, ce type de dimension dégénérée n’apparaît que sur une seule transaction ou sur de petits ensembles de transactions. Deuxième type : dimension qui devient dégénérée en association avec une ou plusieurs dimensions supplémentaires qui présentent le même potentiel en fonction des permutations possibles qui peuvent être générées. Une dimension dégénérée peut avoir un impact significatif sur la performance du processus de clôture de fin d’exercice. Pour limiter les problèmes de performance, définissez toutes les dimensions dégénérées sur **Fermer individuellement** dans la configuration de la clôture de fin d’exercice, comme indiqué dans la section précédente.

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2022"></a>Comptabilité fournisseur : Quels changements ont été apportés pour prendre en charge les rapports de fin d’exercice 1099 pour 2022 ?

#### <a name="update-to-all-1099-forms"></a>Mise à jour de tous les formulaires 1099

Les changements suivants ont été apportés à tous les formulaires 1099 pour l’année fiscale 2022 :

- En 2021, l’année était fixe sur les formulaires 1099. À partir de 2022, l’année est remplie par le rapport.

#### <a name="1099-misc"></a>1099-MISC

Les mises à jour suivantes ont été apportées au formulaire 1099-MISC pour l’année fiscale 2022 :

- Case 13 : indique maintenant les conditions de déclaration de la FATCA (Foreign Account Tax Compliance Act).
- Case 14 : maintenant utilisée pour déclarer les paiements excessifs de parachute doré.
- Case 15 : maintenant utilisée pour déclarer le paiement dans le cadre des régimes de rémunération différée non qualifiée (NQDC).
- Case 16 : maintenant utilisée pour déclarer les impôts d’État retenus.
- Case17 : maintenant utilisée pour déclarer le numéro d’État du contribuable.
- Case 18 : maintenant utilisée pour déclarer les revenus d’État.

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Comptabilité fournisseur : 1099 - Comment puis-je modifier la zone de déclaration des honoraires et les valeurs pour un fournisseur dont les informations n’ont pas fait l’objet d’un suivi tout au long de l’année ?

Utilisez la fonctionnalité **Mettre à jour formulaire de déclaration des honoraires** pour passer en revue les transactions de factures précédemment payées et réaffecter les données de déclaration des honoraires de manière appropriée, selon les paramètres de l’onglet **Taxe sur les honoraires** de la page **Fournisseur**. Pour utiliser la fonctionnalité **Mettre à jour formulaire de déclaration des honoraires**, accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs**, sélectionnez un fournisseur, puis, dans le volet Actions, dans l’onglet **Fournisseur**, sélectionnez **Mettre à jour formulaire de déclaration des honoraires**.

## <a name="can-i-run-the-update-1099-functionality-for-all-my-vendors-at-once"></a>Puis-je exécuter la fonctionnalité Mettre à jour formulaire de déclaration des honoraires pour tous les fournisseurs à la fois ?

Vous pouvez utiliser la page **Mettre à jour les informations 1099 pour plusieurs fournisseurs** pour mettre à jour la zone de déclaration des honoraires sur un enregistrement de fournisseur et pour mettre à jour les transactions avec les informations de la zone de déclaration des honoraires. Pour ouvrir cette page, accédez à **Comptabilité fournisseur \> Tâche périodique \> Taxe sur les honoraires**. Pour accéder à la page, vous devez disposer du privilège de sécurité **Mettre à jour la zone et les transactions 1099 pour plusieurs fournisseurs**.

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Comptabilité fournisseur : 1099 - Recalculer les montants du formulaire 1099 existants et Tout mettre à jour dans l’utilitaire Mettre à jour formulaire de déclaration des honoraires

La case à cocher **Recalculer les montants existants de la déclaration d’honoraires** réinitialise le montant des honoraires sur les valeurs totales payées si elle est cochée en même temps que la case **Tout mettre à jour**.

[![Transactions 1099 fiscales : Avant d’exécuter la routine de mise à jour.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

La case à cocher **Recalculer les montants existants de la déclaration d’honoraires** n’entre en jeu que lorsqu’il y a des valeurs de déclaration d’honoraire partielles sur la facture ou si elle a été modifiée sur le formulaire de taxe sur les honoraires. Par exemple, supposons que vous ayez une facture évaluée à 1 000 $, mais que l’utilisateur tape manuellement un montant d’honoraires de 500 $ sur la facture.

[![Transactions 1099 fiscales : Marquer à la fois Tout mettre à jour et Recalculer les montants des honoraires existants.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Lorsque cette facture est payée, le montant des honoraires payés sera de 500 $. Si vous effectuez la routine de recalcul, le système remplacera le montant des honoraires par 1 000 $, c’est-à-dire le montant total qui a été payé.

[![Transactions 1099 fiscales : Après l’exécution de la routine 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Comptabilité fournisseur : 1099 - Créer manuellement des transactions de déclaration d’honoraires

Une organisation peut avoir besoin de créer manuellement des transactions de déclaration d’honoraires qui ne sont pas associées à une facture. Vous pouvez ajouter des transactions manuelles de déclaration d’honoraires en accédant à **Comptabilité fournisseur \> Tâches périodiques\> Taxe sur les honoraires \> Règlement fournisseur pour les déclarations d’honoraires**. Cliquez sur le bouton **Transactions manuelles de déclaration d’honoraires**.

Les transactions de déclaration d’honoraires créées manuellement ne sont pas mises à jour avec le processus **Tout mettre à jour** ou le processus **Recalculer les montants des honoraires existants** dans l’utilitaire **Mettre à jour formulaire de déclaration des honoraires**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Comptabilité fournisseur : 1099 - Est-ce que Dynamics 365 Finance prend en charge le formulaire 1096 ?

Dynamics 365 Finance n’imprime pas le formulaire 1096 Résumé annuel et transmission des déclarations de renseignements aux États-Unis.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Comptabilité fournisseur : 1099 - Existe-t-il de nouvelles fonctionnalités prenant en charge la génération d’état 1099 pour le secteur public ?

Une nouvelle fonctionnalité du secteur public,**Mettre à jour les informations par compte principal 1099**, a été ajoutée. Vous pouvez l’activer dans l’espace de travail **Gestion des fonctionnalités**. Cette fonction vous permet d’associer les valeurs de déclaration d’honoraire pour un fournisseur par le compte principal dans la répartition comptable, plutôt que le compte par défaut sur l’enregistrement du fournisseur.

Pour plus d’informations, voir [Paramétrer des fournisseurs pour la génération d’état 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
