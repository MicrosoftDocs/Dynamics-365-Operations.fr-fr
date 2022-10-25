---
title: Profil et niveaux de tampon
description: Cet article fournit des informations sur les profils et les niveaux de tampon, qui déterminent les niveaux de stock minimum et maximum qui doivent être conservés pour chaque point de découplage.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: d254b949d31d0b15141646503c64760062b77fc7
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689143"
---
# <a name="buffer-profile-and-levels"></a>Profil et niveaux de tampon

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Après avoir identifié vos points de découplage (éléments clés que vous conserverez stratégiquement en stock), vous devez décider de la quantité de stock (tampon) que vous conserverez à chacun d’eux. Cette tâche est la deuxième étape de la planification des demandes de matériaux pilotées par la demande (DDMRP).

## <a name="buffer-levels-and-zones"></a>Niveaux et zones de tampon

Dans DDMRP, chaque tampon de stock est défini à l’aide de trois valeurs : la quantité minimale, la quantité maximale et le point de réapprovisionnement. Ces valeurs établissent trois zones de différence, qui sont identifiées par les codes de couleur suivants :

- **Zone rouge** : la zone sous la quantité minimale. La quantité minimale est également appelée « Top du rouge » et votre stratégie de planification doit être conçue pour garantir que les niveaux de stock sont toujours au-dessus de ce point.
- **Zone jaune** : la zone entre la quantité minimale et le point de commande. Le point de réapprovisionnement est également appelé « Top du jaune ». Lorsque ce point est atteint, le système doit réorganiser.
- **Zone verte** : la zone entre le point de réapprovisionnement et la quantité maximale. La quantité maximale est également appelée « Top du vert ». Ce point est le niveau maximal auquel le stock sera réapprovisionné.

L’illustration suivante montre les trois zones colorées et leur relation avec la quantité minimale, la quantité maximale et le point de réapprovisionnement.

![Niveaux et zones de tampon DDMRP.](media/ddmrp-buffer-levels.png "Niveaux et zones de tampon DDMRP")

## <a name="calculating-the-buffer-zones"></a>Calcul des zones tampons

Cette section explique comment la hauteur de chaque zone tampon est calculée.

La zone jaune est généralement calculée en premier. Cette zone représente la quantité que vous consommez depuis le moment où vous commandez jusqu’à l’arrivée de la commande. En d’autres termes, il s’agit de la consommation attendue pendant le délai de réapprovisionnement. Elle est calculée à l’aide de l’équation suivante :

- **Zone jaune** = *Consommation moyenne journalière (ADU)* ×*Délai découplé*

Le *délai découplé* représente le temps nécessaire pour produire ou recevoir un article si les points de découplage sont toujours en stock. Il est généralement beaucoup plus court que le *délai cumulé* qui est traditionnellement utilisé dans la planification générale. Des paramètres de tampon corrects sont essentiels pour garantir que les points de découplage sont toujours effectivement en stock, mais pas en surstock.

La zone rouge est calculée à l’aide des équations suivantes :

- **Base rouge** = *ADU* × *Délai découplé* × *Facteur de délai*
- **Sécurité rouge** = *Base rouge* × *Facteur de variabilité*
- **Zone rouge** = *Bases rouge* + *Sécurité rouge*

La zone verte est calculée comme le résultat maximum des trois équations suivantes :

- *Quantité de commande minimale*
- *ADU* × *Cycle de commande*
- *ADU* × *Délai découplé* × *Facteur de délai*

## <a name="calculating-average-daily-usage"></a>Calculer la consommation moyenne journalière

Le système utilise l’une des trois approches pour calculer la quantité que vous consommez par jour :

- **Consommation moyenne journalière (passée)**  : cette approche est basée sur la consommation réelle passée.
- **Consommation moyenne journalière (à venir)**  : cette approche est basée sur la consommation réelle à venir.
- **Consommation moyenne journalière (pondérée)**  : cette approche est basée sur une combinaison pondérée de consommations passées et à venir.

