---
title: "Gestion et comptabilité des projets"
description: "La fonctionnalité de gestion de projets et de comptabilité peut être utilisée dans plusieurs secteurs pour fournir un service, fabriquer un produit, ou atteindre résultat."
author: KimANelson
manager: AnnBe
ms.date: 01/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjTable; ProjProjectManagementWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: b8f2f3a33dc19c2ebc941d1a504eae0c276f3cdf
ms.openlocfilehash: 46c8ecf8a6988c32d0202c631bef6901f467bb89
ms.contentlocale: fr-fr
ms.lasthandoff: 06/25/2018

---

# <a name="project-management-and-accounting"></a>Gestion et comptabilité des projets

[!include [banner](../includes/banner.md)]

La fonctionnalité de gestion de projets et de comptabilité peut être utilisée dans plusieurs secteurs pour fournir un service, fabriquer un produit, ou atteindre résultat.  

Un projet est un groupe d'activités qui est conçu pour fournir un service, fabriquer un produit, ou pour atteindre un résultat. Les projets consomment des ressources et génèrent des résultats financiers sous la forme de produits ou d'immobilisations.

## <a name="projects-across-industries"></a>Projets couvrant plusieurs secteurs
La fonctionnalité de gestion de projets et de comptabilité peut être utilisée dans plusieurs secteurs d'activité, comme le montre l'illustration suivante. [![Projets couvrant plusieurs secteurs](./media/projects-accross-industries.jpg)](./media/projects-accross-industries.jpg) 

Dans un centre d'appels, un ticket peut être utilisé pour décrire l'ensemble des actions requises pour résoudre un appel. Les sociétés de conseil, telles que les sociétés de gestion ou de consultance techniques ou les agences de publicité, désignent leurs activités comme des projets. En marketing, une campagne représente un ensemble de travail qui doit être livré. Dans la fabrication basée sur projet, un ordre de fabrication se rapporte à l'ensemble du travail varié qui doit être effectué pour produire des produits finis donnés. Quelque soit le nom que l'on emploie, ces projets impliquent des ressources, des programmes et des coûts, et la fonctionnalité de gestion de projets et de comptabilité dans Microsoft Dynamics 365 for Finance and Operations peut aider à organiser, exécuter et analyser ces projets.

## <a name="project-phases"></a>Projet de projet
Bien que le flux de processus suivant concerne des projets externes, ou des projets terminés pour un ou plusieurs clients, la fonctionnalité s'applique également aux projets internes et aux projets à coût uniquement. 

