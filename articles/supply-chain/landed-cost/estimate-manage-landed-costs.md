---
title: Estimer et gérer les coûts au débarquement
description: Le système utilise votre configuration de coût automatique pour déterminer une estimation de votre coût au débarquement. Cet article explique comment vous pouvez définir divers scénarios pour fournir une estimation plus précise.
author: Weijiesa
ms.date: 01/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostTemplateTable, ITM CostEstimateDialog, ITMCostEstimateTable, SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-26
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 2e7cdd7c7439a24ec75a59bcee1e8f42f37bb2cd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854439"
---
# <a name="estimate-and-manage-landed-costs"></a>Estimer et gérer les coûts au débarquement

[!include [banner](../../includes/banner.md)]

Le système utilise votre [configuration de coût automatique](auto-cost-setup.md) pour déterminer une estimation de votre coût au débarquement. De plus, vous pouvez définir divers scénarios pour fournir une estimation plus précise. Ces scénarios sont stockés. Par conséquent, vous pouvez les consulter ultérieurement et les comparer aux chiffres réels sur un rapport. Vous pouvez également mettre à jour le prix de l’article.

## <a name="set-up-cost-estimates"></a>Paramétrer des estimations de coût

### <a name="set-up-cost-templates"></a>Paramétrer les modèles de coûts

Les modèles de coût établissent des paramètres par défaut que les utilisateurs qui obtiennent l’estimation ne connaissent pas nécessairement. Les modèles peuvent aider à réduire la complexité du processus d’estimation en minimisant les sélections que les utilisateurs doivent spécifier pour obtenir une estimation précise. Si vous utilisez le modèle de coût standard, vous pouvez utiliser des modèles de coût lors de la configuration du coût des marchandises.

Pour configurer vos modèles de coût, accédez à **Coût au débarquement \> Configuration des coûts \> Modèles de coût**. Sur la page **Modèles de coût**, le volet de liste sur la gauche affiche toutes les modèles de coûts actuels. Vous pouvez utiliser les boutons du volet Actions pour créer, supprimer et modifier les modèles.

Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque modèle.

| Champ | Description |
|---|---|
| Modèle de coût | Entrez un nom unique pour le modèle de coût. Le nom décrit généralement le facteur ou le multiplicateur de coût du modèle. |
| Description | Permet d’entrer une description du modèle de coût. |
| Société d’expédition | Sélectionnez la société de transport qui doit être appliquée lorsque le modèle est utilisé. |
| Mode de livraison | Sélectionnez le mode de livraison, comme la mer ou l’air, qui doit être appliqué lorsque le modèle est utilisé. Ce champ permet de déterminer les coûts automatiques associés aux marchandises sur une estimation des coûts. |
| Type de conteneur d’expédition | Sélectionnez le type de conteneur de transport qui doit être appliquée lorsque le modèle est utilisé. Ce champ permet de déterminer les coûts automatiques associés aux marchandises sur une estimation des coûts. |
| Courtier en douane | Le courtier en douanes (fournisseur) qui doit être appliquée lorsque le modèle est utilisé. Ce champ permet de déterminer les coûts automatiques associés à une estimation des coûts. |
| Facteur | Entrez le multiplicateur (pourcentage) qui doit être automatiquement appliqué à l’estimation des coûts lorsque le modèle est utilisé. Par exemple, pour ajouter 10 % à l’estimation des coûts calculée, entrez *1,10*. |

### <a name="create-a-cost-estimate"></a>Création d’une estimation de coût

Utilisez la boîte de dialogue **Prix estimé** pour générer une nouvelle estimation des coûts basée sur un modèle de coût sélectionné, un ensemble d’éléments sélectionné et d’autres détails d’un trajet. Ces paramètres sont ensuite utilisés pour déterminer les coûts au débarquement estimés des marchandises. Ces estimations de coûts sont principalement utilisées pour travailler avec des éléments de coût standard. En ajoutant les coûts au débarquement estimés au coût standard des marchandises en stock, vous devriez constater des transactions d’écart plus petites lorsque les marchandises sont ajoutées à un voyage, car le coût standard reflétera les estimations de ces coûts au débarquement.

