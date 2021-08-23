---
title: État d’analyse budgétaire
description: Cette rubrique fournit des informations sur l’état d’analyse budgétaire, utilisé pour générer un état récapitulatif qui effectue une comparaison entre les montants budgétés et les dépenses réelles et l’activité de produit pendant une période spécifiée.
author: velofog
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: public sector
ms.author: roschlom
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: e42accc64cb6243d2e3f206a75c9f71eeb5262b534a9b6baa19a104af2072e05
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738406"
---
# <a name="budget-analysis-report"></a>État d’analyse budgétaire

[!include[banner](../includes/banner.md)]

Vous pouvez utiliser l’état **Analyse budgétaire** pour générer un état récapitulatif qui effectue une comparaison entre les montants budgétés et les dépenses réelles et l’activité de produit pendant une période spécifiée. Pour chaque compte, l’état répertorie les montants budgétés, les dépenses ou le produit réel, les montants d’engagement des commandes fournisseur, et les montants d’engagement préalable des demandes d’achat. En outre, l’état répertorie le montant du budget restant pour chaque compte et fonds.

L’état peut être trié selon les fonds puis le numéro de compte. Dans chaque fonds, l’état affiche les sous-totaux, regroupés selon l’ensemble de dimensions financières sélectionné. Lorsque vous utilisez le volet de navigation pour consulter l’activité, le regroupement détermine comment l’activité est affichée ici.

L’état inclut tous les comptes avec une activité dans la plage de dates pour les types de comptes de produit ou de dépenses. Aucun compte marqué comme type Compte de résultat n’est inclus dans l’état. L’état n’inclut également pas les totaux nets. (Les totaux nets sont calculés comme le produit moins les dépenses.)

Pour afficher des informations supplémentaires sur un compte, sélectionnez le nom ou le numéro du compte pour ouvrir l’écran **Recherche d’analyse budgétaire**. Vous pouvez afficher toutes les transactions contribuant au montant dans l’état. Pour afficher les transactions, vous pouvez afficher des liens d’exploration d’états financiers sur l’état. Sélectionnez un lien pour ouvrir l’exploration d’un état ayant des détails de transaction d’un budget révisé, de dépenses ou de produit réel, d’engagements, ou d’engagements préalables. L’exploration d’états peut éventuellement inclure des transactions en attente.

## <a name="filter-the-data-on-this-report"></a>Filtrage des données dans cet état

Lorsque vous générez l’état, les paramètres par défaut suivants sont affichés. Ces paramètres permettent de filtrer les données qui apparaîtront sur l’état. Pour plus d’informations, consultez la section « Utilisation des états » de cette rubrique.

