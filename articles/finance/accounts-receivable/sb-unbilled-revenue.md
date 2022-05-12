---
title: Produit non facturé
description: Cette rubrique explique comment configurer les articles et les comptes pour utiliser la fonctionnalité de produit non facturé dans la facturation de l’abonnement.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 4a5bd016649957d90876d4eb50c358cd9d6fba80
ms.sourcegitcommit: 836695c0e95d366ba993f34eee30f57191f356d8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2022
ms.locfileid: "8629423"
---
# <a name="unbilled-revenue"></a>Produit non facturé

Cette rubrique décrit la fonctionnalité de produit non facturé qui vous permet d’inclure les montants des échéanciers de facturation entiers dans le bilan. Ces montants sont inclus dans un compte de produit non facturé et un compte de contrepartie de produit non facturé, et le contrat est facturé par versements.

## <a name="set-up-unbilled-revenue"></a>Paramétrage de produit non facturé

Pour paramétrer un revenu non facturé, procédez comme suit.

- Sur la page **Paramètres de facturation des contrats récurrents**, définissez les champs de la section **Produit non facturé**.
- La fonctionnalité de Compte de produit non facturé peut être utilisée pour les articles pour lesquels le champ **Type d’article** est défini sur **Standard**. Il peut également être utilisé pour les articles de report. Pour utiliser le produit non facturé avec la fonctionnalité à court terme, configurez les options à court terme sur la page **Paramètres de facturation de contrat récurrent**.

Pour paramétrer les articles afin d’utiliser un produit non facturé, procédez comme suit.

1. Sur la page **Paramétrage des produits non facturés**, sur l’onglet **Articles**, sélectionnez **Ajouter**.
2. Sur la nouvelle ligne, dans **Code article**, sélectionnez le code article.
3. Dans le champ **Relation d’article**, sélectionnez la relation d’article.
4. Répétez ces étapes pour ajouter des lignes.
5. Cliquez sur **Enregistrer**.

Pour paramétrer les articles et les comptes de produits non facturés, procédez comme suit.

1. Sur la page **Paramétrage des produits non facturés**, sur l’onglet **Comptes**, sélectionnez **Ajouter**.
2. Sur la nouvelle ligne, dans **Code article**, sélectionnez le code article.
3. Dans le champ **Relation d’article**, sélectionnez la relation d’article.
4. Sélectionnez les comptes de produits non facturés, de remises non facturées et de contrepartie de produits non facturés. Pour utiliser les comptes à court terme, vous devez définir le champ **Méthode non facturée à court terme** sur **Périodes glissantes** ou **Année fixe** sur la page **Paramètres de facturation de contrat récurrent**.
5. Répétez ces étapes pour ajouter des lignes.
6. Cliquez sur **Enregistrer**.

## <a name="use-unbilled-revenue"></a>Utilisation du produit non facturé

1. Sur la page **Tous les échéanciers de facturation**, créez un échéancier de facturation.
2. Si l’article n’est pas encore configuré pour utiliser un produit non facturé, cochez la case **Produit non facturé** sur la ligne de l’échéancier de facturation.
3. Définissez l’option **Produit non facturé** sur **Oui**. Vérifiez et modifiez le produit non facturé, la remises et les comptes de contrepartie de produits non facturés au besoin.
4. Sur l’échéancier de facturation, sous **Traitement des produits non facturés**, sélectionnez **Créer une entrée de journal** pour créer l’entrée de journal initiale pour le produit non facturé. Cette étape doit être terminée avant que l’échéancier de facturation ne soit facturé.
5. Une fois l’entrée de journal initiale créée, sélectionnez **Générer une facture** pour créer des commandes clients et valider les factures pour les échéanciers de facturation.
6. Une fois les factures validées, vous pouvez consulter les informations d’audit sur l’onglet **Renouvellements** de la page **Tous les échéanciers de facturation**.

### <a name="milestone-billing"></a>Facturation jalonnée

La facturation jalonnée fonctionne avec les produits non facturés dans les conditions suivantes :

