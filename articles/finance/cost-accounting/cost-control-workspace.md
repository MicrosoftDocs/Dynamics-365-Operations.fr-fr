---
title: Espace de travail de contrôle des coûts
description: Cette rubrique fournit des informations sur l'espace de travail Contrôle des coûts. Cet espace de travail est un point central où les responsables chargés de contrôler un objet de coût ou un ensemble d'objets de coûts dans une dimension ou dans plusieurs dimensions peuvent accéder aux états.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfiguration, CAMCostControlWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 82eb312d534a43d48be2dabbf9f9ae3e32545bac
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187979"
---
# <a name="cost-control-overview"></a>Vue d'ensemble du Contrôle des coûts 

[!include [banner](../includes/banner.md)]

L'espace de travail **Contrôle des coûts** est un point central où les responsables chargés de contrôler un objet de coût ou un ensemble d'objets de coûts dans une dimension ou dans plusieurs dimensions peuvent accéder aux états. Les états dans l'espace de travail sont entièrement gérés par des comptables, de sorte que la mise en page et les données utilisées pour la génération des états sont cohérentes dans l'ensemble de l'organisation.

## <a name="cost-control-workspace-configuration"></a>Configuration de l'espace de travail de contrôle des coûts

Les comptables peuvent définir autant de configurations d'état dont ils ont besoin pour la composition ou la présentation des données souhaitée. Une configuration d'état est composé de six sections, qui contribue à la sélection de la composition ou la mise en page des données ciblée.

Pour configurer un espace de travail Contrôle des coûts, cliquez sur **Contrôle de gestion** \> **Paramétrage** \> **Configuration de l'espace de travail de contrôle des coûts**.

### <a name="general"></a>Général

Dans l'organisateur **Général**, vous pouvez créer une présentation d'état. Le nom de l'état est un identificateur unique que les utilisateurs pourront reconnaître dans l'espace de travail **Contrôle des coûts**. Vous pouvez également indiquer si l'état doit être partagé ou conservé en interne pour les comptables.

| Champ       | Description |
|-------------|-------------|
| Nom        | Permet d'entrer un nom unique pour la présentation. |
| Description | Saisissez une description détaillée. |
| Publié   | Si vous définissez ce champ sur **Oui**, un utilisateur doté d'un des rôles suivants peut consulter l'état dans l'espace de travail **Contrôle des coûts** :<ul><li>Gestionnaire de contrôle de gestion</li><li>Contrôleur de gestion</li><li>Commis contrôleur de gestion</li><li>Contrôleur d'objet de coût</li></ul>Si vous définissez ce champ sur **Non**, seuls les utilisateurs dotés d'un des rôles suivants peuvent consulter l'état dans l'espace de travail **Contrôle des coûts** :<ul><li>Gestionnaire de contrôle de gestion</li><li>Contrôleur de gestion</li><li>Commis contrôleur de gestion</li></ul> |

### <a name="data-filtering"></a>Filtrage des données

Dans l'organisateur **Filtrage des données**, définissez la base des données pour l'état. Les utilisateurs de cet état verront des valeurs dans l'état après le traitement des données source.

| Champ                                                             | Description |
|-------------------------------------------------------------------|-------------|
| Comptabilité de contrôle de gestion                                            | La **comptabilité de contrôle de gestion** sur laquelle l'état est basé. La valeur est extraite du champ **Unité de contrôle des coûts**. |
| Unité de contrôle des coûts                                                 | La valeur que vous sélectionnez détermine les objets de comptabilité et le coût de contrôle de gestion sur lesquels cet état sera basé. |
| Hiérarchie de dimension statistique, Hiérarchie des dimensions d'élément de coût | Un enregistrement de configuration de l'espace de travail **Contrôle des coûts** peut générer des états de valeurs non-monétaires ou monétaires, mais pas dans la même mise en page. Sélectionnez une valeur dans le champ **Hiérarchie de dimension d'élément de coût** pour déclarer des valeurs monétaires. Sélectionnez une valeur dans le champ **Hiérarchie de dimension statistique** pour déclarer des valeurs non-monétaires. L'enregistrement de la hiérarchie de dimension que vous sélectionnez détermine la structure des niveaux de génération et d'agrégation d'états.<blockquote>[!NOTE]<br>Pour afficher des valeurs non-monétaires et des valeurs monétaires côte à côte, vous pouvez exporter des données vers Microsoft Excel pour le pack de contenu Microsoft Power BI.</blockquote> |
| Hiérarchie des dimensions d'objet de coût                                   | Sélectionnez la hiérarchie des dimensions de la dimension d'objet de coût qui s'adapte à l'objet de la génération d'états que vous définissez. |
| Version originale du budget                                           | Sélectionnez l'ID de la version de budget agissant comme le budget d'origine dans le contexte de cet état. |
| Version révisée du budget                                            | Sélectionnez l'ID de la version de budget agissant comme le budget révisé dans le contexte de cet état. |

