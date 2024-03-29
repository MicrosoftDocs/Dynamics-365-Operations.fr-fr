---
title: Vue d’ensemble de consolidations financières et conversion de devises
description: Cet article décrit les consolidations financières et la conversion de devises dans le module Comptabilité.
author: jinniew
ms.date: 10/07/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 1b2f5f56e757e89339c12fd41c59848b4c987a2f
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831831"
---
# <a name="financial-consolidations-and-currency-translation-overview"></a>Vue d’ensemble de consolidations financières et conversion de devises

[!include [banner](../includes/banner.md)]

Cet article décrit l’approche utilisée par Microsoft Dynamics 365 Finance et l’outil États financiers pour les consolidations. Elle décrit les scénarios impliquant la génération d’états pour plusieurs sociétés, l’agrégation, l’élimination et la participation minoritaire. Elle explique également comment gérer des cas particuliers, comme les scénarios où des entités juridiques ont différentes périodes fiscales ou différents plans de comptes.

Cet article s’adresse aux utilisateurs et aux consultants fonctionnels, et elle suppose que les lecteurs ont une connaissance générale de Finance et de l’outil États financiers. Le paramétrage de base n’est pas abordé.

> [!NOTE]
> Le terme *entité juridique* est utilisée dans Finance, et le terme *société* est utilisée dans l’outil États financiers. Ces deux termes sont utilisés dans cet article. Toutefois, pour les besoins de cet article, leurs significations sont identiques.

## <a name="audience"></a>Audience
Cet article s’adresse aux utilisateurs chargés des finances et de la comptabilité et aux consultants en application qui souhaitent utiliser Finance and Reporting et l’outil États financiers pour consolider les données de plusieurs sociétés et dans plusieurs devises.

## <a name="approach"></a>Approche
Finance utilise une entité juridique distincte pour traiter une consolidation. Il prend en charge la consolidation d’une seule instance mais fournit une option permettant de regrouper les données d’autres sources. Le processus de consolidation doit être exécuté chaque fois que des modifications sont apportées aux entités juridiques source.

L’outil États financiers peut consolider plusieurs sociétés lors de la génération d’états. Bien que les données soient stockées dans un mini-data warehouse, soient utilisées pour le contrôle de version et puissent être exportées, chaque société source est le propriétaire et le conteneur des données. L’état peut être exécuté à tout moment, même toutes les minutes (par exemple). Il fournit plusieurs avantages supplémentaires, comme la possibilité d’accéder à toutes les sociétés et dimensions.

Les utilisateurs peuvent utiliser la fonctionnalité Consolidation en ligne, l’outil États financiers, ou une combinaison. Leur choix dépend des besoins de leur société et des préférences de leurs auditeurs.

## <a name="consolidations"></a>Consolidations
Le module **Consolidations** propose des options pour consolider plusieurs entités juridiques au cours du processus de consolidation, ainsi que pour importer ou exporter le solde d’une société. Vous pouvez également paramétrer des éliminations et valider des journaux d’élimination.

## <a name="benefits-of-using-consolidate-online"></a>Avantages de l’utilisation de la fonctionnalité Consolidation en ligne
Les clients qui utilisent le module **Consolidations** bénéficieront de plusieurs avantages :

- **Profondeur des données** – Vous pouvez créer des états consolidés qui regroupent les données réelles et budgétées au niveau du compte et de la dimension.
- **Consolidations dynamiques** – Les consolidations peuvent être traitées plusieurs fois.
- **Fonctionnalités d’audit** – Les dimensions et les comptes sont tenus à jour pour l’analyse et l’audit, et les soldes sont créés par date.
- **Conversion de devises** – Vous pouvez définir les plages de compte et les taux pour convertir des données de la devise comptable de la société source vers la devise comptable de la société de consolidation.
- **Traiter les éliminations dans une société consolidée ou d’élimination** – Vous pouvez traiter et valider les éliminations comme un processus unique lors de la consolidation. Vous pouvez également exécuter une proposition séparément.

## <a name="supported-consolidation-scenarios"></a>Scénarios de consolidation pris en charge
Voici quelques-uns des scénarios de consolidation pris en charge par la fonctionnalité Consolidation en ligne :