![Les 3 stades d'un projet](./media/3-stages-of-a-project.png) 

Comme le montre l'illustration précédente, la gestion de projets et la comptabilité peuvent être éclatées en trois phases :

1.  Initier
2.  Exécuter
3.  Analyser

## <a name="initiate-the-project"></a>Initiation du projet
Lors de l'initiation de projet, plusieurs principaux processus se produisent. Vous pouvez utiliser un devis de projet pour communiquer l'estimation du travail, des dépenses et des matières au client. Vous pouvez enregistrer les termes de facturation, les limites et les accords dans un contrat de projet. Vous pouvez utiliser une structure de répartition du travail (WBS) pour planifier et estimer le travail. Vous pouvez paramétrer une prévision et des budgets pour guider l'exécution du projet. La figure suivante indique la structure d'un projet.[![structure de projets](./media/project-structure1.jpg)](./media/project-structure1.jpg)  

### <a name="create-project-quotations"></a>Créer des devis de projet

Dans la première étape de vente d'un projet, un devis de projet vous permet de remettre une offre indicative à un client. Le devis peut comprendre des éléments tels que les articles et services qui font l'objet d'un devis, des informations de contact de base, des accords commerciaux spéciaux et des remises et d'éventuelles taxes et surcharges.

Vous pouvez également émettre une lettre de garantie pour une transaction de devis de projet entre votre organisation et le client. Après la création du devis de projet, vous pouvez créer une demande de lettre de garantie pour le compte du client et la transmettre à la banque. Une fois que la banque a approuvé la demande, la lettre de garantie est remise au client. 

Pour plus d'informations, voir [Devis de projet](project-quotations.md).

### <a name="create-project-contracts"></a>Créer des contrats de projet

Lorsque vous concluez un contrat avec un client ou une autre source de financement pour réaliser un projet, vous devez d'abord créer un contrat de projet. Ensuite, quand vous créez le projet, vous devez l'affecter au contrat correspondant. Le type de projet que vous créez pour un contrat de projet détermine la méthode utilisée pour facturer les clients du projet. Vous pouvez modifier un contrat de projet et le projet lié, mais vous ne pouvez pas modifier le type de projet. Pour plus d'informations sur les types de projets, consultez la section « Création de projet ».

Pour plus d'informations sur les contrats de projet, voir [Contrats de projet](project-contracts.md).

### <a name="create-work-breakdown-structures"></a>Création de structures de répartition du travail

Le degré de détail dans une WBS dépend du niveau de précision souhaité pour les estimations et le niveau de suivi requis par rapport à ces estimations. Les projets qui ont une tolérance très basse aux écarts de durée ou de coût nécessitent généralement une WBS plus détaillée, ainsi qu'un suivi diligent de la progression et du coût des travaux par rapport à la WBS. 

Pour plus d'informations, voir [Structures de répartition du travail](work-breakdown-structures.md).

### <a name="create-project-forecasts-and-budgets"></a>Création des prévisions de projet et des budgets de projet

Vous pouvez utiliser la prévision si votre organisation a une perspective opérationnelle orientée sur les produits et les coûts qui sont dérivés des transactions spécifiques. Toutefois, vous pouvez utiliser la budgétisation si votre organisation s'oriente plus sur les montants financiers. Chaque méthode a ses avantages. Pour plus d'informations, consultez [Prévisions et budgets de projet](project-forecasts-budgets.md).

### <a name="create-projects"></a>Créer des projets

Vous pouvez créer six types de projets dans Microsoft Finance and Operations. Chaque type de projet est paramétré différemment pour les coûts et la constatation du produit. La sélection d'un type de projet dépend de l'objectif du projet. Le tableau suivant décrit l'utilisation typique de chaque type de projet.
                                                                                                            
<table>
  <tr>
    <td>Type de projet</th>
    <td>Description</th>
  </tr>
  <tr>
    <td>Régie</td>
    <td>Dans les projets en régie, le client est facturé pour tous les coûts engagés sur un projet. Ces coûts incluent notamment les heures, les dépenses, les articles et les frais.</td>
  </tr>
  <tr>
    <td>Prix fixe</td>
    <td>Dans les projets à prix fixe, les factures sont composées des transactions en compte. Un projet à prix fixe est facturé selon un programme de facturation basé sur un contrat de projet. Le produit pour un projet à prix fixe peut être calculé et validé tout au long du projet à l'aide de la méthode de pourcentage terminé. Sinon, le produit peut être calculé et validé une fois le projet terminé, à l'aide de la méthode de contrat terminé. Les sociétés peuvent souvent tirer profit de l'utilisation de la valeur des travaux en cours pour calculer le degré d'achèvement d'un projet ou d'un groupe de projets.</td>
  </tr>
  <tr>
    <td>Investissement</td>
    <td>Les projets d'investissements sont des projets sans bénéfice immédiat. Ils sont généralement utilisés pour les projets internes à long terme dans lesquels les coûts doivent être capitalisés. Seul le coût des articles, les heures et les dépenses peuvent être enregistrés dans un projet d'investissement. Les coûts d'un projet d'investissement sont suivis et contrôlés à l'aide de la fonctionnalité d'estimation. Les projets d'investissement peuvent être définis avec une capitalisation maximale (facultative). À mesure de l'avancement des projets d'investissement, vous enregistrez les coûts associés dans les comptes de travaux en cours, dans lesquels les coûts sont conservés jusqu'à l'exécution complète du projet. Si le projet est éliminé, vous transférez la valeur des travaux en cours vers une immobilisation, un compte général ou un nouveau projet. <br></br> <strong>REMARQUE :</strong> les transactions des projets d'investissement ne sont pas affichées dans la page <strong>Valider les coûts<strong>, <strong>Provisionner le produit</strong> ou <strong>Créer des propositions de facture</strong>.</td>
  </tr>
  <tr>
    <td>Projet de coût</td>
    <td>À l'instar des projets d'investissement, les projets de coûts permettent généralement de suivre les projets internes, et uniquement les heures, les dépenses et les articles peuvent être enregistrés pour ces projets. Toutefois, la durée des projets de coûts est généralement plus courte que celle des projets d'investissement. En outre, contrairement aux projets d'investissement, les projets de coûts ne peuvent pas être capitalisés dans les comptes de bilan. Au lieu de cela, les transactions de projet associées sont validées uniquement dans les comptes de résultat. <br></br> <strong>REMARQUE :</strong> les transactions des projets de coûts ne sont pas reflétées dans la page <strong>Valider les coûts</strong>, <strong>Provisionner le produit</strong> ou <strong>Créer des propositions de facture</strong>. Les projets de coûts étant généralement utilisés pour suivre les projets internes, ils ne doivent habituellement pas être associés à un compte client. Toutefois, si votre paramétrage requiert que les demandes d'articles soient créées pour les commandes fournisseur, vous devez associer le projet de coûts à un client. Cette association est obligatoire, du fait que les demandes d'articles sont gérées comme des lignes de commande client, et que le système nécessite qu'un client soit spécifié. Toutefois, ce paramétrage n'entraînera pas la création automatique de demandes d'articles à partir d'une commande fournisseur. Pour les projets de coûts, le paramètre <strong>Créer une demande d'articles</strong> est ignoré. Si vous avez besoin d'une demande d'article dans un projet de coûts, vous pouvez en créer une manuellement, à condition qu'un client soit associé au projet.</td>
  </tr>
  <tr>
    <td>Interne</td>
    <td>Les projets internes permettent de suivre les coûts d'un projet interne à votre organisation. Les projets internes peuvent fournir un outil d'organisation pour gérer la consommation de ressources. <br></br><strong>REMARQUE :<strong> les transactions des projets internes ne sont pas reflétées dans la page <strong>Provisionner le produit</strong> ou <strong>Créer des propositions de facture</strong>.</td>
  </tr>
  <tr>
    <td>Heure</td>
    <td>Les projets de temps permettent de suivre le temps associé à des activités non facturables et non productives, telles qu'un projet visant à suivre les jours de congé maladie des travailleurs. Les transactions associées aux projets de temps ne sont pas validées dans la comptabilité. Au lieu de cela, elles sont incluses dans les états relatifs à l'utilisation des heures du travailleur. Seules les transactions horaires peuvent être enregistrées dans les projets de temps. Vous utilisez un journal des heures ou une feuille de temps pour enregistrer ces heures dans le projet. Une fois les heures enregistrées, elles apparaissent comme transactions de projet, mais sans transaction de N° document correspondante. <br></br><strong>REMARQUE :</strong> les transactions des projets de temps ne sont pas reflétées dans la page <strong>Valider les coûts</strong>, <strong>Provisionner le produit</strong> ou <strong>Créer des propositions de facture</strong>.</td>
  </tr>
</table>


### <a name="assign-workers-categories-and-resources"></a>Affecter des collaborateurs, des catégories et des ressources

Vous pouvez planifier les collaborateurs en fonction des besoins et du programme d'un projet ou en fonction des qualifications et de la disponibilité des collaborateurs. À l'aide des fonctionnalités de planification des ressources, vous pouvez déployer efficacement les collaborateurs de votre organisation. Vous pouvez rapidement rechercher les collaborateurs les plus qualifiés disponibles pour travailler sur le projet. Vous pouvez également facilement voir comment les collaborateurs peuvent être déployés plus efficacement au cours du projet. 

Voici quelques manières dont vous pouvez utiliser la fonctionnalité de planification des ressources :

-   Utiliser les informations sur les attributs d'un collaborateur, telles que la formation, les compétences, les certifications et l'expérience du projet afin de les faire correspondre aux exigences d'un projet.
-   Utiliser les informations sur le calendrier et la disponibilité d'un collaborateur pour que son programme corresponde au calendrier du projet.
-   Examiner la capacité de chaque collaborateur et évaluer l'utilisation de cette capacité. Par exemple, si un collaborateur est sous exploité, il peut être affecté à un projet qui correspond à sa disponibilité et à ses attributs.
-   Examiner la disponibilité des collaborateurs afin de s'assurer de l'absence de conflit de calendrier avec leurs affectations.
-   Examiner les informations sur l'utilisation des collaborateurs sous la forme d'une synthèse (par exemple, par département ou par collaborateur), ou d'une manière détaillée (par exemple, par collaborateur d'un département ou sur une base hebdomadaire pour chaque collaborateur).
-   Modifier les affectations de ressources pour différentes unités de temps, telles que jour, semaine ou mois pour optimiser l'utilisation des collaborateurs.