### <a name="assign-calculation-records"></a>Affecter les enregistrements de calcul

Le calcul des frais généraux effectue plusieurs étapes de calcul sur les données source, telles que la classification du comportement des coûts, la distribution des coûts et la répartition des coûts. Plusieurs calculs de frais généraux peuvent être effectués pour la même période fiscale, en cas de découverte de données source manquantes ou de mise à jour des règles. Chaque calcul des frais généraux est enregistré avec un identificateur unique. Le comptable peut sélectionner un ID de calcul des frais généraux spécifique. Les utilisateurs de l'état, tels que les responsables, voient les résultats du calcul des frais généraux dans l'espace de travail **Contrôle des coûts**.

| Champ                  | Description |
|------------------------|-------------|
| Période de calendrier fiscal | Permet de sélectionner la période du calendrier fiscal pour lui affecter un ID de calcul des frais généraux.<blockquote>[!NOTE]<br>Les périodes fiscales qui figurent dans le champ proviennent du calendrier fiscal associé à la comptabilité de contrôle de gestion.</blockquote> |
| Version réelle         | Sélectionnez l'ID de calcul des frais généraux approprié. |
| Version des budgets         | Sélectionnez l'ID de calcul des frais généraux approprié. |
| Version du budget révisée | Sélectionnez l'ID de calcul des frais généraux approprié. |

### <a name="fiscal-periods-per-column"></a>Périodes fiscales par colonne

Dans l'organisateur **Périodes fiscales par colonne**, le comptable détermine la période fiscale devant être affichée dans la présentation d'état.

Les valeurs des colonnes sélectionnées sont multipliées par les valeurs sélectionnées sous l'organisateur **Périodes fiscales par colonne**.