- Si l’article parent du jalon n’est pas facturé (la case **Produit non facturé** est cochée) et que les éléments enfants du jalon sont facturés (la case **Produit non facturé** est décochée), les dates de début et de fin de l’article parent doivent être spécifiées. Ces dates sont utilisées pour créer l’entrée de journal initiale.
- Si l’article parent du jalon n’est pas facturé (la case **Produit non facturé** est décochée) et que les éléments enfants du jalon sont facturés (la case **Produit non facturé** est cochée), la date de fin doit être spécifiée uniquement pour les articles parents pour lesquels vous souhaitez créer l’entrée de journal.

Chaque article enfant de jalon peut être traité séparément. Les dates de fin peuvent être spécifiées quand vous êtes prêt à créer l’entrée de journal initiale.

> [!NOTE]
> Si l’entrée de journal initiale pour l’article parent ou les articles enfants du jalon a déjà été créée, ou si une facture a été créée, les dates de début et de fin ne peuvent pas être modifiées.

### <a name="unbilled-revenue-with-straight-line-deferrals"></a>Produit non facturé avec des reports linéaires

Pour utiliser le produit non facturé avec des échéanciers de report linéaires, procédez comme suit.

1. Sur la page **Tous les échéanciers de facturation**, créez un échéancier de facturation.
2. Ajoutez un article aux lignes de l’échéancier de facturation.
3. Sélectionnez **Reports** pour la ligne.
4. Sur la page **Report de transaction**, suivez ces étapes :

    1. Définissez l’option **Report** sur **Oui**.
    2. Modifiez les comptes au besoin.
    3. Dans la section **Échéancier**, sélectionnez **Linéaire**, et modifiez les autres valeurs selon vos besoins.
    4. Cliquez sur **OK**.

5. Sélectionnez **Produit non facturé** pour la ligne, puis procédez comme suit :

    1. Définissez l’option **Produit non facturé** sur **Oui**.
    2. Sélectionnez les comptes à utiliser pour le produit, la remise et la contrepartie de produit.

6. Sur l’échéancier de facturation, sous **Traitement de produit non facturé**, sélectionnez **Créer une entrée de journal**. Sinon, utilisez la page **Traitement en bloc des produits non facturés** pour créer l’écriture de journal.
7. L’échéanciers de reports est créé. Vous pouvez vérifier les détails sur la page **Tous les échéanciers de report**. Une fois l’échéancier de report créé, vous pouvez modifier diverses valeurs pour l’article de ligne de l’échéancier de facturation. Par exemple, vous pouvez modifier le prix unitaire, la quantité ou les dates.

### <a name="unbilled-revenue-with-event-based-deferrals"></a>Produit non facturé avec des reports basés sur des événements

Pour utiliser le produit non facturé avec des échéanciers de report basés sur des événements, procédez comme suit.

1. Sur la page **Tous les échéanciers de facturation**, créez un échéancier de facturation.
2. Ajoutez un article aux lignes de l’échéancier de facturation.
3. Sélectionnez **Reports** pour la ligne.
4. Sur la page **Report de transaction**, suivez ces étapes :

    1. Définissez l’option **Report** sur **Oui**.
    2. Modifiez les comptes au besoin.
    3. Dans la section **Échéancier**, sélectionnez **Basé sur des événements**, **Modèle**, **Type de répartition** et **Compte d’expiration**.
    4. Cliquez sur **OK**.

5. Sélectionnez **Produit non facturé** pour la ligne, puis procédez comme suit :

    - Définissez l’option **Produit non facturé** sur **Oui**.
    - Sélectionnez les comptes à utiliser pour le produit, la remise et la contrepartie de produit.

6. Sur l’échéancier de facturation, sous **Traitement de produit non facturé**, sélectionnez **Créer une entrée de journal**. Sinon, utilisez la page **Traitement en bloc des produits non facturés** pour créer l’écriture de journal.
7. L’échéanciers de reports est créé. Vous pouvez vérifier les détails sur la page **Tous les échéanciers de report**. Une fois l’échéancier de report créé, vous pouvez modifier diverses valeurs pour l’article de ligne de l’échéancier de facturation. Par exemple, vous pouvez modifier le prix unitaire, la quantité ou les dates. L’échéancier de report est recalculé en fonction des nouvelles valeurs.