## <a name="execute-the-project"></a>Exécuter le projet
Lors de l'exécution du projet, les membres de l'équipe ou les responsables enregistrent le travail et les dépenses effectués à l'aide de feuilles de temps, d'états de dépenses, et d'autres documents commerciaux. Les chefs de projet ont des outils qui leur permettent de contrôler la consommation des montants budgétés pour le projet. Les chefs de projet peuvent également commander, prélever, ou obtenir des matières pour les projets à l'aide de commandes fournisseur et d'autres documents commerciaux. Les factures sont préparées et approuvées, de sorte que les clients soient facturés pour le travail réel. Enfin, le produit est identifié lors de ce processus pour affecter les finances de l'organisation.

### <a name="manage-work-breakdown-structures"></a>Gestion des structures de répartition du travail

Une WBS est une description du travail qui sera accompli pour un projet. Une WBS est une hiérarchie de tâches. Elle représente non uniquement le travail pour chaque tâche, mais également l'ampleur, le coût et la durée de la tâche. 

Pour plus d'informations, voir [Structures de répartition du travail](work-breakdown-structures.md).

### <a name="manage-project-forecasts-and-budgets"></a>Gestion des prévisions et des budgets de projet

Il existe deux méthodes permettant de gérer et de contrôler vos projets : les prévisions de projet et les budgets de projet. Vous pouvez utiliser la prévision si votre organisation a une perspective opérationnelle orientée sur les produits et les coûts qui sont dérivés des transactions spécifiques. Toutefois, vous pouvez utiliser la budgétisation si votre organisation s'oriente plus sur les montants financiers.

Pour plus d'informations, consultez [Prévisions et budgets de projet](project-forecasts-budgets.md).

### <a name="create-production-orders"></a>Créer des ordres de fabrication

Un ordre de fabrication associé à un projet peut être lié à une commande client ou à une demande d'articles à l'aide de la méthode Article fini ou Article consommé. En outre, si l'ordre de fabrication a été créé manuellement, il n'existe aucun lien entre l'ordre de fabrication et la commande client ou la demande d'articles (pas de lien avec la commande) Cependant, si l'ordre de fabrication a été créé automatiquement pour honorer une commande client ou une demande d'articles, il existe un lien entre l'ordre de fabrication et la commande client ou la demande d'articles (lié à la commande) 

En fonction des combinaisons de ces facteurs, utilisez l'une des méthodes suivantes :

- **Article fini/lié à la commande** – Lie le projet à une commande client ou à une demande d'articles. Avec cette méthode, les coûts de projet réels sont validés lorsque la commande client est facturée ou lorsque le bon de livraison est mis à jour avec la demande d'articles. Le coût est validé en tant qu'article fini.
- **Article fini/pas de lien avec la commande** – Les coûts réels ne peuvent pas être validés tant que le cycle de production d'un article a le statut **Terminé**. Le coût de l'article fini est validé en tant que transaction unique.
- **Article consommé/lié à la commande** – Lie le projet à une demande d'articles. Cette méthode permet d'afficher les coûts de projet réels lorsque la production a le statut **Commencé** ou est déclarée terminée. Les coûts seront validés sous la forme de plusieurs transactions d’article de projet pour les matières premières et les heures consommées pour la production. Lorsque le bon de livraison est mis à jour avec la demande d'articles, aucun coût de projet n'est validé. Vous pouvez également définir le niveau de hiérarchie de la nomenclature auquel les projets sont suivis dans la production.
- *<strong><em>Article consommé/lié à la commande</em></strong>* – Lie le projet à une demande d'articles. Cette méthode permet d'afficher les coûts de projet réels lorsque la production a le statut <strong>Commencé</strong> ou est déclarée terminée. Les coûts sont validés sous la forme de plusieurs transactions d’article de projet pour les matières premières et les heures consommées pour la production. Vous pouvez également définir le niveau de hiérarchie de la nomenclature auquel les projets sont suivis dans la production.

