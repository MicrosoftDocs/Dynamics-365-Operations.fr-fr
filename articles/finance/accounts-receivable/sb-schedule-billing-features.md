---
title: Fonctionnalités de l’échéancier de facturation
description: Cette rubrique explique les fonctionnalités des échéanciers de facturation, telles que les méthodes de tarification, les escalades et les remises, les dates d'alignement, le calcul au prorata, la facturation inversée et les groupes d'articles fractionnés.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ce323565a94e8e70d90a65b7a3143e984a1c159
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8700721"
---
# <a name="billing-schedule-features"></a>Fonctionnalités de l’échéancier de facturation

[!include [banner](../includes/banner.md)]

Cette rubrique explique les fonctionnalités des échéanciers de facturation et des lignes d'échéancier de facturation. Elle décrit les différentes méthodes utilisées pour la tarification, comment utiliser les escalades et les remises et comment contrepasser une période de facturation. Elle comprend également des exemples de calculs au prorata et de groupes d'articles fractionnés.

## <a name="pricing-methods"></a>Méthodes de tarification

Vous pouvez utiliser l'une des méthodes de tarification suivantes pour calculer le prix unitaire d'un article :

* Plat
* Standard
* Niveau
* Forfaitaire

### <a name="flat-pricing"></a>Tarification fixe

Lorsque la méthode de tarification fixe est utilisée, le prix unitaire d'une ligne d'échéancier de facturation sur la page **Tous les échéanciers de facturation** peut être modifiée en n'importe quelle valeur. La valeur **Prix unitaire** est toujours **1**. Par conséquent, les valeurs **Prix unitaire** et **Montant net** d'un article sont les mêmes.

### <a name="standard-pricing-without-a-trade-agreement"></a>Tarification standard (sans accord commercial)

Lorsque la méthode de tarification standard est utilisée sans accord commercial, vous configurez le prix unitaire d'un poste d'échéancier de facturation en sélectionnant **Gestion des informations produit** sur la page **Détails de la version du produit**. Le prix unitaire est indiqué dans la section **Prix de vente de base**. Il est calculé comme *Prix* &divide;*Prix de la quantité*.

### <a name="standard-pricing-with-a-trade-agreement"></a>Tarification standard (avec accord commercial)

Les exemples suivants montrent les calculs de tarification standard lorsqu'un accord commercial existe. Vous pouvez créer des accords commerciaux à partir de la page **Détails de la version du produit**.

Les deux exemples utilisent un article qui a les fourchettes de prix suivantes.

| Qté à partir de | Qté jusqu'à | U de M | Prix | Unité de prix |
|---|---|---|---|---|
| 0 | 100 | Chacun | 1,50 | 1 |
| 100 | 200 | Chacun | 1,25 | 1 |
| 200 | 999999 | Chacun | 1.00 | 1 |

**Exemple 1 :**

La quantité facturée est de 250 et la méthode de tarification standard est utilisée. Étant donné que la quantité se situe dans la plage de prix par quantité 200–999 999, le prix unitaire est de 1,00. 

Le montant net est calculé comme suit :

*Montant net* = (*Quantité* &times; *Prix*) &divide;*Prix unitaire* = (250 &times; 1,00) &divide; 1 = 250

**Exemple 2 :**

La quantité facturée est de 100 et la méthode de tarification standard est utilisée. Étant donné que la quantité de la facture se situe dans la plage de prix par quantité 0-100, le prix unitaire est de 1,50.

> [!NOTE]
> La quantité facturée est comprise entre 0 et 100 au lieu de 100 et 200 car, dans le comportement de correspondance de la quantité standard, une quantité correspond si elle est *supérieure ou égale à* la quantité « à partir de » et *inférieure à* la quantité « jusqu'à ».

Le montant net est calculé comme suit :

*Montant net* = (100 &times; 1,50) &divide; 1 = 150

### <a name="tier-pricing"></a>Tarification par niveau

Pour l'exemple suivant, un article a les fourchettes de prix suivantes.

| Qté à partir de | Qté jusqu'à | U de M | Prix | Unité de prix |
|---|---|---|---|---|
| 0 | 100 | Chacun | 1,50 | 10 |
| 100 | 200 | Chacun | 1,25 | 10 |
| 200 | 999999 | Chacun | 1.00 | 10 |

Si la quantité facturée est de 250 et que la méthode de tarification par niveaux est utilisée, les prix des articles sont calculés de la manière suivante, en fonction des tranches de prix :

