---
title: Validation d’un ordre de fabrication
description: Cette rubrique fournit des informations sur différents types de validation d’un ordre de fabrication.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, ProjCategory, CostSheetDesigner
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: cd1b6c49e59f9480fd831ad5ff143033ca09792c
ms.sourcegitcommit: 5b55f2913e736d12e40c227bf3ce3a9abec815bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2022
ms.locfileid: "8802993"
---
# <a name="production-postings"></a>Validations de la production

Cette rubrique fournit des informations sur différents types de validations du processus d’ordre de fabrication.


## <a name="material-consumption"></a>Consommation de matières

Les matières sont enregistrées comme consommées durant la production lorsque le journal de prélèvement en production est validé. Cela crée des transactions de sortie qui sont déduites du stock disponible. Dans les **Paramètres de production**, vous pouvez spécifier si la valeur des matières premières en cours (travaux en cours) doit être validée dans la comptabilité.

La valeur des matières premières en cours (travaux en cours) est comptabilisée dans les comptes **Estimation du coût des matériaux consommés** et **Estimation du coût des matériaux consommés, travaux en cours**. Le processus de liste de prélèvement pour l’ordre de fabrication est une mise à jour physique des transactions de stock liées à l’ordre de fabrication. Lorsqu’un ordre de fabrication est enregistré comme terminé, les transactions physiques sont annulées et les transactions de stock associées sont mises à jour financièrement. Lorsque le journal final est comptabilisé, les types de validation **Coût des matériaux consommés** et **Coût des matériaux consommés, travaux en cours** sont utilisés.

L’onglet **Production** sur la page **Profils de validation de stock** contrôle la manière dont les ordres de fabrication sont enregistrés dans la comptabilité. Ceci est utilisé lorsque le champ **Validation dans la comptabilité** est défini sur **Article et ressource** ou **Article et catégorie** sur la page **Paramètres de contrôle de production**. 

Pour qu’un journal des prélèvements soit comptabilisé dans la comptabilité pour un ordre de fabrication, les conditions suivantes doivent être remplies :

-   La case **Valider les prélèvements dans la comptabilité** doit être cochée sur la page **Paramètres de contrôle de la production**. Ce paramètre peut être remplacé pour un site spécifique sur la page **Paramètres de contrôle de la production par site**.
-   La case **Valider le stock physique** doit être cochée sur la page **Groupes de modèles d’article** pour l’article sélectionné sur la ligne de commande fournisseur.
-   Les comptes principaux doivent être spécifiés sur la page **Profil de validation de stock**, les comptes principaux doivent être précisés pour les types d’écriture suivants :
    -   **Coût estimé des matières utilisées**
    -   **Coût estimé des matières utilisées, travaux en cours**

## <a name="time-consumption"></a>consommation de temps.

Le temps passé par les collaborateurs sur les tâches de production est enregistré dans le **journal des fiches productions** ou dans le **journal des bons de travail**. Lorsque ces journaux sont validés, la validation de la comptabilité dans un compte dédié pour les ressources en cours (travaux en cours) est traitée. Cette validation représente la valeur du temps passé sur l’ordre de fabrication. Une fois l’ordre de fabrication enregistré comme terminé, les comptes de travaux en cours sont réglés.

Il existe trois façons possibles d’afficher la consommation de temps selon l’option sélectionnée dans le champ **Validation dans la comptabilité** sur la page **Paramètres de contrôle de production**.

## <a name="reporting-finished-goods-and-error-quantities"></a>Déclaration des produits finis et des quantités d’erreur

Lorsqu’un ordre de fabrication est **déclaré terminé**, la quantité des produits finis déclarés terminés est mise à jour dans Gestion des stocks via le journal de **Déclaration de fin**. Si vous utilisez la gestion des travaux en cours, un journal comptable est validé pour réduire les comptes de travaux en cours et augmenter le stock de produits finis. Le journal utilise le coût standard qui a été défini pour le produit. Si l’option **Utiliser le prix de revient estimé** est sélectionnée sur la page **Paramètres de contrôle de production**, le coût estimé de l’ordre de fabrication sera utilisé.