Les répartitions sont recalculées en fonction du type de répartition sélectionné (**Pourcentage**, **Pourcentage d’achèvement** ou **Montants égaux**). Pour le type de répartition **Montants variables**, la distribution est recalculée en fonction de l’équivalent en pourcentage de la valeur initiale de l’événement. Par exemple, le prix unitaire d’origine est 100,00 $ et le pourcentage de la valeur initiale est 55,00 $ (55 %). Si le prix unitaire est passé à 200,00 $, le montant variable de l’événement passe à 110,00 $ (toujours 55 %).

> [!NOTE]
> Si des lignes d’échéancier de report ont été reconnues, l’article de la ligne d’échéancier de facturation ne peut pas être modifiée. Pour modifier l’article de ligne, vous devez d’abord inverser les lignes reconnues. La ligne d’échéancier de facturation peut ensuite être mise à jour.

### <a name="unbilled-revenue-and-top-billing"></a>Produits non facturés et le plus facturés

Un échéancier de facturation est entré pour trois ans, et les factures sont facturées annuellement pendant une période de trois ans. Le montant total du contrat est enregistré dans le compte de produit non facturé d’où les factures annuelles sont créées. Le compte de contrepartie est le compte de produit ou de produit différé.

Notez que les produits les plus facturés et les produits non facturés ne fonctionnent pas ensemble, car des problèmes de rapprochement peuvent survenir dans la comptabilité. Par exemple, sur la page **Configuration du groupe d’articles**, le groupe d’articles A est configuré de sorte que le champ **Nombre de lignes supérieures** est défini sur **2**. Sur la page **Échéanciers de facturation**, trois articles sont ajoutés. Les trois articles appartiennent au groupe d’articles A. Quand l’entrée de journal initiale est créée pour la fonction de produits non facturés, le montant des trois articles est traité sur le compte non facturé. Quand la facture de l’échéancier de facturation est créée, seuls les montants des deux premiers articles sont inclus. Par conséquent, le montant de la facture ne correspond pas au montant traité dans le compte de produit non facturé et des problèmes de rapprochement se produisent dans la comptabilité.

Si vous souhaitez utiliser le produit non facturé, laissez la page **Configuration du groupe d’articles** vide ou configurez tous les groupes d’articles pour que le champ **Nombre de lignes supérieures** soit défini sur **0** (zéro). Si vous souhaitez utiliser la facturation la plus utilisée, aucune action sur les produits non facturés n’est disponible.

### <a name="examples"></a>Exemples

À partir de la version 10.0.27, un nouveau compte est proposé quand un produit non facturé est utilisé. Quand le processus **Créer une entrée de journal** initial est validé, le crédit est effectué sur un nouveau compte de contrepartie de produits non facturés. Ce compte est utilisé à la place du compte de produits, car la même valeur doit être annulée quand l’échéancier de facturation est facturé. Si des différences de taux de change ou d’arrondi sont trouvées, les montants qui sont calculés au moment du processus **Générer une facture** peuvent être différents. Ce comportement garantit que le montant net des comptes est égal à 0 (zéro).

Cet exemple montre comment utiliser les produits non facturés pour comptabiliser le montant total d’un contrat dans le bilan en tant que produits non facturés. L’autre côté de l’entrée est la contrepartie des produits non facturés. Quand vous facturez le client, les produits non facturés et la contrepartie des produits non facturés sont inversés. La comptabilisation des produits se fera au moment de la facturation ou selon l’échéancier de reconnaissance des reports mis en place.

#### <a name="assumptions"></a>Hypothèses

- Le 1er janvier de l’année en cours, un client signe un contrat de trois ans pour 390 $.
- Le contrat comprend deux parties : des licences et un contrat de maintenance.
- Le prix de vente de la licence est de 300 $, et le client sera facturé 100 $ le 1er janvier de chaque année contractuelle. Le montant de la licence de 300 $ sera considéré comme un produit au moment de la signature du contrat.
- Le prix de vente de la maintenance est de 90 $, et le client sera facturé 30 $ le 1er janvier de chaque année contractuelle. Les frais de maintenance de 90 $ seront reportés, et 2,50 $ sera reconnu chaque mois de la durée du contrat.
- Le client sera facturé 130 $ au début (1er janvier) de chacune des trois années du contrat.