Pour ouvrir la boîte de dialogue **Prix estimé**, accédez à **Prix au débarquement \> Tâches périodiques \> Prix estimé**. Ensuite, définissez les champs décrits dans les sous-sections suivantes. Enfin sélectionnez **OK** pour créer l’estimation. La page **Prix estimé** (**Prix au débarquement \> Demandes de renseignements \> Estimations de coût**) apparaît alors et affiche votre nouvelle estimation, comme décrit plus loin dans cet article.

### <a name="settings-on-the-parameters-tab"></a>Paramètres de l’onglet Paramètres

La table suivante les champs disponibles sur l’onglet **Paramètres** de la boîte de dialogue **Estimation du coût**.


| Champ | Description |
|---|---|
| Modèle de coût | Sélectionnez un modèle de coût. Les paramètres associés au modèle sélectionné seront utilisés pour déterminer les coûts automatiques appliqués. |
| Date de l’estimation | Par défaut, ce champ est défini sur la date du jour, mais vous pouvez modifier la valeur. La date spécifiée sera utilisée pour sélectionner les prix de vente, les prix d’achat, les coûts automatiques et le taux de change appropriés si un tarif d’expédition est utilisé. |
| Mesure | Les coûts peuvent dépendre d’une mesure. Par exemple, lorsque le fret aérien est utilisé, une tarification volumétrique peut s’appliquer. Si le coût dépend d’une mesure, entrez la valeur de cette mesure. Sinon, nous vous recommandons de définir ce champ sur *1*, sauf si vous êtes certain qu’aucune répartition ne se produit en utilisant la mesure. Entrer une valeur décimale. L’unité est celle qui est définie dans l’enregistrement de coût automatique applicable. |
| Modèle de parcours | Sélectionnez [un modèle de trajet](multi-leg-journey-setup.md). Ce champ est utilisé pour déterminer les coûts automatiques corrects qui doivent être appliqués. |
| Port de départ | Le port à partir duquel les articles seront expédiés. Ce champ est défini en fonction du modèle de trajet sélectionné. |
| Port d’arrivée | Le port vers lequel les articles seront expédiés. Ce champ est défini en fonction du modèle de trajet sélectionné. |
| Devise | Sélectionnez la devise dans laquelle les articles seront achetés. |
| Conteneurs | Si plusieurs conteneurs sont généralement utilisés, spécifiez le nombre de conteneurs. Le système utilisera ensuite les coûts pour plusieurs conteneurs lorsqu’il estime les coûts. |
| Folios | Si plusieurs folios sont généralement utilisés, spécifiez la quantité. (La quantité est habituellement *1*.) |
| Site | Précisez le site où les marchandises seront livrées. |

### <a name="settings-on-the-items-tab"></a>Paramètres de l’onglet Articles

Sur l’onglet **Articles**, vous pouvez ajouter autant d’articles au devis que vous le souhaitez. Utilisez la barre d’outils pour ajouter des éléments à la grille ou supprimer des éléments. Sélectionnez **Stock \> Afficher les dimensions** dans la barre d’outils pour ouvrir une boîte de dialogue dans laquelle vous pouvez ajouter des colonnes de dimension à la grille ou supprimer des colonnes.

Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque article.

| Champ | Description |
|---|---|
| Numéro d’article | Sélectionnez l’article pour lequel déterminer le prix. (Si l’article n’existe pas encore dans le système, créez un article factice, associez-le éventuellement à un groupe de coûts d’articles de voyage, puis laissez le prix vide ou créez ou modifiez le prix.) |
| Compte fournisseur | Sélectionnez le fournisseur à utiliser pour l’estimation de cet article. Si un fournisseur par défaut est affecté à l’article, ce champ est automatiquement défini. |
| Quantité | Sélectionnez la quantité que vous désirez acheter. |
| Prix de revient | Le système utilise ses règles de tarification pour trouver un prix initial, mais vous pouvez remplacer ce prix si nécessaire. |
| Prix de vente | Entrer le prix de vente attendu pour les marchandises. |
| Mesure | Entrez une valeur décimale pour la mesure des marchandises. L’unité est celle qui est configurée pour le produit lancé applicable. |
| Mettre à jour le poids/le volume de l’article | Cochez cette case pour mettre à jour la mesure du poids ou du volume du produit lancé afin qu’elle corresponde à la valeur de **Mesure** entrée pour cette ligne. |
| (Autres dimensions) | En fonction des dimensions que vous avez choisi d’afficher, vous pouvez voir des colonnes d’informations supplémentaires sur chaque élément. |

