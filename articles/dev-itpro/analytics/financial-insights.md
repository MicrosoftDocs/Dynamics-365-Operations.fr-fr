---
title: Financial Insights
description: "Financial Insights utilise Microsoft Power BI pour regrouper les indicateurs financiers de performance clés, les graphiques et les tableaux d'analyse."
author: kweekley
manager: AnnBe
ms.date: 08/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 4f4cb254ad2d4328e146f5dba471aafb21660986
ms.openlocfilehash: 2c261d2aea66b578bc976a66b6184384f0a5bf5d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/14/2018

---

# <a name="financial-insights"></a>Financial Insights

[!include [banner](../includes/banner.md)]

**Financial Insights** utilise Microsoft Power BI pour regrouper les indicateurs financiers de performance clés, les graphiques et les tableaux d'analyse. Power BI est intégré dans Microsoft Dynamics 365 for Finance and Operations. **Financial Insights** est axé sur la génération d'états analytiques. Les employés d'une organisation peuvent afficher, rechercher, comprendre et agir. 

**Financial Insights** combine les données de la comptabilité et des comptabilités auxiliaires pour donner une vue plus complète de la santé financière d'une organisation.

> [!NOTE]
> Ce document utilise la terminologie Power BI suivante :
> 
> - **État** – Fichier .pbix unique dans lequel tous les éléments visuels de tous les onglets sont enregistrés.
> - **Page** – Onglet dans un fichier .pbix unique. Chaque page peut contenir un ou plusieurs éléments visuels.
> - **Élément visuel** – Source de données unique, telle qu'une carte, un indicateur de performance clé, un graphique, une matrice ou un tableau d'analyse. Une page contenant un tableau d'analyse comme élément visuel ne peut pas avoir d'autres éléments visuels, en raison de la taille des données générées.

Actuellement, **Financial Insights** est utilisé pour afficher les données de l'entité juridique active ou de toutes les entités juridiques. Dans les prochaines versions, l'espace de travail deviendra le lieu où vous pourrez utiliser Power BI pour modifier et créer des éléments visuels.

L'espace de travail **Vue d'ensemble d'un processus CFO** affiche les mêmes éléments visuels que l'espace de travail **Financial Insights**, mais vous permet essentiellement d'afficher et de filtrer les données des états existants. Dans les prochaines versions, vous pourrez ajouter de nouveaux éléments visuels à l'espace de travail **Financial Insights**. Les nouveaux éléments visuels peuvent également être disponibles dans les espaces de travail axés sur d'autres rôles, comme les responsables de projets ou les responsables de la comptabilité fournisseur. L'espace de travail **Vue d'ensemble d'un processus CFO** continue d'afficher les données de toutes les entités juridiques, quelles que soient les entités juridiques auxquelles le rôle a accès.

## <a name="finance-and-operations-setup"></a>Paramétrage de Finance and Operations
**Comptabilité**

Le type de compte principal et les catégories de compte principal permettent de renseigner les comptes principaux par défaut appropriés dans le tableau d'analyse **Bilan** et les différents tableaux d'analyse **Compte de résultat** dans **Financial Insights**.

Dans la page **Comptes principaux**, vous devez définir votre compte principal afin que l'un des types suivants lui soit affecté :

- Recettes
- Dépense
- Actifs
- Passif
- Capitaux propres

N'affectez aucun autre type de compte principal, par exemple **Bilan** ou **Résultat**, à vos comptes principaux. Les états ne peuvent pas déterminer le type de compte principal lorsque d'autres types de comptes principaux sont affectés, car ils ne sont pas assez précis. Le type de compte principal doit être déterminé pour afficher le passif et le produit sous forme de montants positifs dans les états financiers.

Pour apparaître dans les tableaux d'analyse et être inclus dans d'autres éléments visuels, tels que les indicateurs de performance clés, chaque compte principal doit se voir affecter une catégorie de compte principal. Les catégories de compte principal ont été améliorées afin d'inclure un ordre d'affichage. L'ordre d'affichage est utilisé spécifiquement dans les tableaux d'analyse de **Financial Insights**. Une fois que vous avez modifié ou ajouté une nouvelle catégorie de compte principal, vous pouvez modifier la valeur **Ordre d'affichage** pour définir l'ordre d'affichage des catégories de compte principal dans un tableau d'analyse. Si vous devez modifier l'ordre d'affichage de plusieurs catégories de compte principal, vous pouvez utiliser la fonction Ouvrir dans Excel pour modifier et publier rapidement les modifications dans Finance and Operations.