- **100 premiers articles :** 100 &times; 1,50 = 150,00
- **100 articles suivants :** 100 &times; 1,25 = 125,00
- **Articles restants :** 50 &times; 1,00 = 50,00

Le montant net est calculé comme suit :

*Montant net* = (150,00 &divide; 10) + (125,00 &divide; 10) + (50,00 &divide; 10) = 15,00 + 12,50 + 5,00 = 32,50

Une fois le montant net calculé, le prix unitaire est calculé en divisant le montant net par la quantité :

*Prix unitaire* = 32,50 &divide; 250 = 0,13

### <a name="flat-tier-pricing"></a>Tarification fixe par niveau

Pour l'exemple suivant, un article a les fourchettes de prix suivantes.

| Qté à partir de | Qté jusqu'à | U de M | Montant forfaitaire | Unité de prix |
|---|---|---|---|---|
| 0 | 50 | Chacun | 100.00 | 50 |
| 50 | 200 | Chacun | 150.00 | 200 |

Le tableau suivant présente les factures et les prix unitaires pour les différentes quantités achetées. Le montant net est calculé en premier, puis le prix unitaire est calculé.

| Facture | Quantité achetée | Prix unitaire | Montant HT |
|---|---|---|---|
| 1 | 25 | 2,00 &divide; 25 = 0,08 | 100 &divide; 50 = 2,00 |
| 2 | 20 | 2,00 &divide; 20 = 0,10 | 100 &divide; 50 = 2,00 |
| 3 | 50 | 2,00 &divide; 50 = 0,04 | 100 &divide; 50 = 2,00 |
| 4 | 60 | 0,75 &divide; 60 = 0,0125 = 0,01 | 150 &divide; 200 = 0,75 |

## <a name="escalations-and-discounts"></a>Escalades et remises

Une *escalade* est une augmentation de prix pour une période de facturation future pour laquelle la facture n'a pas encore été créée. Une *remise* est une réduction de prix pour une période de facturation future pour laquelle la facture n'a pas encore été créée.

Dans la facturation des abonnements, les escalades et les remises ne peuvent pas être appliquées rétroactivement à un échéancier de facturation. Par exemple, vous ne pouvez pas appliquer une escalade à un échéancier de facturation trois mois dans le passé et le traiter. En d'autres termes, vous ne pouvez pas appliquer une augmentation de prix survenue il y a trois mois.

Vous pouvez appliquer une escalade ou une remise à un échéancier de facturation ou à une ligne d'échéancier de facturation à l'un des endroits suivants :

- La page de liste **Tous/Calendriers de facturation actifs**
- Un échéancier de facturation spécifique
- Une ligne d'échéancier de facturation spécifique

### <a name="apply-an-escalation-or-discount"></a>Appliquer une escalade ou une remise

Pour appliquer une escalade ou une remise à un échéancier de facturation, procédez comme suit.

1. Sélectionnez un échéancier de facturation ou une ligne d'échéancier de facturation.
2. Sélectionnez **Escalade et remise**, soit sur l'onglet **Escalade et remise** ou sur la ligne de l'échéancier de facturation.
3. Si un indice des prix à la consommation est utilisé pour calculer l'escalade ou la remise, sélectionnez une valeur dans le champ **Calcul de l'indice des prix à la consommation**.
4. Sélectionnez **Nouveau** pour ajouter une ligne d'escalade ou de remise.
5. Pour une remise, cochez la case **Remise**. Pour une escalade, laissez la case **Remise** décochée.
6. Définissez les champs **Date de début** et **Fréquence**.
7. Pour les articles reportés qui utilisent la fonction de revenu non facturé, définissez le champ **Date de fin**.
8. Définissez le champ **Pourcentage**, **Montant** ou **Barème de l'indice des prix à la consommation**.
9. Définissez le champ **Date de fin**.
10. Cliquez sur **OK**.
11. Répétez les étapes 4 à 10 pour chaque ligne d'escalade ou de remise supplémentaire nécessaire.

### <a name="fields-on-the-billing-schedule-lines-page"></a>Champs de la page Lignes d'échéanciers de facturation

La page **Lignes d'échéancier de facturation** contient les champs suivants.