| Champ | Description |
|---|---|
| Ensemble de dimensions financières | Sélectionnez le groupe de dimensions des comptes généraux qui doit être répertorié sur l’état.<p>Un ensemble de dimensions financières est un groupe nommé de comptes ou de dimensions contenant des valeurs de compte pour le compte ou des valeurs de dimension pour une seule dimension. Par exemple, un ensemble peut inclure des comptes principaux, des départements et des centres de coût. Sinon, il peut contenir des combinaisons, telles qu’un centre de coût et compte principal, ou un département et un centre de coût. Pour plus d’informations, voir [Créer un ensemble de dimensions financières](/dynamicsax-2012/appuser-itpro/create-a-financial-dimension-set).</p> |
| Modèle de budget | Sélectionner le modèle de budget avec lequel déclarer les montants budgétaires. |
| Période de cycle budgétaire | Spécifiez le cycle budgétaire pour lequel créer l’état. Pour plus d’informations, voir [Définir des cycles budgétaires](/dynamicsax-2012/appuser-itpro/define-budget-cycles). |
| Type de compte | Spécifiez si le budget et les montants réels doivent être déclarés pour les comptes de dépenses ou les comptes de produit. Par défaut, les comptes de dépenses sont déclarés. Si vous modifiez le type de compte après avoir sélectionné les comptes ou entré une requête de sélection, vous devez sélectionner un nouveau groupe de comptes dans les champs **Comptes principaux** et sélectionner **Sélectionner** pour entrer une nouvelle requête. |
| Regrouper les comptes principaux par catégorie | Activer cette case à cocher pour regrouper les comptes par catégorie de compte principal après qu’ils aient été regroupés par dimensions financières dans un compte général. Le niveau le plus bas du regroupement est affiché, indépendamment de la dimension financière sélectionnée. Les catégories de compte principal sont triées selon leur codes alphanumériques. Tous les comptes qui ne sont pas affectés à une catégorie de compte principal sont regroupés à la fin. Vous paramétrez des catégories de compte principal à l’aide de la page **Catégories de compte principal**. |
| Supprimer les comptes avec des zéros | Activez cette case à cocher pour afficher uniquement les comptes avec des montants réels différents de zéro et des montants budgétaires. |
| Afficher les liens de l’état d’analyse | Activez cette case à cocher pour afficher les liens qui peuvent être utilisés pour ouvrir l’exploration d’un état ayant des détails de transaction d’un budget révisé, de dépenses ou de produit réel, d’engagements, ou d’engagements préalables. |
| Afficher les transactions en attente dans les états d’analyse | Si la case à cocher **Afficher les liens de rapport d’exploration** est activée, vous pouvez activer cette case à cocher pour inclure les détails des transactions en attente dans un état d’exploration pour le budget révisé, les dépenses ou le produit réel, les engagements ou les engagements préalables.<blockquote>[!NOTE] Si vous activez cette case à cocher, les soldes affichés peuvent différer des montants qui figurent sur l’état **Analyse budgétaire**. |
| Dates à inclure | Spécifiez si les montants doivent être déclarés pour un cycle budgétaire ou une plage de dates complets. Lorsque vous exécutez cet état pour une année précédente, les colonnes de cumul sont supprimées.<ul><li>Si vous sélectionnez **Cycle budgétaire**, sélectionnez le nom d’un cycle budgétaire. Cette option utilise les dates définies pour le cycle budgétaire sélectionné sur la page **Périodes de cycle budgétaire**. Pour plus d’informations, voir [Créer un ensemble de dimensions financières](/dynamicsax-2012/appuser-itpro/create-a-financial-dimension-set).</li><li>Si vous sélectionnez **Plage de dates**, sélectionnez les dates de début et de fin du budget et des écritures réelles qui doivent être inclus dans l’état. Vous pouvez entrer différentes plages pour les montants budgétaires et les montants réels. Par exemple, si vos budgets d’organisation sont de deux ans, vous pouvez déclarer des montants budgétaires pour une plage de dates de deux ans, mais incluez uniquement l’année en cours des montants de dépenses ou de produit réels.<blockquote>[!NOTE] La plage de dates que vous spécifiez doit se trouver dans un ou plusieurs exercices inclus dans le calendrier fiscal sélectionné lorsque la période de cycle budgétaire a été paramétrée. Par exemple, un calendrier fiscal pour un cycle budgétaire inclut les exercices avec des dates du 1er janvier 2010 au 31 décembre 2014. Dans ce cas, la date de début ne peut pas être avant le 1er janvier 2010.</blockquote></li></ul> |
| Budget | Spécifiez la plage de dates des écritures budgétaires à inclure dans l’état. |
| Chiffres réels | Spécifiez la plage de dates des écritures réelles à inclure dans l’état. |
| Grouper par | Sélectionnez l’ensemble de dimensions utilisé pour afficher les sous-totaux par groupe. Les comptes généraux ayant la même valeur pour les dimensions financières que vous spécifiez dans l’ensemble de dimensions sont regroupés sur l’état. Vous pouvez créer des ensembles de dimensions selon lesquels regrouper les comptes. Pour plus d’informations, voir [Créer un ensemble de dimensions financières](/dynamicsax-2012/appuser-itpro/create-a-financial-dimension-set). |
| Saut de page par | Sélectionnez un ensemble de dimensions financières incluant les dimensions où vous voulez insérer une nouvelle page d’état si la valeur de dimension change. Vous pouvez insérer un saut de page uniquement pour des dimensions dans l’ensemble de dimensions sélectionné dans le champ **Regrouper par**. Par exemple, si vous regroupez par Fonds-département, vous devez insérer la page pour Fonds et départements, ou uniquement pour Fonds. Vous pouvez créer des ensembles de dimensions selon lesquels regrouper les comptes. Pour plus d’informations, voir [Créer un ensemble de dimensions financières](/dynamicsax-2012/appuser-itpro/create-a-financial-dimension-set). |
| Comptes principaux | Entrez la plage de numéros du compte principal qui doivent être répertoriés dans l’état. Laissez les champs vides pour exécuter l’état pour tous les comptes. |

## <a name="review-the-report"></a>Vérifier l’état

L’état couvre les informations suivantes :

- Numéro de compte
- Intitulé du compte
- Budget révisé (= Budget d’origine + Ajustements budgétaires)
- Chiffres réels actuels (pour le produit ou les dépenses, selon le type de compte)
- Pourcentage de budget actuel (chiffres réels/budget révisé)
- Chiffres réels de cumul (seules les transactions validées pour l’exercice en cours sont prises en compte.)
- Engagements (seules les transactions validées pour l’exercice en cours sont prises en compte.)
- Engagements préalables (seules les transactions validées pour l’exercice en cours sont prises en compte.)
- Budget restant (= Budget d’origine + Ajustements budgétaires – Chiffres réels – Engagements – Engagements préalables) (seules les transactions validées sont prises en compte dans ce calcul.)
- Pourcentage de cumul annuel du solde de budget (= Budget restant ÷ Budget révisé) (seules les transactions validées pour l’exercice en cours sont prises en compte dans ce calcul.)

L’état inclut également les totaux de chaque fonds, département et catégorie de compte principal, s’ils sont inclus.

L’état d’exploration couvre les informations suivantes :

- Nom de la catégorie pour l’exploration : budget révisé, dépense ou produit réel, engagements de cumul annuel, ou engagements préalables de cumul annuel
- Nom de l’entité juridique
- Numéro de compte général
- Date de la transaction
- N° de justificatif
- Informations sur le document pour la transaction
- Description de la date de transaction du justificatif
- Détails du justificatif
- Détails de débit et de crédit pour le document des chiffres réels
- Montants positifs et négatifs du budget, de l’engagement, et du N° document d’engagement préalable
- Solde d’ouverture, de clôture et en cours pour le compte général


[!INCLUDE[footer-include](../../includes/footer-banner.md)]