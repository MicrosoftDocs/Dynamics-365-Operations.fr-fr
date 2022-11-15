---
title: Marges de sécurité
description: Cet article décrit le fonctionnement des marges de sécurité pendant la planification générale.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-9-14
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 87b38276a2723374969a67c5413dde15537d04ec
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740439"
---
# <a name="safety-margins"></a>Marges de sécurité

[!include [banner](../../includes/banner.md)]

Cet article décrit le fonctionnement des marges de sécurité pendant la planification générale.

## <a name="safety-margins-overview"></a>Aperçu des marges de sécurité

Le but des marges de sécurité est de permettre une configuration qui fournit un certain temps de tampon au-delà du délai normal. Par exemple, lorsque le matériel doit être déballé ou inspecté après son arrivée chez le fournisseur, vous ne pouvez pas simplement ajouter du temps supplémentaire au délai d’achat, car cette approche donnera un délai supplémentaire au fournisseur. Dans cet exemple, la marge de réception peut être utilisée pour garantir que le fournisseur livre plus tôt. Cette approche fournit un temps tampon afin que les marchandises puissent être manipulées en interne.

Il existe trois types de marges de sécurité :

- **Marge de renouvellement** – Le temps tampon pour passer l’ordre d’approvisionnement
- **Marge de réception** – Le temps tampon pour gérer l’approvisionnement entrant
- **Marge de sortie** – Le temps tampon pour le traitement des expéditions

L’illustration suivante montre comment ces marges de sécurité s’appliquent au fil du temps.

![Marges de sécurité.](media/safety-margins-1.png)

Toutes les marges sont définies en jours. La valeur par défaut, *0* (zéro), indique qu’aucune marge n’est appliquée. Si vous définissez plusieurs marges, elles s’ajoutent toutes au temps total de la *date d’ordre* d’approvisionnement à la *date de demande*. Par exemple, une configuration n’a pas de délai et les trois types de marge sont définis sur un jour. Dans ce cas, il y aura trois jours entre la date de l’ordre d’approvisionnement et la date de demande, donc si la date de l’ordre est le 1er juillet, la date de la demande sera le 4 juillet.

### <a name="receipt-margin"></a>Marge de réception

La marge de réception est probablement la plus utilisée des trois marges de sécurité. Elle est appliquée à la *date de livraison* et en aval de la *date de demande*. En d’autres termes, les produits doivent être reçus le nombre spécifié de jours de marge de réception avant d’être demandés.

L’illustration suivante met en évidence la marge de réception.

![Marge de réception.](media/safety-margins-2.png)

La marge de réception est généralement utilisée comme tampon pour garantir le temps d’enregistrement de l’entrepôt ou d’autres processus chronophages qui ne sont pas capturés dans le cadre du délai général dans le système. Pour les achats, un avantage est que la *date de livraison* de la commande fournisseur est avancée en conséquence. Si vous augmentez le délai au lieu d’utiliser une marge de sécurité, le fournisseur sera toujours invité à livrer à la dernière minute.

Notez que la marge de réception ne change pas la *date de demande* de l’approvisionnement. Par conséquent, la marge de réception n’est pas directement visible lorsque les dates de demande pour la demande et l’offre sont comparées (par exemple, sur la page **Besoins nets**). Par exemple, si la marge de réception est définie sur quatre jours et si une ligne de commande fournisseur est planifiée pour réception le 15 du mois, la planification calcule le 19 du mois comme date de réception ajustée.

Notez qu’une marge de réception n’est pas appliquée lorsque le stock disponible est utilisé comme approvisionnement. Tout le stock disponible est supposé être disponible immédiatement, indépendamment du moment où il a été effectivement reçu.

### <a name="reorder-margin"></a>Marge de renouvellement

L’illustration suivante met en évidence la marge de renouvellement.

![Marge de renouvellement.](media/safety-margins-3.png)

La marge de renouvellement ajoutée avant le délai de livraison de l’article pour tous les ordres prévisionnels pendant la planification. Par conséquent, cela garantit un délai supplémentaire pour qu’un ordre d’approvisionnement soit passé. Cette marge est généralement utilisée comme tampon pour garantir le temps nécessaire aux processus d’approbation ou à d’autres processus internes requis lors de la création d’ordres d’approvisionnement. La marge de renouvellement est placée entre la *date de l’ordre* d’approvisionnement et la *date de début*.