Pour afficher ou régler les détails du volume et/ou du poids d’un article, sélectionnez l’article dans la grille, puis utilisez les champs en bas de la page.

## <a name="manage-estimated-costs"></a>Gérer les coûts estimés

Pour afficher et modifier les estimations de coût que vous avez créées, accédez à **Prix au débarquement \> Demandes de renseignements \> Estimations de coût**. Sur la page **Estimations de coût**, le volet de liste sur la gauche affiche toutes les estimations de coûts actuelles. Vous pouvez utiliser les boutons du volet Actions pour utiliser une estimation sélectionnée. Notez que vous ne pouvez pas créer une estimation des coûts à partir de la page **Estimations de coût**. Au lieu de cela, utilisez la boite de dialogue **Prix estimé** (**Prix au débarquement \> Tâches périodiques \> Prix estimé**), comme décrit précédemment dans cet article.

La page **Estimations de coût** montre comment chaque coût estimé a été calculé. Il montre également le coût au débarquement estimé pour chaque article. Vous pouvez modifier une estimations des coûts en modifiant le prix de revient et/ou la devise associés aux différentes marchandises. Vous pouvez également modifier les coûts de voyage associés au niveau du voyage et au niveau du conteneur. Lorsque vous utilisez cette page pour modifier les coûts, vous êtes invité à recalculer les coûts estimés des articles dans l’estimation de coût. Lorsque vous êtes prêt, vous pouvez utiliser les estimations pour mettre à jour le prix de revient des articles dans le modèle de coût.

### <a name="information-on-the-header"></a>Informations sur l’en-tête

Le haut de la page **Estimations de coût** affiche les paramètres qui ont été utilisés pour générer l’estimation des coûts sélectionnée, comme décrit dans la section précédente. 

### <a name="settings-and-buttons-on-the-lines-fasttab"></a>Paramètres et boutons du raccourci Lignes

Le raccourci **Lignes** répertorie chaque élément inclus dans l’estimation actuelle. Le tableau suivant décrit le champ disponible dans l’en-tête pour chaque ligne.

| Champ | Description |
|---|---|
| Compte fournisseur | Compte fournisseur associé à l’article. |
| Numéro d’article | Numéro d’article. |
| Quantité | Le nombre d’articles utilisés pour déterminer le coût. |
| Prix de revient | Le prix de revient selon l’accord commercial. Cette valeur est exprimée dans la devise locale. |
| Mesure | Mesure individuelle. L’unité est celle qui est définie pour le produit lancé applicable. |
| Coût au débarquement estimé | Le coût au débarquement estimé pour la quantité totale. |
| Par unité | Le coût au débarquement estimé divisé par la quantité. |
| (Autres dimensions) | En fonction des dimensions que vous avez choisi d’afficher, vous pouvez voir des colonnes d’informations supplémentaires sur chaque élément. |

Le tableau suivant décrit les boutons disponibles directement sur la barre d’outils du raccourci **Lignes**.

| Bouton | Description |
|---|---|
| Ajouter | Ajoutez des articles à l’estimation des coûts. Après avoir ajouté des éléments, vous devez sélectionner **Recalculer** dans le volet Actions. |
| Exécute la suppression | Supprimez les éléments de l’estimation des coûts. Après avoir supprimé des éléments, vous devez sélectionner **Recalculer** dans le volet Actions. |
| Coûts du voyage | Ouvrez une page dans laquelle vous pouvez afficher et modifier différents types de frais de voyage pour l’article. |
| Stock \> Afficher les dimensions | Ouvrez une boîte de dialogue dans laquelle vous pouvez ajouter des colonnes de dimension à la grille ou supprimer des colonnes. |

### <a name="settings-on-the-general-fasttab"></a>Paramètres de l’organisateur Général

