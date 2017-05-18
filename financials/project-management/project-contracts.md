---
title: Contrats de projet
description: "Cet article décrit les contrats de projet à créer pour divers types de projets et de sources de financement (et en fournit des exemples), ainsi que la manière de gérer les contrats et facturer les clients des projets dans Microsoft Dynamics 365 for Operations."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 6a9010f34e862400ca0d25ffde3c3d462a77a43a
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="project-contracts"></a>Contrats de projet

[!include[banner](../includes/banner.md)]


Cet article décrit les contrats de projet à créer pour divers types de projets et de sources de financement (et en fournit des exemples), ainsi que la manière de gérer les contrats et facturer les clients des projets dans Microsoft Dynamics 365 for Operations.

Le type de projet que vous créez pour un contrat de projet détermine la méthode utilisée pour facturer les clients du projet. Vous pouvez modifier un contrat de projet et le projet qui lui est associé, mais vous ne pouvez pas modifier le type de projet. 

En utilisant un contrat de projet, vous pouvez facturer un ou plusieurs projets à la fois. Le contrat de projet permet également de garantir qu'une procédure cohérente de facturation s'applique à chaque sous-projet d'une structure de projets. 

Chaque projet qui sera facturé doit être associé à un contrat de projet. Les paramètres pour un contrat de projet s'appliquent à tous les projets et sous-projets associés à ce contrat de projet. 

Dans un contrat de projet, il est possible de spécifier une ou plusieurs sources de financement. Par conséquent, vous pouvez diviser la facturation entre plusieurs investisseurs, définir des limites de financement afin que les sources de financement ne soient pas facturées au delà d'un montant spécifié, et configurer des règles de financement pour le débit des dépenses.

## <a name="funding-for-project-contracts"></a>Financement des contrats de projet
Certains contrats de projet spécifient que plusieurs parties partage la responsabilité du financement pour les coûts d'un projet. Voici quelques exemples :

-   Un client important qui comporte plusieurs divisions demande que le financement d'un projet soit fractionné par division.
-   Votre société partage les coûts d'un projet important avec une organisation externe.
-   Un projet de construction de route est cofinancé par deux municipalités.
-   Un projet de construction de pont est financé par une subvention gouvernementale et une société privée.

Dans Microsoft Dynamics 365 for Operations, vous pouvez fractionner la facturation pour une seule transaction ou un projet entier entre plusieurs clients, subventions, ou organisations. 

Dans les projets impliquant plusieurs investisseurs, les parties contribuant au financement d'un projet de financement avancé sont appelées sources de financement. Une fois qu'un client, une organisation ou une subvention est défini comme source de financement, il peut être affecté à une ou plusieurs règles de financement. Les règles de financement incluent les critères qui déterminent la façon dont les frais sont répartis entre les différentes sources de financement pour un projet. 

Étant donné que les articles stockés, tels que ceux qui figurent sur les demandes d'achat et les commandes fournisseur, ne peuvent pas être fractionnés, le montant des coûts ne peut pas être divisé entre plusieurs sources de financement au moment de distribution. Par conséquent, la valeur de source de financement reste 0 (zéro) jusqu'à la validation de la sortie de stock. Une fois la sortie de stock validée, le montant des coûts est réparti conformément aux règles de répartition comptable du projet.

Voici quelques mesures que vous pouvez prendre pour faciliter le fractionnement de la facturation entre plusieurs sources de financement :

-   Spécifiez l'utilisation par toutes les transactions entrées pour un projet de la même devise de vente que le contrat de projet.
-   Paramétrez les limites de financement afin qu'une source de financement ne soit pas facturée d'un montant supérieur à celui spécifié pour un projet.
-   Configurez les règles et limites de financement pour chaque travailleur, article, catégorie, groupe de catégories et type de transaction (ou pour tous les types de transactions).
-   Sélectionnez les dates de début et de fin facultatives pour définir la période de validité de chaque règle de financement.
-   Spécifiez le pourcentage dont chaque source de financement est responsable.
-   Spécifiez la source de financement responsable des différences d'arrondi causées par le calcul de l'allocation de financement.
-   Paramétrez les règles qui déterminent la facturation des coûts de projet auprès des clients externes et des organisations internes.
-   Enregistrez les transactions dans un compte de financement en attente jusqu'à l'obtention de financements supplémentaires ou la décision de prise en charge interne des coûts.