### <a name="procure-products-and-services"></a>Définition de l'approvisionnement des produits et des services

L'achat et la vente d'articles sont des aspects courants dans de nombreuses sociétés orientées sur les projets.

#### <a name="purchase-orders-for-projects"></a>Commandes fournisseur pour des projets

L'objectif de la commande fournisseur détermine le moment où celle-ci est consommée, et donc quand des articles sont validés sur un projet.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Méthode</th>
<th>Objectif</th>
<th>Consommation d'articles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Création directe d'une commande fournisseur.</td>
<td>Achat d'articles à un fournisseur externe en vue d'une consommation sur un projet. Vous pouvez créer des commandes fournisseur de plusieurs manières :
<ul>
<li>À partir du projet lui-même. Dans ce cas, le projet est déjà défini pour la commande fournisseur.</li>
<li>En accédant à la commande fournisseur. Vous devez sélectionner le fournisseur et le projet pour lequel créer la commande fournisseur.</li>
</ul></td>
<td>Les articles sont consommés lorsque la facture fournisseur est mise à jour.</td>
</tr>
<tr class="even">
<td>Créez une commande fournisseur à partir d'une commande client.</td>
<td>Achetez des articles quand vous créez une commande fournisseur à partir d'un projet.</td>
<td>Des articles sont consommés lorsque la commande client est facturée au client.</td>
</tr>
<tr class="odd">
<td>Créez une commande fournisseur à partir d'une demande d'articles.</td>
<td>Achetez des articles quand vous créez une demande d'articles à partir d'un projet.</td>
<td>Des articles sont consommés lors de la mise à jour du bon de livraison de demande d'articles.</td>
</tr>
</tbody>
</table>

#### <a name="sales-orders-for-projects"></a>Commandes client pour des projets

Dans le module Gestion de projets et comptabilité, vous pouvez enregistrer la consommation des articles de plusieurs manières. Vous pouvez vendre ou acheter des articles à partir d'un projet ou réserver des articles pour un projet. 

Vous pouvez commander des articles du stock de la société pour les consommer dans un projet. Sinon, ou vous pouvez acheter les articles auprès d'un fournisseur externe. Il est possible de consommer des articles sur tous les types de projets, à l'exception des Projets de temps. 

La manière de commander les articles dépend de la provenance de la commande :

-   pour commander des articles sur le stock de la société, vous devez entrer la commande comme une demande d'articles. Si vous utilisez la page **Demandes d'articles**, vous devez configurer la demande afin de recevoir des articles en livraisons partielles. De ce fait, vous pouvez reporter la consommation d'une quantité d'articles jusqu'au moment où ils sont requis.
-   Pour commander des articles à un fournisseur externe, vous devez créer une commande fournisseur dans la page **Commande fournisseur**.

> [!NOTE] 
> Le bon de livraison d'une commande client associée à un projet ne peut pas être annulée si les articles ont déjà été marqués pour l'emballage. 

Le tableau suivant répertorie les méthodes de tri des articles et décrit le mode de consommation de ceux-ci.

| Méthode            | Objectif                                                                                                                                                        | Transactions de consommation des articles                                                                                                                  |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Commande client       | Entrez une transaction directement dans un projet en temps et en matières.                                                                                                   | Les transactions d'article sont consommées lors de la validation de la facture client.                                                                               |
| Journal de stock | Entrez et mettez à jour rapidement les enregistrements d'articles. Par exemple, si vous voulez entrer une demande d'articles sur la base d'une liste imprimée, vous pouvez appliquer le journal de stock. | Les transactions d'article sont consommées lors de la validation du journal.                                                                                        |
| Demande d'articles  | Entrez les articles à ne pas consommer immédiatement. Cette méthode vous permet de suivre le nombre d'articles consommés à l'intérieur d'un enregistrement de demande d'articles.    | Les transactions d'article sont consommées lors de la mise à jour du bon de livraison. En d'autres termes, cela signifie que la demande d'articles est créée lors de la validation du bon de livraison. |
| Commandes fournisseur   | Entrez les transactions dans l'un des trois emplacements, en fonction de la méthode d'achat.                                                                              | Les transactions d'article sont consommées à la mise à jour de bon de livraison ou lors de la facturation du client et/ou du fournisseur.                                      |

### <a name="process-project-invoices"></a>Traitement des factures de projet

Le type de projet détermine la procédure de facturation applicable. Seuls les deux types de projet externes (en régie et à prix fixe), sont facturables. Les projets en régie et les projets à prix fixe sont toujours liés à un contrat de projet. 

Avant de créer une facture client pour un projet, vous pouvez créer une facture préliminaire, ou proposition de facture. Dans une proposition de facture, vous pouvez sélectionner des transactions de projet à inclure dans une facture de projet. Vous pouvez ensuite réviser les détails de la facture avant de valider la facture de projet et l'envoyer au client ou à une autre source de financement. 


Pour plus d'informations sur le traitement des factures de projet, voir [Facturation du projet](../accounts-payable/project-invoicing.md).