## <a name="entity-store"></a>Magasin des entités
Les données de **Financial Insights** sont extraites du magasin des entités (**Administration du système** \> **Paramétrage** \> **Magasin des entités**). Si vous ouvrez l'espace de travail **Vue d'ensemble d'un processus CFO** ou **Financial Insights** et que le message d'avertissement suivant s'affiche dans les éléments visuels, vous devez mettre à jour les entités.

![Avertissement](./media/Cantdisplay.png)

Vous devez mettre à jour les entités suivantes pour visualiser les données dans les espaces de travail **Financial Insights** et **Vue d'ensemble d'un processus CFO** :

- CustCollectionsBIMeasurements
- FinancialReportingOtherData
- FinancialReportingReferenceData
- FinancialReportingTransactionData
- LedgerCovLiquidityMeasurement
- Cube d'achat
- Cube de vente

Dans la version précédente, les entités LedgerActivityMeasure et VendPaymentBIMeasure étaient utilisées pour les données de l'espace de travail **Vue d'ensemble d'un processus CFO**. Toutefois, elles ne sont plus utilisées dans la version actuelle.

Vous pouvez définir un traitement par lots récurrent pour mettre à jour régulièrement les données des entités. Comme chaque entité est complètement recréée pendant une mise à jour, sélectionnez avec précaution l'heure et la fréquence des mises à jour d'entité. L'entité principale utilisée pour les tableaux d'analyse est l'entité FinancialReportingTransactionData. Par conséquent, vous pouvez choisir de mettre à jour cette entité plus souvent.

## <a name="security"></a>Sécurité
Actuellement, les données des états Power BI intégrés ne peuvent pas être limitées aux entités juridiques auxquelles l'utilisateur a accès. Par conséquent, les états Power BI intégrés sont contrôlés par des droits dans le paramétrage de la sécurité. Les droits définis permettent d'accéder aux données de toutes les entités juridiques ou de l'entité active uniquement. Le tableau suivant présente les droits existants et les rôles auxquels ils sont affectés. Les droits peuvent être supprimés ou affectés à différents rôles, selon les besoins de votre organisation.

| Responsabilité                                    | Rôles | Description |
|-----------------------------------------|-------|------------|
| Afficher l'espace de travail Vue d'ensemble d'un processus CFO             | Directeur financier | Ce droit permet d'accéder à l'espace de travail Vue d'ensemble d'un processus CFO. Par défaut, la société active est utilisée comme filtre. Toutefois, vous pouvez ajouter toutes les entités juridiques, que l'utilisateur ait accès ou non aux autres entités juridiques. |
| Afficher les informations financières sur la société actuelle | <ul><li>Comptable</li><li>Responsable comptabilité</li><li>Chef comptable</li><li>Auditeur</li><li>Responsable du budget</li><li>Président directeur général</li><li>Directeur financier</li><li>Contrôleur financier</li></ul> | Ce droit permet d'accéder à Financial Insights. Par défaut, la société active est utilisée comme filtre. Vous ne pouvez pas ajouter d'autres entités juridiques. |
| Afficher les informations financières entre sociétés   | Dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, ce droit n'est pas affecté à un rôle. Dans la prochaine version, ce droit sera affecté au rôle Directeur financier. | Ce droit permet d'accéder à l'option de menu de l'espace de travail Vue d'ensemble d'un processus CFO. Par défaut, la société active est utilisée comme filtre. Toutefois, vous pouvez ajouter toutes les entités juridiques, que l'utilisateur ait accès ou non aux autres entités juridiques. |