### <a name="issue-margin"></a>Marge de sortie

L’illustration suivante met en évidence la marge de sortie.

![Marge de sortie.](media/safety-margins-4.png)

La marge de sortie est déduite de la date de demande lors de la planification. Elle permet de vous assurer que vous avez le temps de réagir et d’expédier les ordres de demande entrantes. Cette marge est généralement utilisée comme tampon pour garantir le temps d’expédition et les processus d’entrepôt sortants associés.

Notez que lorsqu’une marge de sortie est appliquée, les dates des besoins liés à l’offre et à la demande ne correspondent pas. Au lieu de cela, ils diffèrent par la marge de sortie, car la marge de sortie est ajoutée entre la *date de demande* d’approvisionnement et la *date de demande*.

## <a name="set-up-safety-margins"></a>Configurer des marges de sécurité

### <a name="turn-safety-margins-on-or-off"></a>Activer ou désactiver les marges de sécurité

Pour pouvoir utiliser cette fonctionnalité, il doit être activé pour votre système. Depuis la version 10.0.29 de Supply Chain Management, la fonctionnalité est obligatoire et ne peut pas être désactivée. Si vous exécutez une version antérieure à 10.0.29, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Marge de l'optimisation de la planification* dans l’espace de travail [Gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="define-safety-margins"></a>Définir des marges de sécurité

Les marges de sécurité ont une configuration flexible. Elles peuvent être définies sur le *groupe de couverture* et le *plan*. Il est important que vous compreniez que les marges s’ajoutent les unes sur les autres. Par exemple, une marge de réception de deux jours sur le groupe de couverture et de trois jours sur le plan produira une marge de réception effective de cinq jours.

La possibilité de définir la marge sur le plan peut être utile lorsque vous souhaitez simuler des délais plus longs ou une incertitude pour un plan spécifique, mais sans affecter la planification quotidienne.

#### <a name="coverage-group-safety-margins"></a>Marges de sécurité du groupe de couverture

Pour appliquer une marge de sécurité à un groupe de couverture, procédez comme suit.

1. Accédez à **Planification \> Paramétrage \> Groupes de couverture**.
1. Dans le volet de liste, sélectionnez le groupe de couverture souhaité.
1. Sur le raccourci **Autre**, dans la section **Marges de sécurité en jours**, utilisez les champs suivants pour définir les marges de sécurité requises (en jours) :

    - Marge de réception ajoutée à la date de besoin
    - Marge de sortie déduite de la date de besoin
    - Marge de renouvellement ajouté au délai de l’article

#### <a name="master-plan-safety-margins"></a>Marges de sécurité du plan

Pour appliquer une marge de sécurité à un plan, procédez comme suit.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Dans le volet de liste, sélectionnez le plan souhaité.
1. Sur le raccourci **Marges de sécurité en jours**, utilisez les champs suivants pour définir les marges de sécurité requises (en jours) :

    - Marge de réception ajoutée à la date de besoin
    - Marge de sortie déduite de la date de besoin
    - Marge de renouvellement ajouté au délai de l’article

### <a name="define-whether-calculations-are-based-on-calendar-days-or-work-days"></a>Définir si les calculs sont basés sur des jours calendaires ou des jours ouvrés

Vous pouvez définir toutes les marges de sécurité de sorte qu’elles soient calculées en fonction des jours calendaires ou des jours ouvrés.

1. Accédez à **Planification \> Paramétrage \> Paramètres de planification**.
1. Sur l’onglet **Général**, dans la section **Marges de sécurité en jours**, définissez l’option **Jours ouvrables** sur *Oui* pour calculer les marges en fonction des jours ouvrables. Définissez l’option sur *Non* pour calculer les marges en fonction des jours calendaires.

Par exemple, un calendrier est ouvert du lundi au vendredi et fermé du samedi au dimanche. S’il y a une marge de réception d’un jour, une date d’exigence un lundi produit une date de livraison le vendredi précédent, car samedi et dimanche ne sont pas des jours ouvrables.