| Champ | Description |
|---|---|
| Numéro d'article | Numéro d’article de la ligne de l'échéancier de facturation. Ce champ est disponible uniquement lorsque la page est ouverte à partir d'un poste de l’échéancier de facturation. |
| Calcul de l’indice des prix à la consommation | <p>Sélectionnez la méthode utilisée pour calculer l'escalade de l'indice des prix à la consommation :</p><ul><li>**Indice des prix à la consommation antérieur** : utilise la valeur précédente de l'indice des prix à la consommation pour le calcul de l'escalade.</li><li>**Indice des prix à la consommation de base** : utilise la valeur de base de l'indice des prix à la consommation pour le calcul de l'escalade.</li></ul> |
| Grille **Ligne** | |
| Remise | <p>Cochez la case pour spécifier si la modification du montant est une escalade ou une remise :</p><ul><li>**Sélectionné** : la modification applique une remise à l'échéancier de facturation ou à la ligne de l'échéancier de facturation.</li><li>**Désélectionné** : la modification applique une escalade à un échéancier de facturation ou à une ligne de l'échéancier.</li></ul><p>Le paramètre de cette case à cocher ne peut pas être modifié pour les articles qui utilisent la fonctionnalité de revenus non facturés. De plus, les remises ne peuvent pas être appliquées aux articles qui utilisent le fractionnement du revenu.</p> |
| Date de début | Sélectionnez la date de début de l'escalade ou de la remise. |
| Fréquence | Sélectionnez la fréquence de l'escalade ou de la remise : **Aucune**, **Mensuelle**, **Trimestrielle**, **Semestrielle** ou **Annuelle**. |
| Pourcentage | Spécifiez le pourcentage de l'escalade ou de la remise. |
| Montant | Spécifiez le montant de l'escalade ou de la remise. |
| Programmes d’indice des prix à la consommation | Sélectionnez le barème de l'indice des prix à la consommation utilisé pour les calculs. |
| Date de fin | <p>Sélectionnez la date de fin de l'escalade ou de la remise.</p><p>**Remarque :** ce champ est obligatoire pour les articles qui utilisent la fonctionnalité de revenus non facturés.</p> |
| Numéro d’échéancier de report | <p>Le numéro de l'échéancier de report.</p><p>Ce champ est disponible uniquement lorsque la page est ouverte à partir d'une ligne de l’échéancier de facturation.</p> |
| Numéro de lot du journal | <p>Numéro de lot du journal.</p><p>Ce champ est disponible uniquement lorsque la page est ouverte à partir d'une ligne de l’échéancier de facturation.</p> |
| Montant de remise totale | <p>La somme des montants de remise pour toutes les lignes de la grille.</p><p>Ce champ est disponible uniquement lorsque la page est ouverte à partir d'une ligne de l’échéancier de facturation.</p> |
| Montant actuel des revenus non facturés à court terme | <p>Le montant actuel des revenus non facturés à court terme.</p><p>Ce montant apparaît lorsqu'une méthode de report à court terme est sélectionnée sur la page **Paramètres de facturation des contrats récurrents** et que les comptes du poste sont configurés sur la page **Configuration des revenus non facturés**.</p> |
| Montant actuel des revenus non facturés à long terme | <p>Le montant actuel des revenus non facturés à long terme.</p><p>Ce montant apparaît lorsqu'une méthode de report à court terme est sélectionnée sur la page **Paramètres de facturation des contrats récurrents** et que les comptes du poste sont configurés sur la page **Configuration des revenus non facturés**.</p> |

## <a name="proration-examples"></a>Exemples de calculs au prorata

Les calculs au prorata peuvent être basés sur le nombre de jours ou le nombre de mois. La méthode utilisée pour le calcul du prorata est définie sur la page **Paramètres de facturation des contrats récurrents**. La méthode de calcul au prorata affecte la manière dont les montants sont calculés pour un échéancier de facturation dans les situations suivantes :

- Création initiale
- Application d'une escalade ou d'une remise
- Arrêt
- Placement ou suppression d'une suspension
- Ajout de support ou renouvellement

La méthode de calcul au prorata affecte également les calculs du rapport mensuel sur les revenus récurrents (MRR).

### <a name="example-1"></a>Exemple 1

Le montant annuel d'un échéancier de facturation est de 5 000 USD. La date de début est le 12 août 2019 et la date de fin est le 22 décembre 2019. La fréquence de facturation est annuelle. Le montant au prorata est calculé de la manière suivante, selon que la méthode de calcul journalière ou mensuelle est utilisée :

