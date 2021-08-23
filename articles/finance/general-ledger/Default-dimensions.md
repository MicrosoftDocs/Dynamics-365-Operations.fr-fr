---
title: Dimension financières et validation
description: Lorsque vous planifiez et paramétrez votre plan de comptes, vous devez vérifier la manière dont les différents composants fonctionneront ensemble lorsque vous validez un document ou un journal. Ces composants incluent les structures de compte, des règles avancées, et bilan et des dimensions fixes. Cette rubrique explique ce qu’est chaque composant et comment les composants fonctionnent ensemble.
author: aprilolson
ms.date: 08/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerChartofAccounts,DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 9e7416c1ed69fa9783694e2adee7ada4e25e14054daeb1761428855690eb522f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778964"
---
# <a name="financial-dimensions-and-posting"></a>Dimension financières et validation 

[!include [banner](../includes/banner.md)]

Lorsque vous planifiez et paramétrez votre plan de comptes, vous devez vérifier la manière dont les différents composants fonctionneront ensemble lorsque vous validez un document ou un journal. Ces composants incluent les structures de compte, des règles avancées, et bilan et des dimensions fixes. Cette rubrique explique ce qu’est chaque composant et comment les composants fonctionnent ensemble.

## <a name="chart-of-accounts-and-financial-dimension-components"></a>Composants Plan de comptes et Dimension financière

Un système riche en règles est utilisé pour définir des combinaisons valides des principaux comptes et valeurs de dimensions financières. Cette section fournit une brève vue d’ensemble de la fonctionnalité de chaque composant et explique où vous pouvez rechercher le composant.

### <a name="account-structures"></a>Structures de compte

Une structure de compte est obligatoire lorsque vous paramétrez la comptabilité. Vous devez définir et activer au moins une structure de compte, et vous devez l’affecter à la comptabilité. La structure de compte doit se composer d’un compte principal. Vous pouvez définir l’ordre des segments le mieux adapté à l’entreprise. Une fois le compte principal défini, le système peut déterminer la structure de compte qui est utilisée. En mettant le compte principal d’abord ou près de l’avant d’une structure, vous pouvez permettre de restreindre les valeurs et aider également le système à appliquer la dernière valeur valide connue comme valeur par défaut. Vous pouvez avoir jusqu’à 10 dimensions financières supplémentaires dans la structure de compte. La structure de compte définit les valeurs de dimension valides en combinaison avec d’autres valeurs. Elle définit également si des valeurs de dimension doivent être entrées.

### <a name="advanced-rules"></a>Règles avancées

Les règles avancées sont un composant facultatif lorsque vous paramétrez le plan de comptes. Vous pouvez ajouter autant de règles avancées que vous le souhaitez à une structure de compte. Les règles avancées sont généralement utilisées pour gérer les cas où les dimensions financières supplémentaires doivent être suivies lorsque des critères spécifiques sont renseignés. Par exemple, si vous utilisez un compte de frais de déplacement, vous pouvez suivre des informations supplémentaires, telles que l’événement pour lequel l’employé voyage. S’il existe plusieurs règles avancées, elles sont appliquées dans l’ordre alphabétique, selon les noms des règles. Les segments qu’une règle ajoute peuvent être utilisés uniquement après les segments de la structure de compte.

### <a name="balancing-dimension"></a>Dimension d’équilibrage

Vous pouvez définir facultativement une dimension financière d’équilibrage. Dans la page **Comptabilité**, vous pouvez définir la dimension financière qui doit être équilibrée. Puis, chaque fois que les transactions sont validées dans cette dimension financière, le système crée automatiquement et valide les entrées pour activer la dimension financière équilibrée.

### <a name="defaultfixed-financial-dimensions-on-the-main-account"></a>Dimensions financières par défaut/fixes sur le compte principal

Les dimensions par défaut provenant de divers endroits, telles que les enregistrements principaux (par exemple, enregistrements client ou fournisseur), les en-têtes de document, et le compte principal. Cette rubrique décrit sur les dimensions par défaut sur le compte principal par entité juridique. Vous pouvez définir si un compte principal a une valeur **Non fixe** ou **Fixe** pour chaque dimension financière utilisée dans toutes les structures de compte pour la comptabilité. Si une dimension financière est **Non fixe**, elle utilise une valeur par défaut, mais cette valeur peut être remplacée. Ceci s’applique à toutes les valeurs par défaut dans le système, même les valeurs par défaut provenant des enregistrements principaux. Si une dimension financière est égale à une valeur **Fixe**, cette valeur est toujours appliquée, même si elle provenait de quelque part comme valeur par défaut ou que l’utilisateur l’a saisie.

## <a name="order-in-which-default-dimensions-are-applied-during-posting"></a>Ordre dans lequel les dimensions par défaut sont appliquées pendant la validation

Les personnes ont souvent des questions sur l’ordre dans lequel les différents composants sont exécutés. Il est primordial que vous compreniez l’ordre dans lequel les dimensions par défaut sont appliquées, car ce comportement affecte l’approche que vous adoptez pour le paramétrage.

> [!NOTE]
> Ces informations ne s’appliquent qu’à l’application des dimensions par défaut dans l’application. Si vous importez des données à l’aide de Microsoft Excel ou du cadre de gestion des données, le comportement diffère.

### <a name="example-1"></a>Exemple 1 :

**Structure de compte**

| Compte principal            | Unité commerciale           | Département              | Centre de coût             |
|-------------------------|-------------------------|-------------------------|-------------------------|
| Toutes les valeurs sont autorisées. | Toutes les valeurs sont autorisées. | Toutes les valeurs sont autorisées. | Toutes les valeurs sont autorisées. |

**Compte principal**

