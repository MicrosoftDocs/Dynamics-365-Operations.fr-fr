---
title: "Prévision des postes"
description: "Les dépenses liées aux collaborateurs représentent souvent une grande proportion des coûts d'une organisation. La prévision de poste permet de planifier ces dépenses et de les inclure dans la planification des budgets."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmPositionForecast
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 64413
ms.assetid: 35e791d2-1905-4808-a579-7f181ddddd91
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: a44b3d2ee6e47e71103c7be04b731d4faa79c448
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="position-forecasting"></a>Prévision des postes

[!include[banner](../includes/banner.md)]



Les dépenses liées aux collaborateurs représentent souvent une grande proportion des coûts d'une organisation. La prévision de poste permet de planifier ces dépenses et de les inclure dans la planification des budgets.

## <a name="position-forecasting-in-budget-planning"></a>Prévision de poste dans la planification budgétaire

[![Haut du graphique](./media/graphic-top.png)](./media/graphic-top.png) 

La prévision de poste utilise trois composants principaux pour fournir des montants budgétés précis pour les dépenses de poste. Ces montants peuvent ensuite être introduits dans un plan budgétaire pour les calculs de budget. 

Le composant principal est **poste de prévision**, qui représente les données de coût associées à un seul poste. Vous pouvez créer plusieurs versions d'un poste de prévision en affectant un scénario de plan budgétaire différent à chaque version. Plusieurs versions permettent une approche itérative de la budgétisation et permettent de comparer des scénarios hypothétiques. Chaque poste de prévision a un poste correspondant dans les Ressources humaines.

Un **élément de coût budgétaire** est un composant de paramétrage qui représente un coût spécifique associé à un poste, comme le salaire de base, l'assurance maladie payée par l'employeur, l'indemnité de téléphone portable, etc. Un élément de coût budgétaire inclut le compte principal utilisé pour le coût et les options pour le calcul. Chaque élément de coût budgétaire peut être affecté à plusieurs postes de prévision. 

Un **groupe de rémunération** est un composant facultatif de paramétrage utilisé pour appliquer un ensemble d'éléments de coût budgétaire et des calculs de rémunération à des postes ayant des caractéristiques de salaire similaires. Un groupe de rémunération peut inclure une grille de rémunération de taux de salaire. Lorsque le groupe est affecté à un poste de prévision, le niveau et un échelon dans la grille peuvent affecter les revenus du poste de prévision. L'ensemble des éléments de coût est automatiquement ajouté.

### <a name="position-forecasting-processes"></a>Processus de prévision de poste

[![graphic1b](./media/graphic1b.png)](./media/graphic1b.png) 

Dans un processus type de prévision de poste, vous commencez par créer les composants de paramétrage (éléments de coût budgétaire et groupes de rémunération). Les postes de prévision sont alors générés, en fonction des postes existants. Vous pouvez alors effectuer des ajustements. Par exemple, vous pouvez ajouter ou mettre fin à des postes, modifier des taux de salaire et les coûts d'avantages, et ajouter des augmentations de salaire. Vous pouvez créer plusieurs versions d'un poste de prévision pour faciliter les comparaisons entre différents scénarios de budgétisation. Ensuite, vous pouvez inclure les postes de prévision dans les plans budgétaires et importer les coûts afférents aux postes de prévision en tant que lignes de plan budgétaire.

Vous pouvez créer des versions supplémentaires de poste de prévision lors de la révision des plans budgétaires. Ces nouvelles versions constituent une base pour les révisions.

## <a name="position-forecasting-setup"></a>Paramétrage de prévision de poste
[![graphic2](./media/graphic2-1024x327.png)](./media/graphic2.png)

### <a name="budget-cost-elements"></a>Éléments de coût budgétaire

Les éléments de coût budgétaire sont utilisés pour définir les détails du coût d'un poste de prévision. Ces détails incluent le type de coût, la manière dont le coût est calculé, et si le coût est affecté à plusieurs dates lorsque le poste de prévision est inclus dans un plan budgétaire. 