#### <a name="steps"></a>Étapes

1. Configurez les deux articles lancés en tant qu’articles non facturés. Utilisez la page **Paramétrage des produits non facturés** pour configurer les articles et les comptes qui utilisent des produits non facturés.
2. Dans cet exemple, les frais de maintenance sont reportés. L’article nécessite un modèle de report, qui est configuré sur la page **Modèles de report**. Le modèle a une fréquence de périodicité **Mensuelle** et une durée de périodicité de reconnaissance de 36 mois. Par conséquent, le produit par mois et de 2,50 $.
3. Sur la page **Articles reportés par défaut**, définissez le champ **Frais de maintenance** sur **Article reportable**. Cette étape et la suivante entraîneront le report de l’article de frais de maintenance quand il est vendu ou inclus dans un échéancier de facturation.
4. Sélectionnez **Valeurs par défaut de report** \> **Modèle**, et ajoutez l’article pour les frais de maintenance et le modèle linéaire de l’étape 2. L’article de frais de maintenance sera lié à un échéancier de report de 36 mois.
5. Créez un échéancier de facturation qui inclut les deux articles non facturés. L’échéancier de facturation du contrat est configuré avec les articles suivants.

    | Article | Date de début | Date de fin | Montant | Fréquence de facturation | Article de report | Produit non facturé | Description |
    |---|---|---|---|---|---|---|---|
    | Licence | 1er janvier, année en cours | 31 décembre, année en cours+2 | 100,00 $ | Année | Non | Oui | Le client sera facturé 100,00 $ chaque année. Le total de 300,00 $ sera enregistré par anticipation en produit non facturé dans le bilan, et en produit sur le compte de résultat. Chaque facture réduira le montant non facturé. |
    | Maintenance | 1er janvier, année en cours | 31 décembre, année en cours+2 | 30,00 $ | Année | Oui | Oui | Le client sera facturé 30,00 $ chaque année. Le total de 90,00 $ sera enregistré par anticipation en produit non facturé et en produit différé sur le bilan. Chaque facture réduira le montant non facturé. Le produit différé sera comptabilisé mensuellement sur 36 mois. |

6. Sur la page **Tous les échéanciers de facturation**, utilisez le processus **Créer une entrée de journal** pour comptabiliser la valeur du contrat dans le bilan en tant que produit non facturé.

Deux entrées de journal sont créées, une pour chaque ligne de l’échéancier de facturation.

| Compte de produit non facturé | Compte de contrepartie des revenus non facturés | Montant de débit | Montant de crédit |
|---|---|---|---|
| Compte de produit non facturé | | 300,00 $ | |
| | Compte de contrepartie des revenus non facturés | | 300,00 $ |

| Compte de produit non facturé | Produit différé | Montant de débit | Montant de crédit |
|---|---|---|---|
| Compte de produit non facturé | | 90,00 $ | |
| |Produit de maintenance différé | | 90,00 $ |

La première entrée de journal est comptabilisée sur un compte de contrepartie de produits non facturés et la deuxième est comptabilisée sur un compte de produits différés. Si la ligne de facturation comporte à la fois des produits non facturés et des produits différés, le compte de produits différés est utilisé, et non la contrepartie des produits non facturés. Le contrat exige que la facture du client soit créée au début de chaque année. Utilisez le processus **Générer une facture** de création de la facture. Une fois la facture créée, les entrées de journal suivantes sont créées.

| Compte principal | Compte de produit non facturé | Montant de débit | Montant de crédit |
|---|---|---|---|
| Contrepartie des produits non facturés | | 100,00 $ | |
| | Compte de produit non facturé | | 100,00 $ |
| Module Comptabilité client | | 100,00 $ | |
| | Compte de produit | | 100,00 $ |

| Compte principal | Compte de produit non facturé | Montant de débit | Montant de crédit |
|---|---|---|---|
| Compte de produit de maintenance différé | | 30,00 $ | |
| | Compte de produit non facturé | | 30,00 $ |
| Module Comptabilité client | | 30,00 $ | |
| | Compte de produit de maintenance différé | | 30,00 $ |