## <a name="financial-reporting-vs-finanical-insights"></a>Comparaison entre l'outil États financiers et Financial Insights
Bien que **Financial Insights** contienne des tableaux d'analyse, il ne remplace pas l'outil États financiers dans Finance and Operations. Les tableaux d'analyse par défaut dans **Financial Insights** sont limités en portée et n'incluent pas tous les types de tableaux d'analyse. Financial Reporting est toujours l'outil principal pour la conception, la création et la génération de tableaux d'analyse statutaires.

Le tableau de comparaison suivant permet de différencier les deux options :


|                                                          | Outil États financiers                                               | Financial Insights |
|----------------------------------------------------------|-------------------------------------------------------------------|--------------------|
| **Modifier les états par défaut**                                 | Oui                                                               | Non |
| **Créer des rapports**                                   | Oui                                                               | Non |
| **Imprimer des rapports**                                        | Oui                                                               | Non |
| **Exporter vers Excel**                                      | Oui                                                               | Exportations limitées de données brutes vers Excel, et non dans un état formaté |
| **Prise en charge de la hiérarchie/hiérarchie d'organisation de génération d'états**   | Oui                                                               | Non |
| **État sur les données de comptabilité auxiliaire**                             | Oui Limité uniquement au fournisseur, client                              | Oui Fournisseur, client, fournisseur/groupes de clients, adresses fournisseur/client, et ainsi de suite. |
| **Devise de déclaration**                                   | Oui Devise comptable et convertir dans la devise de déclaration       | Non Devise comptable uniquement |
| **Sécurité**                                             | Oui Adhère à Finance and Operations et à la sécurité d'organigramme d'entreprise | Rapports limités à toutes les sociétés (quelle que soit la sécurité de Finance and Operations) ou uniquement la société active |
| **Prend en charge différents plan de comptes et exercices** | Oui                                                               | Non |
| **état sur les données externes**                              | Non                                                                | Non |
| **Prendre en charge les consolidations**                               | Oui                                                               | Limité Peut générer des rapports sur plusieurs sociétés mais utiliser la devise comptable uniquement |

Outre l'interface utilisateur de l'espace de travail **Vue d'ensemble d'un processus CFO** d'origine, de nouveaux indicateurs de performance clés, graphiques et tableaux d'analyse sont désormais disponibles. Les tableaux d'analyse suivants sont disponibles :

- Balance comptable
- Bilan
- Compte de résultat par région
- Compte de résultat réel et budgété
- Compte de résultat avec écarts
- Compte de résultat avec tendance sur 12 mois
- Tendance des dépenses sur trois ans
- Dépenses par fournisseur
- Ventes par client

## <a name="edit-visuals"></a>Modifier les éléments visuels
Dans la version initiale de **Financial Insights**, aucun élément visuel ne peut être modifié. Dans les prochaines versions, les utilisateurs disposant des autorisations de sécurité appropriées pourront créer des éléments visuels, copier des éléments visuels existants et modifier des éléments visuels. Bien que les fichiers .pbix contenant les états soient disponibles comme ressources, il n'est pas recommandé de modifier les états par défaut. Des modifications supplémentaires seront apportées au modèle de données, aux états par défaut et aux éléments visuels personnalisés utilisés pour créer les tableaux d'analyse. Par conséquent, pour bénéficier des nouvelles fonctionnalités et modifications du modèle de données dans la prochaine version, vous devez ignorer les modifications apportées aux états par défaut via Microsoft Power BI Desktop.

## <a name="filtering"></a>Filtrage
Les utilisateurs peuvent filtrer l'état à l'aide du volet **Filtre** à gauche. Ce volet est identique à celui disponible via Power BI Desktop. Il existe différents niveaux de filtrage, dont certains peuvent ne pas être disponibles, selon votre sélection dans une page (onglet) ou selon que vous utilisez les fonctionnalités d'extraction :

- **Filtres au niveau de l'état** – Ces filtres sont appliqués à tous les éléments visuels de toutes les pages (onglets).
- **Filtres au niveau de la page** – Ces filtres sont appliqués à tous les éléments visuels de l'onglet actif. Ces filtres sont appliqués en plus des filtres au niveau de l'état.
- **Filtres au niveau de l'élément visuel** – Ces filtres sont appliqués uniquement à l'élément visuel sélectionné. Ces filtres sont appliqués en plus des filtres au niveau de la page.
- **Filtre d'extraction** – Ce filtre utilise un élément visuel « source » qui est appliqué à l'élément visuel actuel lorsque vous effectuez une extraction de l'élément visuel source vers l'élément visuel actuel.