Des champs spécifiques définissent le comportement de l'élément de coût budgétaire. Chaque élément du coût budgétaire reçoit un type de coût budgétaire **Rémunération**, **Avantage**, **Taxes** ou **Autre**. Les types de coûts budgétaires sont principalement utilisés pour calculer les totaux. La valeur **Remplacement du poste de prévision** indique si les montants de l'élément peuvent être modifiés dans le poste de prévision. Le champ **Mode de répartition** est utilisé lorsqu'un poste de prévision est ajouté à un plan budgétaire. Vous pouvez fractionner le montant des coûts en lignes de plan budgétaire distinctes de différentes dates, sur une base mensuelle, trimestrielle, hebdomadaire ou bihebdomadaire. En sélectionnant une date de début, vous affectez le coût en tant que montant unique à la date de début définie sur le poste de prévision. 

Le calcul du montant de l'élément de coût budgétaire se sert des dates d'effet pour pouvoir utiliser le même élément de coût à différentes périodes. Un compte principal unique est affecté dans chaque période, avec un pourcentage ou un montant annuel qui indique le montant du coût. Un élément de coût budgétaire peut utiliser un pourcentage d'autres éléments de coût ou d'un montant annuel, mais pas les deux. Vous pouvez également spécifier une limite annuelle. 

Si l'élément de coût est basé sur un pourcentage, vous devez spécifier les éléments de coût budgétaire utilisés comme base pour le calcul.

**Exemple** 

L'organisation du Jodi fournit une indemnité de formation de 5 % du salaire de base de l'employé. Jodi souhaite créer un élément de coût budgétaire pour ce coût. Elle crée un nouvel élément de coût budgétaire et lui affecte le type de coût budgétaire **Avantage**.

Jodi ne souhaite pas que les responsables modifient le montant de l'avantage. Par conséquent, elle sélectionne **Ne pas autoriser les modifications de coût** dans le champ **Remplacement du poste de prévision**. L'organisation veut que ce coût soit réparti de manière égale sur chaque mois. Par conséquent, Jodi sélectionne **Trimestriel** dans le champ **Mode de répartition**. 

Ensuite, Jodi ajoute une ligne de calcul du coût, définit les dates et un compte principal, et saisit **5,00** comme pourcentage. Son organisation a un plafond de 5 000 euros par an pour cet avantage. Par conséquent, Jodi entre ce montant comme limite annuelle. 

Enfin, Jodi ajoute tous les éléments de coût de bénéfice utilisés pour le salaire de base comme base de calcul. Son élément de coût budgétaire est maintenant prêt à être utilisé.

### <a name="compensation-groups"></a>Groupes de rémunération

Les groupes de rémunération permettent de regrouper les postes de prévision ayant des attributs de rémunération similaires. Ils peuvent également être utilisés pour définir les bénéfices et les augmentations annuelles d'un poste de prévision, et pour affecter un ensemble d'éléments de coût budgétaires communs. 

Une fonction de base des groupes de rémunération est d'affecter un ensemble d'éléments de coût budgétaires à un poste de prévision. Par conséquent, les groupes de rémunération peuvent être utilisés pour ajouter des coûts communs, tels que des plans d'avantages et des taxes. Un responsable qui crée un poste de prévision n'a pas besoin de connaître tous les éléments de coût qui doivent être ajoutés. Au lieu de cela, les éléments de coût peuvent être ajoutés lorsque le groupe de rémunération est sélectionné. Les éléments sont ajoutés au paramétrage du groupe de rémunération sous l'onglet **Éléments de coût budgétaire**. 

Les groupes de rémunération peuvent également déterminer les taux de rémunération d'un poste de prévision. Vous paramétrez un groupe pour utiliser une base horaire ou une base de salaire annuel pour calculer les revenus de poste de prévision. Sous l'onglet **Tables de taux de rémunération**, une grille de rémunération des taux de salaire détermine les rémunérations ajoutées à un poste de prévision, en fonction du niveau et de l'échelon attribués. Ces grilles peuvent être basées sur les grilles de rémunération existantes des Ressources humaines. Sinon, vous pouvez créer de nouvelles grilles de rémunération pour la planification budgétaire. 

