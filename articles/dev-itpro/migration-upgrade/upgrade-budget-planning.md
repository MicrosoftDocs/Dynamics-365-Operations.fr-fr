---
title: "Mise à jour de la planification budgétaire"
description: "Il existe des différences significatives dans la planification budgétaire entre Microsoft Dynamics AX 2012 et Microsoft Dynamics 365 for Finance and Operations. Certaines fonctions n'ont pas été mises à jour et nécessitent par conséquent une reconfiguration. Cette rubrique explique ce qui doit être reconfiguré et décrit également les nouvelles fonctions qui doivent être examinées après la mise à niveau."
author: ryansandness
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.custom: 272923
ms.assetid: 17cdfe74-bdfd-466a-9bdd-c12583f250c7
ms.search.region: Global
ms.author: ryansand
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 178e4fdef12e4adfe322837fb41597d24943920e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="upgrade-budget-planning"></a>Mise à jour de la planification budgétaire

[!include[banner](../includes/banner.md)]


Il existe des différences significatives dans la planification budgétaire entre Microsoft Dynamics AX 2012 et Microsoft Dynamics 365 for Finance and Operations. Certaines fonctions n'ont pas été mises à jour et nécessitent par conséquent une reconfiguration. Cette rubrique explique ce qui doit être reconfiguré et décrit également les nouvelles fonctions qui doivent être examinées après la mise à niveau.  

La planification budgétaire dans Microsoft Dynamics 365 for Finance and Operations comporte plusieurs fonctions qui n'étaient pas disponibles dans Microsoft Dynamics AX 2012. Cette rubrique explique les modifications que les clients qui mettent à niveau leur système peuvent effectuer. Elle précise également les nouvelles fonctions qui doivent être prises en compte dans le processus de mise à niveau. En raison de l'extension des modifications, aucun plan budgétaire existant ne peut être ouvert avant que les modifications expliquées dans cette rubrique ne soient effectuées. Toutefois, les états devraient fonctionner normalement et sans qu'il soit nécessaire d'apporter des modifications supplémentaires.

## <a name="overview-of-changes"></a>Vue d'ensemble des modifications
De nombreuses modifications importantes ont été apportées dans la budgétisation pour Finance and Operations. Ces modifications visent à faciliter la configuration et l'utilisation de la planification budgétaire, afin de réduire la maintenance et la configuration d'une année sur l'autre. Les zones suivantes dans AX 2012 ne figurent plus dans Finance and Operations :

-   Modèles de plan budgétaire (configuration de la planification budgétaire)
-   Dossiers de plan budgétaire (configuration de la planification budgétaire)
-   Contraintes de scénario (configuration de la planification budgétaire)
-   Modèles de règles de stade de planification budgétaire et autres modèles (processus de planification budgétaire)
-   Champs de matrice pour les modèles de feuille de calcul
-   Assistant de modèles Microsoft Excel pour le plan budgétaire

Certains nouveaux concepts ne peuvent pas directement être mis à niveau depuis les fonctionnalités précédentes. Par conséquent, vous devez effectuer une reconfiguration pour inclure ces nouveaux concepts. Les sections suivantes expliquent les concepts qui ont remplacé les éléments de la liste précédente.

### <a name="columns"></a>Colonnes

Les colonnes sont un nouveau concept qui remplace les parties du modèle Excel et également les champs matriciels. Les colonnes peuvent représenter une période, un mois, un trimestre, l'exercice, ou toutes les périodes. La référence de temps est dynamique. Elle indique une période ou une année associée en référence au processus de budget. Par exemple, une colonne **Année antérieure janvier** fait référence à la période fiscale 1 pour l'année -1. Une colonne est spécifique à un scénario de plan budgétaire, par exemple une demande basée sur des données réelles ou budgétaires.

### <a name="layouts"></a>Mises en page

Les mises en page sont un nouveau concept qui remplace le modèle Excel. Les mises en page contiennent les colonnes qui définissent quelles données et périodes réelles ou budgétaires devraient être affichées. Les mises en page sont également partagées entre le module client et Excel. Par conséquent, lorsque vous entrez ou affichez des données dans le client Finance and Operations, l'expérience utilisateur est meilleure que celle de AX 2012. Pour entrer des données dans le client Finance and Operations, vous n'êtes plus obligé d'afficher et d'entrer un scénario unique dans une vue de transaction. Au lieu de cela, une vue de comparaison vous permet d'afficher et d'entrer facilement des montants pour les heures et les comptes simultanément. Les mises en page peuvent également être définies pour que vous puissiez entrer et afficher la devise, les commentaires, et d'autres données facultatives. Les mises en page vous permettent également de définir les dimensions comptables et les descriptions de dimension qui doivent s'afficher. Les mises en page incorporent également des contraintes de scénario pour définir quelles colonnes dans un modèle peuvent être modifiées et quelles colonnes doivent être disponibles dans Excel. Après avoir défini une mise en page, un modèle est généré pour celle-ci. Ce modèle, à son tour, crée le modèle Excel correspondant. Vous pouvez ensuite modifier le modèle Excel pour répercuter plus de formules et plus de mises en forme, puis les télécharger de nouveau. Les mises en page sont ensuite affectées à chaque règle de stade sur la page **Processus de planification budgétaire**. Par conséquent, les mises en page remplacent les modèles, qui ont été affectés et utilisés de manière similaire.

