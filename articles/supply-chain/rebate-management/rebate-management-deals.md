---
title: Accords de gestion des remises
description: Cette rubrique décrit comment créer des accords de gestion des remises. Les accords sont utilisés pour contrôler différentes méthodes et bases de calcul des remises et des redevances. Ils comprennent des règles pour les inclusions et les exclusions.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 5b8a1beae80ad63f26cd1b532d1d6026a5b38a8701c9c1d0aadfee5da8965477
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716490"
---
# <a name="rebate-management-deals"></a>Accords de gestion des remises

[!include [banner](../includes/banner.md)]

Les accords de gestion des remises sont utilisés pour contrôler différentes méthodes et bases de calcul des remises et des redevances. Ils comprennent des règles pour les inclusions et les exclusions. Il existe trois types d’accords de gestion des remises : les remises client, les redevances client et les remises fournisseur. Les trois types utilisent des paramètres similaires. Cette rubrique met en évidence les différences qui existent.

## <a name="create-a-deal"></a>Créer un accord

1. Accédez à **Gestion des remises \> Accords de gestion des remises \> Tous les accords de gestion des remises**. Sur la page de liste **Tous les accords de gestion des remises**, vous pouvez créer et utiliser les trois types d’accord.

    Autrement, suivez une des étapes suivantes : Dans chaque cas, la page de liste qui apparaît fournit tous les mêmes paramètres que la page de liste **Tous les accords de gestion des remises**, mais elle est filtrée pour afficher les accords d’un seul type.

    - Accédez à **Gestion des remises \> Accords de gestion des remises \> Accords de remise client** pour créer uniquement des accords de remise client.
    - Accédez à **Gestion des remises \> Accords de gestion des remises \> Accords de redevance client** pour créer uniquement des accords de redevance client.
    - Accédez à **Gestion des remises \> Accords de gestion des remises \> Accords de remise fournisseur** pour créer uniquement des accords de remise fournisseur.

1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer un accord**, définissez les champs suivants :

    - **Accord de gestion des remises** : si vous avez [configuré une souche de numéros](rebate-management-parameters.md) pour les accords de remise, ce champ est automatiquement défini sur un ID unique généré par le système. Sinon, saisissez un ID unique.
    - **Description** : entrez une description de l’accord.
    - **Module** : sélectionnez le type de partenaire auquel l’accord s’applique (*Client* ou *Fournisseur*). En fonction de la page à partir de laquelle vous avez commencé, ce champ peut être défini automatiquement sur le type d’accord sélectionné. Dans ce cas, ce champ est en lecture seule.
    - **Type** : sélectionnez le type d’accord (*Remise* ou *Redevance*). En fonction de la page à partir de laquelle vous avez commencé, ce champ peut être défini automatiquement sur le type d’accord sélectionné. Dans ce cas, ce champ est en lecture seule.
    - **Rapprochement par** : sélectionnez le mode de calcul et de rapprochement de l’accord :

        - *Accord* : une seule remise doit être traitée pour toutes les remises et déductions de l’accord.
        - *Ligne* : les remises doivent être traitées pour chaque ligne d’un accord.

    - **Profil de validation** : sélectionnez le [profil de validation](rebate-management-posting.md) à utiliser pour les transactions où l’accord s’applique. Ce champ n’est disponible que si le champ **Rapprochement par** est défini sur *Accord*. S’il est défini sur *Ligne*, vous attribuerez le profil plus tard, pour chaque ligne que vous ajoutez à l’accord.
    - **Profil de validation pour la garantie** : sélectionnez le [profil de validation](rebate-management-posting.md) à utiliser pour les transactions de garantie. Les profils de validation ne sont requis pour les transactions de garantie que si la garantie s’applique à une redevance. Sinon, bien qu’un profil de validation ne soit pas obligatoire, si aucun profil de validation n’est spécifié, une erreur sera affichée lors de la validation des garanties. Ce champ n’est disponible que si le champ **Type** est défini sur *Redevance*. 
    - **Résultat de remise** : sélectionnez le mode de paiement de la remise ou de la redevance :

        - *Financier* : générer un avoir financier ou une note de débit de comptabilité fournisseur, afin que l’argent puisse être payé ou reçu plus tard. Notez que les dispositions **peuvent** être utilisées avec des remises lorsque cette option est sélectionnée. Cette option est la seule disponible lorsque le champ **Type** est défini sur *Redevance*.
        - *Article* : générer une commande client pour les articles en fonction de la configuration de l’accord. Sur cette commande client, un prix de 0 (zéro) est attribué à chaque article. Notez que les dispositions **ne peuvent pas** être utilisées avec des remises lorsque cette option est sélectionnée.

    - **Devise de la remise** : sélectionnez la devise à utiliser lorsque la remise, la déduction ou la redevance est payée.
    - **Notes de document** : entrez des notes sur l’accord, si nécessaire.
    - **Garantie cumulative** : vous pouvez définir cette option sur *Oui* seulement si le champ **Type** est défini sur *Redevance*. Cette option affecte le calcul des paiements de déduction garantie. Voici un exemple :

        - La garantie de l’accord correspond à la vente d’une valeur qui entraînera un paiement de 10 000 USD par trimestre.
        - L’organisation qui vend les marchandises vend une valeur qui entraîne le paiement d’une déduction de 12 000 USD au premier trimestre. Le résultat est une redevance 12 000 USD qui est payée, moins la garantie de 10 000 USD.
        - Si l’option **Garantie cumulative** est définie sur *Oui*, les 2 000 USD supplémentaires de redevance payées au premier trimestre s’appliquent au deuxième trimestre. Par conséquent, le client dispose d’une garantie de 8 000 USD (la garantie de 10 000 USD moins le paiement supplémentaire de 2 000).
        - Au deuxième trimestre, vous enregistrez des ventes qui déclenchent une redevance de 5 000 USD.
        - Le système identifie un paiement de 3 000 USD (la garantie de 8 000 USD moins les 5 000 USD de redevance payée).
        - Si l’option **Garantie cumulative** est définie sur *Non*, les 10 000 USD complets sont garantis chaque trimestre. Cette garantie correspond à une proposition de paiement de 5 000 USD au deuxième trimestre (la garantie de 10 000 USD moins les 5 000 USD de redevance payés).