- **Journalier**

    - *Nombre de jours* = *Date de fin* – *Date de début* + 1 = 133 jours
    - *Nombre de jours dans l'année* = 11 août 2020 – 12 août 2019 + 1 = 366 jours
    - *Montant au prorata* = 5 000 &times; (133 &divide; 366) = 1816,94

- **Tous les mois**

    - *Partie du mois de début* = (31 – 12 + 1) &divide; 31 = 20 &divide; 31
    - *Mois intermédiaires* = 3
    - *Partir du mois de fin* = 22 &divide; 31
    - Montant au prorata = 5 000 &divide; 12 &times; \[(20 &divide; 31) + 3 + (22 &divide; 31)\] = 1814,52

### <a name="example-2"></a>Exemple 2

Le montant annuel d'un échéancier de facturation est de 12 000 USD. La date de début est le 1 août 2019 et la date de fin est le 31 décembre 2019. La fréquence de facturation est annuelle. Le montant au prorata est calculé de la manière suivante, selon la méthode de calcul utilisée :

- **Journalier**

    - *Nombre de jours* = *Date de fin* – *Date de début* + 1 = 153 jours
    - *Nombre de jours dans l'année* = 31 juillet 2020 – 1 août 2019 + 1 = 366 jours
    - *Montant au prorata* = 12 000 &times; (153 &divide; 366) = 5016,39

- **Mensuel (mois complet)**

    - *Nombre de mois* = 5
    - *Nombre total de mois* = 12
    - *Montant au prorata* = (12 000 &times; 5) &divide; 12 = 5 000

## <a name="reversing-a-period-billing"></a>Contrapassation d'une période de facturation

Pour cet exemple, un échéancier de facturation ne comporte qu'une seule ligne :

- La facturation est effectuée mensuellement pendant 12 mois de janvier à décembre.
- Des factures ont été créées pour toutes les périodes jusqu'en avril.

Vous souhaitez annuler la facture pour la période de facturation d'avril.

Si aucune facture client n'a encore été créée pour la période de facturation d'avril, vous pouvez supprimer la commande client. Dans ce cas, le statut **Facturé** du détail sera supprimé. Cependant, étant donné qu'une facture a été créée pour la période de facturation, le statut **Facturé** du détail ne peut pas être effacé. Par conséquent, pour annuler la facturation d'avril, vous devez créer un avoir compensatoire pour la ligne.

1. Sur la page **Tous les échéanciers de facturation**, créez une ligne d'échéancier pour le même article.
2. Changez la valeur **Quantité** de l'article en la valeur négative de la quantité d'origine.
3. Définissez le champ **Fréquence de facturation** sur **Une fois**.
4. Mettez à jour les dates de début et de fin afin qu'elles correspondent aux dates de la ligne de détails de facturation pour laquelle vous souhaitez créer un avoir. Pour cet exemple, définissez la date de début sur le 1er avril 2019 et la date de fin sur le 30 avril 2019.
5. Enregistrez vos modifications.
6. Ouvrez la page **Générer une facture** et créez la commande client contenant l'avoir pour la période spécifiée.
7. Facultatif : validez la facture.

Lorsque vous passez en revue les lignes de l'échéancier de facturation, vous remarquez que la nouvelle ligne comporte un lien vers l'avoir. La ligne d'origine contiendra toujours un lien vers la facture d'avril d'origine.

## <a name="split-item-group-examples"></a>Exemples de groupes d'articles fractionnés

Pour cet exemple, la configuration suivante est en place :

- Sur la page **Paramètres de facturation des contrats récurrents**, **Fractionner par groupe d'articles** est sélectionné, et le champ **Type d'échéancier unique** est défini sur **Client**.
- Trois groupes d'articles ont été créés : **PREFIX**, **DATAHUB**, et **SPP**.
- Le client US-001 a plusieurs échéanciers de facturation où le groupe d'articles est PREFIX ou DATAHUB.
- Le client US-002 a plusieurs échéanciers de facturation où le groupe d'articles est PREFIX ou SPP.

| Numéro d’échéancier de facturation | Client | Groupe d’articles |
|---|---|---|
| SCH001 | US-001 | PREFIX |
| SCH002 | US-001 | DATAHUB |
| SCH003 | US-002 | PREFIX |
| SCH004 | US-002 | SPP |

Le client US-001 achète un article de renouvellement qui appartient au groupe d'articles PREFIX. Cette transaction est une nouvelle commande client.