La valeur des matières premières en cours (travaux en cours) est comptabilisée dans les comptes **Coût de fabrication estimé** et **Coût de fabrication estimé, travaux en cours**. Le processus **Déclarer comme terminé** pour l’ordre de fabrication est une mise à jour physique des transactions de stock liées à l’ordre de fabrication. Lorsqu’un ordre de fabrication est terminé, les transactions physiques sont annulées et les transactions de stock associées sont mises à jour financièrement. Lorsque le journal final est comptabilisé, les types de validation **Coût de fabrication** et **Coût de fabrication, travaux en cours** sont utilisés.

L’onglet **Production** sur la page **Profils de validation de stock** est utilisé pour contrôler la manière dont les commandes de production seront enregistrées dans la comptabilité. Ceci est utilisé lorsque le champ **Validation dans la comptabilité** est défini sur **Article et ressource** ou **Article et catégorie** sur la page **Paramètres de contrôle de production**. Le raccourci **Comptabilité - Articles** sur la page **Groupes de production** peut également être utilisée pour contrôler la validation des ordres de fabrication lorsque le champ est défini sur **Groupes de production**.

Pour qu’un journal **Déclarer comme terminé** soit comptabilisé dans la comptabilité pour un ordre de fabrication, les conditions suivantes doivent être remplies :
-   La case **Valider les déclarations de fin dans la comptabilité** doit être cochée sur la page **Paramètres de contrôle de la production**. Ce paramètre peut être remplacé pour un site spécifique sur la page **Paramètres de contrôle de la production par site**.
-   La case **Valider le stock physique** doit être cochée sur la page **Groupes de modèles d’article** pour l’article sélectionné sur la ligne de commande fournisseur.
-   Les comptes principaux doivent être spécifiés sur la page **Profil de validation de stock**, les comptes principaux doivent être précisés pour les types d’écriture suivants :
    -   **Coût de fabrication estimé**
    -   **Coût de fabrication estimé, travaux en cours**

## <a name="ending-the-production-order"></a>Fin de l’ordre de fabrication

Avant la fin d’un ordre de fabrication, les coûts réels sont calculés pour la quantité produite. Tous les coûts estimés de matière, main d’œuvre et frais généraux sont contrepassés et remplacés par les coûts réels. Le coût total de l’article fini est débité du compte **Coût de fabrication** et crédité sur le compte **Coût de fabrication, travaux en cours**. Les matières qui ont été consommées lors de l’ordre de fabrication sont créditées au **Coût des matériaux consommés** et débité au compte **Coût des matériaux, travaux en cours**.

Si vous sélectionnez la case à cocher **Tâche de fin** lors du calcul des coûts, le statut de l’ordre de fabrication passe sur **Terminé**. Ce statut empêche que tout coût supplémentaire soit validé par erreur dans un ordre de fabrication terminé. Vous pouvez spécifier que la valeur des quantités d’erreur déclarées terminées doit être attribuée aux bonnes quantités déclarées comme terminées. Sinon, vous pouvez spécifier que la valeur des quantités d’erreur est validée dans un compte des rebuts dédié. 

Pour spécifier un compte de rebuts, procédez comme suit :
1.  Accédez à **Contrôle de la production** > **Paramétrage** > **Paramètres de contrôle de la production**.
2.  Sélectionnez l’onglet **Mise à jour standard**.
3.  Dans le champ **Mode de mise au rebut**, sélectionnez **Compte des rebuts**.
4.  Dans le **Compte des rebuts**, sélectionnez le compte principal dans lequel la quantité de rebut pour erreur doit être comptabilisée lorsque l’ordre de fabrication est terminé. Par exemple, sélectionnez un compte de dépenses tel que 510380 : Rebut de production.

Pour qu’un journal de fin soit comptabilisé dans la comptabilité pour un ordre de fabrication, les conditions suivantes doivent être remplies :
-   Les comptes principaux doivent être spécifiés sur la page **Profil de validation de stock** ou **Groupes de production**, les comptes principaux doivent être précisés pour les types d’écriture suivants :
    -   **Coût des matières utilisées**
    -   **Coût des matières utilisées, travaux en cours**
    -   **Coût de fabrication**
    -   **Coût de fabrication, travaux en cours**