Les dates d'effet et d'expiration dans les tables de taux de rémunération permettent de modifier les taux de salaire à n'importe quelle date. Cette fonctionnalité est utile lorsqu'une unité de négociation a négocié une augmentation générale au milieu d'un cycle budgétaire. Dans ce cas, vous remplacez la date d'expiration de la table existante par le jour précédant la date de la modification du taux et vous ajoutez une nouvelle table de taux qui commence à la nouvelle date. Lorsque vous créez une table de taux, si vous sélectionnez **Créer une nouvelle grille de rémunération à partir d'une grille existante**, vous pouvez sélectionner une table existante des Ressources humaines. Dans la table de taux créée, l'option **Modification en masse** permet d'appliquer un pourcentage ou un montant fixe d'augmentation ou de diminution à tous les taux de la grille. 

Les champs **Programme d'augmentation** et **Date d'augmentation** sous le groupe de rémunération sont utilisés lorsque vous devez créer des augmentations de salaire car les postes montent d'un échelon. Une augmentation de salaire annuelle est un scénario typique. Le programme d'augmentation détermine si la date d'anniversaire du poste ou une seule date commune est utilisée pour l'augmentation d'échelon. Le programme d'augmentation s'applique à tous les postes de prévision dans le groupe de rémunération. 

L'élément de coût de bénéfice sélectionné sous le groupe de rémunération est utilisé lorsque vous créez des bénéfices pour les postes de prévision dans le groupe, notamment leur salaire de base et toute augmentation d'échelon. Le champ **Régime de rémunération fixe** lie le groupe de rémunération à un régime de rémunération fixe dans les Ressources humaines. Ce lien peut affecter les informations de rémunération fixe d'un collaborateur à un poste de prévision, et donc peut rendre la planification budgétaire plus précise. N'oubliez pas que la structure de la grille de rémunération (niveaux et échelons) du groupe de rémunération doit correspondre à la structure du régime de rémunération fixe. Sinon, le système ne peut pas correctement lier le groupe de rémunération au régime de rémunération fixe.

## <a name="creating-forecast-positions"></a>Création de postes de prévision
[![graphic3](./media/graphic3-1024x327.png)](./media/graphic3.png)

### <a name="creating-forecast-positions-for-existing-positions"></a>Création de postes de prévision pour les postes existants

Pour une planification budgétaire plus exacte, vous pouvez créer des postes de prévision à l'aide des détails des postes de prévision dans Microsoft Dynamics 365 for Finance and Operations, que le poste soit actuellement rempli ou non. 

La fonction **Ajouter des postes existants** affiche tous les postes d'une organisation. En définissant la date **En date du**, vous pouvez modifier la liste des postes afin qu'elle contienne les postes qui ont existé à une date dans le passé ou, plus couramment, les postes futurs (par exemple, le début du cycle budgétaire suivant). Sélectionnez un processus de planification budgétaire et un scénario de plan budgétaire, sélectionnez des postes dans la liste, puis cliquez sur **OK** pour créer des postes de prévision pour les postes sélectionnés. Notez que vous ne pouvez créer qu'un seul poste de prévision pour chaque poste existant dans un processus et un scénario de planification budgétaire. Toutefois, vous pouvez créer des versions supplémentaires en affectant différents scénarios de plan budgétaire. 

Si des éléments de coût budgétaire ont été affectés au poste dans les Ressources humaines, ces éléments de coût budgétaire sont également affectés au poste de prévision et utilisent les montants par défaut. Le champ **Collaborateur affecté** dans le poste de prévision est défini sur le nom du collaborateur affecté au poste, si un collaborateur est affecté. Ce champ est un champ de texte simple. Aucun lien direct n'est créé. 