### <a name="average-daily-usage-past"></a>Consommation moyenne journalière (passée)

L’ADU passée est calculée comme une moyenne en additionnant les quantités utilisées chaque jour pendant un nombre spécifié de jours passés, puis en divisant le total par le nombre de jours. L’illustration suivante montre comment cette approche fonctionne lorsque le calcul considère trois jours dans le passé.

![Graphique consommation moyenne journalière (passée).](media/ddmrp-adu-past.png "Graphique consommation moyenne journalière (passée)")

Dans l’illustration précédente, si aujourd’hui est le matin du 11 juin, l’ADU des trois jours passés (8, 9 et 10 juin) est de 21.

- **ADU (passé)** = (29 + 11 + 23) ÷ 3 = 21

Les transactions suivantes sont prises en compte pour le calcul de la consommation quotidienne moyenne (passée) :

- Les transactions qui diminuent la quantité de l’article (dans la table `inventtrans` où la quantité est inférieure à zéro)
- Transactions avec un statut défini sur *Sur commande*, *Réservé commandé*, *Physique réservé*, *Prélevé*, *Déduit*, ou *Vendu*
- Transactions datées de la période rétroactive choisie (la consommation quotidienne moyenne de la période écoulée)
- Transactions autres que le travail en entrepôt, la quarantaine, les devis de vente ou les relevés (`WHSWork`,`WHSQuarantine`,`SalesQuotation`, ou `Statement`)
- Transactions autres que les journaux de transfert qui se trouvent dans la même dimension de couverture

### <a name="average-daily-usage-forward"></a>Consommation moyenne journalière (à venir)

Pour un nouveau produit, vous ne disposez peut-être d’aucune donnée de consommation passée. Par conséquent, vous pouvez plutôt utiliser l’ADU à venir (par exemple, en fonction de la demande prévue). L’illustration suivante montre comment cette approche fonctionne lorsque le calcul considère trois jours dans le futur (aujourd’hui inclus).

![Graphique consommation moyenne journalière (à venir).](media/ddmrp-adu-forward.png "Graphique consommation moyenne journalière (à venir)")

Dans l’illustration précédente, si aujourd’hui est le matin du 11 juin, l’ADU des trois jours suivants (11, 12 et 13 juin) est de 21,66.

- **ADU (à venir)** = (18 + 18 + 29) ÷ 3 = 21,66

Les transactions suivantes sont prises en compte pour le calcul de la consommation quotidienne moyenne (à venir) :

- Transactions prévisionnelles pour l’article où la prévision est sélectionnée sur le plan principal
- Transactions datées de la période à venir choisie (la consommation quotidienne moyenne de la période à venir)

### <a name="average-daily-usage-blended"></a>Consommation moyenne journalière (pondérée)

L’ADU pondérée combine la consommation moyenne journalière et la consommation moyenne à venir, comme indiqué dans l’illustration suivante.

![Graphique consommation moyenne journalière (pondérée).](media/ddmrp-adu-blended.png "Graphique consommation moyenne journalière (pondérée)")

Dans l’illustration précédente, si aujourd’hui est le matin du 11 juin, l’ADU pondérée des trois jours passés et trois prochains jours (du 8 au 13 juin) est de 21,33.

- **ADU pondérée** = (*ADU passé* + *ADU à venir*) ÷ 2<br>= (21 + 21,66) ÷ 2<br>= 21,33

## <a name="buffer-calculation-factors"></a>Facteurs de calcul de la marge

Pour chaque élément, vous pouvez définir deux facteurs pour ajuster la taille des zones rouges et vertes. De cette façon, vous pouvez compenser le délai d’approvisionnement prévu et la variabilité de la demande.

![Délais et facteurs de variabilité.](media/ddmrp-zone-factors.png "Délais et facteurs de variabilité")

Le premier facteur est le *facteur de délai*. La valeur est une valeur décimale de 0 à 1. Plus le délai est long, plus la valeur doit être faible. Le Demand Driven Institute recommande les fourchettes suivantes :

