---
title: Intégration de la planification budgétaire avec d'autres modules
description: 'Les plans budgétaires peuvent être générés à partir de plusieurs ressources différentes : Les éléments de base du processus périodique sont identiques pour toutes les ressources.'
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 64443
ms.assetid: f9a94db5-906c-404a-9ca5-91528d67c490
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7456d0c6a9114fae71aff7b4070d86090e2c7c9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834173"
---
# <a name="budget-planning-integration-with-other-modules"></a>Intégration de la planification budgétaire avec d'autres modules

[!include [banner](../includes/banner.md)]

Les plans budgétaires peuvent être générés à partir de plusieurs ressources différentes : Les éléments de base du processus périodique sont identiques pour toutes les ressources. 



<a name="periodic-processes-for-generating-budget-plans"></a>Processus périodiques pour générer des plans budgétaires
----------------------------------------------

Les plans budgétaires peuvent être générés à partir des ressources suivantes :

-   Transactions comptables
-   Immobilisations
-   Postes prévisionnels
-   Prévisions de projet
-   Prévisions d'approvisionnement
-   Prévisions de la demande
-   Écritures de registre budgétaires
-   Autres plans budgétaires

Les éléments de base du processus périodique sont identiques pour tous les processus. Des onglets permettent de définir la source des données, les attributs cibles (plan budgétaire) et les options pour exécuter le processus en arrière-plan comme processus de traitement par lots. Les dernières sections de cet article décrivent les éléments qui peuvent ne pas apparaître dans chaque processus.

### <a name="actions"></a>Actions

Pour chaque processus de génération, trois actions sont disponibles :

-   **Créer un nouveau plan budgétaire** crée un nouveau plan ayant les attributs sélectionnés dans la section **Cible**. Ces attributs ne sont pas nécessairement uniques. Par conséquent, deux plans peuvent avoir le même nom et d'autres valeurs.
-   **Remplacer le scénario de plan budgétaire existant** supprime toutes les données dans le plan budgétaire cible du scénario de plan budgétaire sélectionné et crée de nouvelles lignes qui utilisent les données sources sélectionnées.
-   **Mettre à jour le scénario de plan budgétaire existant et ajouter de nouvelles données** met à jour les lignes existantes du plan cible qui correspondent aux lignes de source et ajoute de nouvelles lignes pour les nouvelles données. La correspondance est basée sur le compte général, la date, la classe de budget, et d'autres champs divers. Par exemple, lorsque vous générez des plans budgétaires à partir de postes prévisionnels, le numéro de position est un champ important. Les lignes qui ont un numéro de position correspondant au numéro de position de la source sont remplacées par les nouvelles lignes de la source.

### <a name="source"></a>Source

Pour tous les processus, l'onglet **Source** permet de filtrer les données à l'aide du bouton **Filtrer**. Par défaut, des champs spécifiques sont ajoutés au filtre pour chaque processus. Par exemple, pour le processus **Générer un plan budgétaire à partir de la comptabilité**, les catégories **Compte général** et **Compte principal** sont disponibles et apparaissent dans la page de génération. Tous les champs que vous ajoutez au filtre sont également ajoutés à la page, avec les critères que vous ajoutez.

### <a name="target"></a>Cible

