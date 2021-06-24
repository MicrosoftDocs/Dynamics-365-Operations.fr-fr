---
title: Tableau de bord de gestion de l’utilisation
description: Cette rubrique explique comment utiliser le tableau de bord de gestion de l’utilisation pour surveiller l’utilisation du service Facturation électronique et préserver la conformité.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130504"
---
# <a name="usage-management-dashboard"></a>Tableau de bord de gestion de l’utilisation

[!include [banner](../includes/banner.md)]

Le tableau de bord **Gestion de l’utilisation** vous aide à surveiller l’utilisation du service Facturation électronique et aide donc votre organisation à rester conforme en termes d’utilisation mensuelle. La conformité est déterminée en calculant le volume d’envois et en le comparant avec le volume d’envois acheté pour identifier les écarts entre le volume acquis et le volume utilisé.

Le tableau de bord comprend les indicateurs suivants :

- Un indicateur de coût que vous pouvez utiliser pour surveiller la consommation à des fins de conformité des licences :

    - Utilisation mensuelle (exportation)

- Trois indicateurs opérationnels permettant de suivre l’utilisation du service Facturation Electronique à des fins de gestion :

    - Utilisation par fonctionnalité
    - Utilisation par environnement
    - Utilisation mensuelle (importation)

## <a name="measurement-scope"></a>Portée de la mesure

- Unité de mesure : 

    Le tableau de bord **Gestion de l’utilisation** comptabilise l’envoi de documents commerciaux et de factures électroniques importées.

- Organisation : 

    Le comptage est résumé par ID de locataire de votre organisation, quel que soit le nombre d’instances de Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management, ou le nombre d’entités juridiques où le service Facturation électronique est activé.


## <a name="indicator-usage-per-month-export"></a>Indicateur : Utilisation par mois (exportation)

Cet indicateur fournit des détails sur les factures électroniques que votre organisation émet au cours d’une période définie.

### <a name="scope"></a>Étendue
- Le nombre de documents commerciaux soumis par Finance et Supply Chain Management au service Facturation électronique, quel que soit le nombre de lignes que contiennent ces documents commerciaux.
- Le nombre de documents commerciaux envoyés qui sont traités avec succès par le service Facturation électronique. Un document est considéré comme traité avec succès lorsque le flux d’actions défini dans la configuration de la fonctionnalité est terminé.

> [!NOTE]
> Lorsqu’une facture électronique est soumise à un service web externe, le comptage est indépendant des résultats du traitement du service web (accepté, rejeté ou erreur de validation de schéma). Si le service web a reçu et répondu à la demande du service Facturation électronique, la soumission est considérée comme un comptage valide.

- **Exception :** les documents commerciaux ne sont pas pris en compte s’ils sont resoumis de Finance et Supply Chain Management au service Facturation électronique, comme dans les scénarios où une nouvelle soumission du même document commercial est requise pour modifier le statut de la facture électronique. Par exemple, l’émission d’une facture électronique brésilienne (document fiscal) est comptée comme valide, mais la demande d’annulation pour celle-ci n’est pas comptée.


### <a name="calculation"></a>Calcul

Le calcul du solde est calculé comme suit :

Solde = Gratuit + Acheté - Utilisé

Où :

- Gratuit :
  
    Un volume gratuit de documents commerciaux que le client peut soumettre par mois. Il comprend un ensemble de 100 documents commerciaux pouvant être soumis au service Facturation électronique. Le volume gratuit n’est pas cumulatif et tout solde restant n’est pas reporté à la période suivante.
  
- Acheté :
  
    Un ensemble de 1 000 documents commerciaux pouvant être soumis au service Facturation électronique. Ce forfait doit être acheté pour votre organisation sur une base mensuelle. Le volume acheté n’est pas cumulatif et tout solde restant n’est pas reporté à la période suivante.
  
- Utilisé : 

    Le nombre des soumissions de documents commerciaux au service Facturation Electronique selon des critères définis.
   
> [!IMPORTANT]
> Si votre organisation prévoit de dépasser le volume mensuel de 100 envois gratuits, achetez le volume maximal pour vous assurer de respecter la politique de licence de Microsoft pour le service Facturation électronique.
>
> Actuellement, le volume acheté doit être saisi manuellement, selon la date d’acquisition, sous forme de plusieurs ensembles de 1 000 envois.

## <a name="indicator-usage-by-feature"></a>Indicateur : utilisation par fonctionnalité

Cet indicateur montre l’utilisation des fonctionnalités de facturation électronique pour l’émission de factures électroniques pendant une période définie.

- Calcul :
  
    Utilisé = Le nombre de fois que chaque fonction de facturation électronique a été utilisée lors de la soumission de documents commerciaux au service Facturation électronique.

## <a name="indicator-usage-by-environment"></a>Indicateur : utilisation par environnement

Cet indicateur montre l’utilisation des environnements de service de facturation électronique pendant une période définie.

- Calcul :
    
    Utilisé = Le nombre de fois que chaque environnement de service de facturation électronique a été utilisé lors de la soumission de documents commerciaux au service Facturation électronique.

## <a name="indicator-usage-per-month-import"></a>Indicateur : Utilisation par mois (importation)

Cet indicateur présente le volume d’importation de factures électroniques par le service Facturation électronique dans Finance et Supply Chain Management pendant une période définie.

- Étendue :

    Factures électroniques importées dans Finance et Supply Chain Management, quel que soit le nombre de lignes que contiennent ces factures électroniques.

- Calcul :

    Reçues = Le nombre de factures électroniques importées dans Finance et Supply Chain Management.

## <a name="functions"></a>Fonctions
### <a name="purchase"></a>Achats

Sur l’onglet **Utilisation par mois (exportation)**, sélectionnez **Acheter** pour enregistrer manuellement le nombre de soumissions achetées.

Pour une date donnée, sélectionnez **Nouveau** et entrez le nombre de **paquets** achetés à cette date.

La **Quantité** est calculée comme suit :

Quantité = Paquets * 1 000

La **Quantité** calculée est répercutée dans l’élément **Acheté** de l’indicateur **Utilisation par mois (exportation)**.

### <a name="update"></a>Mise à jour

Dans le volet Actions, sélectionnez **Mettre à jour** pour actualiser le calcul et mettre à jour les données affichées sur la page et dans le graphique.

### <a name="reset-history-data"></a>Réinitialiser les données de l’historique

Dans le volet Actions, sélectionnez **Réinitialiser les données de l’historique** pour actualiser la base de données à partir de laquelle les indicateurs sont calculés.




> [!NOTE]
> Le tableau de bord **Gestion de l’utilisation** n’affiche pas les montants en devise. Au lieu de cela, il affiche uniquement le volume des envois comptabilisés et des documents importés.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