- **Délai long :** 0,20–0,40
- **Délai moyen :** 0,41–0,60
- **Délai court :** 0,61–1,00

Le second facteur est le *facteur de variabilité*. La valeur est une valeur décimale de 0 à 1. Plus la variabilité de la demande est élevée, plus la valeur doit être faible. Le Demand Driven Institute recommande les fourchettes suivantes :

- **Faible variabilité :** 0,20–0,40
- **Variabilité moyenne :** 0,41–0,60
- **Variabilité élevée :** 0,61–1,00

## <a name="buffer-calculation-examples"></a>Exemples de calcul de marge

Cet exemple poursuit l’exemple de production d’oreillers fourni dans [Positionnement du stock](ddmrp-inventory-positioning.md). Dans cet exemple, vous avez sélectionné des points de découplage qui ont réduit le délai de 21 jours à cinq jours, comme indiqué dans l’illustration suivante.

![Exemple de délai découplé.](media/ddmrp-bom-decoupled-lead-time-example.png "Exemple de délai découplé")

Pour cet exemple, supposons que l’ADU a été calculé comme 23 pièces et, comme indiqué dans l’illustration précédente, le délai découplé est de cinq jours. En utilisant ces valeurs, vous pouvez calculer la zone jaune en utilisant l’équation suivante :

- **Zone jaune** = *UAD* × *Délai découplé* = 115

![Exemple de calcul de zone jaune.](media/ddmrp-example-calc-yellow.png "Exemple de calcul de zone jaune")

Le calcul de la zone rouge ressemble au calcul de la zone jaune, mais il est gonflé pour tenir compte de la variabilité et du délai. Pour cet exemple, supposons que vous ayez observé un délai moyen (facteur = 0,50) et une forte variabilité de la demande (facteur = 0,8). En utilisant ces valeurs avec les composants de l’équation de la zone jaune, vous pouvez calculer la zone rouge à l’aide des équations suivantes :

- **Base rouge** = *ADU* × *Délai découplé* × *Facteur de délai* = 57,5
- **Sécurité rouge** = *Base rouge* × *Facteur de variabilité* = 46
- **Zone rouge** = *Bases rouge* + *Sécurité rouge* = 103,5

Le système arrondira la zone rouge à 104 pièces (ea), car les pièces sont comptées en nombre entier.

![Exemple de calcul de zone rouge.](media/ddmrp-example-calc-red.png "Exemple de calcul de zone rouge")

Le calcul de la zone verte inclut également les composants de l’équation de la zone jaune, mais il permet une taille de commande minimale, un cycle de commande et un facteur de délai. Pour cet exemple, supposons qu’il n’y a pas de cycle de commande (par conséquent, vous n’avez aucune contrainte de temps sur la fréquence de vos commandes) et que la quantité minimale de commande est de 10 pièces. La zone verte est calculée comme le résultat maximum des trois équations suivantes :

- *Quantité de commande minimale* = 10
- *ADU* × *Cycle de commande* = 0
- *ADU* × *Délai découplé* × *Facteur de délai* = 57,5

Le système arrondira la zone verte à 58 pièces (ea), car les pièces sont comptées en nombre entier.

![Exemple de calcul de zone verte.](media/ddmrp-example-calc-green.png "Exemple de calcul de zone verte")

L’illustration suivante résume ces résultats de calcul de zone en utilisant le graphique en entonnoir souvent utilisé dans DDMRP.

![Résumé des résultats des calculs de zone.](media/ddmrp-example-calc-summary.png "Résumé des résultats des calculs de zone")

## <a name="dynamic-adjustments"></a><a name="dynamic-adjustments"></a>Ajustements dynamiques

Les ajustements dynamiques vous permettent d’appliquer un *facteur d’ajustement de la demande* pendant les périodes de forte ou de faible demande. Ce facteur multiplie l’ADU dans tous les calculs pour la période sélectionnée. Les zones tampons sont alors modifiées à leur tour. Vous appliquerez généralement ce facteur après avoir généré vos valeurs de tampon initiales, afin de pouvoir les affiner au fil du temps et en réponse aux conditions changeantes. Cette tâche est la troisième étape de DDMRP.