Pour déterminer le groupe de taxe à associer à une transaction, une recherche d'affectation de groupe de taxe est effectuée dans le projet. Si aucune affectation de groupe de taxe n'a été effectuée au niveau du projet, une recherche est effectuée dans le contrat de projet.

### <a name="example-multiple-funding-sources-simple"></a>Exemple : plusieurs sources de financement (simple)

Le tableau suivant fournit des scénarios pour gérer la répartition de financement entre plusieurs sources de financement. Ces scénarios sont basés sur les suppositions suivantes :

-   Les paramètres de priorité sont factorisés dans la répartition des fonds avant l'application d'autres critères de règle de financement.
-   Aucune plage de dates n'a été spécifiée pour définir la période pendant laquelle la règle de financement est valide.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Scénario</strong></td>
<td><strong>Source de financement </strong></td>
<td><strong>Pourcentage de répartition </strong></td>
<td><strong>Priorité de répartition </strong></td>
</tr>
<tr class="even">
<td>Vous souhaitez affecter des coûts à une source de financement jusqu'à ce que les fonds associés soient épuisés, affecter des coûts à une deuxième source de financement jusqu'à ce que les fonds associés soient épuisés, puis finalement affecter les coûts restants à une troisième source de financement.</td>
<td><ul>
<li>Source　de financement　1</li>
<li>Source　de financement　2</li>
<li>Source　de financement　3</li>
</ul></td>
<td><ul>
<li>100 %</li>
<li>100 %</li>
<li>100 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
<li>3</li>
</ul></td>
</tr>
<tr class="odd">
<td>Vous souhaitez affecter 75 % des coûts à une source de financement et 25 % à une deuxième source de financement. Lorsque l'une de ces sources de financement est épuisée, vous souhaitez payer les coûts restants à partir d'une troisième source de financement.</td>
<td><ul>
<li>Source　de financement　1</li>
<li>Source　de financement　2</li>
<li>Source　de financement　3</li>
</ul></td>
<td><ul>
<li>75 %</li>
<li>25 %</li>
<li>100 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
<tr class="even">
<td>Vous souhaitez affecter 75 % des coûts à une source de financement et 25 % à une deuxième source de financement. Lorsque l'une des sources de financement est épuisée, vous souhaitez fractionner les coûts restants entre une troisième et une quatrième sources de financement.</td>
<td><ul>
<li>Source　de financement　1</li>
<li>Source　de financement　2</li>
<li>Source　de financement　3</li>
<li>Source　de financement　4</li>
</ul></td>
<td><ul>
<li>75 %</li>
<li>25 %</li>
<li>50 %</li>
<li>50 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
<li>2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Vous souhaitez affecter les premiers 25 % des coûts à une source de financement et le reste à une seconde source de financement.</td>
<td><ul>
<li>Source　de financement　1</li>
<li>Source　de financement　2</li>
</ul></td>
<td><ul>
<li>25 %</li>
<li>100 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a>Exemple : plusieurs sources de financement (complexe)

Vous avez trois sources de financement que vous souhaitez utiliser dans l'ordre suivant :

1.  Utilisez la source de financement 2 et la source de financement 3 de manière égale jusqu'à ce que la source de financement 2 soit épuisée.
2.  Continuez à utiliser la source de financement 3 jusqu'à ce qu'elle soit épuisée.
3.  Utilisez la source de financement 1 après épuisement de la source de financement 3.

Pour atteindre cet objectif, vous devez procéder comme suit :

-   Paramétrez des limites de financement pour la source de financement 2 et la source de financement 3 pour leurs montants respectifs.
-   Créez les règles de financement suivantes :
    -   Règle 1 (Priorité 1) : affectez 50 % des transactions à la source de financement 2 et 50 % à la source de financement 3.
    -   Règle 2 (Priorité 2) : affectez 100 % des transactions à la source de financement 3.
    -   Règle 3 (Priorité 3) : affectez 100 % des transactions à la source de financement 1.