Cette même entrée de journal sera créée par les factures qui sont comptabilisées au début des deux prochaines années. Le montant net du compte de produits différés sera de 0 (zéro), car il n’y a pas d’arrondi ni de différences de taux de change. Les produits différés doivent être contrepassés exactement tels qu’ils ont été crédités au moment du processus **Créer une entrée de journal**. Étant donné que les produits sont toujours différés et seront reconnus ultérieurement, le crédit au compte de produits différés se produit à nouveau.

Dans la dernière étape, l’entrée de journal de reconnaissance est créée chaque mois pour comptabiliser les produits de frais de maintenance différés. L’entrée de journal peut être créée sur la page **Traitement de la reconnaissance**. Sinon, elle peut être créée en sélectionnant **Reconnaître** pour les lignes des pages **Échéancier de report**.

| Compte de produit différé | Compte de produit | Montant de débit | Montant de crédit |
|---|---|---|---|
| Produit de maintenance différé | | 2,50 $ | |
| | Produit de maintenance | | 2,50 $ |

Cette entrée de journal sera créée chaque fois que le processus de reconnaissance sera exécuté pour cet article différé (un total de 36 fois).

#### <a name="short-term-fixed-year"></a>À court terme : Année fixe

Vous pouvez utiliser le produit non facturé avec la fonctionnalité à court terme en configurant le champ **Non facturé à court terme** sur la page **Paramètres de facturation de contrat récurrent**. L’exemple suivant montre les calculs effectués quand les revenus non facturés sont utilisés avec la méthode non facturée à court terme **Année fixe**.

Un échéancier de facturation comportant les critères suivants est créé :

- **Date de début :** 1er juin 2020
- **Date de fin :** 31 décembre 2021
- **Prix unitaire :** 100 $
- **Fréquence :** Mensuelle

Sur la page **Tous les échéanciers de facturation**, l’entrée de journal initiale est créée par le processus **Créer une entrée de journal**. Les montants actuels à court terme et à long terme sont calculés de la manière suivante :

- **Montant actuel des produits non facturés à court terme :** 700 $
- **Montant actuel des produits non facturés à long terme :** 1 200 $

La facture est créée pour la période de facturation du 1er juin 2020 au 30 novembre 2020. Les montants actuels à court terme et à long terme sont calculés de la manière suivante :

- **Montant actuel des produits non facturés à court terme :** 100 $
- **Montant actuel des produits non facturés à long terme :** 1 200 $

La facture est créée pour la période de facturation du 1er décembre 2020 au 31 décembre 2020. Les montants actuels à court terme et à long terme sont calculés de la manière suivante :

- **Montant actuel des produits non facturés à court terme :** 1 200 $
- **Montant actuel des produits non facturés à long terme :** 0 $

#### <a name="short-term-rolling-periods"></a>Court terme : Périodes glissantes

Vous pouvez utiliser le produit non facturé avec la fonctionnalité à court terme en configurant la méthode non facturée à court terme sur la page **Paramètres de facturation de contrat récurrent**. L’exemple suivant montre les calculs effectués quand les revenus non facturés sont utilisés avec la méthode non facturée à court terme **Périodes glissantes**.

Un échéancier de facturation comportant les critères suivants est créé :

- **Date de début :** 1er juin 2020
- **Date de fin :** 31 décembre 2021
- **Prix unitaire :** 100 $
- **Fréquence :** Mensuelle

Sur la page **Tous les échéanciers de facturation**, l’entrée de journal initiale est créée par le processus **Créer une entrée de journal**. Les montants actuels à court terme et à long terme sont calculés de la manière suivante :

- **Montant actuel des produits non facturés à court terme :** 1 200 $
- **Montant actuel des produits non facturés à long terme :** 700 $

La facture est créée pour la période de facturation du 1er juin 2020 au 30 novembre 2020. Les montants actuels à court terme et à long terme sont calculés de la manière suivante :

- **Montant actuel des produits non facturés à court terme :** 1 200 $
- **Montant actuel des produits non facturés à long terme :** 100 $

La facture est créée pour la période de facturation du 1er décembre 2020 au 31 décembre 2020. Les montants actuels à court terme et à long terme sont calculés de la manière suivante :

- **Montant actuel des produits non facturés à court terme :** 1 200 $
- **Montant actuel des produits non facturés à long terme :** 0 $