- Consolidations sur un seul niveau dans les entités juridiques
- Consolidations impliquant des éliminations
- Participation minoritaire (pour ce scénario, le calcul et la saisie manuels dans la société doivent être utilisés.)
- Plans de comptes multiples dans les entités juridiques
- Différents calendriers fiscaux dans plusieurs entités juridiques
- Consolidations impliquant plusieurs devises de déclaration

## <a name="legal-entity-setup"></a>Paramétrage de l’entité juridique
Avant de traiter une consolidation, vous devez paramétrer l’entité juridique. Vous pouvez exécuter la consolidation autant de fois que nécessaire, et toutes les données seront converties de la devise comptable de la société source ou la devise de déclaration vers la devise définie pour la société de consolidation. Par conséquent, pour la structure organisationnelle suivante, si vous devez d’abord convertir toutes les sociétés nord-américaines en dollar américain (USD) puis en euro (EUR), la devise de la société parent, vous devez avoir au moins deux sociétés de consolidation.

![Structure organisationnelle.](./media/organizational-structure.png "Structure organisationnelle")

Dans la structure organisationnelle précédente, vous devez avoir une entité juridique pour la consolidation nord-américaine, car les consolidations s’effectuent toujours de la devise comptable de la société source vers la devise de la société de consolidation. Dans l’exemple, si toutes les sociétés sont incluses dans une consolidation unique, la filiale mexicaine sera convertie de pesos mexicains (MXN) en EUR, et non de MXN en USD puis en EUR.

Lorsque vous créez l’entité juridique, vous pouvez spécifier si la société est utilisée pour le processus de consolidation et le processus d’élimination, ou pour l’un d’eux uniquement. Dans l’illustration suivante, la société est utilisée pour les deux processus. Notez que vous ne pouvez pas valider les journaux d’opérations diverses dans une société de consolidation, mais vous pouvez les valider dans une société d’élimination. Par conséquent, vous souhaitez peut-être avoir une société d’élimination distincte.

![Entité juridique utilisée pour la consolidation et l’élimination.](./media/sep-elimination-company.png "Entité juridique utilisée pour la consolidation et l’élimination")

## <a name="main-accounts-and-consolidation-account-groups"></a>Comptes principaux et groupes de comptes de consolidation
Vous devez choisir la manière dont vous souhaitez consolider votre plan de comptes. Au cours du processus de consolidation, trois options sont disponibles pour consolider les comptes principaux.

La première option consiste à utiliser les comptes principaux des sociétés source. Dans ce cas, chaque compte de toutes les sociétés sera consolidé. Par exemple, si les espèces correspondent au compte 100000 dans la société USMF et au compte 1100 dans la société DEMF, la société de consolidation inclura les deux comptes. Chaque compte aura son solde respectif.

La deuxième option consiste à spécifier un compte de consolidation par défaut dans la page **Comptes principaux**. Le compte sera ensuite mis en correspondance avec le compte de consolidation. Cette option peut être utile si vous avez différents plans de comptes ou vous devez les mettre en correspondance avec un graphique défini par le siège.

![Compte de consolidation par défaut spécifié sur la page Comptes principaux.](./media/main-accounts.png "Compte de consolidation par défaut spécifié sur la page Comptes principaux")

La troisième option consiste à utiliser des groupes de comptes de consolidation. Vous pouvez définir autant de groupes de comptes de consolidation que nécessaire. Ensuite, dans la page **Comptes de consolidation supplémentaires**, vous mettez en correspondance le compte principal du plan de comptes avec le compte requis pour ce groupe.

![Mise en correspondance sur la page Comptes de consolidation supplémentaires.](./media/additional-consolidation-accounts.png "Mise en correspondance sur la page Comptes de consolidation supplémentaires")

## <a name="consolidating-online"></a>Consolidation en ligne
Pour savoir comment entrer les détails des consolidations en ligne, voir [Consolidations financières en ligne](./consolidate-online.md).

## <a name="managing-consolidation-transactions"></a>Gestion des transactions de consolidation
Pour afficher les résultats de la consolidation, plusieurs options sont disponibles :