Si un élément de coût budgétaire est sélectionné, le montant annuel de rémunération fixe est affecté au poste de prévision à l'aide de l'élément de coût sélectionné, à condition que le collaborateur affecté ait un régime de rémunération fixe. Si le collaborateur n'a pas de régime de rémunération fixe, ou si aucun collaborateur n'est affecté, le montant par défaut est utilisé pour l'élément de coût budgétaire. 

Lorsque l'option **Affecter un groupe de rémunération** est définie sur **Oui**, si le collaborateur affecté au poste a un régime de rémunération fixe basé sur l'échelon qui est lié à un groupe de rémunération (comme décrit précédemment), le niveau et l'échelon du collaborateur sont affectés au poste de prévision, ainsi que le groupe de rémunération. L'élément de coût budgétaire des bénéfices du groupe de rémunération est ajouté au poste de prévision, et le taux de salaire au niveau et à l'échelon du groupe de rémunération sont utilisés. 

Le paramètre de l'option **Affecter un groupe de rémunération** prime sur le paramètre **Affectation d'un élément de coût budgétaire**. Il est possible d'utiliser jusqu'à deux paramètres en même temps. 

[![graphic4](./media/graphic4.png)](./media/graphic4.png) 

Une autre option consiste à affecter une date d'anniversaire. La date sélectionnée (date de début ajustée, date de début du collaborateur, date de début d'emploi, ou date d'ancienneté) du collaborateur affecté est alors définie comme la date d'anniversaire du poste de prévision, et est utilisée pour informations et lorsque des augmentations de salaire sont générées.

### <a name="creating-new-forecast-positions"></a>Création de postes de prévision

Vous pouvez créer des postes de prévision de deux manières : en copiant un poste de prévision existant et en créant un poste de prévision entièrement nouveau. 

Lorsqu'un poste de prévision est sélectionné, choisissez **Copier le poste de prévision sélectionné** pour créer un nouveau poste de prévision avec l'état des prévisions **Proposé**. Ce poste de prévision contient toutes les données du poste de prévision qui a été copié, hormis le collaborateur affecté et toutes les notes sur les éléments de coût budgétaire. Notez qu'une nouvelle position correspondante est également créée dans Ressources humaines. Ce poste a pour description **Créé par prévision**. 

Vous pouvez également créer un poste de prévision entièrement nouveau. Sélectionnez une tâche existante, ainsi que le processus de planification budgétaire et le scénario de plan budgétaire. Vous pouvez ensuite ajouter tous les autres détails nécessaires. De nouveau, un nouveau poste est créé simultanément dans les Ressources humaines.

## <a name="working-with-forecast-positions"></a>Utilisation des postes de prévision
[![graphic5](./media/graphic5-1024x327.png)](./media/graphic5.png)

### <a name="multiple-versions-of-a-forecast-position"></a>Multiples versions d'un poste de prévision

Vous pouvez modifier les postes de prévision pour appliquer les modifications connues du cycle budgétaire ou pour modéliser les modifications proposées. Une pratique courante consiste à créer un paramétrage de base des postes de prévision, créer des copies de ces postes de prévision, puis utiliser les copies pour modéliser différents ensembles de modifications. Les copies sont affectées à un scénario de plan budgétaire différent, mais, au moins jusqu'à ce que des modifications soient apportées, elles sont identiques aux postes de prévision à partir desquels elles ont été copiées. Les originaux et les copies partagent le même poste dans les Ressources humaines. 

La fonction **Copier dans le scénario** fournit cette fonctionnalité. Notez que chaque poste de Ressources humaines ne peut avoir qu'un poste de prévision dans chaque scénario de plan budgétaire.

### <a name="modifying-forecast-positions"></a>Modification de postes de prévision