L'option **Historique** de l'onglet **Cible** permet d'utiliser les dates des données sources comme date d'effet dans le plan budgétaire. Généralement, la date d'effet doit être comprise dans le cycle budgétaire du plan. Lorsque vous définissez l'option **Historique** sur **Oui**, la date (même l'année) de la source est utilisée, afin de pouvoir utiliser des données passées comme base de comparaison. Vous ne pouvez pas modifier les données historiques dans le plan budgétaire, et le plan est défini sur le statut de workflow Approuvé. Toutefois, vous pouvez réinitialiser le statut si d'autres scénarios dans le plan exigent des modifications.

Le champ **Total regroupement par** en haut de la page détermine également la date utilisée. Ce champ calcule le total des montants et fixe éventuellement la date d'effet au premier jour de l'exercice ou de la période fiscale. 

Plusieurs champs sous l'onglet <strong>Cible</strong> deviennent modifiables ou en lecture seule, selon l'action que vous sélectionnez. Lorsque vous passez de la création d'un plan budgétaire à la mise à jour d'un plan existant, le champ **Nom du plan budgétaire** n'est plus disponible, et les champs associés à la sélection d'un plan existant deviennent disponibles. Sous les deux onglets **Cible** et **Source**, le champ **Comptabilité** n'est jamais disponible, car la valeur est déterminée par le processus de planification budgétaire sélectionné. 

Le champ **Classe de budget** permet de définir les lignes du plan budgétaire en tant que transactions de dépense ou transactions de produit. Généralement, les transactions de produit sont des crédits dans un compte général et sont donc enregistrées comme montants négatifs. Généralement, ces transactions apparaissent également comme des montants négatifs dans le plan budgétaire. Toutefois, en ajoutant la classe budget comme champ dans la structure du plan, vous pouvez autoriser le produit à afficher des montants positifs.

### <a name="generation-rules"></a>Règles de génération

Trois champs fournissent des fonctionnalités supplémentaires : **Facteur**, **Minimum** et **Règle** **d'arrondi**. 

La valeur du champ **Facteur** est multipliée par le montant source pour définir le montant du plan budgétaire. Vous pouvez ensuite procéder à des ajustements lorsque vous créez des lignes de plan budgétaire. Par exemple, vous pouvez entrer **1.03** pour une augmentation de 3 %. Le facteur doit être un nombre positif. 

Le champ **Minimum** permet de définir le montant du seuil pour créer une ligne de plan budgétaire. Si le montant source est inférieur à ce nombre, la ligne de plan budgétaire n'est pas créée. La valeur **0.00** permet tous les montants mais ne limite pas les lignes à des montants positifs. (Aucune valeur ne limite les lignes à des montants positifs. Les montants négatifs sont toujours inclus et représentent généralement des entrées de crédit.)

Le champ **Règle d'arrondi** permet de définir la précision des lignes de plan budgétaire créées. Vous pouvez arrondir les montants au 1.00 le plus proche, 10.00, 100.00, etc., de devise.

## <a name="notes-for-specific-processes"></a>Remarques pour les processus spécifiques
### <a name="generate-budget-plan-from-general-ledger"></a>Générer un plan budgétaire à partir de la comptabilité

Lorsque vous créez un plan budgétaire à partir des données de comptabilité, vous devez définir le champ **Total regroupement par** sur **Exercice** si l'option **Historique** est définie sur **Non**. Les périodes et les dates dans la source risquent de ne pas correspondre aux périodes et aux dates de la cible. Étant donné que le processus n'a pas de manière fiable de faire correspondre ces valeurs, vous devez limiter le processus à la première de l'année. 

Dans la cible, le champ **Classe de budget** est défini sur **Dépense** ou **Produit**. Ce paramètre permet de sélectionner l'attribut **Type de budget** pour les lignes créées, lorsque le compte principal dans une ligne n'est pas de type **Produit** ou **Dépense**.

### <a name="generate-budget-plan-from-fixed-assets"></a>Générer un plan budgétaire à partir des immobilisations

Le processus **Générer un plan budgétaire à partir des immobilisations** n'a aucune option pour regrouper par période ou jour. Il n'existe également aucune option pour définir le plan comme historique. Vous pouvez utiliser ce processus périodique pour inclure des transactions prévues pour les immobilisations dans votre planification budgétaire.

### <a name="generate-budget-plan-from-forecast-positions"></a>Générer un plan budgétaire à partir des postes de prévision

Le processus **Générer un plan budgétaire à partir des postes de prévision** affecte le poste de prévision source à la ligne de plan budgétaire. Vous pouvez afficher le poste en ajoutant le poste de prévision comme une ligne dans la structure du plan budgétaire ou à l'aide de la fonction recherche de **Lignes de plan budgétaire**. Si vous ne souhaitez pas que le poste de prévision soit affecté aux lignes de plan budgétaire, définissez l'option **Inclure le poste dans la ligne de plan budgétaire** sur **Non**.

Les lignes du plan budgétaire sont regroupées par compte général et poste. Toutefois, vous pouvez exclure le numéro de poste, afin que les lignes soient regroupées par compte général uniquement. Sous l'onglet **Cible**, définissez l'option **Inclure le poste dans la ligne de plan budgétaire** sur **Non**.

Dans le champ **Scénario ETP de plan budgétaire**, vous pouvez sélectionner un scénario pour inclure le nombre d'équivalents à temps plein (ETP) dans le plan budgétaire. Ce champ est limité à des scénarios de type quantitatifs inclus dans la structure du plan budgétaire cible. Si vous sélectionnez un scénario ETP, vous devez également sélectionner un compte principal ETP. Ce compte est utilisé pour créer des lignes de plan budgétaire de quantité. 

Le processus de planification budgétaire et le scénario de plan budgétaire qui sont sélectionnés dans la source définissent le processus et le scénario cibles de planification budgétaire. Étant donné que ces attributs sont attribués aux postes de prévision, ils doivent correspondre au plan budgétaire. C'est pourquoi, ces attributs ne peuvent pas être modifiés dans la cible.

### <a name="generate-budget-plan-from-project-forecasts"></a>Générer un plan budgétaire à partir des prévisions de projet

Le processus **Générer un plan budgétaire à partir des prévisions de projet**, comme le processus **Générer un plan budgétaire à partir des postes de prévision**, a une option pour inclure les quantités du projet (heures, dépenses et articles) dans un scénario de quantité. Les deux processus ont également des filtres similaires pour les colonnes dans la structure de plan budgétaire. 

Sous l'onglet **Source**, trois options dans la section **Inclure le relevé** déterminent les lignes de plan budgétaire qui sont créées. Ces options sont identiques aux options disponibles lorsque vous créez des écritures de registre budgétaires directement à partir des prévisions de projet. Définissez l'option **Résultat** sur **Oui** pour créer des lignes pour les coûts et les produits. Définissez l'option **Travaux en cours** sur **Oui** pour créer des entrées de travaux en cours. Définissez l'option **Répartition des salaires** sur **Oui** pour créer des lignes pour les comptes de répartition des salaires pour les transactions horaires. 

Il n'existe aucun champ **Classe de budget**, car la classe budget (**Dépense** ou **Produit**) est déterminée par la source. 

Vous pouvez utiliser des budgets de projet comme source en sélectionnant le modèle de prévision qui contient les montants de budget de projet. N'oubliez pas que les budgets de projet créent des entrées de prévision de projet en tant qu'approuvées.

Pour sélectionner uniquement des coûts ou des produits pour les lignes de plan budgétaire, utilisez le filtre pour sélectionner <strong>Mises à jour budgétaires : Type de montant = coût</strong>. Pour sélectionner un seul type de prévision, utilisez le filtre pour sélectionner <strong>Mises à jour budgétaires : Type de transaction = *xxx</strong>*. 

Seul un modèle de prévision peut être utilisé pour générer un scénario de plan budgétaire. Si vous exécutez le processus pour un modèle de prévision, puis effectuez une mise à jour et essayez de spécifier un autre modèle, le premier modèle est remplacé si le même projet et les mêmes comptes généraux s'appliquent. Pour générer un scénario de plan budgétaire à partir de plusieurs modèles de prévision, générez-le en différents scénarios de plan budgétaire, et utilisez les options de répartition pour les regrouper dans un autre scénario. 

Le processus **Générer un plan budgétaire à partir des prévisions de projet** affecte également le projet source à la ligne de plan budgétaire.

### <a name="generate-budget-plan-from-supply-forecast"></a>Générer un plan budgétaire à partir des prévisions d'approvisionnement

Les options de filtre source dans le processus **Générer un plan budgétaire à partir des prévisions d'approvisionnement** ont été modelées sur les options de la fonction **Transférer le budget des achats dans la comptabilité**, en raison de similitudes entre le processus et la fonction.

### <a name="generate-budget-plan-from-demand-forecast"></a>Générer un plan budgétaire à partir d'une prévision de la demande

Pour le processus **Générer un plan budgétaire à partir d'une prévision de la demande**, vous pouvez définir l'option **Commande client** sur **Oui** pour générer des lignes de produit dans le plan budgétaire, définir **Consommation** sur **Oui** pour créer des lignes de dépense, ou définir les deux options sur **Oui**.

### <a name="generate-budget-plan-from-budget-register-entries"></a>Générer un plan budgétaire à partir des entrées du registre du budget

Pour le processus **Générer un plan budgétaire à partir des entrées du registre du budget**, la source doit spécifier un sous-modèle, un code budgétaire et un numéro d'entrée. Autrement dit, vous pouvez créer des lignes de plan budgétaire pour une seule écriture de registre budgétaire à la fois. Vous pouvez utiliser des entrées supplémentaires dans le même plan budgétaire en exécutant le processus une fois pour chaque entrée source.

### <a name="generate-budget-plan-from-budget-plan"></a>Générer un plan budgétaire à partir d'un plan budgétaire

Pour le processus **Générer un plan budgétaire à partir d'un plan budgétaire**, un ensemble d'options supplémentaire sous l'onglet **Cible** permet d'affecter de nouvelles dimensions financières. Si une dimension financière est sélectionnée, cette valeur est utilisée pour toutes les lignes de plan budgétaire. Par conséquent, vous pouvez utiliser un plan budgétaire comme base pour d'autres plans budgétaires, mais vous pouvez également affecter, par exemple, un service ou un centre de coût différents aux nouveaux plans budgétaires.

## <a name="looking-back-from-the-budget-plan"></a>Faire une recherche historique à partir du plan budgétaire
### <a name="budget-plans-by-dimension-set-inquiry"></a>Recherche de plans budgétaires par ensemble de dimensions

La recherche **Plans budgétaires par ensemble de dimensions** inclut plusieurs options qui permettent d'exécuter une requête afin d'identifier la source des données du plan budgétaire. 

Sélectionnez une ligne, puis cliquez sur le bouton **Lignes de plan budgétaire** pour exécuter la requête **Lignes de plan budgétaire**. Les résultats sont filtrés par les valeurs de dimension de la ligne sélectionnée. Vous pouvez ensuite appliquer des paramètres supplémentaires. 

Utilisez les boutons **Prévision d'approvisionnement** et **Prévision de la demande** pour exécuter ces requêtes. Dans les deux cas, la requête recherche des lignes de prévision qui peuvent avoir créé les lignes du plan budgétaire. 

Les états supplémentaires disponibles sont notamment l'état **Postes de prévision par plan budgétaire**. Cet état est particulièrement utile si vous souhaitez déterminer si un poste a été correctement affecté aux plans budgétaires.