Ce paramétrage fonctionne car les transactions sont vérifiées par rapport aux règles et aux limites afin de déterminer si l'une de celles-ci s'applique à la transaction. Si aucune règle ni limite spécifique ne s'applique à la transaction, la règle Toutes les transactions s'applique. La règle Toutes les transactions met en correspondance toutes les transactions. 

Si une règle est trouvée qui correspond à une transaction, le pourcentage affecté à cette règle est appliqué en premier, mais seulement une fois que les correspondances sont vérifiées par rapport aux limites paramétrées. Si une limite a été respectée et que les fonds d'une source de financement sont épuisés, la règle de financement associée à la limite de financement est ignorée et le programme recherche la règle suivante qui s'applique. 

Dans certains cas, seule une partie d'une transaction peut être affectée en fonction d'une règle. Cela peut se produire car une limite est atteinte lorsque la transaction est affectée. Dans ce cas, seul un certain montant est affecté conformément à cette règle, par exemple, 50 % à chaque source de financement. C'est le cas dans la règle 1, décrite plus haut dans cette section. Le reste est affecté conformément à la règle suivante de la séquence. 

Le tableau suivant présente ce scénario plus en détail.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Vue </strong></td>
<td><strong>Détails</strong></td>
</tr>
<tr class="even">
<td>Règles de financement</td>
<td><ul>
<li>Règle 1 (Priorité 1) : Toutes les transactions. Affectez 50 % à la source de financement 2 et 50 % à la source de financement 3.</li>
<li>Règle 2 (Priorité 2) : Toutes les transactions. Affectez 100 % à la source de financement 3.</li>
<li>Règle 3 (Priorité 2) : Toutes les transactions. Affectez 100 % à la source de financement 1.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Limites de financement</td>
<td><ul>
<li>Limite de la source de financement 1 = 10 000,00</li>
<li>Limite de la source de financement 2 = 500,00</li>
<li>Limite de la source de financement 3 = 750,00</li>
</ul></td>
</tr>
<tr class="even">
<td>Transaction 1</td>
<td><strong>Montant de la transaction :</strong> 100,00<strong>Financement :</strong> la transaction est payée conformément à la règle 1 uniquement, car la transaction est intégralement payée une fois la règle 1 appliquée. La transaction est financée de manière égale entre la source de financement 2 et la source de financement 3.
<ul>
<li>Source de financement 2 : 50,00</li>
<li>Source de financement 3 : 50,00</li>
</ul></td>
</tr>
<tr class="odd">
<td>Transaction 2</td>
<td><strong>Montant de la transaction :</strong> 5 000,00<strong>Financement :</strong> la transaction est payée conformément aux trois règles.<strong>Règle 1</strong>
<ul>
<li>Source de financement 2 : 450,00</li>
<li>Source de financement 3 : 450,00</li>
</ul>
<strong>Règle 2</strong>
<ul>
<li>Source de financement 3 :: 250,00 (= 750,00 – 50,00 – 450,00)</li>
</ul>
<strong>Règle 3</strong>
<ul>
<li>Source de financement 1 : 3 850,00 (= 5 000,00 – 450,00 – 450,00 – 250,00)</li>
</ul></td>
</tr>
<tr class="even">
<td>Total des fonds distribués pour chaque source de financement</td>
<td><ul>
<li>Source de financement 1 : 3 850,00</li>
<li>Source de financement 2 : 500,00</li>
<li>Source de financement 3 : 750,00</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a>Règles de facturation
Lorsque vous négociez un contrat de projet avec un client, vous définissez comment et quand facturer le client pour le travail effectué sur le projet. Après avoir établi le contrat de projet et le projet, vous pouvez définir des règles de facturation spécifiques au projet. Les règles de facturation sont basés sur les conditions du projet qui sont spécifiées dans le contrat de projet. Les règles de facturation que vous pouvez créer dépendent des conditions du contrat de projet et du type de projet, par exemple Régie ou Prix fixe, que vous associez à la règle de facturation. Vous pouvez créer plusieurs règles de facturation pour un contrat de projet. Vous pouvez également affecter une règle de facturation à plusieurs projets associés au même contrat de projet et avoir des conditions de facturation similaires. 

Vous pouvez définir les types de règles de facturation suivants :