1. Cliquez sur **OK** pour créer l’accord et fermer la boîte de dialogue.

Cette procédure crée le niveau d’en-tête du nouvel accord. Ensuite, vous ajouterez des lignes à l’accord.

## <a name="add-lines-to-a-deal"></a>Ajouter des lignes à un accord

Une fois que vous avez créé un accord comme décrit dans la section précédente, vous pouvez l’ouvrir à partir de la page de liste. Vous pouvez alors y ajouter des lignes pour identifier les clients ou fournisseurs, les articles, les délais, une base et les méthodes de calcul de l’accord. Un accord peut avoir une ou plusieurs lignes. Si un accord comporte plusieurs lignes, elles sont généralement du même type, ou les mêmes paramètres leur sont associés. Tant que vous n’ajoutez pas de lignes à un accord, celui-ci n’aura aucun effet.

1. Ouvrez la page de liste des accords de remise appropriée, comme décrit dans la section précédente.
1. Trouvez et ouvrez l’accord que vous souhaitez utiliser.
1. Sur le raccourci **Gestion des remises**, sélectionnez l’un des boutons suivants pour ajouter une ligne d’accord à la grille :

    - **Ajouter une ligne** : ajouter une nouvelle ligne d’accord vide.
    - **Copier une ligne** : si une ligne d’accord existante ressemble à la ligne d’accord que vous souhaitez ajouter, vous pouvez sélectionner ce bouton pour la copier et en ajouter une copie. La nouvelle ligne d’accord comprendra tous les paramètres des détails de gestion des remises associés. Vous pouvez ensuite modifier les paramètres. Par exemple, vous mettrez généralement à jour la relation d’article et le pourcentage de remise.