| Compte principal | Nom          | Entité juridique | Département                                 |
|--------------|---------------|--------------|--------------------------------------------|
| 401100       | Ventes de produits | USMF         | Fixe – 022 Département Ventes et marketing |

L’illustration suivante présente la dimension par défaut fixe définie sur le compte principal 401100.

[![Dimensions financières par défaut.](./media/default-dimensions.png)](./media/default-dimensions.png)

Pour cet exemple très élémentaires, nous entrons un journal des opérations diverses où la dimension Département est définie pour utiliser la valeur **023** par défaut (Operations). Nous entrons et validons un compte général. L’illustration suivante présente la dimension financière par défaut sous l’en-tête de comptabilité.

[![Journaux des opérations diverses.](./media/general-journal.png)](./media/general-journal.png)

La dimension par défaut de l’en-tête de journal va générer le département 023 à appliquer par défaut dans la ligne de compte de vente. L’illustration suivante présente la ligne de journal des opérations diverses, où la valeur de dimension par défaut **023** de l’en-tête est appliquée.

[![N° document de journal.](./media/journal-voucher.png)](./media/journal-voucher.png)

Toutefois, si la ligne est validée, la dimension fixe est appliquée, et la ligne est validée dans le département 022. L’illustration suivante présente le document validé, où la dimension fixe est appliquée pour le compte de vente.

[![Justificatifs de transaction avec une dimension fixe appliquée.](./media/voucher-transactions.png)](./media/voucher-transactions.png)

### <a name="example-2"></a>Exemple 2

Cet exemple utilise le même paramétrage que le premier exemple. Cependant, nous ajoutons un second composant et utilisons la dimension Département en tant que dimension d’équilibrage. Dans l’illustration suivante, **Département** est défini comme dimension financière pour la comptabilité USMF.

[![Illustration montrant le Département comme dimension financière d'équilibrage.](./media/ledger.png)](./media/ledger.png)

Lorsque le même paramétrage d’en-tête de journal est utilisé, et que la même transaction est validée, la dimension fixe est appliquée en premier. Puis la logique d’équilibrage est appliquée pour garantir que chaque département a une entrée équilibrée. L’illustration suivante présente des pièces comptables incluant l’entrée d’équilibrage après que la dimension fixe a été appliquée.

[![Justificatifs de transaction après l'application de l'entrée d'équilibrage.](./media/voucher-transactions2.png)](./media/voucher-transactions2.png)

### <a name="example-3"></a>Exemple 3

Dans cet exemple, nous ajoutons une règle avancée. La règle avancée spécifie que si le compte de vente 401100 et le département 022 (Ventes et marketing) sont utilisés, le système doit suivre un segment supplémentaire nommé Client.

Cet exemple est important en raison de la commande. La structure de compte est déterminée une fois le compte principal entré. Si vous faites référence au paramétrage de la structure de compte, le système peut déterminer que le compte principal, les unités commerciales, le département, le centre de coût sont appropriés. À ce stade, la règle avancée n’a pas été déclenchée, car les dimensions fixes ne sont pas appliquées jusqu’à ce que les dimensions par défaut aient été appliquées pour le justificatif de journal lors de la validation. Dans l’illustration suivante, le segment Client n’est pas présent, car les critères de la règle avancée n’ont pas été remplis.

[![Compte général.](./media/drop-down.png)](./media/drop-down.png)

La validation ne sera pas réussi, car la dimension fixe a été appliquée à la fin du processus. La validation de la dimension détermine que le segment Client est nécessaire si le compte principal est 401100 et que le département est 022. La validation ne peut pas se produire en raison d’une erreur de validation. L’illustration suivante présente le message qui apparaît après que la validation de dimension détermine que le client est un segment requis.

[![Détails du message.](./media/message.png)](./media/message.png)

Dans cet exemple, vous devez remplacer la valeur par défaut pour que la règle avancée se déclenche et que vous puissiez entrer le segment Client. Toutefois, cette solution n’est pas toujours possible, et certains utilisateurs ne se rendent même pas compte des règles de validation. Par conséquent, il est important que vous compreniez dans quel l’ordre les dimensions par défaut sont appliquées lorsque vous paramétrez votre plan de comptes.

Pour atteindre ce que vous souhaitez dans cet exemple, vous pouvez modifier la configuration de plusieurs façons. Par exemple, vous pouvez créer une structure de compte pour les comptes de vente et inclure le segment Client à la structure. Vous pouvez également ajouter des lignes dans une structure de compte existante, puis spécifier le compte principal et les valeurs de département valides. Puis, dans la structure client supplémentaire, vous pouvez trouver utile d’avoir une structure de compte distincte des comptes de vente dans lesquels le segment Client est présent.

## <a name="additional-resources"></a>Ressources supplémentaires 

Certaines des ressources suivantes se réfèrent à une version antérieure de notre logiciel. Toutefois, une grande partie des informations sur l’application des dimensions par défaut et sur bon nombre des concepts sont identiques dans la version précédente, et les références sont toujours valides.

[Journaux équilibrés pour la comptabilité interunités](example-balanced-journals-interunit-accounting.md)

[Plan de comptes](plan-chart-of-accounts.md) 

[Planification de votre plan de comptes dans le blog AX 2012](/archive/blogs/axsa/planning-your-chart-of-accounts-in-ax-2012-part-1-of-7) – Ce lien mène à la partie 1 d’une série de 7 parties.

[Utilisation de valeurs par défaut pour les dimensions dans les répartitions comptable](/archive/blogs/ax_gfm_framework_team_blog/dimension-defaulting-in-accounting-distributions-part-1-introduction)

[Utilisation de valeurs par défaut pour les dimensions dans la structure de dimensions](/archive/blogs/ax_gfm_framework_team_blog/dimension-defaulting-part-1-financial-dimensions-discovery)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