Les modifications apportées aux postes de prévision sont limitées à ces postes de prévision. Les modifications n'affectent pas les enregistrements des postes de prévision dans les Ressources humaines. La plupart des modifications sont également limitées au poste de prévision qui est modifié. Autrement dit, les modifications sont spécifiques au processus de planification budgétaire et au scénario de plan budgétaire affectés. Les exceptions sont les modifications apportées aux champs qui sont partagés pour le poste entre plusieurs processus et scénarios. Ces champs comprennent les champs de l'onglet **Général** et l'onglet **Dimensions financières**. Lorsque ces champs sont modifiés, les nouvelles valeurs s'appliquent à la position dans tous les scénarios de planification budgétaire. C'est pourquoi, ces champs permettent de mettre rapidement toutes les versions à jour.

#### <a name="budget-cost-elements"></a>Éléments de coût budgétaire

Les éléments de coût budgétaires fournissent des informations principales pour les plans budgétaires : le montant budgétaire et le compte principal. Le montant budgétaire est le montant qui est envoyé au plan budgétaire lorsqu'un poste de prévision est inclus dans un plan. Le montant budgétaire est calculé et ne peut pas directement être modifié. Ce montant correspond au montant annuel ou à un calcul du pourcentage des éléments de base du montant annuel (tel que défini sous le paramétrage de l'élément de coût budgétaire). Le montant est ensuite factorisé par le nombre de jours dans la période de l'élément (date de début à date de fin) et également par la valeur **Équivalent temps plein** (ETP) du poste de prévision. 

Par exemple, une ligne d'élément de coût budgétaire du 1er janvier 2017 au 30 juin 2017, dont le montant annuel est 100 000 et la valeur ETP **0,50**, est calculée comme suit : 100 000 × (181 jours ÷ 365 jours) × 0,50 = 24 794,52. 

Les lignes d'élément de coût budgétaire doivent être recalculées lorsque la valeur ETP est modifiée dans le poste de prévision. Les lignes doivent également être recalculées lorsque les dates d'activation ou de suppression sont modifiées. Les modifications apportées à ces dates peuvent entraîner une mise à jour des dates de début et de fin de l'élément de coût budgétaire, qui doivent être incluses dans les dates du poste de prévision. Lorsqu'un nouveau calcul est nécessaire, le bouton **Recalculer** devient disponible, et un message « Nécessite un calcul » s'affiche. Le nouveau calcul est également nécessaire si vous ajoutez ou supprimez un élément de coût budgétaire.

**Exemple** 

L'organisation envisage deux options pour réduire le coût d'un poste de comptable. Une option consiste à mettre fin au poste en milieu d'année. L'autre option consiste à modifier le poste en travail à mi-temps pour l'année entière. Brad a créé un poste de prévision pour le poste de comptable existant dans un scénario de référence. Il copie ce poste de prévision de référence dans le scénario A, fixe la date de suppression au 31 mai et recalcule. Brad copie ensuite le poste de prévision de référence dans le scénario B, modifie la valeur ETP à **0,50**, et recalcule. Brad a désormais trois versions, chacune avec des totaux de coût correspondant à ses options.

#### <a name="assigning-a-compensation-group"></a>Affectation d'un groupe de rémunération

Lorsque vous affectez d'abord un groupe de rémunération à un poste de prévision, les éléments de coût budgétaire par défaut du groupe de rémunération sont ajoutés. Si des éléments de coût sont déjà affectés au poste de prévision, ces éléments de coût restent. Si un groupe de rémunération a déjà été affecté et est modifié, les éléments de coût budgétaire existants sont supprimés et sont remplacés par l'ensemble du groupe de rémunération. 