### <a name="budget-planning-processes"></a>Processus de planification budgétaire

Les processus de planification budgétaire sont pour la plupart les mêmes que dans AX 2012. La modification la plus cruciale est le remplacement des modèles avec les mises en page. Si des processus ont été précédemment suivis dans AX 2012, ils sont mis à jour avec le statut « en cours » pour que les modifications soient appliquées. Vous devez affecter les mises en page requises pour chaque règle de stade pour déterminer les scénarios et les périodes qui apparaissent lorsque le plan est ouvert dans le client. Les mises en page déterminent également quel modèle Excel est ouvert hors de Dynamics 365 for Finance and Operations afin de pouvoir afficher le budget. **Structure de compte par défaut** est un champ obligatoire pour le processus de planification budgétaire. Pour chaque processus de planification budgétaire, affectez la principale structure de compte qui doit être utilisée pour la budgétisation.

### <a name="attachments"></a>Documents joints

Dans Dynamics AX 2012, les documents justificatifs ont été enregistrés dans un dossier joint. Aucun document justificatif précédent n'est mis à niveau. Les documents justificatifs sont maintenant stockés dans la base de données. Si ces informations doivent est enregistrées dans la version mise à niveau, vous pouvez télécharger les documents justificatifs pour chaque plan en tant que pièce jointe à l'aide du bouton **Justification** du volet Actions. Dans AX 2012, les feuilles de calcul Excel pour chaque plan budgétaire ont été créées sur la base du modèle. Dans Finance and Operations, tous les plans ouvrent une copie de la mise en page. Toutefois, aucune modification du fichier Excel n'est enregistrée. Toutes les formules ou informations de support utilisées pour chaque plan doivent être ajoutées au moyen de commentaires, de documents justificatifs, ou d'un autre processus supplémentaire.

## <a name="configuring-an-upgraded-environment-from-ax-2012"></a>Configurer un environnement mis à niveau depuis AX 2012
Pour vous aider à déterminer comment configurer le système mis à niveau, l'exemple suivant illustre un processus de mise à niveau du budget à partir des données de démonstration d'AX 2012. Les données de configuration par défaut pour les colonnes ont été créées pour vous aider lors du processus de mise à niveau. Vous pouvez mettre à jour ou supprimer ces données par défaut si elles ne répondent pas à vos exigences de configuration. **Remarque :** il y a de nouveaux champs obligatoires qui ne sont pas définis dans le système. Si vous êtes coincé sur une page, telle que la page **Configuration de planification budgétaire**, et ne pouvez pas accéder à d'autres pages, vous pouvez fermer votre navigateur puis le rouvrir à une autre page pour entrer les détails dans l'ordre correct. Il existe des champs obligatoires qui ne sont pas encore définis. Par conséquent, des problèmes peuvent se produire jusqu'à ce que tout soit configuré et tous les champs requis aient été définis. Cette rubrique explique comment définir ces champs, tel que réquis. Voici quelques exemples de champs requis :

-   Page **Processus de planification budgétaire** : champ **Structure de compte par défaut**
-   Page **Processus de planification budgétaire** : champ **Mise en page** sur l'organisateur **Règles et mises en page du stade de planification budgétaire**

### <a name="define-columns-and-layouts"></a>Définir les colonnes et les mises en page