- Générez un état financier pour la société de consolidation.
- Consultez la page de liste **Balance comptable** dans la société de consolidation.
- Dans la liste des transactions de consolidation sur la page **Consolidations**, affichez les soldes créés par date pour chaque société source pour chaque période.

    ![Transactions de consolidation sur la page Consolidations.](./media/managing-consolidation-transactions.png "Transactions de consolidation sur la page Consolidations")

Pour réexécuter la consolidation, vous pouvez simplement traiter la consolidation. Sinon, vous pouvez d’abord sélectionner **Supprimer les transactions** dans la page **Consolidations**.
Dans le cas où les soldes de votre compte consolidé ne sont pas exacts, ces soldes peuvent être corrigés à l’aide de la page **Ajustements de la période de clôture**.

## <a name="consolidate-with-import"></a>Consolider avec importation
La fonctionnalité Consolider avec importation fonctionne comme la fonctionnalité Consolidation en ligne. Lorsque vous sélectionnez les entités juridiques, vous naviguerez jusqu’au fichier source contenant les données.

## <a name="export-company-balances"></a>Exporter soldes de la société
La fonctionnalité Exporter soldes de la société fonctionne également comme la fonctionnalité Consolidation en ligne. Lorsque vous sélectionnez les entités juridiques, vous définissez un chemin d’accès au fichier pour la sortie.

## <a name="elimination-rules"></a>Règles d’élimination
Pour éliminer des transactions intersociétés, vous pouvez créer une règle d’élimination. Vous pouvez également créer une entrée d’élimination manuelle dans une société désignée comme société d’élimination. Si vous créez une règle d’élimination, deux options sont disponibles pour la méthode d’élimination : **Modification nette** et **Fixe**.

### <a name="set-up-elimination-rules"></a>Configurer les règles d’élimination
Lorsque vous définissez des règles d’élimination dans Finance, vous pouvez créer une dimension financière qui est utilisée spécialement pour l’élimination. La plupart des clients nomment cette dimension financière **Partenaire commercial** ou un nom similaire. Si vous décidez de ne pas utiliser une dimension financière, assurez-vous que vos comptes principaux sont utilisés uniquement pour les transactions intersociétés.

Vous trouverez les paramètres des éliminations dans la zone **Paramétrage** du module **Consolidations**. Après avoir entré une description pour la règle, vous devez sélectionner la société dans laquelle le journal d’élimination sera validé. L’option **Utiliser pour le processus d’élimination financière** doit être sélectionnée dans les paramètres de l’entité juridique pour la société que vous sélectionnez.

Vous pouvez définir la date d’effet de la règle d’élimination et sa date d’expiration, selon vos besoins. Si vous souhaitez que la règle d’élimination soit disponible dans le processus de proposition d’élimination, vous devez définir l’option **Actif** sur **Oui**. Sélectionnez un nom de journal du type **Élimination**.

![Propriétés de base sur une règle d’élimination.](./media/ledger-elimination-rule-journal.png "Propriétés de base sur une règle d’élimination")

Après avoir défini les propriétés de base, sélectionnez **Lignes** pour définir les règles de traitement réelles. Il existe deux options pour les éliminations : vous pouvez éliminer le montant de modification net ou définir un montant fixe.

Sélectionnez les comptes source. Vous pouvez utiliser un astérisque (\*) comme caractère générique. Par exemple, **1\**_ sélectionne tous les comptes qui commencent par _* 1** comme source de données pour la répartition.

Après avoir sélectionné les comptes source, utilisez le champ **Spécification de compte** pour spécifier le compte utilisé dans la société de destination. Sélectionnez **Source** pour utiliser le même compte principal que celui défini dans le compte source. Si vous sélectionnez **Défini par l’utilisateur**, vous devez spécifier un compte de destination.

![Page de ligne de règle d’élimination comptable.](./media/ledger-elimination-rule-line.png "Page de ligne de règle d’élimination comptable")

