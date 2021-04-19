---
title: Configuration des paramètres de coût au débarquement
description: Ces rubriques décrivent comment configurer les informations générales et les paramètres de configuration qui sont utilisés dans le module de coûts dédouanés pour la validation, les mises à jour de statut, les séquences de numéros et le comportement.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 973f23a18166abeb05bdea660ef69230d9a8c4c0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833903"
---
# <a name="landed-cost-parameters-setup"></a>Configuration des paramètres de coût au débarquement

[!include [banner](../../includes/banner.md)]

La page **paramètres de coût au débarquement** vous permet de configurer les informations générales et les paramètres de configuration qui sont utilisés dans le module de **coûts dédouanés** pour la validation, les mises à jour de statut, les séquences de numéros et le comportement. La configuration des paramètres est partagée entre les entités juridiques et peut être modifiée par un administrateur.

## <a name="open-the-landed-cost-parameters-page"></a>Ouvrez la page des paramètres de coût au débarquement

Pour travailler avec les paramètres, accédez à **Prix au débarquement \> Configurer \> Paramètres de coût au débarquement**, puis définissez les champs comme décrit dans les sous-sections suivantes.

![Page Paramètres de coût au débarquement](media/landed-cost-parameters.png "Page Paramètres de coût au débarquement")

## <a name="general-tab"></a>Onglet Général

### <a name="general-fasttab"></a>Organisateur Général

Le tableau suivant décrit les champs disponibles sur le raccourci **Général** de l’onglet **Général** de la page **Paramètres des coûts au débarquement**.

| Paramètre | Description |
|---|---|
| Utiliser les frais d’expédition | Un tarif d’expédition est défini pour une période définie et est utilisé pour l’estimation des coûts des marchandises qui utilisent plusieurs devises. Définissez cette option sur *Oui* pour utiliser un tarif d’expédition. |
| Type de taux de change | Ensemble de taux de change par défaut utilisé pour les calculs multidevises pour un voyage et les coûts de voyage. |
| Mettre à jour la quantité de la commande fournisseur | Sélectionnez ce qui se produit si un utilisateur modifie la quantité sur une ligne de commande fournisseur :<ul><li>**Accepter** – La quantité de voyage est automatiquement ajustée.</li><li>**Avertissement** – Si la ligne est attachée à un voyage, un avertissement est affiché, mais la quantité de voyage est mise à jour.</li><li>**Erreur** – Si la ligne est attachée à un voyage, un message d’erreur s’affiche et la commande fournisseur ne peut pas être mis à jour. Par conséquent, la ligne de commande doit d’abord être supprimée du voyage.</li></ul> |
| Mettre à jour le nombre de cartons automatiquement | Lorsque cette option est définie sur *Oui*, tous les cartons sont ajoutés ensemble et affichés au niveau du voyage et du conteneur. Quand il est réglé sur *Non*, le nombre de cartons est initialement réglé sur 0 (zéro) et peut être modifié manuellement si nécessaire. |

### <a name="costing-fasttab"></a>Raccourci Coût

Le tableau suivant décrit les champs disponibles sur le raccourci **évaluation des coûts** de l’onglet **Général** de la page **Paramètres des coûts au débarquement**.