Lorsque vous sélectionnez un niveau de rémunération et un échelon, un élément de coût budgétaire des bénéfices (tel que défini dans le groupe de rémunération) est ajouté. Le montant annuel est calculé à l'aide du taux correspondant au niveau et à l'échelon sélectionnés, et des heures annuelles dans le groupe de rémunération (ou, pour un salaire annuel, le montant total dans le niveau et l'échelon). De nouveau, ce montant est factorisé par la période de la ligne d'élément de coût et la valeur ETP du poste de prévision.

#### <a name="generating-increases"></a>Génération d'augmentations

Les augmentations annuelles (une par année civile) peuvent être créées automatiquement pour les postes de prévision ayant un groupe de rémunération basé sur l'échelon affecté. Cliquez sur **Générer des augmentations** pour ajouter un élément de coût budgétaire des bénéfices à l'échelon le plus élevé suivant. La date de début du nouvel élément de coût budgétaire des bénéfices est la date prévue d'augmentation qui figure sur le poste de prévision. Cette date est définie à partir du groupe de rémunération de deux manières. Si le programme d'augmentation du groupe de rémunération est défini sur **Date courante**, la date d'augmentation est spécifiée sur le groupe de rémunération. Si le programme d'augmentation est défini sur **Date d'anniversaire**, le champ de date d'anniversaire sur le poste de prévision est utilisé, et le cycle budgétaire fournit l'année. S'il existe plusieurs années civiles dans un cycle budgétaire, plusieurs augmentations sont ajoutées. 

La date de fin de l'élément de coût budgétaire des bénéfices actuel est mise à jour au jour précédant la date d'augmentation. Le processus de recalcul est automatiquement utilisé lorsque des augmentations sont générées. Par conséquent, vous ne devez pas recalculer manuellement. 

Si vous cliquez sur **Générer des augmentations** une deuxième fois, le processus est réexécuté, mais n'ajoute pas d'autres enregistrements. Une seule augmentation par année civile est créée.

#### <a name="changes-from-other-pages"></a>Modifications à partir d'autres pages

Les mises à jour des postes de prévision peuvent également provenir d'autres zones, telles que les pages de paramétrage de l'élément de coût budgétaire et des groupes de rémunération. Vous pouvez également modifier les postes de prévision à l'aide du processus de mise à jour collective. 

Deux options sont disponibles dans la page de paramétrage de l'**Élément de coût budgétaire** : **Ajouter à des postes** et **Mettre les postes à jour**. L'option **Ajouter à des postes** permet d'ajouter l'élément de coût budgétaire aux postes de prévision sélectionnés. Si l'élément est déjà affecté à un poste de prévision, ce poste de prévision est ignoré. L'option **Mettre les postes à jour** applique les valeurs courantes (le compte principal, le pourcentage, le montant annuel, etc.) aux postes de prévision sélectionnés. 

Chaque processus a une page similaire dans laquelle vous pouvez sélectionner les postes de prévision. La page **Ajouter à des postes** affiche tous les postes de prévision disponibles pour la sélection, alors que la page **Mettre les postes à jour** affiche uniquement les postes de prévision qui ont déjà l'élément de coût budgétaire affecté. (Par conséquent, la page **Mettre à jour des postes** vous permet de savoir quelles postes de prévisions ont déjà l'élément de coût joint.) Déplacez les postes de prévisions d'une grille supérieure vers une grille inférieure pour les inclure dans la mise à jour. 

Notez que la fonction **Dates de modification** sous l'onglet **Calcul des coûts** modifie immédiatement les dates de début et de fin de l'élément de coût budgétaire sur les postes de prévision. Aucune option de sélection n'est disponible. 

Dans la page **Groupe de rémunération**, la fonction **Mettre à jour les taux des postes** applique les taux actuels de la table de taux de rémunération aux postes de prévision affectés au groupe. Les taux sont mis à jour, et des lignes d'élément de coût supplémentaires sont ajoutées pour toutes les nouvelles lignes de la table de taux (en fonction des dates). Toutefois, les éléments de coût budgétaire et les dates d'augmentation ne sont pas mis à jour. Vous pouvez sélectionner le processus de planification budgétaire et le scénario de plan budgétaire à mettre à jour. Par conséquent, vous pouvez mettre à jour un scénario mais laisser d'autres scénarios inchangés à des fins de comparaison. 