| Champ                | Description |
|----------------------|-------------|
| Période en cours       | Le solde de la période fiscale actuelle s'affiche.<blockquote>[!NOTE]<br>Par défaut, la période actuelle est déterminée par la date de la session. Dans l'espace de travail **Contrôle des coûts**, une période fiscale particulière peut être sélectionnée. La valeur sélectionnée représente la période actuelle.</blockquote> |
| Période précédente      | Le solde de la période fiscale précédente s'affiche. La formule utilisée est la suivante :<br>Période fiscale actuelle – 1<blockquote>[!NOTE]<br>Par défaut, la période précédente est dérivée de la date de la session. Dans l'espace de travail **Contrôle des coûts**, une période fiscale particulière peut être sélectionnée comme la période actuelle. La **Période précédente** est ensuite recalculée en conséquence.</blockquote> |
| Année en cours         | Les données pour l'année en cours s'affichent. La formule utilisée est la suivante :<br>YearToDate (Solde de l'exercice actuel)<blockquote>[!NOTE]<br>Par défaut, la période actuelle est déterminée par la date de la session. Dans l'espace de travail **Contrôle des coûts**, une période fiscale particulière peut être sélectionnée. La valeur sélectionnée représente la période actuelle, et la valeur **Année en cours** est mise à jour en conséquence.</blockquote> |
| Moyenne de l'année en cours | La moyenne pour l'année en cours s'affiche. La formule utilisée est la suivante :<br>(YearToDate [période fiscale actuelle]) ÷ (Count [Période fiscale actuelle])<p><strong>Exemple</strong></p><ul><li>**Membre de la dimension statistique** : Employés à temps plein</li><li>**Date actuelle** : 21-03-2017</li><li>**Période** : Période fiscale 1, Période fiscale 2, Période fiscale 3</li><li>**Ampleur** : 10, 10, 12</li></ul>Dans ce cas, **Moyenne de l'année en cours** = (10 + 10 + 12) ÷ 3 = 10,67<p>La valeur **Moyenne de l'année en cours** peut être calculée pour les membres de la dimension d'élément de coût et les membres de la dimension statistique.</p><blockquote>[!NOTE]<br>Par défaut, la période actuelle est déterminée par la date de la session. Dans l'espace de travail **Contrôle des coûts**, une période fiscale particulière peut être sélectionnée. La valeur sélectionnée représente la période actuelle, et les valeurs **Année en cours** et **Moyenne de l'année en cours** seront mises à jour en conséquence.</blockquote> |

### <a name="columns-to-display-for-costs"></a>Colonnes à afficher pour les coûts

Dans l'organisateur **Colonnes à afficher pour les coûts**, le comptable détermine quelles colonnes la présentation d'état doit contenir. Il existe trois catégories : Coût fixe, Coût variable et Coût non classifié.

| Champ                 | Description |
|-----------------------|-------------|
| Coût fixe            | Ce type de colonne indique le coût fixe en fonction de l'ID de calcul des frais généraux sélectionné.<blockquote>[!NOTE]<br>Ce type de colonne affiche un solde uniquement lorsqu'un ID de calcul des frais généraux est sélectionné pour la période fiscale.</blockquote> |
| Coût variable         | Ce type de colonne indique le coût variable en fonction de l'ID de calcul des frais généraux sélectionné.<blockquote>[!NOTE]<br>Ce type de colonne affiche un solde uniquement lorsqu'un ID de calcul des frais généraux est sélectionné pour la période fiscale.</blockquote> |
| Coût fixe + Coût variable | Ce type de colonne indique le coût fixe et le coût variable en fonction de l'ID de calcul des frais généraux sélectionné.<blockquote>[!NOTE]<br>Ce type de colonne affiche un solde uniquement lorsqu'un ID de calcul des frais généraux est sélectionné pour la période fiscale.</blockquote> |
| Coût total            | Ce type de colonne affiche le coût total (coût non classifié, coût fixe et coût variable).<blockquote>[!NOTE]<br>Le type de colonne affichera le solde à tout moment.</blockquote> |
| Coût non classifié     | Le type de colonne indique le coût non classifié.<blockquote>[!NOTE]<br>Cette colonne peut être utilisée pour contrôler si tous les coûts ont été correctement classifiés par le calcul des frais généraux, ou si les règles de comportement de coût doivent être ajustées.</blockquote> |

### <a name="columns-to-display-for-budgeted-costs"></a>Colonnes à afficher pour les coûts budgétés

Dans l'organisateur **Colonnes à afficher pour les coûts budgétés**, le comptable détermine quelles colonnes la présentation d'état doit contenir. Différentes sélections peuvent être effectuées pour les budgets d'origine et révisé.

> [!NOTE]
> Comme les champs suivants se comportent de la même manière pour le budget d'origine et le budget révisé, ils ne sont expliqués qu'une seule fois.

| Champ                     | Description |
|---------------------------|-------------|
| Budget                    | Les soldes budgétaires sont affichés par colonnes sélectionnées.<blockquote>[!NOTE]<br>Les soldes seront basés sur les versions de budget sélectionnées sous l'organisateur **Filtrage des données**.</blockquote> |
| Écart de budget           | Calculez et affichez la différence entre le budget et le solde réel. La formule utilisée est la suivante :<br>Solde budgétaire – solde réel |
| Écart de budget en %      | Calculez et affichez la différence en pourcentage entre le budget et le solde réel. La formule utilisée est la suivante :<br>(Solde budgétaire – solde réel) ÷ Solde budgétaire |
| Seuil de période d'écart | Définissez un seuil pour l'écart dans le montant en devises pour la période actuelle. Si le seuil est dépassé, la ligne est mise en surbrillance en rouge dans l'espace de travail **Contrôle des coûts**.<blockquote>[!NOTE]<br>Ce champ s'applique uniquement aux éléments de coût qui représentent des dépenses.</blockquote> |
| Seuil d'année d'écart   | Définissez un seuil pour l'écart dans le montant en devises pour l'année. Si le seuil est dépassé, la ligne est mise en surbrillance en rouge dans l'espace de travail **Contrôle des coûts**. |
| % seuil d'écart      | Définissez un seuil pour l'écart en pourcentage. Si le seuil est dépassé, la ligne est mise en surbrillance en rouge dans l'espace de travail **Contrôle des coûts**.<blockquote>[!NOTE]<br>Le même seuil de pourcentage s'applique à la période et l'année en cours.</blockquote> |

## <a name="cost-control-workspace"></a>Espace de travail de contrôle des coûts

L'espace de travail **Contrôle des coûts** est conçue comme un état Web. Par conséquent, tous les responsables chargés d'un objet de coût peuvent bénéficier de l'accès comme décrit dans [Définir les droits d'accès des contrôleurs d'objet de coût](access-rights-cost-object-controller.md).

La liste des états disponibles pour les utilisateurs, tels que les responsables, est contrôlée par le paramètre de l'option **Publié** sur la page **Configurations de l'espace de travail de contrôle des coûts**.

![État que les utilisateurs peuvent voir dans l'espace de travail Contrôle des coûts](./media/report-cost-control.png)

Un responsable peut sélectionner la période de calendrier fiscal à afficher. La date de la session permet de déterminer la période actuelle par défaut.

Les valeurs dans la période de calendrier fiscal sont déterminées par le nom de l'état et le calendrier fiscal sélectionné pour la comptabilité de contrôle de gestion associée au nom d'état dans la page **Configurations de l'espace de travail de contrôle des coûts**.

Dans la hiérarchie des dimensions d'objet de coût, les utilisateurs peuvent sélectionner le niveau d'agrégation dans lequel les soldes doivent être affichés. En activant la sécurité de niveau d'accès, vous devez vérifier les autorisations, afin que les utilisateurs puissent uniquement sélectionner les niveaux de la hiérarchie auxquels ils ont accès. Par conséquent, ils peuvent uniquement consulter les soldes agrégés auxquels ils ont accès.

### <a name="add-or-remove-columns"></a>Ajouter ou supprimer des colonnes

Les utilisateurs peuvent personnaliser les colonnes dans un état pour se conformer à leurs conditions.

### <a name="view-details"></a>Afficher les détails

Les utilisateurs peuvent zoomer sur les détails relatifs aux soldes affichés dans l'espace de travail. Si les utilisateurs sélectionnent un nœud de hiérarchie de dimension d'élément de coût, puis cliquent sur **Afficher les détails**, la boîte de dialogue **Détails de l'élément de coût** affiche les informations détaillées relatives au nœud.

Une grille montre chaque élément de coût associé au nœud de hiérarchie de dimension d'élément de coût et ses valeurs. Les colonnes affichées dans la grille correspondent aux paramètres de l'espace de travail.

Deux graphiques affichent une synthèse du comparatif entre le budget et l'écart du budget par période.

![Graphiques qui affichent une synthèse du comparatif entre le budget et l'écart du budget par période](./media/cost-element-details-operations.png)

Les utilisateurs peuvent cliquer sur **Écritures de coût** pour explorer les détails d'écritures au besoin.

![Écritures de coût](./media/cost-entries.png)

Par exemple, le loyer est une dépense qui est répartie entre les centres de coût. Un utilisateur qui veut comprendre le coût du loyer que son centre de coûts doit supporter peut voir de manière détaillée comment le loyer a été calculé.

Si les utilisateurs cliquent sur **Base de répartition** sur la page **Écritures de coût**, une boîte de dialogue apparaît. Les utilisateurs peuvent ensuite affecter la base de répartition à la règle et afficher les mesures statistiques correspondantes qui sont enregistrées pour la période.

Dans l'exemple suivant, la base de répartition est du type **Base de répartition de la formule**, et la formule s'affiche. Les facteurs qui définissent la formule sont répertoriés. En outre, une grille affiche le calcul qui est effectué par objet de coût.

![Calculs par objet de coût](./media/cost-entries-allocation-base.png)

Ressources supplémentaires 

[Définir les droits d'accès des contrôleurs d'objet de coût](access-rights-cost-object-controller.md)