1. Dans la nouvelle ligne d’accord, définissez les champs suivants :

    - **Numéro de gestion des remises** : si vous avez [configuré une souche de numéros](rebate-management-parameters.md) pour les numéros de gestion des remises, ce champ est automatiquement défini sur un ID unique généré par le système. Sinon, saisissez un ID unique.
    - **Type** : le type d’accord auquel s’applique la ligne, (*Remise* ou *Redevance*). La valeur est copiée à partir de l’en-tête et ne peut pas être modifiée.
    - **Description** : entrez une description de la ligne d’accord.
    - **Société** : sélectionnez la société (entité juridique) à laquelle s’applique la ligne d’accord. Lors du traitement, les utilisateurs ne peuvent traiter que les lignes d’accord affectées à la société qu’ils utilisent actuellement. La page de liste **Accords de remise client** fournit une vue multi-sociétés, basée sur l’accès sécurisé de l’utilisateur. Cependant, vous ne pouvez modifier et traiter les remises que pour la société que vous utilisez actuellement.
    - **Code de compte** : sélectionnez l’étendue des clients ou des fournisseurs auxquels s’applique la ligne d’accord :

        - *Table* : la ligne d’accord s’applique à un client ou à un fournisseur spécifique.
        - *Groupe* : la ligne d’accord s’applique à un groupe de clients ou de fournisseurs. Pour plus d’informations sur le paramétrage des groupes, voir [Groupes de gestion des remises](rebate-management-groups.md).
        - *Tous* : la ligne d’accord s’applique à tous les clients ou fournisseurs.

    - **Relation de compte** : si vous avez sélectionné *Table* dans le champ **Code compte**, sélectionnez le client ou le fournisseur auquel s’applique l’accord. Si vous avez sélectionné *Groupe*, choisissez le groupe de clients ou de fournisseurs. Si vous avez sélectionné *Tous*, ce champ n’est pas disponible.
    - **Code article** : sélectionnez l’étendue des articles auxquels s’applique la ligne d’accord :

        - *Table* : la ligne d’accord s’applique à un article spécifique.
        - *Groupe* : la ligne d’accord s’applique à un groupe d’articles. Pour plus d’informations sur le paramétrage des groupes, voir [Groupes de gestion des remises](rebate-management-groups.md).
        - *Tous* – La ligne d’accord s’applique à tous les articles.

    - **Relation d’article** : si vous avez sélectionné *Table* dans le champ **Code article**, sélectionnez l’article auquel s’applique la ligne d’accord. Si vous avez sélectionné *Groupe*, choisissez le groupe d’articles. Si vous avez sélectionné *Tous*, ce champ n’est pas disponible.
    - **Type d’unité** – Sélectionnez le type d’unité qui s’applique à la ligne de transaction (*Unité de stock* ou *Unité en poids variable*). Notez que ce champ peut être vide pour les enregistrements plus anciens. Dans ce cas, la valeur *Unité de stock* est supposée.
    - **(Paramètres de gestion des stocks)**  : dans les champs restants de la ligne d’accord, spécifiez des valeurs pour les paramètres de gestion des stocks qui seront utilisés pour définir les articles inclus dans l’accord (tels que la taille, la couleur, le style, le site et l’entrepôt). Pour ajouter ou supprimer les dimensions, sélectionnez **Afficher les dimensions** dans le volet Actions.

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Si vous souhaitez limiter davantage l’ensemble des articles auxquels s’applique une ligne d’accord, sélectionnez la ligne, puis sur le raccourci **Gestion des remises**, sélectionnez **Filtre** pour ouvrir une boîte de dialogue **Recherche** standard.
1. Pour chaque ligne d’accord que vous ajoutez, définissez les détails du calcul et d’autres détails sur le raccourci **Détails de la gestion des remises**, comme décrit dans la section suivante.

## <a name="add-rebate-management-details-to-a-deal-line"></a>Ajouter les détails de la gestion des remises à une ligne d’accord

Pour chaque ligne de votre accord, vous devez définir les détails sur le raccourci **Détails de la gestion des remises**. Sélectionnez d’abord la ligne de l’accord sur le raccourci **Gestion des remises**. Définissez ensuite les valeurs de cette ligne d’accord en utilisant les différents onglets du raccourci **Détails de la gestion des remises**. Les sous-sections suivantes décrivent comment utiliser chaque onglet.

### <a name="settings-on-the-general-tab"></a>Paramètres de l’onglet Général

L’onglet **Général** du raccourci **Détails de la gestion des remises** vous permet de configurer la base et la méthode de calcul de la ligne d’accord sélectionnée. Cette configuration contrôle si un achat minimum est requis, les profils de validation associés à la ligne d’accord et les détails du calcul. Le tableau suivant décrit les champs disponibles.