### <a name="calculate-the-cost-to-complete-a-project"></a>Calcul du coût à terminer d'un projet

Lorsque vous créez une estimation, vous pouvez choisir la méthode utilisée pour calculer le coût de réalisation du projet. Vous sélectionnez une méthode dans le champ **Méthode de coût à terminer** de la page **Créer une estimation**. La méthode que vous choisissez est appliquée séparément à chaque ligne de coût dans l'estimation de coût. Quand une ligne a le statut **Créé**, vous pouvez modifier la méthode appliquée à celle-ci dans la page **Estimation des coûts**. 

Le tableau suivant décrit les méthodes de calcul du coût à terminer du projet.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Méthode</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Coût total – Réel</td>
<td>Les coûts estimés doivent être entrés manuellement. Une fois que la colonne <strong>Coût total</strong> ou <strong>Quantité totale</strong> de la page <strong>Estimation des coûts</strong> est remplie, les coûts réels sont soustraits des totaux entrés par l'utilisateur. Le résultat est le coût pour terminer le projet. En règle générale, le suivi de la progression des coûts n'est pas basé, par exemple, sur le nombre de séjours à l'hôtel et de repas enregistré dans chaque période. Au lieu de cela, le suivi est généralement basé sur une comparaison par rapport au montant total d'heures estimées. Cette approche ne nécessite pas de modèle de prévision, et le coût total ou la quantité totale peut être modifiée manuellement. Lorsqu'une valeur est entrée dans la colonne <strong>Coût total</strong> ou <strong>Quantité totale</strong>, Finance and Operations compare cette valeur aux transactions réelles validées dans la période, puis diminue la valeur dans la colonne <strong>Quantité à atteindre</strong> ou <strong>Coût à terminer</strong>.</td>
</tr>
<tr class="even">
<td>Budget total – Réel</td>
<td>Les coûts réels sont comparés au modèle de prévision que vous sélectionnez pour déterminer le coût. Cette méthode utilise un modèle de budget total contenant les transactions de prévision. Pour obtenir un aperçu plus exact du projet, vous pouvez ajuster le modèle de budget pendant que le projet est en cours. Si vous devez ajuster la prévision, suivez ce processus général :
<ol>
<li>Copiez les transactions de prévision dans un autre modèle de prévision.</li>
<li>Comparez les transactions de prévision avec les transactions réelles.</li>
<li>Mettez à jour, soustrayez ou additionnez les estimations pour la période suivante.</li>
</ol>
Finance and Operations ne diminue pas automatiquement les estimations prévues. Par conséquent, il est judicieux de tenir à jour un modèle de prévision d'origine pour le projet à prix fixe afin d'établir une ligne de base pour comparaison une fois le projet terminé. 
<br></br> <strong>REMARQUE :</strong> lorsque vous sélectionnez cette méthode, utilisez au moins deux modèles de prévision. Un modèle doit contenir la prévision d'origine. Pour l'autre modèle, vous devez copier les transactions de prévision d'un autre modèle. Cette méthode est valide uniquement pour les projets à prix fixe ou d'investissement.</td>
</tr>
<tr class="odd">
<td>Budget restant</td>
<td>Cette méthode utilise un modèle de budget restant pour calculer le coût à terminer du projet. Lorsque vous utilisez cette méthode, les coûts réels et les montants prévus dans le modèle de budget restant sont additionnés entre eux. Le résultat est un coût total. Avant d'utiliser cette méthode, un modèle de budget restant doit être paramétré pour déduire les transactions en fonction des transactions réelles enregistrées dans le système. Dans la page <strong>Modèles de prévision</strong>, vérifiez que les champs sont marqués dans le groupe <strong>Réduction automatique des prévisions</strong>. En règle générale, un budget restant est copié à parti d'un budget d'origine. À mesure que les transactions sont entrées, les transactions du budget restant sont diminuées. Au fur et à mesure de la progression du projet, si vous déterminez le budget restant doit être ajusté, vous pouvez facturer des transactions de prévision sur le budget restant. <br></br> <strong>REMARQUE :</strong> cette méthode peut être appliquée uniquement si un modèle de prévision est associé à l'estimation.</td>
</tr>
<tr class="even">
<td>Comme estimation précédente</td>
<td>La même méthode d'estimation que celle utilisée dans la période précédente est appliquée. Cette méthode nécessite un modèle de prévision si la période précédente en requérait un.</td>
</tr>
<tr class="odd">
<td>Définir le coût à terminer sur zéro</td>
<td>En général, cette méthode est utilisée avant l'élimination du projet d'estimation. Cette méthode correspond à toutes les estimations totales avec les transactions réelles qui ont été validées et efface la colonne <strong>Coût à terminer</strong>. Le pourcentage de réalisation qui en résulte est toujours 100 %. Le champ <strong>Prévision</strong> est désactivée pour chaque ligne de coût que vous créez, et le total de l'estimation est copié à partir de l'estimation de coût précédent. La consommation réelle de la période d'estimation est déduite du coût de réalisation du projet. Cette méthode ne requiert aucun modèle de prévision.</td>
</tr>
<tr class="even">
<td>À partir du modèle de coût</td>
<td>La méthode de coût à terminer paramétrée dans le modèle de coût associé au projet d'estimation sélectionné est appliquée.</td>
</tr>
</tbody>
</table>

## <a name="analyze-the-project"></a>Analyser le projet
À son niveau le plus élémentaire, un projet permet de regrouper des transactions d'enregistrement des coûts, puis de les valider dans la comptabilité. 