-   **Unité de livraison** – Facturer le client à la fin d'une unité de livraison. Les unités de livraison sont définies dans le contrat.
-   **Progression** – Facturer le client après avoir accompli un pourcentage défini du projet. Vous pouvez paramétrer une règle de facturation pour calculer automatiquement le pourcentage de travail réalisé ou calculer manuellement le pourcentage de travail accompli et le montant à facturer au client.
-   **Jalon** – Facturer au client le montant total correspondant à un jalon du projet une fois celui-ci atteint.
-   **Frais** – Facturer au client les services fournis plus les frais de gestion ; ces derniers correspondant généralement à un pourcentage du coût des services.
-   **Régie** – Facturer le client pour la valeur des heures et du matériel affectés à un projet en régie.

Pour tous les types de règles de facturation, vous pouvez spécifier un pourcentage de rétention qui est déduit des factures client jusqu'à ce qu'un projet atteigne un stade convenu. Le pourcentage de rétention de paiement est spécifié dans le contrat de projet. Le montant est calculé selon et soustrait de la valeur totale des lignes d'une facture client. 

Pour les règles de facturation **Régie** et **Progression**, vous pouvez affecter des catégories facturables. Les catégories facturables indiquent les transactions à inclure dans les factures client. 

Ainsi, au moment de la facturation, le montant de la facture pour le projet est calculé sur la base de ces règles et une proposition de facture de projet est générée. 

Les sections suivantes présentent des exemples qui illustrent la manière de paramétrer et de gérer les règles de facturation pour un projet.

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a>Exemple : création d'une règle de facturation basée sur le nombre d'unités livrées

Votre organisation conclut un accord pour fournir un total de cinq sessions de formation aux employés d'un client à un coût de 10 000 par session de formation. Vous établissez votre facture à la fin de chaque session de formation. 

Lorsque vous paramétrez les règles de facturation du contrat, vous utilisez les valeurs suivantes :

-   Une unité de livraison correspond à une session de formation.
-   Le prix unitaire est de 10 000 euros par session de formation.
-   Le nombre total d'unités est de cinq sessions de formation.

À la fin d'une session de formation, vous pouvez créer une facture d'un montant de 10 000 pour la première unité livrée et envoyer la facture au client.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a>Exemple : création d'une règle de facturation basée sur un pourcentage défini d'achèvement du projet (calcul manuel)

Votre organisation, une société spécialisée dans la consultance logicielle, conclut un accord avec un client pour assurer le développement d'une partie d'un produit développé par le client. Votre organisation s'est engagée à livrer le code logiciel sur une période de six mois. Le client a accepté de verser à votre organisation un total de 100 000 euros en échange de ce travail. Vous créez une règle de facturation pour facturer le client sur la base du pourcentage de travail accompli pour le projet, tel que défini dans le contrat.

-   À la fin du premier mois, vous rencontrez le client pour déterminer le pourcentage de travail réalisé. Après examen du projet par vous-même et votre client, vous décidez que le projet est réalisé à 15 %.
-   Vous créez une facture d'un montant de 15 000 (15 % de 100 000) et l'envoyez au client.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a>Exemple : création d'une règle de facturation basée sur un pourcentage défini d'achèvement du projet (calcul automatique)

Votre organisation, une société de développement de logiciels, accepte de développer un module de gestion des salaires pour un client pour un montant de 30 000. Le client s'est engagé à payer votre organisation sur la base du pourcentage de travail réalisé. Vous estimez que le coût du projet s'élève à 20 000 euros. Le contrat de projet spécifie les catégories de travail que vous utilisez dans le processus de facturation. Vous paramétrez des règles de facturation qui calculent automatiquement les montants à facturer pour le pourcentage de travail réalisé dans chaque catégorie. Vous définissez un budget pour chaque catégorie :

-   **Développement** – Coût de 15 000 et produit de 20 000
-   **Installation** – Coût de 5 000 et produit de 10 000

Lorsque vous créez votre première facture client, son montant est automatiquement calculé sur la base des informations suivantes :

-   Après un mois, le salarié qui travaille sur le projet soumet une feuille de temps pour le projet. Le coût des heures du consultant est de 5 000 euros pour le développement et de 1 000 euros pour l'installation. Le travail de développement est réalisé à 33 % (coût réel de 5 000/coût budgétaire de 15 000) et le travail d'installation à 20 % (coût réel de 1 000/coût budgétaire de 5 000).
-   Le montant de 8 667 est calculé automatiquement (33 % de 20 000 + 20 % de 10 000).
-   Vous créez une facture d'un montant de 8 667 et l'envoyez au client.

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a>Exemple : création d'une règle de facturation basée sur des jalons prédéfinis