| Champ | Description |
|---|---|
| Méthode de calcul | Sélectionnez la méthode à utiliser lorsque la ligne d’accord sélectionnée est combinée avec d’autres lignes d’accord (*Par paliers*, *Cumulatif*, *Roulant*, ou *Total*). La valeur de ce champ peut considérablement affecter le résultat de vos calculs de remise. Pour une description complète de chaque méthode et des exemples qui montrent comment elle affecte le calcul de la remise, consultez la section [Méthodes de calcul des lignes d’accord](#calc-methods), plus loin dans cette rubrique. |
| Base | Sélectionnez si la remise est appliquée en fonction de la quantité (c’est-à-dire du nombre total d’unités achetées ou vendues) ou de la valeur (c’est-à-dire du prix total des produits achetés ou vendus). |
| Type de transaction | <p>Sélectionnez le point du processus où le calcul doit avoir lieu :</p><ul><li>*Commande* : utilisez la quantité ou la valeur commandée comme base de calcul.</li><li>*Livraison* : utilisez la quantité ou la valeur livrée comme base de calcul.</li><li>*Facturation* : utilisez la quantité ou la valeur facturée comme base de calcul.</li></ul> |
| Unité | Si vous avez sélectionné *Quantité* dans le champ **Base**, sélectionnez l’unité dans laquelle la quantité doit être spécifiée. |
| Montant minimum | Entrez le montant minimum à payer par période. Vous pouvez saisir une valeur négative pour autoriser des montants de remise négatifs si les notes de crédit dépassent les ventes de la période. |
| Principe de réduction des remises | Sélectionnez le [Principe de réduction des remises](rebate-reduction-principle.md) qui s’applique à la ligne d’accord. |
| Numéro de variante | Si la ligne d’accord s’applique à un article comportant des variantes, sélectionnez la variante à laquelle s’applique la ligne d’accord. |
| Base de la remise fournisseur | <p>Ce champ s’affiche uniquement pour les remises fournisseur (c’est-à-dire les accords où le champ **Module** est défini sur *Fournisseur*). Sélectionnez la base de la remise fournisseur :</p><ul><li>*Commande fournisseur* : la remise que le fournisseur reçoit est basée sur la quantité ou la valeur figurant sur la commande fournisseur.</li><li>*Commande client* : le fournisseur ne reçoit de remise qu’après la vente des marchandises. La remise est basée sur la quantité ou la valeur de la commande client.</li></ul> |
| Base de prix | <p>Ce champ s’affiche uniquement pour les remises fournisseur (les accords où le champ **Module** est défini sur *Fournisseur*). Si vous avez sélectionné *Commande client* dans le champ **Base de la remise fournisseur**, sélectionnez la base de prix applicable :</p><ul><li><p>*FIFO* : la tâche périodique **Calculer le prix d’achat FIFO** doit être exécutée pour calculer la remise. (Pour exécuter la tâche, accédez à **Gestion des remises \> Tâches périodiques \> Calculer le prix d’achat FIFO**.) Une règle Premier entré, premier sorti (FIFO) sera utilisée pour calculer la valeur du stock vendu. Cette valeur sera ensuite utilisée pour calculer les remises fournisseur. Voici un exemple :</p><ul><li>**Stock vendu :** 1000 unités à 3,00 USD chacune = 3 000 USD</li><li>**Prix d’achat actuel, basé sur le FIFO :** 2,00 USD</li><li>**Calcul de travail :** *Unités vendues* × *Prix d’achat actuel* = 1 000 × 2,00 USD = 2 000 USD</li></ul></li><li><p>*Dernier prix d’achat* : la valeur de la dernière transaction d’achat sera utilisée pour calculer les remises fournisseur. Voici un exemple :</p><ul><li>**Stock vendu :** 1000 unités à 3,00 USD chacune = 3 000 USD</li><li>**Dernier prix d’achat :** 2,00 USD</li><li>**Calcul de travail :** *Unités vendues* × *Dernier prix d’achat* = 1 000 × 2,00 USD = 2 000 USD</li></ul></li><li><p>*Prix d’achat moyen* : la valeur moyenne pondérée des derniers *X* mois sera utilisée pour calculer les remises fournisseur. Si vous sélectionnez cette option, vous devez entrer le nombre de mois dans le champ **Nombre de mois** (qui n’est disponible que lorsque le champ **Base de prix** est défini sur *Prix d’achat moyen*). Voici un exemple :</p><ul><li>**Stock vendu :** 1000 unités à 3,00 USD chacune = 3 000 USD</li><li>**Prix d’achat moyen :** 2,00 USD</li><li>**Calcul de travail :** *Unités vendues* × *Prix d’achat moyen* = 1 000 × 2,00 USD = 2 000 USD</li></ul></li><li><p>*Prix de vente* : le prix de vente sera utilisé pour calculer les remises fournisseur. Voici un exemple :</p><ul><li>**Stock vendu :** 1000 unités à 3,00 USD chacune = 3 000 USD</li><li>**Prix d’achat moyen :** 2,00 USD</li><li>**Calcul de travail :** *Unités vendues* × *Prix de vente* = 1 000 × 3,00 USD = 3 000 USD</li></ul></li></ul> |
| Nombre de mois | Ce champ s’affiche uniquement pour les remises fournisseur (les accords où le champ **Module** est défini sur *Fournisseur*). Si vous avez sélectionné *Prix d’achat moyen* dans le champ **Base de prix**, entrez le nombre de mois à utiliser. |
| Profil de validation | Sélectionnez le [profil de validation](rebate-management-posting.md) qui s’applique à la ligne d’accord sélectionnée. Ce profil est utilisé uniquement lorsque le champ **Rapprochement par** sur l’en-tête de l’accord est défini sur *Ligne*. Si le champ **Rapprochement par** est défini sur *Accord*, le profil de validation défini sur l’en-tête de l’accord est toujours utilisé. Si aucun profil de validation n’est défini sur la ligne d’accord, le profil de validation défini sur l’en-tête de l’accord est utilisé. |
| Profil de validation pour garantie | Ce champ fonctionne comme le champ **Profil de validation**, mais il ne s’applique qu’aux redevances. |
| Type de paiement | Le type de paiement pour le profil de validation sélectionné pour l’accord. |
| Taxe incluse | Sélectionnez si la transaction est TTC. L’inclusion de la taxe n’est pertinente que lorsque le champ **Base** est défini sur *Valeur*. Le montant de la facture sera utilisé comme montant TTC. Si le calcul de la remise est basé sur un pourcentage, le système multipliera le pourcentage de remise par le montant TTC. Notez que le calcul utilise la valeur de la taxe provenant de la ligne d’accord. |
| Inclure les avoirs | <p>Définissez cette option sur *Oui* pour inclure les avoirs dans le calcul de la remise.</p><p>Si vous définissez cette option sur *Oui*, l’effet varie en fonction de la valeur du champ **Type de transaction** :</p><ul><li>Si le champ **Type de transaction** est défini sur *Facturation*, le calcul prendra en compte les avoirs. Cette configuration est la configuration habituelle.</li><li>Si le champ **Type de transaction** est défini sur *Commande*, le calcul prendra en compte à la fois les commandes client qui ont des valeurs négatives et les commandes retournées ouvertes.</li></ul> |
| Montant avec remise | Définissez cette option sur *Oui* pour baser le calcul sur le montant avec remise de l’article ou des articles dans les cas où des remises sur la ligne d’accord sont accordées. |
| Factures payées uniquement | Définissez cette option sur *Oui* si le calcul doit prendre en compte uniquement les factures entièrement payées. (En d’autres termes, les remises ne seront pas calculées pour les factures partiellement payées.) Cette option n’est disponible que lorsque le champ **Type de transaction** est défini sur *Facturation*. |
| Inclure les factures financières | Définissez cette option sur *Oui* pour inclure les factures financières dans le calcul. Les factures financières ne peuvent être incluses que pour les lignes d’accord où le champ **Code article** est défini sur *Tous*. |
| Inclure l’escompte de règlement | Définissez cette option sur *Oui* pour réduire la remise du montant du premier escompte de règlement. On suppose que l’organisation prendra le premier escompte de règlement. Définissez cette option sur *Non* pour permettre l’utilisation ultérieure de l’escompte de règlement. |
| Notes de document | Saisissez les notes qui devront être utilisées comme texte de transaction sur les lignes du journal des transactions de remise. |

### <a name="settings-on-the-dates-tab"></a>Paramètres de l’onglet Dates

Les paramètres de l’onglet **Dates** du raccourci **Détails de la gestion des remises** définissent la fréquence et le moment des calculs spécifiés sur l’onglet **Général**. Ils déterminent comment les calculs se produisent au moment du traitement.

Cet onglet vous permet de spécifier la plage de dates pour laquelle la ligne d’accord sélectionnée est valide, ainsi que la fréquence de calcul. Vous pouvez également spécifier si la garantie doit être validée et quand.

Vous pouvez utiliser les boutons sur la barre d’outils pour ajouter des lignes de date à la grille ou en supprimer. S’il existe plusieurs lignes de dates, les plages de dates valides ne doivent pas se chevaucher. Sinon, vous recevrez un message d’erreur lorsque vous tenterez de sauvegarder l’accord.

Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque ligne de date.

| Champ | Description |
|---|---|
| Date de début | Saisissez la première date à laquelle la ligne de date s’applique. Si les dates « de » et « à » sont spécifiées dans l’en-tête de l’accord, elles sont utilisées comme valeurs par défaut pour chaque nouvelle ligne de date. |
| Au | Saisissez la dernière date à laquelle la ligne de date s’applique. Si les dates « de » et « à » sont spécifiées dans l’en-tête de l’accord, elles sont utilisées comme valeurs par défaut pour chaque nouvelle ligne de date. |
| Par | Spécifiez la fréquence à laquelle la ligne d’accord doit être calculée. Entrez un entier ici, puis sélectionnez une unité dans le champ **Cumuler par**. Par exemple, pour calculer toutes les deux semaines, définissez le champ **Tous les** sur *2* et le champ **Cumuler par** sur *Semaines*. |
| Cumuler par | Sélectionnez l’unité qui s’applique au paramètre **Tous les**. Sélectionnez *Durée de vie* pour calculer sur toute la durée de vie de la ligne d’accord. Sélectionnez *Période personnalisée* pour sélectionner une période définie dans la comptabilité. Dans ce cas, vous devez également définir le champ **Type de période**. |
| Type de période | Ce champ n’est disponible que si le champ **Cumuler par** est défini sur *Période personnalisée*. Les valeurs disponibles pour la sélection proviennent des types de période définis dans la comptabilité. |
| Premier jour de la semaine | Précisez comment les semaines sont identifiées pour la période. Ce champ n’est disponible que si le champ **Cumuler par** est défini sur *Semaines*. |
| Périodicité de revendication | Spécifiez la fréquence à laquelle les remises peuvent être réclamées pour la ligne d’accord. Entrez un entier ici, puis sélectionnez une unité dans le champ **Modalité de revendication**. |
| Modalité de revendication | Sélectionnez l’unité qui s’applique au paramètre **Périodicité de revendication**. Sélectionnez *Durée de vie* pour autoriser les revendications une seule fois pendant toute la durée de vie de la ligne d’accord. Sélectionnez *Période personnalisée* pour sélectionner une période définie dans la comptabilité. Dans ce cas, vous devez également définir le champ **Type de période de revendication**. |
| Type de période de revendication | Ce champ n’est disponible que si le champ **Modalité de revendication** est défini sur *Période personnalisée*. Les valeurs disponibles pour la sélection proviennent des types de période définis dans la comptabilité. |
| Traitement à la validation | Cochez cette case si la ligne de revendication doit être traitée au moment de la validation. Cette option n’est disponible que pour les lignes d’accord où le champ **Type de transaction** sur l’onglet **Général** est défini sur *Livraison* ou *Facturation*. Pour les provisions, la provision sera validée lors de la génération de la note de livraison ou de la facture. |
| Garantie par | Ce champ s’applique uniquement aux accords de redevance. Précisez à quelle fréquence la garantie de la redevance doit être calculée pendant la période définie par le paramètre **Cumuler par**. Entrez un entier ici, puis sélectionnez un délai de paiement dans le champ **Garantie payée**. |
| Garantie payée | <p>Ce champ s’applique uniquement aux accords de redevance. Il fonctionne en conjonction avec le champ **Garantie par** pour définir la fréquence du calcul de la garantie. Vous devez sélectionner l’une des valeurs suivantes :</p><ul><li><p>*Début de période* : la garantie est payée au début de la période contractuelle définie pour la ligne de date. La garantie complète est traitée en premier. Seule la valeur des redevances excédant le montant garanti est comptabilisée en tant que redevance. Voici un exemple :</p><ul><li>**Garantie minimum :** 10 000 USD sur deux mois.</li><li>**Mois 1 :** 10 000 USD ont été validés comme garantie, et 0 USD ont été validés en redevance.</li><li>**Mois 2 :** 2 000 USD ont été validés en redevance, et 0 USD ont été validés en garantie.</li><li>**Calcul de travail :** *Garantie restante* - *Redevances validées* = 0 USD - 2 000 USD = - 2 000 USD.</li></ul><p>Étant donné qu’un paiement de redevance de 2 000 USD est requis, un journal est créé pour 2 000 USD.</p><p>**Remarque :** la garantie doit être calculée et validée avec la provision pour déductions pour la première période.</p></li><li><p>*Fin de période* : la garantie n’est payée qu’à la fin du contrat de déductions, comme défini sur la ligne de date. Voici un exemple :</p><ul><li>**Garantie minimum :** 10 000 USD sur deux mois.</li><li>**Mois 1 :** 5 000 USD ont été validés en tant que redevances et un journal a été créé.</li><li>**Mois 2 :** 7 000 USD ont été validés en tant que redevances et un journal a été créé.</li><li>**Calcul de travail :** étant donné que les redevances dépassent le montant de la garantie, 0 USD sont comptabilisés en garantie.</li></ul><p>**Remarque :** la garantie doit être calculée et validée uniquement avec la transaction de déductions et remises pour la période finale.</p></li></ul> |
| Garantie minimum | Ce champ s’applique uniquement aux accords de redevance. Saisissez le montant minimum de la garantie pour une redevance, dans la devise définie dans l’en-tête de l’accord. |

### <a name="settings-on-the-lines-tab"></a>Paramètres de l’onglet Lignes

L’onglet **Lignes** du raccourci **Détails de la gestion des remises** vous permet de définir les lignes de calcul de la ligne d’accord sélectionnée. Chaque ligne de calcul établit un seuil de quantité ou de valeur, et un montant de rémunération ou des articles associés. Le champ **Base** de l’onglet **Général** spécifie si chaque ligne de calcul est basée sur une quantité ou une valeur.

Vous pouvez utiliser les boutons sur la barre d’outils pour ajouter des lignes de calcul à la grille ou en supprimer. Vous pouvez avoir n’importe quel nombre de lignes de calcul. Cependant, s’il existe plusieurs lignes de calcul, les plages de quantité ou de valeur « à » et « de » ne doivent pas se chevaucher.

Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque ligne de calcul.

| Champ | Description |
|---|---|
| Quantité/valeur de départ | Saisissez la quantité ou la valeur minimale à laquelle s’applique la ligne de calcul. |
| Quantité/valeur de fin | Saisissez la quantité ou la valeur maximale à laquelle s’applique la ligne de calcul. |
| Méthode de gestion des remises | <p>Ce champ n’est disponible que pour les accords où le champ **Résultat de la remise** de l’en-tête est défini sur *Financier*. Sélectionnez la méthode à utiliser pour calculer la remise :</p><ul><li>*Fixe* : un montant forfaitaire est utilisé pour la ligne.</li><li>*Pourcentage* : un pourcentage du montant de la vente est utilisé.</li><li>*Taux* : un montant forfaitaire par commande est utilisé.</li></ul><p>**Important :** nous vous recommandons vivement d’utiliser la même méthode pour chaque ligne de calcul sur l’onglet **Lignes**. Si une nouvelle méthode est requise, créez une nouvelle ligne d’accord. N’oubliez pas que vous pouvez utiliser le bouton **Copier une ligne** du raccourci **Gestion des remises** pour créer une nouvelle ligne d’accord à partir d’une ligne d’accord existante.</p><p>**Remarque :** si le champ **Résultat de la remise** est défini sur *Article*, ce champ est toujours défini sur *Fixe*. Pour plus d’informations sur la spécification des articles, consultez le texte qui suit ce tableau. |
| Montant de gestion des remises | Ce champ n’est disponible que pour les accords où le champ **Résultat de la remise** de l’en-tête est défini sur *Financier*. Entrez le montant à utiliser pour calculer la remise, en fonction de la méthode que vous avez sélectionnée dans le champ **Méthode de gestion des remises**. |

Comme indiqué dans le tableau précédent, pour les accords où le champ **Résultat de la remise** de l’en-tête est défini sur *Article*, vous devez spécifier les articles qui seront fournis pour chaque ligne de calcul sur l’onglet **Lignes**. Pour spécifier des articles, procédez comme suit :

1. Sur l’onglet **Lignes**, créez la ligne de calcul requise si elle n’existe pas et sélectionnez-la.
1. Si l’accord n’a pas été enregistré depuis que vous avez créé la ligne de calcul, sélectionnez **Enregistrer** dans le volet Actions.
1. Dans l’onglet **Lignes**, sélectionnez **Articles**.
1. Sur la page **Articles**, utilisez les boutons du volet Actions pour ajouter des articles à la grille ou en supprimer, selon les besoins. Pour chaque ligne, définissez les champs suivants :

    - **Numéro d’article** : sélectionnez l’article qui sera fourni.
    - **(Autres dimensions)**  : si vous devez utiliser plus de dimensions pour définir l’article (par exemple, la configuration de l’article, la taille, la couleur, le style, le site ou l’entrepôt), spécifiez-les. Pour ajouter ou supprimer des dimensions disponibles, sélectionnez **Afficher les dimensions** dans le volet Actions.
    - **Quantité** : entrez la quantité qui sera fournie une fois que le seuil de la ligne de calcul sélectionnée sera atteint.
    - **Unité** : sélectionnez l’unité en laquelle est spécifiée la valeur **Quantité**.
    - **Multiple** : ce champ fonctionne conjointement avec le champ **Quantité**. Par exemple, sur une ligne d’article, vous définissez le champ **Quantité** sur *2* et le champ **Multiple** sur *100*. Si vous avez alors une quantité totale de commande client de 150, deux des articles seront gratuits (deux pour 100).

### <a name="settings-on-the-inventory-dimensions-tab"></a>Paramètres de l’onglet Dimensions de stock

L’onglet **Dimensions de stock** du raccourci **Détails de la gestion des remises** affiche toutes les valeurs de dimension disponibles pour le produit spécifié pour la ligne d’accord sélectionnée. Il comprend des dimensions qui ne figurent pas sur le raccourci **Gestion des remises**. Vous ne pouvez modifier les valeurs que pour les dimensions qui s’appliquent au produit sélectionné.

Vous pouvez ajouter d’autres dimensions à la grille sur le raccourci **Gestion des remises** en sélectionnant **Afficher les dimensions** dans le volet Actions.

## <a name="calculation-methods-for-deal-lines"></a><a name="calc-methods"></a>Méthodes de calcul des lignes d’accord

Chaque fois que vous définissez les détails de l’une de vos lignes d’accord, comme décrit dans la section précédente, vous devez sélectionner la méthode de calcul pour cette ligne. Cette section explique chaque méthode de calcul et fournit des exemples qui montrent comment chaque méthode calcule la remise totale pour les commandes et les lignes d’accord. Dans ces exemples, les commandes et les lignes d’accord sont identiques. Seules les méthodes de calcul diffèrent.

### <a name="stepped-calculation-method"></a>Méthode de calcul par paliers

La méthode de calcul par paliers calcule, étape par étape, chaque ligne d’accord contribuant progressivement à la remise jusqu’à ce que la quantité ou la valeur des ventes soit atteinte. Les paliers peuvent être basés soit sur la quantité, soit sur la valeur des marchandises vendues, selon le réglage du champ **Base** de l’onglet **Général** du raccourci **Détails de la gestion des remises**.

Par exemple, une ligne d’accord est configurée pour que le champ **Méthode de calcul** soit défini sur *Par paliers* et le champ **Base** soit défini sur *Valeur*. Il comprend des lignes de calcul qui offrent les remises suivantes :

- **Ligne A :** 10 pour cent jusqu’à 1000 USD
- **Ligne B :** 25 pour cent jusqu’à 2 500 USD

Si la valeur des biens achetés ou vendus est de 2 000 USD, la remise de 350 USD qui en résulte est calculée de la manière suivante :

- **Remise (A) :** *Seuil (A)* × *Pourcentage (A)* = 1000 USD × 10 pour cent = 100 USD
- **Remise (B) :** (*Valeur vendue* – *Seuil (A)*) × *Pourcentage (B)* = (2 000 USD - 1000 USD) × 25 pour cent = 250 USD
- **Remise totale :** *Remise (A)* + *Remise (B)* = 100 USD + 250 USD = 350 USD

Si le champ **Base** est défini sur *Quantité* à la place de *Valeur*, la méthode de calcul par paliers fonctionne de la même manière. Le premier palier est utilisé pour la quantité identifiée jusqu’à ce que le deuxième palier soit atteint. Le deuxième palier est ensuite utilisé pour toute la quantité supérieur au premier palier, jusqu’à ce que le troisième palier soit atteint. Ce processus se poursuit ensuite à travers toutes les étapes suivantes.

### <a name="cumulative-calculation-method"></a>Méthode de calcul cumulative

La méthode de calcul cumulative utilise une seule ligne de calcul pour calculer la remise. Si plusieurs lignes de calcul sont disponibles pour la ligne d’accord, la ligne de calcul de la valeur la plus élevée ou de la quantité la plus élevée atteinte est utilisée pour la quantité ou la valeur totale. Comme les autres méthodes de calcul, la méthode cumulative utilise le paramètre du champ **Base** de l’onglet **Général** du raccourci **Détails de la gestion des remises** pour déterminer si la quantité des ventes ou la valeur des ventes est utilisée pour calculer les remises.

Par exemple, une ligne d’accord est configurée pour que le champ **Méthode de calcul** soit défini sur *Cumulative* et le champ **Base** soit défini sur *Valeur*. Il comprend des lignes de calcul qui offrent les remises suivantes :

- **Ligne A :** 10 pour cent jusqu’à 1000 USD
- **Ligne B :** 25 pour cent jusqu’à 2 500 USD

Si la valeur des biens achetés ou vendus est de 2 000 USD, le calcul utilise uniquement la ligne B. La remise de 500 USD qui en résulte est calculée de la manière suivante :

- **Remise totale :** *Valeur vendue* × *Remise (B)* = 2 000 USD × 25 pour cent = 500 USD

### <a name="rolling-calculation-method"></a>Méthode de calcul roulante

La méthode de calcul roulante calcule toutes les lignes de calcul possibles pour l’accord. S’il existe plusieurs lignes de calcul et que plusieurs d’entre elles sont atteintes, toutes les lignes de calcul atteintes seront utilisées, mais des seuils supérieurs s’appliquent à chaque pourcentage. Comme les autres méthodes de calcul, la méthode roulante utilise le paramètre du champ **Base** de l’onglet **Général** du raccourci **Détails de la gestion des remises** pour déterminer si la quantité des ventes ou la valeur des ventes est utilisée pour calculer les remises.

Par exemple, une ligne d’accord est configurée pour que le champ **Méthode de calcul** soit défini sur *Roulante* et le champ **Base** soit défini sur *Valeur*. Il comprend des lignes de calcul qui offrent les remises suivantes :

- **Ligne A :** 10 pour cent jusqu’à 1000 USD
- **Ligne B :** 25 pour cent jusqu’à 2 500 USD

Si la valeur des biens achetés ou vendus est de 2 000 USD, la remise de 600 USD qui en résulte est calculée de la manière suivante :

- **Remise (A) :** *Seuil (A)* × *Pourcentage (A)* = 1000 USD × 10 pour cent = 100 USD
- **Remise (B) :** *Valeur vendue* × *Pourcentage (B)* = 2 000 USD × 25 pour cent = 500 USD
- **Remise totale :** *Remise (A)* + *Remise (B)* = 100 USD + 500 USD = 600 USD

### <a name="total-calculation-method"></a>Méthode de calcul totale

La méthode de calcul totale utilise toutes les lignes de calcul pour calculer la remise. Elle applique la quantité totale pour calculer la remise pour chaque ligne de calcul atteinte, et chaque ligne de calcul applique son pourcentage au montant total. Comme les autres méthodes de calcul, la méthode totale utilise le paramètre du champ **Base** de l’onglet **Général** du raccourci **Détails de la gestion des remises** pour déterminer si la quantité des ventes ou la valeur des ventes est utilisée pour calculer les remises.

Par exemple, une ligne d’accord est configurée pour que le champ **Méthode de calcul** soit défini sur *Totale* et le champ **Base** soit défini sur *Valeur*. Il comprend des lignes de calcul qui offrent les remises suivantes :

- **Ligne A :** 10 pour cent jusqu’à 1000 USD
- **Ligne B :** 25 pour cent jusqu’à 2 500 USD

Si la valeur des biens achetés ou vendus est de 2 000 USD, la remise de 700 USD qui en résulte est calculée de la manière suivante :

- **Remise (A) :** *Valeur vendue* × *Pourcentage (A)* = 2 000 USD × 10 pour cent = 200 USD
- **Remise (B) :** *Valeur vendue* × *Pourcentage (B)* = 2 000 USD × 25 pour cent = 500 USD
- **Remise totale :** *Remise (A)* + *Remise (B)* = 200 USD + 500 USD = 700 USD