1.  Sur la page **Configuration de planification budgétaire**, cliquez sur l'onglet **Colonnes**. Dans le cadre de la mise à niveau, de nouvelles colonnes sont créées automatiquement en fonction de vos lignes de plan budgétaire. Les colonnes utilisent désormais des dates dynamiques, où l'heure et l'année sont déduites de l'exercice défini dans le processus de planification budgétaire. **Remarque :** pour des raisons de performances lors de la mise à niveau, il est supposé que tous les cycles budgétaires représentent des années civiles, et non des exercices. Si vous utilisez des exercices, vous devez apporter des modifications pour bien mettre en correspondance les colonnes et leur exercice. Par exemple, les éléments suivants existaient dans AX 2012 :
    -   Scénarios de plan budgétaire : Chiffres réels, Référence, Demande budgétaire, Budget approuvé
    -   Lignes de plan budgétaire pour tous les scénarios en 2017, et chiffres réels pour 2017 et 2016

    Les colonnes suivantes sont créées dans Finance and Operations :
    | Nom de la colonne    | Scénario de plan budgétaire | Période de la colonne | Contrepartie de l'année |
    |----------------|----------------------|--------------------|-------------|
    | Scénario 1 Janvier | Chiffres réels              | 1                  | 0           |
    | Scénario 2 Janvier | Référence             | 1                  | 0           |
    | Scénario 3 Janvier | Demande budgétaire       | 1                  | 0           |
    | Scénario 4 Janvier | Budget approuvé      | 1                  | 0           |
    | Scénario 5 Janvier | Chiffres réels              | 1                  | -1          |
    | Scénario 1 Février | Chiffres réels              | 1                  | 0           |
    | ...            | ...                  | ...                | ...         |

    Dans cet exemple, une colonne appelée **Scénario 1 Janvier** est créée pour les données de transaction du plan budgétaire les plus récentes qui se trouvent là où des transactions existent en janvier. Une colonne similaire est créée pour chaque scénario qui contient des données. Une fois les colonnes créées pour toutes les périodes de cette année, des colonnes sont créées pour les années précédentes.
2.  Modifiez les noms et descriptions de colonne, et les autres détails, soit manuellement dans le client soit en effectuant des mises à jour en vrac dans le complément Excel qui pointe vers l'entité de données des colonnes du plan budgétaire. Tous les filtres qui ont été définis précédemment pour les champs de matrice sont maintenant définis dans les colonnes.
3.  Créez une nouvelle mise en page de plan budgétaire. Une mise en page pointe vers plusieurs colonnes pour définir l'affichage qui apparaît dans Excel et le client. La mise en page nécessite d'abord que vous spécifiez un ensemble de dimensions comptables pour déterminer les dimensions financières qui peuvent être entrées. Une fois que vous avez spécifié l'ensemble de dimensions, cliquez sur **Description** pour sélectionner des descriptions de dimension à inclure dans la mise en page.
4.  Dans l'organisateur **Éléments de mise en page**, cliquez sur **Ajouter** pour ajouter les métadonnées pour chaque ligne, telles qu'une devise, un commentaire, ou une classe de budget qui détermine le produit par rapport aux lignes de dépense. Ensuite, ajoutez les colonnes pour la période, et les scénarios qui s'appliquent à ce cycle budgétaire et à ce stade. Vous pouvez effectuer ces modifications manuellement dans le client ou via le complément Excel qui pointe vers l'entité de données des éléments de mise en page du plan budgétaire.
5.  Pour chaque élément de mise en page, indiquez si la colonne doit être modifiée, et si la colonne doit également être affichée dans le classeur Excel pour cette mise en page. **Remarque :** pour nos plans historiques, il peut être utile d'utiliser une mise en page qui indique 12 colonnes mensuelles pour tous les scénarios de plan budgétaire de ce processus.

### <a name="update-budget-planning-processes-to-use-the-appropriate-layout-for-each-budget-stage"></a>Mettez les processus de planification budgétaire à jour pour utiliser la mise en page appropriée pour chaque stade de budget

1.  Dans la page **Processus de planification budgétaire**, sélectionnez le processus à configurer.
2.  Dans le volet Actions, cliquez sur **Modifier**.
3.  Spécifiez la structure de compte par défaut pour ce processus de planification budgétaire. **Structure de compte par défaut** est un champ obligatoire qui doit être défini.
4.  Dans l'organisateur **Règles et mises en page du stade de planification budgétaire**, dans le champ **Mise en page**, sélectionnez une mise en page précédemment configurée, et pertinente pour ce stade.
5.  Continuez de sélectionner la même compte ou les différentes mises en page pour les différents stades de planification budgétaire, puis enregistrez vos modifications.

## <a name="additional-features-to-consider-in-your-budgeting-process"></a>Fonctions supplémentaires à prendre en compte dans le processus de budgétisation
### <a name="budget-planning-workspace"></a>Espace de travail de planification budgétaire

Cet espace de travail est conçu aussi bien pour le propriétaire du budget que pour les différents contributeurs au budget. Il inclut des liens vers les documents budgétaires qui nécessitent votre attention. Il comporte également des états et des indicateurs de performance clé (KPI) pour le processus budgétaire. L'administrateur de budget peut définir le processus de planification budgétaire actuel pour tous les utilisateurs de la page **Paramètres de budget**. Dans l'onglet **Paramètres des espaces de travail**, l'organisateur **Planification budgétaire** inclut un champ dans lequel vous pouvez sélectionner le processus de planification budgétaire.

### <a name="alternate-layouts"></a>Autres mises en page