![Filtre](./media/filter.png)

Pour supprimer une valeur de filtre spécifique, sélectionnez le symbole d'effacement en regard de celle-ci. Ne supprimez pas un filtre en cliquant sur la croix (X). Si vous cliquez sur la croix (X), le champ de filtrage est supprimé comme option de filtre. Si vous supprimez par erreur un champ du filtre, fermez l'espace de travail, puis rouvrez-le. Les paramètres de filtre par défaut seront réappliqués.

Par défaut, lorsque vous ouvrez pour la première fois les espaces de travail, l'entité juridique active est utilisée comme filtre au niveau de l'état. Selon leur sécurité, les utilisateurs peuvent ajouter d'autres entités juridiques ou modifier l'entité juridique par défaut sélectionnée dans le filtre.

Le filtre **Calendrier fiscal** est requis pour que le calendrier correct soit utilisé pour l'élément visuel. Par défaut, le filtre au niveau de l'état est défini sur le calendrier fiscal de l'entité juridique active. Si vous définissez le filtre sur un calendrier fiscal qui a une date de début ou de fin différente, les soldes d'ouverture ne seront pas inclus. Par conséquent, vos tableaux d'analyse **Bilan** n'afficheront pas les soldes corrects. Si vous sélectionnez un calendrier fiscal supplémentaire dans le filtre, un ensemble supplémentaire de colonnes s'affiche. Chaque ensemble supplémentaire de colonnes affiche les montants pour un calendrier fiscal différent.

Le filtre **Couche de validation** est également requis. Par défaut, le filtre est défini sur Actuel. Vous pouvez sélectionner des couches de validation supplémentaires dans le filtre pour afficher les montants agrégés.

Des filtres sont également disponibles pour les champs **Date** et **Exercice**. Généralement, ces filtres sont appliqués au niveau de la page. Par défaut, le filtre **Date** utilise une date relationnelle que vous pouvez modifier. Vous pouvez également supprimer le filtre de date relationnelle et utiliser le filtre **Exercice** à la place.

## <a name="currency"></a>Devise

Tous les éléments visuels qui génèrent des données de comptabilité affichent les montants dans la devise comptable. Par conséquent, lorsque vous filtrez l'entité juridique, vous devez veiller à inclure uniquement les entités juridiques qui ont la même devise comptable. Sinon, vous regrouperez les données dans différentes devises.

Tous les éléments visuels qui génèrent des données de comptabilité auxiliaire, comme les éléments visuels **Prévisions de flux de trésorerie** et **10 meilleurs**, affichent les montants dans la devise du système. La devise du système et le type de taux de change du système sont définis dans la page **Paramètres système**.

L'élément visuel **Solde par compte bancaire** utilise les montants dans la devise du compte bancaire.

## <a name="dimensions"></a>Dimensions

Les tableaux d'analyse par défaut n'incluent pas de dimensions financières mais sont axés uniquement sur le compte principal. La prise en charge des dimensions financières sera disponible dans les prochaines versions, lorsque les états seront modifiables. Les organisations pourront alors filtrer les valeurs des dimensions financières.

Certains tableaux d'analyse contiennent des dimensions basées sur les transactions de la comptabilité auxiliaire. L'objectif des nouveaux tableaux d'analyse est d'activer le filtrage des dimensions qui ne sont pas définies comme dimensions financières. Par exemple, l'état Dépenses par fournisseur par défaut permet d'aller au delà du compte principal, pour que vous puissiez afficher les soldes répartis par fournisseur. Le fournisseur n'est pas paramétré comme dimension financière. À la place, le système retourne à la transaction de comptabilité auxiliaire d'origine pour rechercher le fournisseur.

Les dimensions suivantes sont utilisées dans les états par défaut. Aucune de ces dimensions n'est une dimension financière.