Le champ **Spécification de dimension** fonctionne comme le champ **Spécification de compte**. Sélectionnez **Source** pour utiliser les mêmes dimensions dans la société de destination et la société source. Si vous sélectionnez **Défini par l’utilisateur**, vous devez spécifier les dimensions dans la société de destination en sélectionnant **Dimensions de destination**. Sélectionnez ensuite les dimensions source et les dimensions financières et valeurs utilisées comme source de l’élimination.

### <a name="process-elimination-transactions"></a>Traiter les transactions d’élimination
Il existe deux manières de traiter les transactions d’élimination. La transaction peut être traitée pendant le processus de consolidation en ligne, ou vous pouvez créer un journal d’élimination et exécuter le processus de proposition d’élimination. Cette section porte sur la deuxième option.

Dans une société définie comme société d’élimination, sélectionnez **Journal d’élimination** dans le module **Consolidations**. Après avoir sélectionné le nom du journal, sélectionnez **Lignes**. Pour exécuter la proposition, sélectionnez **Propositions** \> **Proposition d’élimination**.

Sélectionnez la société qui est la source des données consolidées, puis sélectionnez la règle à traiter. Entrez les dates de début et de fin pour définir la plage de dates dans laquelle rechercher des montants d’élimination. Le champ **Date de validation dans la Comptabilité** spécifie la date utilisée pour valider le journal dans la comptabilité. Après avoir cliqué sur **OK**, vous pouvez vérifier les montants et valider le journal.

> [!NOTE]
> Le journal d’élimination affiche les montants des valeurs du compte dans la devise de leurs transactions d’origine, et non dans la devise comptable. Lorsque vous vérifiez les montants du journal d’élimination, vous pouvez avoir du mal à vous y retrouver.

Pour plus d’informations et pour obtenir des exemples, voir [Règles d’élimination](./elimination-rules.md).

## <a name="currency-revaluation-in-a-consolidation-company"></a>Réévaluer une devise dans une société de consolidation
Lorsque vous consolidez des données d’une devise comptable à une autre, vous devez toujours exécuter la réévaluation des devises en cas de changement des taux de change, afin que vos soldes de compte soient correctement réévalués. Lorsque vous consolidez initialement les données, utilisez l’onglet **Conversion de devises** pour sélectionner les taux de change initiaux à utiliser pour la conversion pendant le processus de consolidation. Une fois qu’un nouveau taux de change est entré (par exemple, le mois prochain), vous devez réévaluer les soldes de compte. Les profits ou pertes non réalisés sont alors mis à jour, selon le nouveau taux de change et la nouvelle date.

Pour plus d’informations sur la réévaluation des devises dans une société de consolidation, voir [Réévaluation d’une devise dans une société de consolidation](currency-revaluation-consolidation-company.md).

Pour plus d’informations sur le fonctionnement de la réévaluation des devises dans le module **Comptabilité**, voir [Réévaluation des comptes en devises dans la comptabilité](./foreign-currency-revaluation-general-ledger.md).

### <a name="additional-information"></a>Informations supplémentaires
- Toutes les couches de validation sont consolidées lorsque la consolidation est traitée.
- Les journaux d’élimination peuvent être validés uniquement dans la couche actuelle.
- Seuls les soldes d’exploitation sont consolidés. Par conséquent, pour afficher les soldes d’ouverture, vous devez exécuter une clôture de fin d’exercice dans la société de consolidation.
- Vous pouvez valider un journal d’opérations diverses dans une société d’élimination, mais pas dans une société de consolidation.
- Les ajustements de soldes d’une société de consolidation ne peuvent être effectués qu’à l’aide de la page **Ajustements de la période de clôture**. 

## <a name="benefits-of-using-financial-reporting-for-financial-consolidations-and-currency-translation-or-to-complement-consolidate-online-for-consolidated-reporting"></a>Avantages de l’utilisation de l’outil États financiers pour les consolidations financières et la conversion de devises, ou en complément de la consolidation en ligne pour la génération d’états consolidés
Les clients qui utilisent l’outil États financiers pour les consolidations financières et la conversion de devises, ou en complément de la consolidation en ligne pour la génération d’états consolidés bénéficieront de plusieurs avantages :

