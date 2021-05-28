---
title: Configuration des valeurs des paramètres d’évaluation des coûts
description: Lorsque vous configurez le module de coût au débarquement, vous pouvez définir plusieurs ensembles de valeurs communes qui seront disponibles lorsque vous sélectionnez des types spécifiques de valeurs de paramètres d’évaluation des coûts dans d’autres parties de l’application. Cette rubrique explique comment configurer ces ensembles de valeurs.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostTypeTable, ITMCostTypeGroup, ITMCostTransferGroup, ITMCostTemplateTable, ITMVolumetricDivisorTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ce655cc85212699864e0ac4430ce79f24d2563a8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021634"
---
# <a name="costing-parameter-values-setup"></a>Configuration des valeurs des paramètres d’évaluation des coûts

[!include [banner](../../includes/banner.md)]

Lorsque vous configurez le module **Prix au débarquement**, vous pouvez définir plusieurs ensembles de valeurs communes et de paramètres associés par valeur. Ces valeurs seront ensuite disponibles lorsque vous sélectionnez des types spécifiques de valeurs de paramètres d’évaluation des coûts dans d’autres parties de l’application. Cette rubrique explique comment configurer ces ensembles de valeurs.

## <a name="set-up-cost-type-codes"></a>Configurer des codes de type de coût

Les codes de type de coût déterminent le type de coût encouru lorsque les marchandises sont débarquées dans l’entrepôt ou les coûts au débarquement du voyage. Bien qu’ils augmentent généralement la valeur des marchandises, ils peuvent également être utilisés pour enregistrer des montants dans la comptabilité. Les ajustements comptables sont utilisés lorsqu’un coût est comptabilisé au fil du temps ou au cours d’une série de voyages et compensé en une seule transaction.

> [!NOTE]
> Si le tableau des types de coût est partagé entre les entités juridiques, le plan comptable doit également être partagé entre les entités juridiques. Sinon, les transactions de validation ne fonctionneront pas correctement.

Pour configurer vos codes de types de coûts, accédez à **Coût au débarquement \> Configuration des coûts \> Codes de types de coûts**. Vous pouvez utiliser les boutons du volet Actions pour créer des codes de types de coûts, modifier des codes existants ou supprimer un type de coût sélectionné.

Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque code de type de coût.

| Champ | Description |
|---|---|
| Code de type de coût | Entrez le nom du code de type de coût. |
| Description | Permet d’entrer la description du code de type de coût. |
| Utiliser les frais d’expédition | Définissez cette option sur *Oui* si le taux de change du voyage (parfois appelé taux de gestion) doit être utilisé pour calculer la valeur de ces coûts. Dans ce cas, le taux d’expédition sera utilisé à la place du taux de change standard par défaut ou au comptant pour échanger les factures en devises étrangères. |
| Catégorie de génération d’états | Ce champ établit une catégorie de génération d’états pour le type de coût. Les rapports peuvent être imprimés soit par catégories de rapport, soit par type de coût. |
| Type de débit | Sélectionnez si le type de coût doit débiter l’article, le compte général ou le fournisseur. |
| Validation des débits | Si le champ **Type de débit** est défini sur *Compte général*, sélectionnez la description de publication. |
| Compte à débiter | Si le champ **Type de débit** est défini sur *Compte général*, sélectionnez le compte général à utiliser. |
| Type de crédit | Sélectionnez si ce type de coût doit créditer l’article, le compte général ou le fournisseur. |
| Validation des crédits | Si le champ **Type de crédit** est défini sur *Compte général*, sélectionnez la description de publication. |
| Compte à créditer | Si le champ **Type de crédit** est défini sur *Compte général*, sélectionnez le compte général à utiliser. |
| Compte de compensation | Sélectionnez le type de compte de compensation pour le type de coût. Nous vous recommandons de spécifier un compte de compensation distinct par type de coût pour faciliter le rapprochement. |
| Type de validation du coût standard | Si vous utilisez l’évaluation des coûts standard, sélectionnez la description de la validation. |
| Compte d’écart de coût standard | <p>Si vous utilisez l’évaluation des coûts standard, le compte spécifié ici sera utilisé pour comptabiliser tout écart. Ce compte utilise la ventilation des coûts au débarquement sur la page **Prix des articles**. Cette ventilation est créée en utilisant la routine périodique pour mettre à jour les prix.</p><p>Par exemple, le coût standard d’un article est 15,00 USD, le FAB est 13,00 USD et le fret est 2,00 USD. Lorsque la facture est reçue pour le stock, l’article est reçu à 15,00 USD, mais il existe un écart de prix standard de 2,00 USD pour l’article, car le FAB réel est 13,00 USD. Cet écart est imputé au compte d’écart de prix standard configuré dans le profil de validation article. Étant donné que le fret estimé est 2,00 USD, il n’y a pas d’écart lorsque la facture de stock est validée. Cependant, lorsque la facture de fret est reçue, le fret est de 2,50 USD par unité. Par conséquent, un écart 0,50 USD est imputé au coût spécifié. |
| Compte d’écart de moyenne mobile | <p>Si vous utilisez l’évaluation des coûts moyenne mobile, le compte spécifié ici sera utilisé pour comptabiliser tout écart.</p><p>Par exemple, le fret estimé est 2,00 USD. Cependant, lorsque la facture de fret est reçue, le fret est de 2,50 USD par unité. Par conséquent, un écart 0,50 USD doit être affiché.</p><p>Quand l’option **Valider les ajustements en tant que variance** est définie sur *Oui* sur la page **Paramètres de coût au débarquement**, tous les écarts entre les coûts d’expédition estimés et réels seront enregistrés dans le compte d’écart de moyenne mobile spécifié ici. Quand l’option **Enregistrer les ajustements en tant que variance** est définie sur *Non*, la fonctionnalité standard sera utilisée et l’écart sera appliqué soit à l’inventaire, soit au compte d’écart de moyenne mobile spécifié ici, en fonction du stock disponible.</p> |
| Compte de régularisation de frais | Sélectionnez le compte utilisé pour provisionner les estimations des coûts lorsque la facture d’achat est validée. Ce champ est utilisé uniquement lorsque l’option **Utiliser le compte de provisionnement des frais de type de coût** est définie sur *Oui* sur le raccourci **Coût** sur l’onglet **Général** de la page **Paramètres de coût au débarquement**. |
| Compte de frais | Sélectionnez le compte utilisé pour capturer les frais de transport entrant qui ont été facturés par un fournisseur. Le montant est validé en tant que débit. Le compte de contrepartie est le compte de variation de stock. Cette validation est utilisée que si l’option **Valider sur le compte de frais dans la comptabilité** est définie sur *Oui* sur la page **Paramètres de la comptabilité fournisseur**. |
| Compte d’écart | Le compte qui sera utilisé pour compenser les charges à payer lors de la validation de la facture d’achat. Ce champ est utilisé uniquement lorsque l’option **Utiliser le compte de provisionnement des frais de type de coût** est définie sur *Oui* sur le raccourci **Coût** sur l’onglet **Général** de la page **Paramètres de coût au débarquement**. |