-   Les comptes principaux doivent être précisés sur la page **Catégories de coûts**, **Ressources** ou **Groupes de ressources** pour les types suivants :
    -   **Coût de fabrication absorbé**
    -   **Coût de production absorbé, travaux en cours**

## <a name="indirect-costs-for-production-orders"></a>Coûts indirects des ordres de fabrication

Lorsque vous traitez des transactions pour un ordre de fabrication, vous pouvez configurer des coûts indirects pour saisir les frais généraux ou les frais supplémentaires dans votre comptabilité. Les transactions physiques pour les coûts indirects sont reconnues dans le stock lorsque vous publiez un journal de prélèvement ou un rapport en tant que journal terminé. Les transactions financières pour les coûts indirects sont reconnues dans le stock lorsque vous validez le journal de fin.

Vous pouvez reconnaître des coûts indirects sur votre consommation de temps liés aux journaux **Fiche production** ou **Bon de travail**. Ces transactions sont annulées et comptabilisées dans les comptes financiers lorsque vous terminez l’ordre de fabrication. - Pour plus d’informations, consultez [Feuilles de coûts](/supply-chain/cost-management/costing-sheets.md).

## <a name="controlling-the-level-of-ledger-posting"></a>Contrôle du niveau de validation de la comptabilité

Sur la page **Paramètres de contrôle de production**, vous pouvez utiliser le champ **Validation dans la comptabilité** pour définir le niveau de validation de la comptabilité pour les processus de production. 

Les champs disponibles sont les suivants :

### <a name="item-and-resource"></a>Article et ressource

Lorsque vous sélectionnez l’option **Article et ressource** dans le champ **Validation dans la comptabilité**, les comptes d’écriture proviennent de la ressource ou du groupe de ressources en opération dans la gamme. Les comptes sur la ressource spécifique seront la première option de validation. Si aucun compte n’est spécifié, les comptes spécifiés sur le groupe de ressources seront utilisés. Chaque ligne d’opération d’une gamme peut avoir une ressource spécifiée comme **Ressource d’évaluation des coûts**. Cette ressource est utilisée pour déterminer le compte à utiliser. Cette option est couramment utilisée lorsqu’une organisation affecte des coûts d’exploitation aux ressources. Les coûts sont souvent plus élevés pour les ressources et sont utilisés pour aider à prendre des décisions "fabriquer ou acheter". Il s’agit de la configuration de validation la plus détaillée et permet le contrôle le plus granulaire des validations et des analyses très détaillées du processus de production.

### <a name="item-and-category"></a>Article et catégorie

Lorsque vous sélectionnez l’option **Article et catégorie** dans le champ **Validation dans la comptabilité**, les comptes d’écriture proviendront de la page **Catégorie de coût** relative à chaque ligne de la gamme. Chaque ligne d’opération de la gamme peut avoir trois catégories de coût : Temps de **Réglage**, Temps d’**Exécution** et **Quantité**. Cette option est couramment utilisée lorsque l’objectif principal de votre organisation est l’efficacité des processus et la durée des activités. Cette option est une manière plus résumée de valider, et fournit toujours un moyen de regrouper les coûts en catégories.

### <a name="production-group"></a>Groupe de production

Lorsque vous sélectionnez l’option **Groupes de production** dans le champ **Validation dans la comptabilité**, les comptes d’écriture proviennent de la page **Groupes de production**. Les **groupes de production** sont généralement utilisés lorsque plusieurs lignes de production utilisent des produits similaires ou disposent d’équipements similaires. Vous pouvez utiliser cette option pour comparer les coûts entre deux groupes de production différents.  
  
> [!NOTE]
> Si la méthode standard de calcul du coût de l’article fini a été appliquée, les transactions finales tiendront également compte de cela. Si les coûts réels et les coûts calculés par la méthode standard sont différents, les différences sont validées sur le compte qui affiche un profit ou une perte.