| Paramètre | Description |
|---|---|
| Spécification de validation | Sélectionnez l’ajustement de valeur dans la comptabilité :<ul><li>**Total** – Un chiffre total est enregistré dans la comptabilité.</li><li>**Groupe d’articles** – L’ajustement est spécifié par groupe d’articles.</li><li>**Nombre d’articles** – L’ajustement est spécifié par article. Cette valeur fournit le plus de détails.</li></ul> |
| Autoriser les coûts nuls | Définissez cette option sur *Non* pour afficher une erreur si un utilisateur tente de publier une estimation des coûts pour une facture de voyage ou une commande fournisseur qui n’inclut pas une valeur pour le coût de voyage prévu. Le message d’erreur indique qu’un coût de 0 (zéro) ne peut pas être attribué et la validation de la facture échouera. Dans ce cas, l’utilisateur peut mettre à jour manuellement l’estimation (ou reconfigurer le coût automatique), puis soit extraire la valeur mise à jour, soit supprimer le coût s’il ne s’applique pas.<p>Définissez cette option sur *Oui* pour que le coût du voyage soit vierge. Dans ce cas, un prix de 0 (zéro) sera attribué en fonction de la zone de coût. Une facture de coût fournisseur peut ensuite être traitée par rapport au coût à prix nul lors de la réception du voyage.</p><p>Nous vous recommandons de configurer l’estimation sur l’enregistrement de coût automatique pour éviter l’apparition d’un coût à prix nul. Bien que cette estimation ne soit pas complètement exacte, elle devrait tout de même être plus précise qu’un coût nul supposé.</p> |
| Date de validation de l’ajustement | Lorsque vous enregistrez une facture de frais de voyage des comptes fournisseurs, le tableau des règlements (ajustements de stock) est également mis à jour. Sélectionnez la date définie par défaut la page **Sélectionnez les frais de voyage** pendant que vous êtes dans le journal des factures :<ul><li>**Date de transaction** – Utilisez la date du journal (date de validation).</li><li>**Date de la facture de la commande fournisseur** – Utilisez la date comptable de la facture de stock (commande fournisseur).</li><li>**Date sélectionnée** – L’utilisateur peut spécifier une date de publication. Bien que la date puisse être laissée vide, si elle est toujours vide lorsque la facture de coût est validée, l’utilisateur recevra une erreur.</li></ul> |
| Utiliser le n° document de facture d’achat | Lorsque cette option est définie sur *Oui*, les transactions de régularisation des coûts utiliseront le même N° document que celui utilisé pour la facture d’achat. Quand il est réglé sur *Non*, le système utilisera le prochain numéro disponible pour la séquence de numéros **N° document de régularisation des coûts** configurée sur l’onglet **Séquences de numéros** de la page **Paramètres de coût au débarquement**.<p>Cette option n’est effective que si l’option **Valider sur le compte de frais dans la comptabilité** est définie sur *Oui* sur l’onglet **Facture** de la page **Paramètres de la comptabilité fournisseur**.</p> |
| Bloquer la validation manuelle dans le compte de compensation | Définissez cette option sur *Oui* pour empêcher l’enregistrement sur des comptes de compensation où la transaction n’a pas été liée à un voyage en sélectionnant **Fonctions \> Sélectionnez les frais de voyage** dans le volet Actions du journal des factures fournisseur. Nous vous recommandons de définir cette option sur *Oui*, afin que le compte de voyage et de compensation puisse être correctement réglé. |
| Utiliser le compte de régularisation des frais de type de coût | Lorsque cette option est définie sur *Oui*, le compte de régularisation des charges configuré pour le code de type de coût correspondant sur la page **Codes de type de coût** sera utilisée pour comptabiliser les coûts en tant que dépense.<p>Cette option n’est effective que si l’option **Valider sur le compte de frais dans la comptabilité** est définie sur *Oui* sur l’onglet **Facture** de la page **Paramètres de la comptabilité fournisseur**. |
| Valider les ajustements comme écart | Lorsque cette option est définie sur *Oui*, il remplace la fonctionnalité standard et force les mouvements d’ajustement de stock liés aux écarts entre les coûts estimés et les coûts réels à être imputés dans un compte d’écart.<p>Lorsque cette option est définie sur *Non*, les transactions d’ajustement de stock liées aux écarts sont traitées en fonction de la configuration de la méthode de valorisation et du code de type de coût. Pour le coût standard, les écarts seront toujours imputés au compte d’écart. Pour la moyenne pondérée (WMA), les écarts seront comptabilisés soit dans le compte d’écarts, soit dans l’inventaire.</p><p>Cette option n’est effective que si l’option **Valider sur le compte de frais dans la comptabilité** est définie sur *Oui* sur l’onglet **Facture** de la page **Paramètres de la comptabilité fournisseur**.</p> |

### <a name="validation-fasttab"></a>Raccourci Validation

Le tableau suivant décrit les champs disponibles sur le raccourci **validation** de l’onglet **Général** de la page **Paramètres des coûts au débarquement**.