## <a name="vendor-cost-type-groups"></a>Groupes de type de coût du fournisseur

Les groupes de types de coûts fournisseur aident à déterminer comment les frais de *coût automatique* sont trouvés et appliqués à un voyage. Les fournisseurs qui ont des coûts d’importation similaires sont liés entre eux. Par exemple, tous les fournisseurs des marchés émergents paient le même pourcentage de droits pour le même type de produit acheté sur un marché établi.

Vous pouvez gérer les groupes de types de coûts fournisseur en accédant à **Prix au débarquement \> Configuration des coûts \> Groupes de types de coûts du fournisseur**. La page **Groupes de types de coûts du fournisseur** fournit une grille qui répertorie tous les groupes de types de coûts fournisseur existants. Vous pouvez utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des lignes dans la grille.

Le tableau suivant décrit les champs disponibles sur chaque ligne de la grille.

| Champ | Description |
|---|---|
| Groupes de type de coût du fournisseur | Entrez un nom unique pour le groupe de types de coûts fournisseur (tel que *Marchés émergents*). |
| Description | Permet d’entrer la description du groupe de types de coûts fournisseur. Cette description peut fournir des détails sur le niveau ou le type de frais associé au groupe de fournisseurs. |

## <a name="item-cost-type-groups"></a>Groupes de type de coût de l’article

Les groupes de types de coûts article aident à déterminer comment les frais de *coût automatique* sont trouvés et appliqués à un voyage. Les articles similaires sont liés entre eux. Par exemple, tous les articles qui ont un taux de droit de 5 pour cent peuvent appartenir à un groupe de types de coûts spécifique.

Vous pouvez gérer les groupes de types de coûts article en accédant à **Prix au débarquement \> Configuration des coûts \> Groupes de types de coûts article**. La page **Groupes de types de coûts article** fournit une grille qui répertorie tous les groupes de types de coûts article existants. Vous pouvez utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des lignes dans la grille.

Le tableau suivant décrit les champs disponibles sur chaque ligne de la grille.

| Champ | Description |
|---|---|
| Groupes de type de coût de l’article | Entrez un nom unique pour le groupe de types de coûts article (tel que *Droits de douane 5 %*). |
| Description | Permet d’entrer la description du groupe de types de coûts article. Cette description peut fournir des détails sur le niveau ou le type de frais associé au groupe d’articles. |

> [!NOTE]
> Le type de coût de l’article est lié à l’article via le champ **Groupe de types de coûts** sur le raccourci **Achat** de la page **Produit sorti** de l’article.

## <a name="transfer-order-cost-type-groups"></a>Groupes de types de coûts d’ordre de transfert

Les groupes de types de coûts d’ordres de transfert aident à déterminer comment les frais de *coût automatique* sont trouvés. Les articles similaires sont liés entre eux. Par exemple, tous les articles qui ont un taux de droit de 7 pour cent peuvent appartenir à un groupe de types de coûts spécifique.