En sélectionnant des postes de prévision, puis en cliquant sur **Mise à jour collective**, vous pouvez ajouter ou modifier plusieurs postes de prévision en même temps. De nombreuses options sont disponibles. Une option de l'onglet **Dimensions financières** diffère légèrement des autres et est liée aux éléments de coût budgétaire. Vous pouvez ajouter des éléments de coût budgétaires en définissant l'option **Valeurs par défaut du budget** sur **Oui**. Si aucun élément de coût budgétaire n'est sélectionné, mais que **Valeurs par défaut du budget** est défini sur **Oui**, tous les éléments de coût budgétaire qui sont actuellement affectés sont supprimés. 

Le processus de nouveau calcul est automatiquement utilisé sur tous les postes de prévision qui ont été modifiés.

## <a name="bringing-forecast-positions-into-budget-plans"></a>Importer les postes de prévision dans les plans budgétaires

[![graphic6](./media/graphic6-1024x327.png)](./media/graphic6.png)

L'objet de la création et de la modification des postes de prévision est de les ajouter à des plans budgétaire, de sorte que les plans budgétaires incluent des montants budgétaires plus exacts. Il existe deux méthodes pour ajouter des postes de prévision aux plans budgétaires. Vous pouvez utiliser un processus de génération ou un processus de sélection dans le plan budgétaire.

### <a name="generating-a-budget-plan-from-forecast-positions"></a>Génération d'un plan budgétaire à partir des postes de prévision

La fonction **Générer un plan budgétaire à partir des postes de prévision** crée ou met à jour des plans budgétaires afin qu'ils aient les montants budgétaires et les comptes ETP des postes de prévision. Les montants budgétaires du poste de prévision deviennent les montants de ligne de plan budgétaire et sont agrégés aux valeurs de dimension financière et à la date d'effet. Le processus de génération affecte le poste de prévision source à la ligne de plan budgétaire. Pour afficher le poste, vous pouvez soit ajouter le poste de prévision comme une ligne dans la structure du plan budgétaire, soit utiliser la fonction recherche de **Lignes de plan budgétaire**. Pour ignorer cette affectation, définissez l'option **Inclure le poste dans la ligne de plan budgétaire** sur **Non**. 

Vous pouvez sélectionner un scénario ETP de plan budgétaire pour inclure le nombre d'ETP dans le plan budgétaire. Vous ne pouvez sélectionner que des scénarios de type quantitatifs inclus dans la structure du plan budgétaire cible. Si vous sélectionnez un scénario ETP, vous devez également spécifier un compte principal ETP. Ce compte est utilisé pour créer des lignes de plan budgétaire de quantité. 

Le processus de planification budgétaire et le scénario de plan budgétaire qui sont sélectionnés dans la source déterminent le processus et le scénario cibles de planification budgétaire. Étant donné que ces attributs sont attribués aux postes de prévision, ils doivent être synchronisés avec le plan budgétaire. Par conséquent, les attributs ne peuvent pas être modifiés dans la cible. 

En ce qui concerne les autres processus de génération, trois options sont disponibles :

-   **Créer un nouveau plan budgétaire** – Crée un nouveau plan ayant les attributs sélectionnés dans la section **Cible**.
-   **Remplacer le scénario de plan budgétaire existant** – Supprime toutes les données dans le plan budgétaire cible du scénario de plan budgétaire sélectionné et crée de nouvelles lignes avec les données du poste de prévision sélectionné.
-   **Mettre à jour le scénario de plan budgétaire existant et ajouter de nouvelles données** – Met à jour les lignes existantes du plan cible qui correspondent aux lignes de source et ajoute également de nouvelles lignes pour les nouvelles données. La correspondance est basée sur le compte général, la date, la classe budget, ainsi que d'autres valeurs, telles que le poste de prévision. Les lignes qui ont un numéro de position correspondant au numéro de position de la source sont remplacées par les nouvelles lignes de la source.

### <a name="selecting-forecast-positions"></a>Sélection des postes de prévision