| Paramètre | Description |
|---|---|
| Plusieurs factures de coûts | Sélectionnez ce qui se passe si plusieurs factures sont traitées par rapport à un voyage, un folio ou un conteneur pour les mêmes frais divers.<ul><li>**Accepter** – Le système doit autoriser plusieurs factures de coûts.</li><li>**Avertissement** – Un avertissement s’affiche.</li><li>**Erreur** – Un message d’erreur s’affiche.</li></ul> |
| Plusieurs fournisseurs par folio | Sélectionnez ce qui se produit si plusieurs commandes fournisseur sont ajoutées à un folio.<ul><li>**Accepter** – Le système doit permettre l’action.</li><li>**Avertissement** – Un avertissement s’affiche, mais l’action peut toujours être effectuée.</li><li>**Erreur** – Un message d’erreur s’affiche et l’action est empêchée.</li></ul><p>Votre courtier en douane ou les lois locales peuvent imposer une valeur spécifique pour ce champ.</p> |
| Mode de tolérance de réception multiple | Sélectionnez ce qui se passe si des marchandises d’une commande fournisseur utilisant un mode de livraison différent du voyage sont ajoutées à ce voyage.<ul><li>**Accepter** – Le système doit permettre l’action.</li><li>**Avertissement** – Un avertissement s’affiche, mais l’action peut toujours être effectuée.</li><li>**Erreur** – Un message d’erreur s’affiche et l’action est empêchée.</li></ul> |
| Tolérance de plusieurs entrepôts | Sélectionnez ce qui se passe si un voyage comprend plusieurs lignes de commande qui doivent être livrées à différents entrepôts. Ces lignes de commande peuvent être réparties sur une ou plusieurs commande fournisseur.<ul><li>**Accepter** – Le système doit permettre l’action.</li><li>**Avertissement** – Un avertissement s’affiche.</li><li>**Erreur** – Un message d’erreur s’affiche.</li></ul> |
| Volume manquant | Sélectionnez ce qui se produit si un utilisateur ajoute un élément sans volume à un voyage.<ul><li>**Accepter** – Le système doit accepter l’article.</li><li>**Avertissement** – Un avertissement s’affiche.</li><li>**Erreur** – Un message d’erreur s’affiche.</li></ul><p>Si les volumes sont utilisés pour calculer et répartir les coûts, nous vous recommandons de sélectionner soit *Avertissement* ou *Erreur*.</p> |
| Fournisseur de services sans coût de voyage | Sélectionnez ce qui se passe si un utilisateur tente de traiter une facture pour un fournisseur de services qui n’a pas été lié à un voyage. <ul><li>**Accepter** – Le système doit permettre l’action.</li><li>**Avertissement** – Un avertissement s’affiche.</li><li>**Erreur** – Un message d’erreur s’affiche.</li></ul><p>Nous vous recommandons de sélectionner *Avertissement*.</p> |

### <a name="defaults-fasttab"></a>Raccourci Valeurs par défaut

Le tableau suivant décrit les champs disponibles sur le raccourci **Valeurs par défaut** de l’onglet **Général** de la page **Paramètres des coûts au débarquement**.