Votre organisation, une société spécialisée en conseil de gestion, accepte de réaliser une étude de marché sur un produit de consommation que le client prévoit de vendre. L'accord prévoit que le client utilisera vos services pendant une période de trois mois à compter du mois du mars contre la somme de 50 000 euros. Le projet comporte trois jalons :

-   Jalon 1 : collecte de données sur les consommateurs – 31 mars
-   Jalon 2 : analyse des données sur les consommateurs – 30 avril
-   Jalon 3 : présentation d'une proposition de viabilité du produit – 31 mai

Le client s'est engagé à payer à votre organisation 10 000 pour le premier jalon, 20 000 pour le second jalon et 20 000 pour le troisième jalon. 

Le contrat de projet stipule que le client sera facturé en fonction du jalon qui est atteint. La règle de facturation doit être définie en deux étapes :

-   Définition des jalons du projet.
-   Définissez le montant à facturer au client lorsque chaque jalon est atteint.

Lorsque le premier jalon est atteint, le 31 mars, vous marquez le jalon comme terminé, puis créez une facture d'un montant de 10 000 et vous l'envoyez au client. Vous ne pouvez pas créer une facture pour un jalon tant vous n'avez pas marqué le jalon comme terminé.

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a>Exemple : création d'une règle de facturation basée sur des services fournis plus les frais de gestion associés

Votre organisation, une société spécialisée dans le conseil de gestion, accepter de réaliser une étude de marché pour évaluer la viabilité d'un produit que le client, une société de vente au détail, est en train de développer. Les conditions de l'accord spécifient que vous fournirez les services de vos trois meilleurs consultants en gestion, qui mèneront les recherches dans le cadre d'un contrat en régie. Le client s'engage à payer 100 par heure, plus 10 % de frais de gestion calculés à partir des heures de conseil facturées pour le projet. 

Au moment de la définition du contrat de projet, créez une règle de facturation pour ajouter 10 % de frais de gestion aux heures de conseil facturées pour le projet. 

Lors de la création d'une facture, vous facturez les heures de consultance plus 10 % de frais de gestion. Par exemple, si les trois consultants ont travaillé pendant un total de 200 heures sur le projet, une facture d'un montant de 22 000 est créée, sur la base du calcul suivant :

-   200 heures à 100 euros l'heure = 20 000 euros
-   10 % de frais de gestion = 2 000
-   Montant total facturé = 22 000

Si les frais sont imposable pour un client, et que vous sélectionnez un groupe de taxe dans le contrat de projet, le groupe de taxe est automatiquement entré dans une règle de facturation pour les frais.

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a>Exemple : création d'une règle de facturation pour un contrat en régie

Votre organisation, une société spécialisée dans le conseil en matière de développement de logiciels, s'est engagée auprès d'un client à fournir cinq consultants techniques pour travailler sur un projet de développement logiciel durant les six prochains mois. Le client accepte de payer 150 pour chaque heure de conseil, plus le coût des fournitures de bureau. Votre organisation envoie une facture au client à la fin de chaque mois. 

Lorsque vous définissez le contrat de projet, vous convenez que le temps passé et le matériel utilisé pour le projet seront facturé au client sur une base mensuelle. Vous créez une règle de facturation qui comporte les informations suivantes :

-   La durée du contrat est de six mois.
-   Les prestations de conseil sont calculées à un taux de 150 de l'heure.
-   Les fournitures de bureau sont facturées au prix de revient, et le coût total du projet ne doit pas dépasser 10 000 pour le projet.
-   Vous créez une facture client à la fin de chaque mois du calendrier pendant la durée du projet.

Durant le premier mois, un total de 800 heures sont enregistrées par les consultants. Le coût des fournitures de bureau facturées pour le projet s'élève à 2 000. Par conséquent, à la fin du mois, vous créez une facture de 122 000, qui englobe 800 heures à 150 de l'heure, plus 2 000 de fournitures de bureau.