Vous pouvez gérer les groupes de types de coûts d’ordre de transfert en accédant à **Prix au débarquement \> Configuration des coûts \> Groupes de types de coûts d’ordre de transfert**. La page **Groupes de types de coûts de l’ordre de transfert** fournit une grille qui répertorie tous les groupes de types de coûts l’ordre de transfert existants. Vous pouvez utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des lignes dans la grille.

Le tableau suivant décrit les paramètres disponibles sur chaque ligne de la grille.

| Champ | Description |
|---|---|
| Groupes de types de coûts d’ordre de transfert | Entrez un nom unique pour le groupe de types de coûts d’ordre de transfert (tel que *Droits de douane 7 %*). |
| Description | Permet d’entrer la description du groupe de types de coûts l’ordre de transfert. Cette description peut fournir des détails sur le niveau ou le type de frais associé au groupe de types de coûts d’ordre de transfert. |

> [!NOTE]
> Le type de coût de l’ordre de transfert est lié à l’article via le champ **Groupe de types de coûts de l’ordre de transfert** sur le raccourci **Achat** de la page **Produit sorti** de l’article.

## <a name="cost-templates"></a>Modèles de coût

Vous utilisez des modèles de coût pour définir les valeurs par défaut des paramètres que les utilisateurs qui obtiennent l’estimation des coûts peuvent ne pas connaître. Les modèles de coût peuvent aider à réduire la complexité du processus d’estimation en minimisant les sélections que les utilisateurs doivent effectuer pour obtenir une estimation précise.

Pour utiliser les modèles de coût, accédez à **Coût au débarquement \> Configuration des coûts \> Modèles de coût**. Sur la page **Modèles de coût**, le volet de liste sur la gauche affiche toutes les modèles de coûts actuels. Vous pouvez utiliser les boutons du volet Actions pour ajouter, supprimer et modifier les modèles.

Le tableau suivant décrit les paramètres disponibles dans l’en-tête pour chaque modèle.

| Champ | Description |
|---|---|
| Modèle de coût | Entrez un nom unique pour le modèle de coût. Le nom décrit généralement le facteur ou le multiplicateur de coût du modèle. |
| Description | Permet d’entrer une description du modèle de coût. |
| Société d’expédition | Sélectionnez le compte fournisseur de la société de transport à associer au modèle de coût. |
| Mode de livraison | Sélectionnez le mode de livraison que le modèle de coût doit utiliser lors du calcul du coût estimé d’un article. Ce champ permet de déterminer les coûts automatiques associés aux marchandises sur l’estimation des coûts. |
| Type de conteneur d’expédition | Sélectionnez le type de conteneur de transport à associer au modèle de coût. Ce champ permet de déterminer les coûts automatiques associés aux marchandises sur l’estimation des coûts. |
| Courtier en douane | Sélectionnez le courtier en douane (fournisseur) à associer au modèle de coût. Ce champ permet de déterminer les coûts automatiques associés à l’estimation des coûts. |
| Facteur | Saisissez un facteur à appliquer à l’estimation du coût de revient final des marchandises. Par exemple, pour ajouter 10 % à l’estimation des coûts calculée, entrez *1,10*. |

## <a name="volumetric-divisors"></a>Diviseurs volumétriques

Les diviseurs volumétriques sont utilisés pour calculer le poids volumétrique. Chaque entreprise d’expédition/de fret formule ses propres diviseurs volumétriques. De plus, les diviseurs d’une entreprise varient généralement en fonction du mode de livraison. Par exemple, l’air et la mer ont souvent des diviseurs très différents. Une entreprise peut également rendre ses règles plus complexes, en fonction de son origine.

Par exemple, un colis envoyé par avion a un volume de 3 mètres cubes (m³). L’entreprise facture en fonction du poids volumétrique et applique un diviseur volumétrique de 6. Ce diviseur est multiplié par le volume pour déterminer le poids volumétrique. Par conséquent, le poids volumétrique pour cet exemple est de 3 × 6 = 18 kilogrammes (kg).

Pour configurer vos diviseurs volumétriques, accédez à **Coût au débarquement \> Configuration des coûts \> Diviseurs volumétriques**. La page **Diviseurs volumétriques** fournit une grille qui répertorie tous les diviseurs volumétriques existants. Vous pouvez utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des lignes dans la grille.

Le tableau suivant décrit les champs disponibles sur chaque ligne de la grille.

| Champ | Description |
|---|---|
| Société d’expédition | Sélectionnez le compte fournisseur du transporteur associé au diviseur volumétrique. |
| Code de type de coût | Sélectionnez le code de type de coût associé au diviseur volumétrique. Utilisez ce champ pour placer les types de coûts dans des groupes de rapports. Les rapports peuvent être imprimés soit par catégories de rapport, soit par type de coût. |
| Port de départ | Sélectionnez le port "De" auquel s’applique le diviseur volumétrique. |
| Diviseur volumétrique | Entrez la valeur du diviseur volumétrique qui s’applique à la ligne. La valeur que vous entrez sera *multipliée* par le volume de chaque colis pour déterminer le poids volumétrique de ce colis. |