### <a name="route-groups-and-ledger-posting"></a>Groupes de gammes et validation dans la comptabilité

Chaque ligne d’opération d’une gamme a un **Groupe de gammes** spécifié. Les champs **Temps de réglage**, **Temps d’exécution** et **Quantité** dans le **Groupe de gammes** au sein du groupe **Estimation et chiffrage** sont utilisés pour contrôler si le temps sera utilisé pour le calcul des coûts lors de la validation d’un **Bon de travail** ou d’un **Journal des fiches productions** sur l’ordre de fabrication. Si les options sont désactivées, un bon ne sera pas créé dans la comptabilité pour la consommation de temps.

Pour qu’une **Fiche de production** ou qu’un **Journal des bons de travail** soit comptabilisé.e dans la comptabilité pour un ordre de fabrication, les conditions suivantes doivent être remplies :

-   Le champ **Temps de réglage**, **Temps d’exécution** ou **Quantité** doit être sélectionné dans le groupe **Estimation et chiffrage** de la page **Groupe de gammes**.
-   Les comptes principaux doivent être spécifiés sur la page **Catégorie de coûts**, **Gamme**, **Groupe de gammes** ou **Groupes de production** doivent être précisés pour les types d’écriture suivants :
    -   Coût de fabrication estimé absorbé
    -   Coût estimé du coût de fabrication consommé, travaux en cours

Le diagramme suivant montre la relation entre le groupe de gammes et le calcul du coût total pour chaque opération (ligne de gamme) dans une gamme donnée. Chaque ligne de routage possède un groupe de gammes. Le groupe de routage contrôle les paramètres de temps de configuration, de temps d’exécution et de quantité. L’onglet **Catégorie de coûts** a trois options pour **Configurer**, **Exécuter** et **Quantité** qui sont activées en fonction du paramètre des groupes de routage. Le raccourci **Horaires** a trois champs basés sur le groupe de routage.

La formule utilisée est basée sur l’activation ou non de l’option dans le groupe de routage. Le coût de la catégorie de coût sélectionnée est multiplié par la quantité saisie dans les délais pour calculer le coût total.

:::image type="complex" source="media/RouteGroupRelationship.png" alt-text="Relation entre les groupes de gammes et le coût total calculé.":::
Relation entre les groupes de gammes et le coût total calculé. Chaque ligne de routage possède un groupe de gammes. Le groupe de routage contrôle les paramètres de temps de configuration, de temps d’exécution et de quantité. L’onglet Catégorie de coûts a trois options pour Configurer, Exécuter et Quantité qui sont activées en fonction du paramètre des groupes de routage. Le raccourci Horaires a trois champs qui sont activés et facturés en fonction du groupe de gammes. La formule utilisée est basée sur l’activation ou non de l’option dans le groupe de routage. Le coût de la catégorie de coût sélectionnée est multiplié par la quantité saisie dans les délais pour calculer le coût total.
:::image-end:::

## <a name="sample-posting-profile-configuration"></a>Exemple de configuration de profil de publication

Le tableau suivant montre des exemples de types de comptabilisation par défaut avec des exemples de comptes principaux et des descriptions. 

 - La colonne **Débit/Crédit** indique si la transaction est généralement débitée ou créditée ou, dans certains cas, peut être enregistrée. 
 - La colonne **Compte de compensation** indique si le type de validation est un compte de compensation. Le montant enregistré sur ce compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée. 
 - La colonne **P/F** indique **P** pour l’affichage physique et **F** pour la comptabilisation financière. 
 - La colonne indique **Suivre** si le compte principal d’un type de validation spécifique est généralement le même qu’un autre type de validation. La valeur dans la colonne indique le type de validation généralement suivi.

> [!NOTE]
> Les comptes principaux et noms de comptes principaux ne sont que des suggestions. Nous vous recommandons de travailler avec votre comptable pour déterminer la meilleure configuration pour les besoins de votre entreprise.