- Fournisseur
- Groupe de fournisseurs
- Client 
- Groupe de clients
- Pays/région
- Région/Province
- Ville

> [!IMPORTANT] 
> Si vous synthétisez les transactions de plusieurs fournisseurs ou clients dans un seul document à l'aide des journaux financiers, les données seront incorrectes. Les états ne peuvent pas déterminer quel fournisseur ou client est associé à un compte général spécifique dans une entrée de journal, car ces informations ne sont pas tenues à jour. Par conséquent, il n'est pas recommandé d'entrer plusieurs fournisseurs, clients, immobilisations ou projets dans un seul document.

## <a name="drill-on-data"></a>Explorer les données

Plusieurs niveaux d'exploration sont disponibles via Power BI. Chaque niveau a un nom différent et une fonctionnalité différente. Vous pouvez également explorer les lignes et les colonnes. Cette section décrit les différentes options disponibles en utilisant le tableau d'analyse **Balance comptable** comme exemple. Elle explique également comment explorer les lignes. La même fonctionnalité existe pour les colonnes. Vous devez simplement modifier le paramètre **Explorer**.

Dans l'illustration suivante, l'instruction **Balance comptable** est réduite au niveau le plus élevé de la hiérarchie de ligne, à savoir le type de compte principal.

![Balance comptable](./media/trial-balance.png)

Pour afficher le niveau suivant de la hiérarchie, à savoir les catégories de compte principal, vous pouvez définir le champ **Explorer** sur **Lignes**, puis sélectionnez le bouton **Développer** (le troisième bouton après le champ Explorer). Toutes les catégories de compte principal sont maintenant développées. Actuellement, Power BI ne permet pas de développer une seule ligne ou colonne, mais affiche toutes les autres lignes ou colonnes.

![Balance comptable](./media/trial-balance2.png)

Pour développer les comptes principaux de toutes les lignes, vous pouvez utiliser à nouveau le bouton **Développer**. Toutefois, pour accéder aux comptes principaux d'une seule ligne, sélectionnez d'abord le bouton **Descendre dans la hiérarchie** (la flèche unique pointant vers le bas à droite de la fenêtre), puis sélectionnez la ligne à explorer. L'illustration suivante montre le résultat lorsque la ligne **Ventes** est sélectionnée après activation du bouton **Descendre dans la hiérarchie**.

![Balance comptable](./media/trial-balance3.png)

Une fois que vous avez exploré une ligne unique, plusieurs clics sont nécessaires pour revenir à la balance comptable complète. Le bouton **Monter dans la hiérarchie** (le premier bouton après le champ **Explorer**) est utilisé uniquement dans le contexte de la catégorie **Ventes**, comme le montre l'illustration suivante.

![Balance comptable](./media/trial-balance4.png)

Vous pouvez continuer à utiliser le bouton **Monter dans la hiérarchie** pour revenir au niveau le plus élevé de la récapitulation des lignes.

Power BI dispose également d'un bouton permettant d'accéder au niveau suivant de la hiérarchie (le deuxième bouton après le champ **Explorer**). L'effet de ce bouton diffère de celui du bouton **Développer** (le troisième bouton après le champ **Explorer**), qui permet de développer la hiérarchie. Lorsque vous développez la hiérarchie, celle-ci est conservée dans l'état. Par exemple, comme indiqué précédemment, si vous développez le type de compte principal, l'état affiche toujours le type de compte principal. Toutefois, lorsque vous accédez au niveau suivant de la hiérarchie, l'état n'affiche plus le parent de la hiérarchie, comme le montre l'illustration suivante.

![Balance comptable](./media/trial-balance5.png)

Pour afficher les détails de transaction des soldes résumés, vous pouvez sélectionner des montants à explorer dans Financial and Operations.

L'exploration à partir des tableaux d'analyse vous redirige vers l'Explorateur de source comptable (ASE), et non vers les transactions de document. L'explorateur ASE n'affiche pas seulement les entrées comptables dans le compte général. Il affiche les détails de la transaction de comptabilité auxiliaire. Par conséquent, vous obtenez plus de détails sur la transaction d'origine et vous pouvez l'utiliser pour l'analyse. Par exemple, vous pouvez voir l'identité du fournisseur ou du client, ce que le client a acheté ou le client a vendu et même le projet concerné par la transaction.