Vous pouvez également ajouter des montants budgétaires du poste de prévision directement dans un plan budgétaire. Utilisez la fonction **Ajouter à des postes** au-dessus des lignes de plan budgétaire pour sélectionner les postes de prévision à inclure. 

Les scénarios de plan budgétaire que vous pouvez sélectionner comme source sont limités aux scénarios inclus dans la structure du plan. Une option de l'onglet **Cible** permet de spécifier que le scénario et le compte principal d'ETP sont disponibles pour inclure les comptes ETP, mais elle n'est pas obligatoire. 

Ce processus de sélection se comporte comme l'option **Mettre à jour le scénario de plan budgétaire existant et ajouter de nouvelles données** pour un processus de génération. Toutes les lignes de plan budgétaire existantes dans lesquelles le poste de prévision est ajouté sont supprimées et remplacées par les nouvelles lignes basés sur l'état actuel du poste de prévision.

#### <a name="date-options"></a>Options de date

Pour le processus de génération et le processus de sélection, la date de début de la ligne d'élément de coût budgétaire détermine la date d'effet de la ligne de plan budgétaire correspondante. Le champ **Mode de répartition** dans la page de paramétrage de l'élément de coût budgétaire spécifie le mode de répartition :

-   **Date de début** – La date de début de l'élément de coût budgétaire est utilisée comme date d'effet de la ligne de plan budgétaire.
-   **Mensuel** – Le montant budgétaire est divisé équitablement par le nombre de mois dans la plage de dates pour produire un montant mensuel classique affecté le premier jour de chaque mois. Si la première période est un mois partiel, le montant de ce mois est factorisé par le nombre de jours pendant lesquels le coût est actif dans ce mois, et le résultat est affecté à la date de début. Le montant du dernier mois est la différence entre le montant budgétaire total et la somme de tous les autres mois. Par conséquent, un arrondi peut affecter le montant du dernier mois.
-   **Trimestriel** – Cette méthode est identique à **Mensuel**, mais les calculs sont effectués pour des périodes de trois mois.
-   **Hebdomadaire** – La logique ressemble à la logique des méthodes **Mensuel** et **Trimestriel**. Le montant budgétaire est divisé équitablement par le nombre de semaines dans la plage de dates pour produire un montant hebdomadaire classique affecté le premier jour de chaque semaine. Si la première période est une semaine partielle, le montant de cette semaine est factorisé par le nombre de jours pendant lesquels le coût est actif dans cette semaine, et le résultat est affecté à la date de début. Le montant de la dernière semaine est la différence entre le montant budgétaire total et la somme de toutes les autres semaines. Par conséquent, un arrondi peut affecter le montant de la dernière semaine.
-   **Bihebdomadaire** – Cette méthode est identique à **Hebdomadaire**, mais les calculs sont effectués pour des périodes de deux semaines.

#### <a name="changing-budget-plan-lines-that-have-forecast-positions"></a>Modification des lignes de plan budgétaire qui ont des postes de prévision

Les lignes de plan budgétaire indiquent la source des montants budgétaires (le numéro du poste de prévision) mais ne sont pas liées. Par conséquent, les modifications apportées au poste de prévision ne sont pas affichées dans la ligne de plan budgétaire, et les modifications apportées à la ligne de plan budgétaire sont indiquées dans le poste de prévision. Si vous modifiez un poste de prévision et souhaitez que les mises à jour soient incluses dans un plan budgétaire, vous devez réimporter le poste de prévision dans le plan. Toutefois, n'oubliez pas que ce processus supprime toutes les lignes auxquelles ce poste de prévision est affecté. Par conséquent, toutes les modifications apportées à ces lignes sont supprimées. 

Pour afficher les plans budgétaires dans lesquels un poste de prévision a été inclus, vous pouvez générer l'état **Postes de prévision par plan budgétaire**. Sinon, sur le poste de prévision, vous pouvez ouvrir le récapitulatif **Plans budgétaires associés** pour afficher les plans.