Généralement, ces transactions sont le résultat de documents commerciaux, tels que des feuilles de temps, des états de dépenses, des factures fournisseur ou des mouvements de stock. Le cycle de vie d'un projet débute généralement par des estimations, des prévisions, et des budgets qui aident à organiser et anticiper le travail et l'impact financier du projet. À mesure que vous analysez un projet, vous pouvez évaluer non seulement les transactions qui ont eu lieu au cours du projet, mais également l'exactitude de vos évaluations et prévisions, les taux d'utilisation des membres de l'équipe projet, et le succès global du projet.

### <a name="analyze-cash-flow"></a>Analyse des flux de trésorerie

Le contrôle des flux de trésorerie permet d'examiner les flux de disponibilités prévus et réels d'un projet. Vous pouvez examiner les flux de disponibilités lorsque le projet est en cours ou lorsqu'il est terminé. 

La surveillance des flux de trésorerie vous permet d'évaluer un projet unique, d'utiliser les états pour afficher plusieurs projets et de transférer les flux de trésorerie du projet vers les estimations de flux de trésorerie dans la comptabilité.

#### <a name="cash-inflow-forecasting"></a>Prévision des encaissements

Selon votre paramétrage, vous pouvez prévoir les apports de disponibilités pour un projet sélectionné. Par exemple, si la date d'un projet est le 5 mars 2012 et que vous le facturez le 31 mars 2012, vous pouvez prévoir la date d'échéance et la date prévue de paiement des ventes.

-   **Date de projet :** 5 mars 2012.
-   **Date de la facture :** 31 mars 2012. Cette date est déterminée en fonction de la fréquence de facture. Dans cet exemple, vous définissez la fréquence de facturation au mois actuel. Par conséquent, cela signifie que toutes les transactions validées en mars sont facturées le dernier jour du mois.
-   **Date d'échéance :** 14 avril 2012. Cette date est déterminée d'après les conditions de paiement définies pour le projet. Pour cet exemple, vous avez sélectionné des conditions de paiement de 14 jours. Par conséquent, 14 jours sont ajoutés à la date de facture pour qu'elle parvienne à la date d'échéance du 14 avril 2012.
-   **Date prévue de paiement des ventes :** 27 avril 2012. Cette date est calculée en ajoutant le nombre de jours dans le champ **Jours intermédiaires généraux** dans la page **Paramètres de gestion de projets et comptabilité** au nombre de jours dans le champ **Jours de marge individuelle** de la page **Contrats de projet**, et en additionnant le total au nombre de jours dans le champ **Date d'échéance**. Pour cet exemple, vous avez entré **3** dans le champ **Jours intermédiaires généraux** et **10** dans le champ **Jours de marge individuelle**. Par conséquent, 13 jours sont ajoutés à la date d'échéance pour qu'elle parvienne à la date prévue de paiement des ventes du 27 avril 2012.

Les jours intermédiaires généraux peuvent remplacer les jours intermédiaires individuels ou être ajoutés à ces derniers :

-   pour utiliser les jours intermédiaires généraux en remplacement des jours de marge individuelle, entrez le nombre moyen de jours entre la date d'échéance et la date réelle de paiement des clients.
-   Pour ajouter les jours intermédiaires généraux aux jours intermédiaires individuels, entrez dans le champ **Jours intermédiaires généraux** votre estimation du nombre de jours entre le moment où le paiement est envoyé par le client et celui où il est reçu par votre organisation.

Configurez les jours intermédiaires individuels dans le contrat de projet. Les jours sont calculés sur la base de la date d'échéance de la facture client et de l'expérience de votre organisation avec le modèle de paiement du client.

#### <a name="actual-cash-inflow"></a>Encaissement réel

Les encaissements réels sont semblables à la prévision, mais vous pouvez commencer vos calculs à partir de la première date de la facture. Voici un exemple :

-   **Date de la facture :** 2 mars 2012.
-   **Date d'échéance :** 16 mars 2012. Les conditions de paiement sont définies sur 14 jours.
-   **Date prévue de paiement des ventes :** 29 mars 2012. Le calcul inclut trois jours intermédiaires généraux et 10 jours intermédiaires individuels.

#### <a name="cost-forecasting"></a>Prévision des coûts

En fonction du nombre de jours définis, la date de paiement des coûts peut différer de la date du projet. Dans ce cas, la date de paiement des coûts est calculée en ajoutant le nombre de jours à partir de la date du projet au nombre de jours dans les conditions de paiement. 

Par exemple, la date du projet de la transaction est le 5 mars 2012 et vous avez défini les conditions de paiement suivantes :

-   **Heures :** Mois en cours (**M**)
-   **Dépenses :** 14 jours (**D14**)
-   **Articles :** 30 jours (**D30**)

Selon ces paramètres, voici la date de paiement des coûts pour chaque type de transaction :

-   **Heures :** 31 mars 2012, qui est le dernier jour du mois sélectionné.
-   **Dépenses :** 19 mars 2012, qui est 14 jours après la date de la transaction.
-   **Articles :** 4 avril 2012, qui est 30 jours après la date de la transaction.

> [!NOTE] 
> La date d'échéance pour la commande fournisseur est basée sur la transaction fournisseur effectuée lorsque la commande fournisseur du projet est créée. La date d'échéance n'est déterminée par aucun paramètre par défaut. 