Par exemple, il pourrait y avoir plus de demande pour un produit de type oreiller en août alors que les gens partent en vacances. Par conséquent, les ventes devraient être plus élevées. Dans ce cas, vous pouvez modifier la valeur **Facteur d’ajustement de la demande** pour le produit sur *1,5* pour toutes les semaines d’août.

De cette façon, vous pouvez calculer les valeurs de tampon au fil du temps, puis les ajuster en fonction de plus que les seules informations dont dispose le système. Dans une implémentation DDMRP complète, vous calculerez chaque jour de nouvelles valeurs de tampon via une tâche par lots et accepterez automatiquement les valeurs. Vous exécuterez ensuite la planification en tant que traitement par lots et examinerez les ordres planifiés chaque jour pour remplir les tampons.

## <a name="implement-buffers-in-supply-chain-management"></a>Mettre en œuvre les tampons dans Supply Chain Management

Cette section décrit comment implémenter votre stratégie de zone tampon dans Microsoft Dynamics 365 Supply Chain Management. Cela suppose que vous ayez déjà effectué les analyses et les calculs décrits dans la première moitié de cet article.

### <a name="set-up-buffers-for-a-decoupling-point-item"></a><a name="set-up-buffers"></a>Configurer des tampons pour un élément de point de découplage

Suivez ces étapes pour configurer des valeurs tampons pour un point de découplage.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez un poste validé configuré comme point de découplage. (Pour plus d’informations, voir [Positionnement du stock](ddmrp-inventory-positioning.md).)
1. Dans le volet Actions, sur l’onglet **Plan**, sélectionnez **Couverture de l’article**.
1. Sur la page **Couverture de l’article**, sélectionnez un enregistrement de couverture d’article qui crée un point de découplage. (Cet enregistrement affichera le nom d’un groupe de couverture configuré pour créer des points de découplage.)
1. Sélectionnez l’onglet **Général**.
1. Si vous souhaitez que le système recalcule les valeurs tampons chaque jour ou chaque semaine, en fonction de votre historique des ventes, de vos prévisions et des paramètres de groupe de couverture, procédez comme suit :

    1. Réglez l’option **Valeurs du buffer au fil du temps** sur *Oui*.
    1. Une boîte de message vous informe que vos paramètres manuels de tampon (**Minimum**, **Point de réapprovisionnement** et **Maximum**) seront réinitialisés si vous continuez. Sélectionnez **Oui** pour conserver le nouveau paramètre.

    Sinon, si vous préférez calculer ou entrer vos paramètres de tampon une seule fois, suivez ces étapes :

    1. Réglez l’option **Valeurs du buffer au fil du temps** sur *Non*.
    1. Définissez les champs **Minimum**, **Point de réapprovisionnement** et **Maximum** sur les valeurs tampon que vous avez calculées pour l’élément, comme décrit précédemment dans cet article.

1. Définissez les champs suivants pour terminer la configuration des calculs DDMRP pour l’article :

    - **Cycle de commande** : spécifiez le nombre de jours qui doivent s’écouler entre les bons de commande de l’article. Définissez la valeur sur *0* (zéro) s’il n’existe aucune restriction de commande. Ce champ affecte le tampon de quantité maximale, comme indiqué précédemment dans cet article.
    - **Consommation moyenne journalière** : vous pouvez éventuellement entrer une ADU estimée pour l’article. Ce champ est fourni uniquement à titre indicatif. Habituellement, la valeur est calculée automatiquement dans le cadre des calculs de tampon.
    - **Seuil du pic de commande** : spécifiez le nombre minimum de ventes quotidiennes de l’article qui sont considérées comme un pic de ventes (demande exceptionnellement élevée). Le système utilise ce champ pour augmenter la quantité de réapprovisionnement des ordres planifiés en période de forte demande. Pour plus d’informations, voir [Planification axée sur la demande](ddmrp-planning.md).