- **Profondeur des données** – Vous pouvez créer des états consolidés qui regroupent les données réelles et budgétées au niveau du compte et de la dimension. Pour Finance, ces données englobent les données du contrôle budgétaire et de la planification budgétaire.
- **Consolidations dynamiques** – Les consolidations peuvent être effectuées à tout moment et n’importe quel niveau de la hiérarchie d’organisation.
- **Fonctionnalités d’audit complètes** – Les dimensions, les comptes et les détails des transactions sont tenus à jour pour l’analyse et l’audit. En outre, l’outil États financiers permet d’accéder à la transaction d’origine dans les entités juridiques consolidées.
- **Conversion simplifiée des devises** – Après le paramétrage minimal dans Finance, vous pouvez convertir un état de l’outil États financiers dans une devise de déclaration paramétrée. En outre, vous pouvez définir un nombre illimité de devises de déclaration.
- **Valider les éliminations à la source** – Vous pouvez créer et imprimer un état d’élimination pour vérifier les transactions d’élimination. Vous pouvez ensuite valider les nouvelles éliminations comme des transactions intersociétés standard. Vous pouvez également utiliser une entité juridique d’élimination pour toute transaction que vous ne souhaitez pas voir apparaître dans vos entités juridiques.

## <a name="supported-consolidation-scenarios-for-financial-reporting"></a>Scénarios de regroupement pris en charge pour Financial Reporting

Voici quelques-uns des scénarios de consolidation pris en charge par l’outil États financiers :

- Consolidations sur un seul niveau et plusieurs niveaux dans les entités juridiques
- Consolidations qui utilisent des structures d’organisation créées à partir des entités juridiques
- Consolidations impliquant des éliminations
- Participation minoritaire
- Plans de comptes multiples dans les entités juridiques
- Différents calendriers fiscaux dans plusieurs entités juridiques
- Consolidations impliquant plusieurs devises de déclaration
- Consolidations d’unité commerciale

## <a name="generating-consolidated-financial-statements"></a>Génération de tableaux d’analyse consolidés
Pour plus d’informations sur les scénarios où vous pouvez générer des tableaux d’analyse consolidés, voir [Générer des tableaux d’analyse consolidés](./generating-consolidated-financial-statements.md).

## <a name="performance-enhancement-for-large-consolidations"></a>Améliorations des performances pour les consolidations importantes

Les environnements comportant de nombreuses transactions comptables peuvent s’exécuter plus lentement que ce qui est optimal. Pour résoudre ce problème, vous pouvez configurer un traitement parallèle des lots qui utilise un nombre de dates défini par l’utilisateur. Pour vous assurer que la solution fonctionne comme prévu, ajoutez un point d’extension à la consolidation pour renvoyer un conteneur de plages de dates. L’implémentation de base doit contenir une plage de dates pour l’état de début et la date de fin de la consolidation. Les plages de dates dans l’implémentation de base seront validées pour s’assurer qu’elles ne contiennent pas d’espaces ou de chevauchement. Les plages de dates seront utilisées pour créer des lots de lots parallèles pour chaque entreprise.

Vous pouvez personnaliser le nombre de plages de dates pour répondre aux besoins de votre organisation. En personnalisant le nombre de plages de dates, vous pouvez contribuer à simplifier les tests et à minimiser l’impact sur le code existant, car il n’y a pas de logique d’allocation. Les seuls nouveaux tests requis valident la création de lots de lots, valident des plages de dates et testent un sous-ensemble de plages de dates pour vérifier que les lots peuvent être réunis pour la tâche de lot finale. 

Cette fonctionnalité améliore le processus de consolidation dans la comptabilité lorsque le processus est exécuté dans un lot. L’amélioration améliore les performances du processus de consolidation de la comptabilité en divisant la consolidation en plusieurs tâches pouvant être traitées en parallèle. Dans la méthode par défaut d’exécution d’une consolidation, chaque tâche traite huit jours d’activité de la comptabilité. Cependant, un point d’extension a été ajouté qui vous permet de personnaliser le nombre de tâches qui sont créées.

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail **gestion des fonctionnalités** pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** Comptabilité
- **Nom de la fonctionnalité :** Amélioration des performances pour les grandes consolidations

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