La date de paiement des coûts n'est pas calculée en fonction des jours intermédiaires. Une fois qu'un projet est terminé, quand l'évaluation des coûts et la facturation sont terminées, le coût et les ventes sont validés sur les comptes de résultat. 

Lorsque toutes les ventes et factures fournisseur sont terminées, vous pouvez afficher la relation entre les champs dans la page **Flux de trésorerie** la page et les champs de la page **Statistiques du projet**.

:::row::: :::column:::
        #### Cash flow page
        - Cash inflows 
        - Cash outflows
        - Net cash flows
    :::column-end:::
    :::column:::
        #### Project statements page
        - Revenue
        - Total cost
        - Gross margin
    :::column-end:::
:::row-end:::

### <a name="review-costs"></a>Examen des coûts

Vous pouvez utiliser la page **Contrôle des coûts** pour surveiller les coûts que votre organisation engage lors d'un projet. En comparant les coûts budgétés d'origine pour le projet avec les coûts réels actuels et les coûts engagés, vous pouvez déterminer si le projet est suivi, a dépassé le budget, ou est en dessous du budget. 

> [!NOTE] 
> Lorsque vous utilisez la page **Contrôle des coûts** pour afficher le statut actuel des coûts du projet, utilisez les modèles de prévision sélectionnés pour les budgets d'origine et restant. Si vous sélectionnez d'autres modèles de prévision pendant le calcul des coûts, les résultats du calcul ne seront pas précis.

#### <a name="viewing-the-remaining-budgeted-amounts"></a>Affichage des montants budgétés restants

Si **Budget restant** est sélectionné comme méthode de contrôle des coûts dans la page **Paramètres de gestion de projets et comptabilité**, la page **Contrôle des coûts** calcule les coûts qui n'ont pas été validés comme réels ou marqués comme engagés. En particulier, les montants indiqués dans l'onglet **Général** du volet inférieur de la page **Contrôle des coûts** sont calculés comme suit :

-   **Coût réel** – Montant total dépensé pour le projet pour la ligne de coût sélectionnée. Le montant du coût réel est calculé dans la page **Mises à jour comptables**.
-   **Coût engagé** – Montant supplémentaire de dépenses que l'entité juridique s'est engagée à payer. Les montants spécifiques des coûts engagés sont calculés dans la page **Coûts engagés**.
-   **Budget restant** – Montant budgété d'origine qui est toujours disponible pour la ligne de coût sélectionnée. Le montant budgété restant est calculé dans la page **Aperçu comptable**.
-   **Coût total**– Somme du coût réel, du coût engagé et du budget restant.

Dans la page **Contrôle des coûts**, sous l'onglet **Écart**, vous pouvez afficher la comparaison du coût total prévu avec le budget d'origine. Cette comparaison indique les différences entre ces montants. Par conséquent, vous pouvez voir l'origine des disparités entre les données. Les montants des écarts sont calculés comme suit :