### <a name="items-with-revenue-allocation"></a>Articles avec répartition du produit

Deux articles avec des fréquences de facturation différentes sont ajoutés à un échéancier de facturation. Tous deux utilisent des produits non facturés et sont des articles reportables.

- **Numéro d’article 1 000 :** Surface Pro 128 Go

    - **Périodicité de facturation :** Une fois
    - **Prix unitaire :** 1 500 $
    - **Prix de vente autonome :** 1 600 $
    - **Produit du contrat :** 1 465,26 $

- **Numéro d’article S0021 :** Assurance vendue avec le numéro d’article 1 000

    - **Périodicité de facturation :** Mensuelle pendant 12 mois
    - **Prix unitaire :** 20 $/mois
    - **Prix de vente autonome :** 25 $
    - **Produit du contrat :** 264,74 $

Étant donné que les deux articles utilisent les produits non facturés et la répartition des produits, le montant total du contrat sur la ligne de renouvellement est de 0 (zéro). La colonne **Produits du contrat** est ajoutée et affiche le montant des produits du contrat.

Le tableau suivant montre l’entrée de journal initiale pour les articles et la facture.

| Compte de produit non facturé | Compte de produit différé | Montant de débit | Montant de crédit |
|---|---|---|---|
| **Entrée de journal – Article n° 1 000** | | | |
| Compte de produit non facturé au débit (401250) | | 1 465,26 $ | |
| | Compte de produit différé au crédit (250600) | | 1 465,26 $ |
| **Entrée de journal – Article n° 0021** | | | |
| Compte de produit non facturé au débit (401250) | | 274,74 $ | |
| | Compte de produit différé au crédit (250600) | | 274,74 $ |
| **Facture** | | | |
| | Compte de produit non facturé au crédit | | 1 465,26 $ |
| | Compte de produit non facturé au crédit | | 274,74 $ |
| Compte comptabilité client débiteur (130100) | | 1 488,16 $ | |

#### <a name="changes-to-the-billing-schedule-line-billing-detail-line-or-revenue-allocation"></a>Modifications apportées à la ligne d’échéancier de facturation, à la ligne de détails de facturation ou à la répartition des produits

Quand le prix unitaire ou la quantité est modifiée, le montant du produit du contrat pour chaque article faisant partie de la répartition du produit doit être mis à jour. Par conséquent, l’entrée de journal est recalculée.

Par exemple, le prix unitaire de l’article n° 1 000 passe de 1 500 $ à 1 600 $. Dans ce cas, le montant du produit du contrat est automatiquement recalculé et passe à 1 549,47 $. Le produit du contrat pour l’article n° S0021 est recalculé et passe à 290,53 $.

Quand la modification est confirmée et engagée, les entrées de journal initiales pour les deux articles sont contrepassées et des entrées de journal sont créées :

- **Article n° 1 000 :** L’entrée de journal initiale d’origine de 1 465,26 $ est contrepassée. Une entrée de journal de 1 549,47 $ est créée.
- **Article n° S0021 :** L’entrée de journal initiale d’origine de 274,74 $ est contrepassée. Une entrée de journal de 290,53 $ est créée.

#### <a name="termination"></a>Arrêt

L’article n° S0021 a une date de début en janvier 2020 et une date de fin en décembre 2020, mais est arrêté en juin 2020. Le montant du produit du contrat pour les deux articles doit être recalculé :

- **Article n° 1 000 :** Le produit du contrat est recalculé et passe à 1 567,67 $.
- **Article n° S0021 :** Le produit du contrat est recalculé et passe à 124,00 $.

Une entrée de journal d’ajustement est créée pour la ligne résiliée. L’entrée de journal de la ligne avec le même numéro d’arrangement d’éléments multiples (MEA) est annulée et une entrée de journal est créée :

- **Article n° 1 000 :** L’entrée de journal initiale d’origine de 1 465,26 $ est contrepassée. Une entrée de journal d’ajustement de 1 549,47 $ est créée.
- **Article n° S0021 :** L’entrée de journal initiale d’origine de 274,74 $ est contrepassée. Une entrée de journal de 124,00 $ est créée.