| Commande client n° | Client | Article principal | Article de renouvellement | Groupe d’articles de renouvellement | Numéro d’échéancier de facturation |
|---|---|---|---|---|---|
| SO0001 | US-001 | D0001 | D0002 | PREFIX | SCH001 |

Lorsque la facture de la commande client est validée, l'article de renouvellement est ajouté à l'échéancier de facturation existant (SCH001) pour le client. Cet échéancier de facturation utilise le groupe d'articles PREFIX. Tous les articles de renouvellement qui appartiennent au même groupe d'articles sont placés dans le même échéancier de facturation.

**En-tête**
 
| Numéro d’échéancier de facturation | Client | Groupe d’articles |
|---|---|---| 
| SCH001 | US-001 | PREFIX |

**Ligne**

| Numéro d’échéancier de facturation | Client | Groupe d’articles |
|---|---|---|
| SCH001 | US-001 | D0002 |

Le client US-001 achète maintenant un article de renouvellement qui appartient au groupe d'articles SPP. Cette transaction est une nouvelle commande client.

| Commande client n° | Client | Article principal | Article de renouvellement | Groupe d’articles de renouvellement | Numéro d’échéancier de facturation |
|---|---|---|---|---|---|
| SO0002 | US-001 | D0003 | D0004 | SPP | |

Actuellement, le client US-001 n'a pas d'échéancier de facturation qui utilise le groupe d'articles SPP. Par conséquent, un nouvel échéancier de facturation est créé.

**En-tête**

| Numéro d’échéancier de facturation| Client | Groupe d’articles |
|---|---|---|
| SCH005 | US-001 | SPP |

**Ligne**

| Numéro d’échéancier de facturation | Client | Groupe d’articles |
|---|---|---|
| SCH005 | US-001 | D0004 |

### <a name="multiple-billing-schedules-for-the-same-end-user-and-customer"></a>Échéanciers de facturation multiples pour le même utilisateur final et client

Pour cet exemple, la configuration suivante est en place :

- Sur la page **Paramètres de facturation des contrats récurrents**, **Fractionner par groupe d'articles** est sélectionné, et le champ **Type d'échéancier unique** est défini sur **Utilisateur final**.
- Sur la page **Utilisateurs finaux**, la relation client et utilisateur final suivante est établie.

    | Compte client | Compte d’utilisateur final |
    |---|---|
    | US-001 | US-221 |

Plusieurs échéanciers de facturation sont créés pour les combinaisons client-utilisateur final. Comme **Fractionner par groupe d'articles** est sélectionné sur la page **Paramètres de facturation des contrats récurrents**, plusieurs échéanciers de facturation peuvent être créés pour la même relation client et utilisateur final.

| Numéro d’échéancier de facturation | Client | Compte d’utilisateur final | Groupe d’articles d'en-tête |
|---|---|---|---|
| SCH005 | US-001 | US-221 | IG1 |
| SCH006 | US-001 | US-221 | IG2 |
| SCH007 | US-001 | US-221 | IG3 |

Sur la page **Configuration de l'article**, vous créez des relations entre les articles de support et de renouvellement.

| Article - valide pour | Relation d’article | Article de support | Article de renouvellement | Groupe d’articles de renouvellement |
|---|---|---|---|---|
| Table | D001 | ITEM27 | D007 | IG1 |
| Table | D002 | ITEM28 | D005 | IG2 |
| Table | D003 | ITEM29 | D006 | IG3 |

Vous créez maintenant une commande client pour le client US-001. Cette commande client contient des articles de la page **Configuration de l'article**. Lorsque vous créez la commande client, ouvrez la page **Processus de support et de renouvellement** et définissez le champ **Compte utilisateur final** et toute autre information requise pour l'article de renouvellement.

Lorsque la facture de la transaction est créée et validée, différents échéanciers de facturation sont créés pour la combinaison client/utilisateur final et groupe d'articles. Plusieurs lignes d'une même commande client peuvent être affectées au même échéancier de facturation.

| Commande client n° | Client | Compte d’utilisateur final | Article principal | Article de support | Article de renouvellement | Numéro d’échéancier de facturation |
|---|---|---|---|---|---|---|
| SO0001 | US-001 | US-221 | D001 | ITEM27 | D007 | SCH005 |
| SO0001 | US-001 | US-221 | D002 | ITEM28 | D005 | SCH006 |
| SO0001 | US-001 | US-221 | D003 | ITEM29 | D006 | SCH005 |