| Paramètre | Description |
|---|---|
| Nom de journal | Sélectionnez le journal par défaut que la fonction *Créer un journal des arrivées* doit utiliser. |
| Statut du voyage | Sélectionnez le statut qu’un voyage doit avoir avant que les utilisateurs puissent configurer un conteneur d’expédition de location pour celui-ci dans le système. Cette action se produit généralement lorsque les marchandises sont en transit ou au quai. |
| Modèle de parcours | Sélectionnez le modèle de trajet par défaut à utiliser pour les nouveaux conteneurs d’expédition de location. Vous sélectionnerez généralement un modèle de voyage qui comprend les frais de location. |
| Mouvement | Si la quantité en sur/sous pour une livraison se situe dans la tolérance définie, un journal des mouvements sera automatiquement traité. Sélectionnez le journal des mouvements par défaut à utiliser. Le champ **Compte de contrepartie** du nom du journal des mouvements sélectionné doit avoir une valeur. |
| Transférer | Lorsqu’une sous-livraison est traitée, la quantité de réception courte est transférée vers un entrepôt de sous-livraison. Sélectionnez le journal des transferts par défaut à utiliser. |
| Désactiver les commandes fournisseur ne comportant pas de voyage | Désactivez la fonctionnalité de livraison sur/sous-coût au débarquement pour les commande fournisseur qui ne sont pas associés à un voyage. |
| Désactiver les commandes fournisseur qui ne sont pas des marchandises en transit | Désactivez la fonctionnalité de livraison sur/sous-coût au débarquement pour les commande fournisseur qui n’utilisent pas la fonctionnalité marchandises en transit. |
| Période de grâce du dépassement des marchandises en transit | Indiquez le nombre de jours après la première réception d’un conteneur d’expédition pendant lesquels des excédents supplémentaires peuvent encore être effectués pour ce conteneur d’expédition. |

## <a name="status-updates-tab"></a>Onglet Mises à jour du statut

Le système utilise des valeurs de statut pour indiquer le statut de chaque voyage. Les valeurs de statut du voyage peuvent être automatiquement appliquées aux voyages via le suivi du voyage ou des travaux par lots périodiques. Vous pouvez également les appliquer manuellement en ouvrant le voyage, puis en sélectionnant un statut dans le groupe **Mise à jour du voyage** sur l’onglet **Gérer** du volet Actions. 

Vous pouvez créer autant de valeurs de statut de voyage que vous le souhaitez. Cependant, quatre d’entre eux doivent être définis comme étant utilisés à des fins spéciales sur l’onglet **Mises à jour de statut** de la page **Paramètres de coût au débarquement**. Le tableau suivant décrit les champs disponibles ici.

| Paramètre | Description |
|---|---|
| Évaluer les coûts | Sélectionnez le statut du voyage qui identifie qu’un voyage a été finalisé. |
| En transit | Sélectionnez le statut du voyage qui identifie qu’un voyage est en transit. |
| Prêt pour l’évaluation des coûts | Sélectionnez le statut du voyage qui identifie qu’un voyage est prêt pour l’évaluation des coûts. Ce statut est utilisé lorsque toutes les factures d’achat de stock et les factures de frais de voyage où le champ **Crédit sur le coût du voyage** est défini sur *fournisseur* ont été traités pour le voyage. Les voyages qui échouent au processus chiffré auront un statut de *Prêt pour l’évaluation des coûts*.|
| Coût prédéfini | Sélectionnez le statut du voyage qui identifie qu’un voyage est en préparation pour l’évaluation des coûts. Ce statut est utilisé lorsqu’une nouvelle transaction de coût est ajoutée à un voyage après qu’il a déjà été évalué. De nouvelles transactions de coût peuvent être ajoutées à un voyage précédemment chiffré lorsqu’une deuxième facture de fret ou des surestaries imprévus sont reçus. Ce statut est automatiquement appliqué lorsqu’un nouveau coût de voyage est ajouté à un voyage chiffré. |

## <a name="voyage-creator-tab"></a>Onglet Créateur de voyage

Le tableau suivant décrit les sections sur l’onglet **Créateur de voyage** de la page **Paramètres de coût au débarquement**.

| Section | Description |
|---|---|
| Tolérances | Les champs **Tolérance de volume extérieur** et **Tolérance de poids extérieur** définissent des seuils au-dessus desquels les marchandises sont considérées comme en sur-volume et en surpoids. Lorsqu’un utilisateur ajoute des marchandises sur la page **Éditeur de voyage**, si le volume ou le poids dépasse la valeur que vous avez définie ici, le système affiche un avertissement. La valeur de chaque champ est exprimée en pourcentage du volume ou du poids maximum défini pour le type de conteneur d’expédition concerné. Nous recommandons que la valeur soit comprise entre 5 et 10 pour cent du volume ou du poids maximum. |
| Paramétrage de création du folio | Le système peut créer plusieurs folios pendant le processus de création du voyage. Utilisez cette section pour définir quand un folio doit être créé. Pour chaque ligne de cette section, le système vérifiera la table et le champ spécifiés et créera un folio pour chaque valeur de champ unique. |