Le raccourci **Général** affiche des détails sur l’élément actuellement sélectionné sur le raccourci **Lignes**. Une grande partie de ces informations est répétée à partir du raccourci **Lignes** et peut être modifié dans les deux endroits. Cependant, des détails supplémentaires sont également disponibles ici. Les valeurs des champs supplémentaires sont basées sur la configuration du produit lancé applicable.

### <a name="settings-on-the-dimension-fasttab"></a>Paramètres de l’organisateur Dimension

Le raccourci **Dimension** affiche les valeurs de toutes les dimensions de stock disponibles pour l’article sélectionné sur le raccourci **Lignes**, quelles que soient les dimensions que vous avez choisi d’y afficher. Toutes les valeurs affichées ici proviennent du modèle d’estimation des coûts applicable. Ils sont facultatifs dans le modèle de devis.

### <a name="buttons-on-the-action-pane"></a>Boutons sur le volet Action

Vous pouvez utiliser les boutons du volet Actions de la page **Estimations de coût** pour travailler avec l’estimation des coûts sélectionnée. Le tableau suivant décrit les boutons disponibles.

| Action | Description |
|---|---|
| Recherche de coût | Voir tous les coûts du voyage. Vous pouvez afficher les coûts au niveau de l’article individuel selon vos besoins. |
| Mettre à jour le coût standard | <p>Mettez à jour le coût standard en utilisant la version de valorisation par défaut définie sur la page **Paramètres de coût au débarquement**. Vous pouvez remplacer cette version.</p><p>**Remarque :** si un article a plusieurs dimensions d’article (par exemple, différentes tailles, couleurs et configurations), mais que ces dimensions n’ont pas été sélectionnées pour l’estimation, le système créera un prix en attente pour chaque combinaison.</p><p>**Important :** La ventilation des prix est créée et utilisée pour déterminer l’écart de coût standard par coût au débarquement.</p> |
| Coûts du voyage | Affichez et modifiez les coûts de voyage pour toutes les marchandises de l’envoi. |
| Recalculer | Mettez à jour les coûts estimés au débarquement après la mise à jour, l’ajout ou la suppression des coûts de voyage. |
| Verrouiller | Verrouillez l’enregistrement de l’estimation des coûts afin qu’aucune autre modification ne puisse être apportée. |

## <a name="item-cost-price-update"></a>Mise à jour du prix de revient de l’article

La tâche périodique **Mise à jour du prix de revient de l’article** met à jour toutes les estimations de coût qui correspondent aux filtres que vous définissez lorsque vous exécutez la tâche. L’effet est similaire à celui de la sélection **Mettre à jour le coût standard** dans le volet Actions pour une seule estimation. Cependant, dans ce cas, la mise à jour s’applique à toutes les estimations correspondantes.

Procédez comme suit pour exécuter la tâche périodique.

1. Aller à **Prix au débarquement \> Tâches périodiques \> Mise à jour du prix de revient de l’article**.
1. Dans la boîte de dialogue **Mettre à jour le prix de revient à partir de l’estimation**, définissez les champs suivants selon vos besoins pour limiter la portée de la mise à jour :

    - **Version** – Ne mettez à jour que les estimations qui utilisent la version de coût spécifiée.
    - **Site** – Ne mettez à jour que les estimations qui utilisent le site spécifiée.
    - **Modèle de coût** – Ne mettez à jour que les estimations qui utilisent le modèle spécifiée.
    - **Port À** – Ne mettez à jour que les estimations qui utilisent le port « À » spécifiée.
    - **Date estimée** – Mettre à jour uniquement les estimations qui ont la date spécifiée.

1. Définissez les options sur les raccourcis **Enregistrements à inclure** et **Exécuter en arrière-plan** comme d’habitude pour les tâches périodiques.
1. Sélectionnez **OK** pour lancer la tâche.

> [!NOTE]
> Cette tâche périodique ne s’exécutera avec succès que si les informations suivantes sont disponibles :
>
> - Chaque produit concerné doit avoir une **Profondeur brute**, **Largeur brute**, et **Hauteur brute** défini.
> - Chaque fournisseur concerné doit avoir un **Port De** défini.