Les filtres suivants des tableaux d'analyse sont envoyés à l'explorateur ASE, pour qu'il affiche les transactions agrégées :

Champs obligatoires pour le filtrage :

- Entité juridique
- Calendrier fiscal
- Année
- ID compte principal

Champs facultatifs pour le filtrage :

- Trimestre
- Mois
- Période

Si vous ne développez pas suffisamment une ligne vers le bas, l'exploration ne fonctionne pas. Par exemple, si vous développez uniquement la catégorie de compte principal, vous ne pouvez pas accéder à l'explorateur ASE, car le compte principal est un champ obligatoire pour le filtrage dans l'explorateur ASE.

Si vous développez trop loin une ligne vers le bas, les filtres supplémentaires des tableaux d'analyse ne sont pas envoyés vers l'explorateur ASE. Vous pouvez donc constater une différence dans vos chiffres. Par exemple, si vous développez vers le bas jusqu'au pays ou la région pour les lignes du tableau d'analyse Compte de résultat par région, le pays ou la région n'est pas inclus comme filtre dans l'explorateur ASE.

> [!NOTE]
> Vous pouvez explorer plus en détail les lignes ou les colonnes des tableaux d'analyse que l'explorateur ASE prend en charge actuellement pour le filtrage. Par conséquent, dans certaines situations, la somme des transactions détaillées dans l'explorateur ASE ne correspond pas au solde à explorer. Cette fonctionnalité continuera à être améliorée dans le futur.

## <a name="hierarchies"></a>Hiérarchies

Les tableaux d'analyse par défaut utilisent deux hiérarchies pour explorer et développer les données. Une hiérarchie s'applique aux lignes et l'autre aux colonnes. Les deux hiérarchies sont prédéfinies dans la conception du tableau d'analyse. Pour la plupart des tableaux d'analyse, la hiérarchie des lignes est **Type de compte principal** \> **Catégories de compte** \> **Compte principal**. Toutefois, certains états ont des champs supplémentaires, tels que Pays ou Région. Les nœuds supplémentaires de la hiérarchie sont basés sur les données de la comptabilité auxiliaire pour chaque transaction.

Pour les colonnes, la hiérarchie est axée sur les entités juridiques et les périodes fiscales. Pour la plupart des tableaux d'analyse, la hiérarchie des colonnes est **Entité juridique** \> **Calendrier fiscal** \> **Exercice** \> **Trimestre** \> **Période**.

Actuellement, les tableaux d'analyse ne prennent pas en charge les hiérarchies d'organisation qui permettent de regrouper les données.

## <a name="data-limitations"></a>Limitations des données
Les éléments visuels des tableaux d'analyse ont une limite au nombre de lignes qui peuvent être affichées. Actuellement, la limite est définie sur 30 000. Si vous dépassez cette limite, un symbole d'avertissement s'affiche sur l'élément visuel pour vous en informer.

![Limitations des données](./media/data-limit.png)

Si le nombre maximal est dépassé, les totaux indiqués dans le tableau d'analyse sont incorrects, car toutes les lignes n'ont pas été chargées dans l'élément visuel.

### <a name="empty-rows"></a>Lignes vides
Power BI ne fournit pas une option pour masquer et afficher les lignes vides. Si une ligne ne contient pas de données, elle ne s'affiche pas dans l'élément visuel.


## <a name="additional-resources-for-power-bi"></a>Ressources supplémentaires pour Power BI

Les informations des ressources suivantes ne sont pas requises pour activer les états intégrés de l'espace de travail **Vue d'ensemble d'un processus CFO** ou **Financial Insights** dans un environnement de production. Elles sont utiles pour les environnements de développement et si vous souhaitez intégrer vos propres états Power BI dans Finance and Operations.

- <https://blogs.msdn.microsoft.com/dynamicsaxbi/2017/07/29/accessing-analytical-workspaces-on-1box-environment/>

- <https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/add-analytics-tab-workspaces>