Les mises en page secondaires sont une nouvelle fonction qui vous permet d'afficher les plans selon plusieurs mises en page. Une ou plusieurs mises en page peuvent être fournies comme options. Vous pouvez ensuite afficher un plan budgétaire selon une mise en page mensuelle ou une mise en page trimestrielle. Vous pouvez définir des mises en page supplémentaires dans l'organisateur **Règles et mises en page du stade de planification budgétaire** de la page **Processus de planification budgétaire**.

### <a name="budget-milestones"></a>Jalons de budget

Dans le cadre du processus budgétaire, il est essentiel que vous compreniez les dates et les délais clés. Vous pouvez désormais configurer les dates afin qu'elles comportent des descriptions. Les utilisateurs de la budgétisation ont accès à ces descriptions lorsqu'ils ouvrent des budgets pour modifier ou afficher tout ce qui leur est affecté.

### <a name="copy-from-budget-plan-allocation"></a>Copie à partir d'une répartition de planification budgétaire

Une nouvelle méthode de répartition permet de distribuer un plan parent sur un plan enfant sans passer par un niveau intermédiaire dans la hiérarchie. Cette méthode est particulièrement utile pour les clients ayant déjà créé une dimension financière juste pour la distribution et les approbations de budget.

### <a name="generating-budget-plans-from-new-budget-sources"></a>Génération de plans budgétaires à partir de nouvelles sources budgétaires

Les options suivantes ont été ajoutées en tant que processus périodiques. Ces options permettent de générer un plan budgétaire à l'aide des données existantes d'un autre module comme point de départ :

-   Générer un plan budgétaire à partir d'une prévision de la demande
-   Générer un plan budgétaire à partir des prévisions d'approvisionnement
-   Générer un plan budgétaire à partir d'un projet
-   Générer un plan budgétaire à partir d'un registre budgétaire

### <a name="more-complete-tracking-of-amounts"></a>Suivi plus complet des montants

Dans Dynamics AX 2012, la planification budgétaire comportait un seul montant de plan qui était enregistré pour chaque valeur. Dans Finance and Operations, le modèle de données a été développé. Il existe désormais des montants de devise comptable, de devise de la transaction et de devise de déclaration pour chaque valeur. Pendant la mise à niveau, les nouvelles colonnes sont automatiquement renseignées pour les données existantes.

### <a name="do-not-convert-currency-in-aggregation"></a>Ne pas convertir la devise en agrégation

Généralement, lorsqu'un plan enfant est lié à un plan parent, les montants sont automatiquement convertis de la devise de la transaction à la devise comptable de l'organisation. Lorsque vous définissez l'option **Ne pas convertir la devise en agrégation** sur **Non**, les montants liés restent dans la devise d'origine. Le cas échéant, cette option permet des ajustements plus précis pour suivre les variations du taux de change.

### <a name="looking-back-from-a-budget-plan-to-other-modules-that-contributed-to-the-budget"></a>Comparaison d'un plan budgétaire et des autres modules qui contribuent au budget

Les plans budgétaires peuvent être générés à partir des prévisions de la demande ou des prévisions d'approvisionnement, du projet, et d'autres zones. La recherche Plans budgétaires par ensemble de dimensions inclut plusieurs options qui permettent d'exécuter des requêtes afin d'identifier les données sources du plan budgétaire.

### <a name="overwrite-or-append-to-plan-for-allocation-schedules"></a>Remplacer ou ajouter des montants pour planifier les programmes de répartition

S'il existe plusieurs sources pour les montants qui doivent être répartis, vous pouvez spécifier que les montants doivent être affichés à la suite. Dans ce cas, les montants ne remplacent aucun montant existant. Sinon, ils sont ajoutés aux montants existants.

### <a name="default-financial-dimension-set-for-budget-planning-configuration"></a>Ensemble de dimensions financières par défaut pour la configuration de planification budgétaire

La page **Configuration de planification budgétaire** comprend désormais un champ dans lequel vous pouvez spécifier l'ensemble de dimensions financières par défaut. Bien que ce champ soit un champ facultatif, il peut être exigé pour certaines recherches. Il est également nécessaire si vous souhaitez regrouper ou filtrer des états par ensemble de dimensions.

### <a name="data-entities"></a>Entités de données

Plusieurs entités de données ont été ajoutées pour activer l'implémentation rapide de la planification budgétaire. Les entités vous permettent également d'effectuer de nombreuses modifications dans Excel. Par conséquent, vous ne devez pas créer les élements les uns après les autres via le client. Voici une liste des entités de données :

-   Nom d'entité
-   Paramètres du budget
-   Paramètre de plan budgétaire
-   Scénarios de plan budgétaire
-   Stades du plan budgétaire
-   Stade de workflow de plan budgétaire
-   Programmes de répartition du plan budgétaire
-   Répartition de stade du plan budgétaire
-   Priorités de plan budgétaire
-   Colonnes du plan budgétaire
-   Éléments de mise en page du plan budgétaire