Le calendrier utilisé pour déterminer les jours ouvrables dépend de la configuration et du type d’approvisionnement. Il peut être contrôlé par les calendriers du groupe de couverture, de l’entrepôt et du fournisseur.

> [!NOTE]
> Si *entrepôt* ne fait pas partie de la dimension de couverture (en d’autres termes, la planification est basée uniquement sur *site*), le calendrier de l’entrepôt n’est pas utilisé.

Le système peut gérer une configuration dans laquelle un ou plusieurs calendriers sont définis. Les sous-sections suivantes décrivent les combinaisons possibles qui peuvent être utilisées pour contrôler le résultat.

#### <a name="calendar-that-is-used-for-the-duration"></a>Calendrier utilisé pour la durée

Les calendriers définis contrôlent le délai total réel en jours calendaires, de la date de l’ordre d’approvisionnement à la date de la demande. La hiérarchisation de calendrier suivante est utilisée :

- **Délai d’achat** – Seul le calendrier du groupe de couverture est pris en compte.
- **Marge de réception** – Le calendrier du groupe de couverture est utilisé, s’il est défini. Sinon, le calendrier de l’entrepôt est utilisé.
- **Marge de sortie** – Le calendrier du groupe de couverture est utilisé, s’il est défini. Sinon, le calendrier de l’entrepôt est utilisé.
- **Marge de commande** – Seul le calendrier du groupe de couverture est pris en compte.

#### <a name="calendar-that-is-used-for-the-final-date"></a>Calendrier utilisé pour la date finale

Les règles suivantes sont appliquées pour déterminer si le moteur de planification peut utiliser une date donnée pour un type de date donné :

- **Date de réception d’achat** – Le calendrier du fournisseur est utilisé, s’il est défini. Sinon, le calendrier du groupe de couverture est utilisé, s’il est défini. Si aucun de ces calendriers n’est défini, le calendrier de l’entrepôt est utilisé.
- **Date de réception de transfert** – Le calendrier du groupe de couverture est utilisé, s’il est défini. Sinon, le calendrier de l’entrepôt est utilisé.
- **Date de réception de production** – Le calendrier du groupe de couverture est utilisé, s’il est défini. Sinon, le calendrier de l’entrepôt est utilisé.
- **Jour ouvert de sortie de la demande** – Le calendrier de l’entrepôt est utilisé, s’il est défini. Sinon, le calendrier du groupe de couverture est utilisé.
- **Jour ouvert de commande** – Une combinaison (intersection) du calendrier du groupe de couverture et du calendrier du fournisseur est utilisée. Les deux calendriers doivent être ouverts pour utiliser la date. Si un seul des calendriers est défini, ce calendrier est utilisé seul.

#### <a name="calendar-setup-overview-matrix"></a>Matrice de présentation de la configuration du calendrier

L’illustration suivante présente une matrice qui résume les calendriers qui s’appliquent lorsque les marges de sécurité sont calculées. (Sélectionnez l’image pour en ouvrir une version haute résolution.) Les abréviations et couleurs suivantes sont utilisées pour indiquer où chaque type de calendrier est spécifié :

- **Groupe de couverture (GC) :** Vert
- **Entrepôt (WH) :** Jaune
- **Fournisseur (F) :** Bleu

[![Matrice de présentation de la configuration du calendrier.](media/safety-margins-calendar-matrix.png)](media/safety-margins-calendar-matrix-high.png)

## <a name="calculating-delays"></a>Calcul des retards

Les trois types de marges de sécurité sont inclus lorsque le système détermine si une commande est retardée.

Par exemple, un article a un délai d’un jour et une marge de réception de trois jours. Une commande client pour cet article est définie comme requise aujourd’hui. Dans ce cas, le retard est calculé comme suit *délai* + *marge de réception* = quatre jours. Par conséquent, si aujourd’hui est le 14 août, les quatre jours de retard produisent une livraison le 18 août. L’illustration suivante présente cet exemple.

![Exemple de calcul de retard.](media/safety-margins-delays.png)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]