-   **Budget d'origine** – Montant initialement budgété pour la ligne de coût sélectionnée. Le montant budgété d'origine est calculé dans la page **Aperçu comptable**.
-   **Coût total** – Somme du coût réel, du coût engagé et du budget restant, telle qu'indiquée sous l'onglet **Général**.
-   **Écart** – Différence entre le coût total et le budget d'origine.
-   **Écart basé sur la quantité** – Différence totale de montant entre la prévision d'origine et la prévision totale. Cette différence peut être exprimée mathématiquement comme suit : (Quantité totale prévue) × (Prix moyen d'origine – Prix moyen total). Ce calcul s'applique uniquement aux heures de projet.
-   **Écart basé sur le prix** – Différence totale de montant entre la prévision d'origine et la prévision totale. Cette différence peut être exprimée mathématiquement comme suit : (Prix d'origine prévu) × (Quantité d'origine prévue – Quantité prévue totale). Ce calcul s'applique uniquement aux heures de projet.

#### <a name="viewing-the-total-budgeted-amounts"></a>Affichage des montants budgétés totaux

Si **Budget total** est sélectionné comme méthode de contrôle des coûts dans la page **Paramètres de gestion de projets et comptabilité**, la page **Contrôle des coûts** calcule les coûts réels et les coûts totaux du projet pour vous aider à détecter toute différence entre les deux. En particulier, dans la page **Contrôle des coûts**, les montants indiqués dans le volet inférieur de l'onglet **Général** sont calculés comme suit :

-   **Coût budgété total** – Montant budgété total pour la ligne de coût sélectionnée.
-   **Coût réel** – Montant total des coûts qui ont été engagés à ce jour sur le projet pour les lignes de coût sélectionnées.
-   **Coût engagé** – Montant total engagé pour la ligne de coût sélectionnée.
-   **Écart** – Différence entre la somme des coûts réels et engagés et le coût total. Il indique si des coûts supplémentaires doivent être spécifiés pour le budget total.

Dans la page **Contrôle des coûts**, sous l'onglet **Écart**, vous pouvez visualiser la différence entre le budget total et le budget d'origine en regardant les champs suivants :

-   **Budget d'origine** – Montant initialement budgété pour la ligne de coût sélectionnée. Le budget d'origine est calculé dans la page **Aperçu comptable**.
-   **Coût budgété total** – Coût total initialement budgété pour la ligne de coût. Le coût budgété total est calculé dans la page **Aperçu comptable**.
-   **Écart** – L'écart pour la ligne de coût. Ce montant est calculé en soustrayant le coût total du budget d'origine.
-   **Écart basé sur la quantité** – Différence totale de montant entre le budget d'origine et le budget total. Ce montant est calculé en soustrayant les heures budgétaires totales des heures budgétaires d'origine, puis en multipliant la différence par le prix de revient budgété d'origine. Cette différence peut être exprimée mathématiquement comme suit : (Prix de revient budgété d'origine) × (Heures budgétaires d'origine – Heures budgétaires totales). Ce calcul s'applique uniquement aux heures de projet.
-   **Écart basé sur le prix** – Ce montant est calculé en soustrayant les heures budgétaires totales des heures budgétaires d'origine, puis en multipliant la différence par le nombre total d'heures écoulées. Cette différence peut être exprimée mathématiquement comme suit : (Heures consommées totales) × (Heures budgétaires d'origine – Heures budgétaires totales). Ce calcul s'applique uniquement aux heures de projet.

### <a name="analyze-utilization"></a>Analyse de l'utilisation

Le taux d'utilisation est le pourcentage de temps qu'un collaborateur engage dans un travail facturable ou un travail de production pendant une période de travail spécifique. Les heures facturables sont les heures du travailleur qui peuvent être facturées à un client particulier. 

Pour calculer le taux d'utilisation d'un collaborateur, le système divise le nombre d'heures facturables par le nombre d'heures de travail pendant une période spécifique. Par exemple, si un collaborateur a 30 heures facturables dans une période et que le nombre d'heures de travail de cette même période est de 40, le taux d'utilisation du collaborateur est de 75 %. 

Lorsque vous calculez le taux d'utilisation d'un collaborateur, vous pouvez calculer le taux facturable ou le taux de rendement :

-   **Taux facturable** – Différence entre les heures facturables et non facturables ou les heures normales.
-   **Taux de rendement** – Différence entre les heures productives et non productives ou les heures normales. Les heures productives sont les heures que le collaborateur passe à travailler sur un projet spécifique. Les heures productives sont généralement facturées aux clients, hormis dans le cas des projets internes. Les heures non productives ne sont jamais facturées à un client.

Vous calculez les taux d'utilisation dans la page **Utilisation des heures**. Les calculs sont basés sur des préférences par défaut. Ces préférences spécifient également comment les heures sont calculées par l'affectation de **Utilisation** ou de **Charge** à chaque type de projet. Cela s'applique aux calculs du taux facturable et du taux de rendement.

-   **Utilisation** – Les heures déclarées pour ce type de projet sélectionné sont toujours considérées comme une utilisation facturable ou de rendement.
-   **Charge** – Les heures déclarées pour ce type de projet sélectionné sont toujours considérées comme une utilisation non-facturable ou de non-rendement.
-   **Conformément à la Propriété de ligne** – Les propriétés de ligne d'une transaction horaire particulière déterminent si les heures sont considérées comme une utilisation facturable ou de rendement.
-   **Non inclus** – Les heures ne sont pas factorisées dans le calcul de l'utilisation facturable ou de rendement.

Dans la page **Utilisation des heures**, à côté du pourcentage global de taux d'utilisation pour un collaborateur ou un projet, vous pouvez afficher le nombre d'heures qui ont été utilisées dans les calculs du taux d'utilisation de chacun des types d'heure suivants :

-   **Heures non incluses** – Ces heures ne sont pas incluses dans le taux d'utilisation des heures.
-   **Heures incluses** – Ces heures sont calculées par l'addition des heures d'utilisation et des heures de charge. Ces heures sont incluses dans le taux d'utilisation.
-   **Heures non facturables** – Si vous calculez un taux facturable, ces heures sont les mêmes que les heures non imputables. Si vous calculez un taux de rendement, ces heures sont les mêmes que les heures non productives.
-   **Heures d'utilisation** – Si vous calculez un taux facturable, ces heures sont les mêmes que les heures imputables. Si vous calculez un taux de rendement, ces heures sont les mêmes que les heures productives.

Lorsque vous calculez le taux d'utilisation d'un travailleur, vous pouvez utiliser les heures normales ou incluses. Si vous utilisez les heures incluses, vous devez vérifier que les collaborateurs enregistrent tout leur temps de travail pour les périodes des feuilles de temps, car le calcul est exprimé en pourcentage des heures entrées. Lorsque vous calculez le taux d'utilisation des heures pour un projet, un contrat de projet, un enregistrement client, ou une catégorie, vous devez utiliser les heures incluses pour votre calcul.

### <a name="review-project-statements"></a>Examiner les statistiques du projet

Vous pouvez créer des statistiques de projet pour afficher un instantané rapide de la progression d'un projet. Lorsque vous exécutez les statistiques d'un projet, vous pouvez préciser les critères utilisés pour calculer les statistiques de projet en faisant des sélections sous l'onglet **Général** de la page **Statistiques de projet**. Vous pouvez choisir d'inclure ou d'exclure les informations suivantes :

-   Types de projets
-   Types de transactions
-   Date de projet/Date de comptabilité
-   Données

Une fois que les statistiques sont calculées, vous pouvez afficher les informations suivantes dans les différents onglets de la page **Statistiques de projet** :

-   **Général** – Informations générales sur la structure de résultat de base du projet.
-   **Résultat** – Informations sur le produit à recevoir.
-   **Travaux en cours** – Informations sur les soldes de compte de travaux en cours.
-   **Consommation** – Informations sur la consommation d'heures, d'articles, de dépenses, et de transactions de paie.
-   **Facture** – Informations sur les factures et la facturation en compte.
-   **Taux horaire** – Taux horaires des heures validées sur les comptes de produit et de coût.