| Type de validation  | Exemple de compte principal | Exemple de nom de compte principal| Type de compte | Débit/Crédit ? | Compte de compensation | Physique ou Financier ? | Suivre | Description |
|---------------|----------------------|--------------------------|--------------|----------------|------------------|-----------------------|--------|------------|
| Coût estimé des matières utilisées      | 140100               | Inventaire des matériaux        | Actif        | Crédit         | Y                | P                     | Coût des matières utilisées                | Ce compte est utilisé lorsque vous validez un journal des prélèvements pour un ordre de fabrication. La compensation de ce compte est le coût estimé des matériaux, travaux en cours. Le montant enregistré sur ce compte est automatiquement annulé lorsque l’ordre de production est terminé. Ce compte représente le compte de stock dans le bilan.       |
| Coût estimé des matières utilisées, travaux en cours | 150150               | Travaux de production en cours – Matériaux | Actif        | Débit          | Y                | P                     | Coût de fabrication estimé, travaux en cours          | Ce compte est utilisé lorsque vous validez un journal des prélèvements pour un ordre de fabrication. La compensation de ce compte est le coût estimé des matériaux consommés. Le montant enregistré sur ce compte est automatiquement annulé lorsqu’un ordre de production est terminé. Ce compte représente les travaux en cours sur votre bilan.                  |
| Coût de fabrication estimé               | 140200               | Stock des marchandises terminées   | Actif        | Débit          | Y                | P                     | Coût de fabrication                         | Ce compte est utilisé lorsque vous validez un état en tant que journal terminé pour un ordre de fabrication. La compensation de ce compte est le coût estimé des matériaux, travaux en cours. Le montant enregistré sur ce compte est automatiquement annulé lorsque l’ordre de production est terminé. Ce compte représente le compte de stock dans le bilan. |
| Coût de fabrication estimé, travaux en cours          | 150150               | Travaux de production en cours – Matériaux | Actif        | Crédit         | Y                | P                     | Coût de fabrication, travaux en cours                    | Ce compte est utilisé lorsque vous validez un état en tant que journal terminé pour un ordre de fabrication. La compensation de ce compte est le coût estimé des matériaux. Le montant enregistré sur ce compte est automatiquement annulé lorsqu’un ordre de production est terminé. Ce compte représente les travaux en cours sur votre bilan.                     |
| Coût des matières utilisées                | 140100               | Inventaire des matériaux        | Actif        | Crédit         | N                 | V                     | Coût estimé des matières utilisées      | Ce compte est utilisé pour reconnaître les matières qui sont consommées dans l’ordre de fabrication lors du processus de fin. La compensation de ce compte est le coût des matériaux consommés, travaux en cours.                                                                                                    |
| Coût des matières utilisées, travaux en cours           | 150150               | Travaux de production en cours – Matériaux | Actif        | Débit          | N                 | V                     | Coût estimé des matières utilisées, travaux en cours | Ce compte est utilisé pour reconnaître les matériaux pour les travaux en cours qui sont consommés dans l’ordre de fabrication lors du processus de fin. La compensation de ce compte est le coût des matériaux consommés.                                                |
| Coût de fabrication                         | 140200               | Stock des marchandises terminées   | Actif        | Débit          | N                 | V                     | Coût de fabrication estimé               | Ce compte est utilisé pour comptabiliser le coût du produit fini qui est produit par un ordre de fabrication lorsque vous terminez l’ordre de fabrication. La compensation de ce compte est le coût manufacturé, compte des travaux en cours.                                                                  |
| Coût de fabrication, travaux en cours                    | 150150               | Travaux de production en cours – Matériaux | Actif        | Crédit         | N                 | V                     | Coût de fabrication estimé, travaux en cours          | Ce compte est utilisé pour comptabiliser le coût du produit fini pour les travaux en cours, qui est produit par un ordre de fabrication lorsque vous terminez l’ordre de fabrication. La compensation de ce compte est le coût manufacturé.                                     |

> [!NOTE]
> **Réception des travaux en cours du service au plus juste** et **Compte de compensation pour les travaux en cours du service au plus juste** sont utilisés avec le calcul des coûts à rebours pour la fabrication au plus juste. - Pour plus d’informations, consultez [Calcul des coûts de post-consommation](/supply-chain/cost-management/backflush-costing.md).