## <a name="cost-estimates-tab"></a>Onglet Estimations des coûts

L’onglet **Estimations de coût** de la page **Paramètres de coût au débarquement** fournit un seul champ : **Version d’évaluation des coûts par défaut**. Ce champ s’applique uniquement lorsque la méthode de calcul des coûts est *Coût standard*. Sélectionnez la version de tarification par défaut à utiliser pour la tâche périodique *Mise à jour du prix de revient de l’article*. Vous devrez peut-être modifier ce paramètre chaque fois qu’un nouvel exercice comptable commence.

## <a name="inventory-dimensions-tab"></a>Onglet Dimensions de stock

Vous utilisez l’onglet **Dimensions de stock** de la page **Paramètres de coût au débarquement** pour contrôler les dimensions de stock disponibles qui doivent être affichées par défaut sur chaque page de coût au débarquement où les dimensions sont utilisées.

Sélectionnez une dimension, puis définissez l’option **Lignes de voyage**, **Marchandises en transit**, et/ou **Estimations de coût** sur *Oui* pour chaque page où cette dimension doit être affichée par défaut. Répétez cette étape pour les autres dimensions, si nécessaire.

Les paramètres de cet onglet définissent les dimensions par défaut pour chaque page désignée dans les entités juridiques. Cependant, les utilisateurs qui travaillent sur l’une des pages désignées peuvent remplacer les dimensions par défaut en sélectionnant **Stock \> Afficher les dimensions** dans le volet Actions.

## <a name="number-sequences-tab"></a>Onglet Souches de numéros

L’onglet **Souche de numéros** de la page **Paramètres de coût au débarquement** répertorie chaque type de Souche de numéros de référence requis par les coûts au débarquement, mais qui n’est pas partagée entre les entités juridiques. Pour chaque référence de la liste, sélectionnez un code souche de numéros.

> [!NOTE]
> Dans une configuration multi-sociétés, différentes Souche de numéros doivent être créées pour chaque société (entité juridique).

## <a name="shared-number-sequences-tab"></a>Onglet Souches de numéros partagées

L’onglet **Souche de numéros partagée** de la page **Paramètres de coût au débarquement** répertorie chaque type de Souche de numéros de référence requis par les coûts au débarquement, mais qui est partagée entre les entités juridiques pour les coûts au débarquement. Actuellement, il n’y a qu’une seule Souche de numéros dans la liste. Cette Souche de numéros est utilisée pour l’ID de voyage.

Sur la page **Tous les voyages**, les utilisateurs peuvent afficher tous les voyages dans toutes les entités juridiques. Cependant, pour modifier et traiter un voyage, les utilisateurs doivent appartenir à l’entité juridique de l’enregistrement sélectionné.

## <a name="feature-visibility-tab"></a>Onglet Visibilité des fonctionnalités

Le coût au débarquement ajoute des fonctionnalités (champs et fonctions) à plusieurs pages fréquemment utilisées dans Microsoft Dynamics 365 Supply Chain Management. Ces pages incluent des pages liées aux données de base du fournisseur, aux produits lancés, aux commande fournisseur, aux ordres de transfert et à la configuration de l’entrepôt. Si vous utilisez le coût au débarquement, vous devez rendre ces fonctionnalités visibles partout avant de pouvoir en bénéficier. Si vous n’utilisez pas le coût fixe, vous pouvez masquer les fonctionnalités pour les garder à l’écart.

Sur l’onglet **Visibilité des fonctionnalités** de la page **Paramètres de coût au débarquement**, définissez l’option **Activer** sur *Oui* pour rendre visibles les fonctionnalités de coût au débarquement partout où elles sont disponibles. Réglez-le sur *Non* pour masquer les fonctionnalités sur les pages communes en dehors du coût au débarquement. Cependant, même lorsque l’option est définie sur *Non*, le module lui-même, y compris la page **Paramètres de coût au débarquement**, restera disponible pour les utilisateurs disposant des autorisations appropriées pour y accéder.