### <a name="calculate-or-enter-decoupled-lead-times"></a><a name="calc-lead-time"></a>Calculer ou saisir les délais découplés

Pour les éléments pour lesquels vous choisissez d’autoriser le système à [calculer automatiquement vos zones tampons](#set-up-buffers), suivez ces étapes pour calculer ou saisir des délais découplés pour un article de point de découplage.

1. Ouvrez la page **Couverture de l’article** de votre point de découplage. (Pour plus d’informations, voir [Configurer des tampons pour un élément de point de découplage](#set-up-buffers).)
1. Sélectionnez un enregistrement de couverture d’article qui crée un point de découplage.
1. Sélectionnez l’onglet **Valeurs tampons**.
1. Si aucune période n’est affichée dans la grille, dans le volet Actions, sur l’onglet **Valeurs tampons**, sélectionnez **Ajouter des périodes**. Le système remplit la grille avec des lignes pour chaque période quotidienne ou hebdomadaire, selon que le champ **Période Min., Max. et Point de réapprovisionnement** pour le [groupe de couverture](ddmrp-inventory-positioning.md) est réglé sur *Journalier* ou *Hebdomadaire*. Le système ajoutera suffisamment de lignes pour atteindre la plage horaire spécifiée pour le groupe de couverture affecté à l’élément.
1. Sélectionnez la période pour laquelle vous souhaitez calculer le délai découplé. (Habituellement, cette période est la période qui inclut la date d’aujourd’hui.)
1. Dans le volet Actions, sur l’onglet **Valeurs tampons**, sélectionnez **Calculer le délai découplé**.
1. Dans la boîte de dialogue **Calculer le délai découplé**, définissez les champs suivants :

    - **Nomenclature** : sélectionnez la nomenclature (BOM) sur laquelle vous souhaitez exécuter le calcul.
    - **Date** : sélectionnez la date à laquelle vous souhaitez exécuter le calcul. L’ensemble des nomenclatures disponibles sera filtré afin que seules les nomenclatures actives pour la date sélectionnée soient affichées.
    - **Quantité** : entrez la quantité du produit pour laquelle vous souhaitez exécuter le calcul. L’ensemble des nomenclatures disponibles sera filtré afin que seules les nomenclatures qui s’appliquent à la quantité spécifiée sont affichées.

1. Sélectionnez **OK** pour exécuter le calcul et fermez la boîte de dialogue **Calculer le délai découplé**. La colonne **Délai découplé** pour la période que vous avez sélectionnée affiche maintenant la valeur calculée.

### <a name="calculate-or-enter-average-daily-usage"></a><a name="calc-adu"></a>Calculer ou saisir la consommation moyenne journalière

Pour les éléments pour lesquels vous choisissez d’autoriser le système à [calculer automatiquement vos zones tampons](#set-up-buffers), suivez ces étapes pour calculer ou saisir l’ADU pour un article de point de découplage.

1. Ouvrez la page **Couverture de l’article** de votre point de découplage. (Pour plus d’informations, voir [Configurer des tampons pour un élément de point de découplage](#set-up-buffers).)
1. Sélectionnez un enregistrement de couverture d’article qui crée un point de découplage.
1. Sélectionnez l’onglet **Valeurs tampons**.
1. Si aucune période n’est affichée dans la grille, dans le volet Actions, sur l’onglet **Valeurs tampons**, sélectionnez **Ajouter des périodes**. Le système remplit la grille avec des lignes pour chaque période quotidienne ou hebdomadaire, selon que le champ **Période Min., Max. et Point de réapprovisionnement** pour le [groupe de couverture](ddmrp-inventory-positioning.md) est réglé sur *Journalier* ou *Hebdomadaire*. De plus, les valeurs par défaut des champs **Facteur de délai** et **Facteur de variabilité** sont extraits du groupe de couverture. Vous pouvez modifier ces valeurs pour chaque ligne selon vos besoins.
1. Sélectionnez une période pendant laquelle vous souhaitez calculer l’ADU.
1. Dans le volet Actions, sur l’onglet **Valeurs tampons**, sélectionnez **Calculer la consommation moyenne quotidienne**. Le système tente de collecter les données nécessaires au calcul de l’ADU, telles que définies pour le [groupe de couverture](ddmrp-inventory-positioning.md).
1. Utilisez l’une des procédures suivantes :

    - Si les données requises sont disponibles, les résultats des calculs sont ajoutés à la colonne **Consommation moyenne journalière**. Dans ce cas, aucune action n’est requise.
    - Si les données requises ne sont pas disponibles, aucune valeur n’est automatiquement ajoutée. Dans ce cas, entrez manuellement les valeurs estimées pour chaque ligne où vous prévoyez de calculer les valeurs de tampon.

### <a name="calculate-and-apply-buffer-values"></a>Calculer et appliquer les valeurs de buffer

Pour les éléments pour lesquels vous choisissez d’autoriser le système à [calculer automatiquement vos zones tampons](#set-up-buffers), vous pouvez déclencher manuellement le calcul des valeurs de buffer en procédant comme suit.

1. Pour le point de découplage concerné, [configurez le calcul du buffer](#set-up-buffers), [calculer ou saisir des délais découplés](#calc-lead-time) et [calculer ou entrer la consommation moyenne journalière](#calc-adu) pour toutes les périodes pertinentes, comme décrit précédemment dans cet article.
1. Ouvrez la page **Couverture de l’article** de votre point de découplage.
1. Sélectionnez l’onglet **Valeurs du buffer**, qui devrait déjà afficher une liste de périodes de temps.
1. Sélectionnez la période pendant laquelle vous souhaitez calculer les valeurs tampon. (Généralement, cette période sera la période qui inclut aujourd’hui.) La ligne que vous sélectionnez doit déjà avoir des valeurs non nulles dans les colonnes **Consommation moyenne journalière** et **Délai découplé**.
1. Modifiez le champ **Facteur d’ajustement de la demande** pour une ou plusieurs lignes selon les besoins. Le système appliquera ce facteur à la valeur **Consommation moyenne journalière** dans tous les calculs de tampon où cette valeur est utilisée. Ce facteur vous permet d’ajuster la façon dont la demande fluctue par date (par exemple, pour les vacances ou les articles saisonniers).
1. Dans le volet Actions, sur l’onglet **Valeurs du buffer**, sélectionnez **Calculer les quantités min, max et point de réapprovisionnement**. Le système calcule et remplit les colonnes **Min. calculée**, **Point de réapprovisionnement calculé** et **Max. calculée** de la grille sur la page **Couverture de l’article**.
1. Lorsque vous avez terminé d’examiner les valeurs calculées, vous devez les appliquer. Sinon, ils n’auront aucun effet. Lorsque vous appliquez un calcul à une ou plusieurs lignes, les valeurs des champs **Min. calculée**, **Réapprovisionnement calculé** et **Max. calculée** sont copiées dans les colonnes **Min.**, **Point de réapprovisionnement** et **Max.**, respectivement. Dans le volet Actions, sous l’onglet **Valeurs du buffer**, dans le groupe **Prendre des mesures**, sélectionnez l’un des boutons suivants :

    - **Accepter tous les calculs** : appliquer toutes les valeurs calculées dans la grille.
    - **Accepter les calculs pour les lignes sélectionnées** : appliquer les valeurs calculées uniquement pour les lignes sélectionnées.
    - **Ignorer tous les calculs** : ignorer toutes les valeurs calculées pour les quantités minimales, les quantités maximales et les points de réapprovisionnement dans la grille.
    - **Ignorer les calculs pour les lignes sélectionnées** : ignorer toutes les valeurs calculées pour les quantités minimales, les quantités maximales et les points de réapprovisionnement dans la grille.

### <a name="schedule-automatic-buffer-value-calculations"></a>Planifier des calculs automatiques de valeur de buffer

Une fois que vous avez entièrement configuré vos paramètres DDMRP et confirmé qu’ils fonctionnent comme prévu, vous souhaiterez probablement configurer une tâche par lots pour recalculer périodiquement l’ADU et les valeurs de tampon associées selon les besoins, en fonction des données de consommation réelles et/ou des prévisions mises à jour. Cette procédure s’applique uniquement aux éléments pour lesquels vous choisissez d’autoriser le système à [calculer automatiquement vos zones tampons](#set-up-buffers).

Suivez ces étapes pour planifier des calculs automatiques de valeur de buffer.

1. Accédez à **Planification \> Planification \> DDMRP \> Calculer les valeurs de buffer**.
1. Dans la boîte de dialogue **Calculer les valeurs de buffer**, définissez les champs suivants :

    - **Calculer la consommation moyenne journalière** : réglez cette option sur *Oui* pour recalculer l’ADU des éléments de point de découplage à chaque exécution de la tâche. Définissez-la sur *Non* pour ignorer ce calcul. Habituellement, vous devez définir cette option sur *Oui*.
    - **Calculer le délai découplé** : réglez cette option sur *Oui* pour recalculer les délais découplés à chaque exécution de la tâche. Définissez-la sur *Non* pour ignorer ce calcul. Habituellement, vous devez définir cette option sur *Oui*.
    - **Calculer les valeurs de buffer** : définissez cette option sur *Oui* pour recalculer les valeurs de buffer à chaque exécution de la tâche. Définissez-la sur *Non* pour ignorer ce calcul. Habituellement, vous devez définir cette option sur *Oui*.
    - **Accepter les calculs pour le point min, max et de réapprovisionnement** : définissez cette option sur *Oui* pour approuver et appliquer automatiquement les valeurs de buffer recalculées à chaque exécution de la tâche. Définissez-la sur *Non* pour laisser les valeurs recalculées non appliquées. Dans ce cas, les valeurs recalculées ne prendront effet que si quelqu’un les applique manuellement plus tard à partir de chaque page **Couverture de l’article** du produit. Habituellement, vous devez définir cette option sur *Oui*.
    - **Plan général** : sélectionnez un plan général qui comprend les éléments concernés par le calcul. Le calcul s’appliquera à tous les éléments du filtre du plan, qui sera encore limité par le paramètre **Filtre** dans cette boîte de dialogue.

1. Pour limiter l’ensemble des enregistrements sur lequel cette tâche de traitement par lots doit être exécutée, sur le raccourci **Enregistrements à inclure**, sélectionnez **Filtrer** pour ouvrir la boîte de dialogue **Recherche**. Cette boîte de dialogue fonctionne comme pour d’autres types de [tâches d’arrière-plan](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Sur le raccourci **Exécuter en arrière-plan**, spécifiez comment, quand et à quelle fréquence les calculs sélectionnés doivent être effectués pour les éléments sélectionnés. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Sélectionnez **OK** pour ajouter la nouvelle tâche à une file d’attente des traitements par lots pour exécution.

### <a name="review-and-recalculate-decoupled-lead-times-for-all-items"></a>Examiner et recalculer les délais découplés pour tous les articles

Suivez ces étapes pour examiner et recalculer tous les délais découplés disponibles dans votre entité juridique (entreprise).

1. Accédez à **Planification \> Planification \> DDMRP \> Délai découplé**.
1. Sur la page **Délai découplé**, parcourez et filtrez la liste selon vos besoins pour trouver les informations que vous recherchez. Pour afficher encore plus d’informations sur un élément, sélectionnez son lien dans la colonne **Numéro d’article**.
1. Si vous souhaitez recalculer le délai découplé pour un article, sélectionnez l’article, puis sélectionnez **Calculer le délai découplé** dans le volet Actions. La boîte de dialogue **Calculer le délai découplé** apparaît. Cette boîte de dialogue fonctionne exactement comme lorsque vous [calculez des délais découplés](#calc-lead-time) pour le même article sur la page **Couverture de l’article**.
