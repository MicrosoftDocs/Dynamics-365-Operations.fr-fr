---
title: "Nouveautés ou modifications apportées à la version 1611 de Dynamics 365 for Operations (novembre 2016)"
description: "Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version 1611 de Dynamics 365 for Operations."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations
ms.custom: 221294
ms.assetid: 357931ed-f843-4bf5-bc85-0da3de0619ec
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: c4f26f7363be3c06de931b4f50b54ee8b3452d42
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="whats-new-or-changed-in-dynamics-365-for-operations-version-1611-november-2016"></a>Nouveautés ou modifications apportées à la version 1611 de Dynamics 365 for Operations (novembre 2016)

[!include[banner](../includes/banner.md)]


Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version 1611 de Dynamics 365 for Operations.

<a name="cost-accounting"></a>Contrôle de gestion
---------------

<table>




<thead>
<tr class="header">
<th>Ce que vous pouvez faire</th>
<th>Pourquoi c'est important</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Définissez les dimensions d'élément de coût, et importez les membres de la dimension d'élément de coût.</td>
<td>Les éléments de coût sont utilisés dans le contrôle de gestion pour catégoriser les coûts et documenter le flux des coûts. Les principaux éléments de coût sont importés à l'aide d'un connecteur de données Microsoft Dynamics 365 for Operations pour obtenir les comptes principaux directement auprès d'Operations ou à l'aide d'un connecteur de données générique, dans lequel vous obtenez des comptes principaux via Microsoft Excel à partir de n'importe quel autre type de système source. Une fois les comptes principaux importés dans le contrôle de gestion, ils sont utilisés comme des membres de la dimension d'élément de coût. Les éléments de coût secondaires sont définis par l'utilisateur et sont utilisés dans les répartitions pour documenter le flux des coûts.</td>
</tr>
<tr class="even">
<td>Mappez les dimensions d'éléments de coût.</td>
<td>Si les comptes principaux entre vos entités juridiques ne peuvent pas être partagés en raison de conditions comptables statutaires, vous pouvez les mapper après les avoir importés dans le contrôle de gestion pour obtenir une vue holistique de l'ensemble de l'organisation.</td>
</tr>
<tr class="odd">
<td>Définissez les dimensions d'objet de coût, et importez les membres de la dimension d'objet de coût.</td>
<td>Les objets de coût correspondent à tous les types d'objets auquel les coûts sont affectés. Les objets de coût comprennent les produits, les projets, les ressources, les services, les centres de coût, et les zones géographiques. Vous pouvez utiliser un connecteur de données Microsoft Dynamics 365 for Operations pour obtenir des dimensions financières et des valeurs auprès d'Operations ou utiliser un connecteur de données générique, dans lequel vous pouvez obtenir des dimensions et des valeurs via Excel auprès de n'importe quel type de système source. Par exemple, si vous utilisez la dimension financière Centre de coût comme dimension d'objet, tous les centres de coût qui sont importés sont des membres de la dimension de l'objet de coût.</td>
</tr>
<tr class="even">
<td>Définissez ou importez des dimension statistiques.</td>
<td>Les membres de la dimension statistique sont mesurés en unités non monétaires, tels que les heures-machine, le nombre d'employés, et carré. Ils sont utilisés dans les relevés, ou comme base pour les répartitions et les distributions.</td>
</tr>
<tr class="odd">
<td>Créez des modèles de fournisseur de mesures statistiques.</td>
<td>Un modèle de fournisseur de mesures statistiques est utilisé pour transformer les données Dynamics 365 for Operations en mesures statistiques. Le modèle est alors associé à un membre de dimension statistique donné. Les modèles sont préfiltrés afin qu'ils affichent uniquement les tables associées aux dimensions financières.</td>
</tr>
<tr class="even">
<td>Créez des comptabilités de contrôle de gestion.</td>
<td>Une comptabilité de contrôle de gestion est une comptabilité agnostique utilisant son propre calendrier et sa propre devise. Elle joue un rôle important dans le traitement de toutes les transactions de coût. Par exemple, une comptabilité de contrôle de gestion classifie les coûts selon ses propres éléments de coût et regroupe les coûts selon ses propres dimensions d'objets. Vous pouvez créer autant de comptabilités de contrôle de gestion que vous le souhaitez pour effectuer la génération d'états de gestion de différentes perspectives.</td>
</tr>
<tr class="odd">
<td>Créez des unités de contrôle des coûts.</td>
<td>Les unités de contrôle des coûts constituent la structure de coût et définissent le flux des coûts dans la comptabilité de contrôle de gestion. Elles doivent être associées à plusieurs dimensions d'objets de coût pour représenter les dimensions d'objets de coût dans la comptabilité.</td>
</tr>
<tr class="even">
<td>Traitez les écritures de comptabilité.</td>
<td>Pour mesurer les performances réelles, vous devez disposer de données. Les données sont importées à l'aide des connecteurs que vous définissez pour la comptabilité de contrôle de gestion. Lorsque vous traitez les écritures de comptabilité, les données sont importées de façon incrémentielle.</td>
</tr>
<tr class="odd">
<td>Traites les écritures budgétaires.</td>
<td>Pour mesurer les performances budgétées, vous devez disposer de données. Les données sont importées à l'aide des connecteurs que vous définissez pour la comptabilité de contrôle de gestion. Lorsque vous traitez les écritures budgétées, les données sont importées de façon incrémentielle.</td>
</tr>
<tr class="even">
<td>Créez et appliquez les stratégies de comportement de coût.</td>
<td>Vous utilisez une stratégie de comportement de coût pour classer les coûts comme fixes, variables ou semi-variables. Une stratégie est basée sur les règles et les dates d'effet. Par défaut, tous les coûts sont marqués comme non classés jusqu'à ce que vous appliquiez une stratégie de comportement de coût et que vous calculiez et les effets de la règle. Après le calcul, les coûts sont classés.</td>
</tr>
<tr class="odd">
<td>Effectuez le suivi des coûts.</td>
<td>Pour vous aider à comprendre l'impact des stratégies de coûts, le contrôle de gestion vous permet de suivre les coûts jusqu'aux valeurs sources et aux règles appliquées d'où ils proviennent. Cette fonctionnalité fournit la traçabilité complète du moment où les coûts sont survenus, des types de coûts survenus, et des règles de comportement de coût appliquées.</td>
</tr>
<tr class="even">
<td>Définissez des hiérarchies de dimensions.</td>
<td>Vous pouvez créer des hiérarchies de dimensions à des fins de catégorisation ou de classification. Par exemple, vous pouvez définir une hiérarchie de catégorisation basée sur une dimension d'élément de coût et ses membres. Sinon, vous pouvez définir une hiérarchie de classification basée sur une dimension d'objet de coût et ses membres. Les structures de génération d'états sont utilisées dans les situations suivantes :
<ul>
<li>Vous définissez des répartitions, des taux de coût, et des règles de repositionnement des coûts.</li>
<li>Vous affichez des relevés à l'aide de l'espace de travail.</li>
<li>Vous définissez l'accès pour afficher les données agrégées.</li>
<li>Vous affichez les données dans Excel.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Créez des relevés qui peuvent être affichés dans l'espace de travail.</td>
<td>Utilisez l'espace de travail pour obtenir une vue d'ensemble rapide des coûts réels et budgétés, ainsi que les écarts. Vous pouvez filtrer les données par période ou par niveau de coût. L'espace de travail est conçu pour les responsables en charge du contrôle des coûts. Il s'applique aux règles d'accès définies pour les hiérarchies de dimensions.</td>
</tr>
<tr class="even">
<td>Créez des états à l'aide d'Excel. <strong>Remarque :</strong> vous devez exécuter Microsoft Excel 2016.</td>
<td>Vous pouvez exporter les données de contrôle de gestion directement vers Excel via les entités de données et utiliser Microsoft PivotTable pour créer des rapports.</td>
</tr>
</tbody>
</table>

## <a name="expense-management"></a>Gestion des dépenses
| Ce que vous pouvez faire                                                            | Pourquoi c'est important                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Réaffectez les transactions de carte de crédit de l'employé dont le contrat est terminé.                     | Parfois, lorsque le contrat d'un employé est terminé, le compte Services de domaine Active Directory (AD DS) de celui-ci est désactivé lorsque des transactions de carte de crédit actives devant être mises en dépenses sont importées. Auparavant, vous ne pouviez pas affecter un délégué pour la saisie de dépenses ou joindre les transactions de carte de crédit à un état de dépenses. Vous pouvez désormais utiliser la page **Transactions de carte de crédit** pour réaffecter à l'employé toute transaction de carte de crédit pour laquelle le contrat de l'employé associé a pris fin. Après avoir réattribué la transaction de carte de crédit, la transaction peut être sélectionnée pour un état de dépenses et être réglée au cours du processus habituel de remboursement d'état de dépenses. |
| Modifiez les informations de carte de crédit de dépenses pour les employés en attente et passés. | Vous pouvez modifier les informations de carte de crédit de gestion des dépenses pour les collaborateurs en attente et les collaborateurs passés. Auparavant, vous pouviez modifier les informations de carte de crédit de dépense uniquement si le collaborateurs était un employé actif.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Copiez un état de dépenses.                                                    | Vous pouvez maintenant copier une dépense existante lorsque vous créez une dépense sur le même état de dépenses. Vous pouvez copier un état de dépenses et toutes les dépenses sans carte de crédit associées à un nouvel état de dépenses. Vous devez toujours exécuter toutes les ventilations requises et joindre les reçus requis, selon les stratégies et catégories des dépenses définies. Vous pouvez ajouter des transactions de carte de crédit à un état de dépenses en sélectionnant l'ajout des dépenses non rapprochées.                                                                                                                                                                                                                        |
| Modifiez en bloc les dépenses.                                                        | Certaines transactions de carte de crédit ne peuvent pas être mappées à une catégorie de dépenses, ou elles peuvent être incorrectement mappées lorsqu'elles sont importées. Dans ce cas, les employés doivent modifier manuellement la catégorie de dépenses associée. Lorsque vous gérez les dépenses non rapprochées, vous pouvez désormais modifier en bloc la catégorie de dépenses pour les dépenses sélectionnées. En outre, lorsque vous gérez les dépenses sélectionnées pour un état de dépenses spécifique, vous pouvez modifier en bloc le projet et les informations supplémentaires.                                                                                                                                                                                    |
| Modifiez le taux de change pour les transactions de carte de crédit.                     | Le taux de change réel utilisé pour une transaction de carte de crédit peut différer du taux de change qui est paramétré dans le système. Auparavant, les employés ne pouvaient pas modifier le taux de change pour une transaction de carte de crédit importée dans la gestion des dépenses. Vous pouvez désormais définir un paramètre sur la page **Paramètres de gestion des dépenses** pour autoriser la modification du taux de change pour les transactions de carte de crédit.                                                                                                                                                                                                                                            |
| Configurez l'attestation anticorruption de paramétrage pour les dépenses.                            | Certains employés d'une organisation peuvent avoir des relations commerciales avec des fonctionnaires, et certaines dépenses effectuées dans le cadre de ces affaires peuvent être perçues comme de la corruption. Dans la gestion des dépenses, vous pouvez désormais configurer une attestation anticorruption affichée pour les catégories de dépenses sélectionnées, telles que les repas et les cadeaux. Les employés doivent sélectionner si les dépenses configurées pour l'attestation anticorruption satisfont aux critères définis par les stratégies de votre organisation.                                                                                                                                                                                     |
| Empêchez la saisie manuelle des dépenses pour des catégories de dépenses spécifiques.          | Une catégorie de dépenses peut être configurée pour représenter une transaction de carte de crédit pour laquelle la catégorie ne peut pas être modifiée. Par exemple, les frais de paiement tardif de la carte de crédit. Vous pouvez désormais configurer une catégorie de dépenses autorisant a création de dépenses uniquement via l'importation. Cette fonction permet aux employés de créer manuellement une dépense pour la catégorie. De plus, elle n'autorise pas la catégorie à être modifiée pour les transactions importées et qui utilisent cette catégorie.                                                                                                                                                                                   |
| Joignez un reçu aux dépenses multiples.                                     | Un reçu téléchargé dans la gestion des dépenses peut être associé à plusieurs dépenses. Auparavant, un reçu associé à plusieurs dépenses devait être téléchargé une fois pour chaque dépense. Vous pouvez maintenant joindre un reçu à une dépense qui a déjà été téléchargé et l'associer à une autre dépense sur le même état des dépenses. En outre, si vous téléchargez un reçu dans l'en-tête de l'état des dépenses, vous pouvez sélectionner une ou plusieurs lignes auxquelles joindre le reçu.                                                                                                                                                                                        |
| Créez des dépenses prévues à une date future.                                              | Lorsque vous copiez un état des dépenses, par exemple, la date de la transaction d'une dépense peut se situer ultérieurement. Les versions antérieures n'autorisent pas des dépenses à une date ultérieure. Vous pouvez désormais créer et enregistrer des dépenses à une date ultérieure. Toutefois, vous ne pouvez pas envoyer une dépense à une date ultérieure.                                                                                                                                                                                                                                                                                                                                                                                 |
| Configurez les taxes des dépenses d'une région/province.                              | Dans certains pays ou certaines régions, les dépenses qui sont effectuées dans différentes régions/provinces peuvent être soumises à des taux de taxe différents. Vous pouvez désormais paramétrer les configurations de taxes de dépenses au niveau de la région/province, pas uniquement au niveau du pays ou de la région. Si vous laissez le champ **Région/province** vide sur la page **Configuration de taxe**, le groupe de taxe s'applique à toutes les régions/provinces du pays ou de la région spécifié(e).                                                                                                                                                                                                                                       |
| Configurez des type de cartes de crédit pour les dépenses.                                          | Auparavant, il n'y avait aucune page sur laquelle vous pouviez créer des types de cartes de crédit, comme Visa, MasterCard ou AMEX, qui pouvaient être utilisés avec la gestion des dépenses. Vous pouvez désormais créer des types de cartes de crédit à utiliser avec la gestion des dépenses. La page est située dans la zone **Paramétrage**, dans la section **Calculs et codes**.                                                                                                                                                                                                                                                                                                                                                 |
| Définissez un workflow d'approbation à plusieurs niveaux pour les états des dépenses.                 | Un nouveau workflow pour l'état des dépenses prend en charge un processus d'approbation à plusieurs niveaux. Les employés entrent les approbateurs intermédiaires et les approbateurs finaux lorsqu'ils créent l'état des dépenses. Le workflow achemine ensuite d'abord l'état des dépenses vers les approbateurs intermédiaires. Une fois l'état des dépenses approuvé à ce niveau, le workflow l'achemine vers les approbateurs finaux pour approbation finale.                                                                                                                                                                                                                                                                                          |
| Création et mise à jour des dépenses qui ne sont pas associées à un état des dépenses.    | L'utilisateur peut désormais créer des dépenses et les tenir à jour (par exemple, en associant ou en ventilant les reçus, ou en affectant des invités) sans devoir d'abord créer un état des dépenses. Une ou plusieurs dépenses peuvent être sélectionnées et ajoutées à un nouvel état des dépenses, afin qu'elles puissent être envoyées pour approbation. Une nouvelle page de mise à jour des dépenses est disponible sous **Gestion des dépenses** &gt; **Mes dépenses** &gt; **Dépenses**.                                                                                                                                                                                                                                                       |

## <a name="financial-management"></a>Gestion financière
<table>




<thead>
<tr class="header">
<th>Ce que vous pouvez faire</th>
<th>Pourquoi c'est important</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Effectuez le suivi des évaluations des immobilisations à l'aide d'un concept de « registre » unique.</td>
<td>Auparavant, deux types distincts d'évaluation étaient utilisés pour effectuer le suivi des valeurs des immobilisations : les modèles de valeur et les registres des amortissements. Dans la version actuelle, ces deux concepts ont été fusionnés en un concept d'évaluation unique nommé « registres ». Les registres ont tous la fonctionnalité des modèles de valeur et des registres des amortissements. Par exemple, vous pouvez désactiver la validation dans la comptabilité. Les registres qui valident dans la comptabilité sont généralement utilisés pour les états financiers d'entreprise. Les registres qui ne valident pas dans la comptabilité peuvent être utilisés à des fins de déclaration de taxe.</td>
</tr>
<tr class="even">
<td>Effectuez la clôture de fin d'exercice de la comptabilité pour plusieurs entités juridiques.</td>
<td>Pour accélérer le processus de clôture de fin d'exercice, vous pouvez désormais exécuter la clôture de fin d'exercice pour plusieurs entités juridiques sur une page de clôture de fin d'exercice partagée. Les groupes d'entités juridiques peuvent être définis, ainsi que les paramètres qui doivent être conservés d'un an à l'autre. D'autres améliorations apportées à la convivialité ont également été apportées au processus de clôture de fin d'exercice.</td>
</tr>
<tr class="odd">
<td>Utilisez les améliorations apportées à la réévaluation des comptes en devises dans la comptabilité.</td>
<td>Les améliorations suivantes ont été apportées au processus de comptabilité pour la réévaluation des comptes en devises :
<ul>
<li>Un type de taux de change a été ajouté au compte principal. Ce type de taux de change est désormais utilisé pour déterminer le taux de change lors de la réévaluation d'une devise. Si aucun type de taux de change n'est défini, le processus continue à utiliser le type de taux de change défini dans la comptabilité.</li>
<li>Il est désormais plus simple de sélectionner une plage de comptes principaux et de devises pour exécuter le processus de réévaluation.</li>
<li>La réévaluation peut être exécutée pour plusieurs entités juridiques.</li>
<li>Le système conserve désormais un historique de chaque processus de réévaluation exécuté, comme pour les processus de réévaluation de la comptabilité client et de la comptabilité fournisseur.</li>
<li>Lorsque vous exécutez le processus, vous pouvez désormais prévisualiser les résultats de la réévaluation. L'aperçu affiche les résultats de toutes les entités juridiques pour lesquelles le processus a été exécuté. Vous pouvez ensuite valider toutes les entités juridiques, ou un sous-ensemble de celles-ci, dans l'aperçu. Vous pouvez également exporter les résultats de l'aperçu vers Excel.</li>
</ul></td>
</tr>
<tr class="even">
<td>Affichez les transactions de couches de validation supplémentaires.</td>
<td>Sur la page de liste <strong>Balance comptable</strong> et l'état <strong>Relevé de dimension</strong>, vous pouvez désormais sélectionner des couches de validation supplémentaires qui ont été ajoutées à la comptabilité. Lorsque vous sélectionnez les couches de validation supplémentaires, les ajustements de ces couches de validation sont inclus dans les soldes de la page de liste ou de l'état.</td>
</tr>
<tr class="odd">
<td>Associez la documentation sur les procédures au modèle de clôture de période comptable.</td>
<td>Précédemment, vous pouviez joindre la documentation une fois une tâche terminée. Par exemple, vous pouvez joindre un état qui avait été généré. Vous pouvez désormais également joindre un document sur la procédure au modèle. Ce document sur la procédure est ensuite copié vers chaque tâche du programme de la période comptable, de sorte que le propriétaire de la tâche puisse afficher des instructions sur la procédure permettant de terminer la tâche.</td>
</tr>
<tr class="even">
<td>Définissez le paramétrage de la comptabilité intersociétés dans une page partagée.</td>
<td>La <strong>page paramétrage de Comptabilité intersociétés</strong> est désormais partagée, afin qu'une organisation puisse définir toutes les paires d'entités juridiques qui peuvent traiter les unes avec les autres. En outre, vous pouvez désormais entrer une transaction dans l'entité juridique d'origine mais pas dans l'entité juridique de destination. Si l'une des entités juridiques peut lancer une transaction intersociétés, la paire réciproque doit être définie. C'est pourquoi, l'entité juridique de destination est également paramétrée comme entité juridique d'origine.</td>
</tr>
<tr class="odd">
<td>Envoyez des documents justificatifs pour les plans budgétaires.</td>
<td>Vous pouvez créer un modèle de justification comme documentation supplémentaire pour tous les montants budgétaires demandés. Les utilisateurs peuvent renseigner les détails du modèle et joindre le modèle au plan budgétaire, afin qu'il puisse être utilisé au cours du processus d'approbation.</td>
</tr>
<tr class="even">
<td>Activez les règles avancées des entrées de registre budgétaires.</td>
<td>Si des règles avancées sont configurées dans la comptabilité, ces règles peuvent être utilisées pour les nouvelles entrées et les transferts dans le registre budgétaire.</td>
</tr>
<tr class="odd">
<td>Utilisez la visibilité améliorée de l'activité de facturation de l'acompte.</td>
<td>Une nouvelle page de liste <strong>Ouvrir les acomptes</strong> fournit un instantané du statut de l'activité de facturation de l'acompte. La page fournit au service des Achats des informations sur les commandes fournisseur ayant des valeurs d'acompte restant à facturer, des valeurs facturées devant être réglées, et des valeurs de factures réglées qui doivent être appliquées aux factures standard. En outre, les améliorations apportées à l'application automatique des factures d'acompte réglées aux factures standard permettent aux commis de facturation de saisir les données plus efficacement.</td>
</tr>
<tr class="even">
<td>Utilisez l'espace de travail <strong>Facturation de collaboration fournisseur</strong>.</td>
<td>Un nouvel espace de travail <strong>Facturation</strong> dans la zone <strong>Collaboration fournisseur</strong> permet aux fournisseurs externes d'accéder de manière sécurisée à leurs propres informations de facturation. Par exemple, les fournisseurs peuvent voir si une facture a été payée et envoyer leur propre facture. Cette modification encourage une communication plus efficace et plus rapide avec les fournisseurs externes. Par conséquent, les commis de facturation subissent moins d'interruptions.</td>
</tr>
<tr class="odd">
<td>Remplacez les entités juridiques lors de la saisie d'une facture.</td>
<td>Les améliorations permettent aux commis de facturation qui doivent entrer des factures pour plusieurs entités juridiques de modifier rapidement l'entité juridique dans les pages de facturation. Cette fonction permet aux commis de facturation de gagner du temps, car ils ne doivent plus se déconnecter de l'entité juridique actuelle et se connecter à une autre entité juridique. La page <strong>Journal des factures global</strong> et la page <strong>Factures fournisseur</strong> permettent aux utilisateurs de modifier l'entité juridique lors de la saisie de données.</td>
</tr>
<tr class="even">
<td>Prise en charge des fichiers électroniques pour le programme de déclaration combiné fédéral/local 1099 de l'Internal Revenue Service (IRS) aux États-Unis</td>
<td>Lorsque la clé de configuration <strong>États-Unis</strong> est activée, le processus de transmission électronique 1099 fournit des fonctionnalités supplémentaires qui répondent aux réglementations de l'administration fiscale concernant le programme de déclaration combiné fédéral/local. L'administration fiscale des États-Unis a établi ce programme afin qu'il puisse transférer de manière électronique les retours d'informations aux états participants.</td>
</tr>
<tr class="odd">
<td>Améliorations des règlements</td>
<td>Les améliorations permettent aux commis d'effectuer les règlements plus efficacement, car les commis peuvent autoriser plusieurs paiements non validés à régler pour la même facture.</td>
</tr>
<tr class="even">
<td>Vue de société croisée</td>
<td>Les commis de paiement centralisé peuvent désormais afficher les factures en retard entre sociétés. Les espaces de travail <strong>Paiements fournisseur</strong> et <strong>Paiements client</strong> fournissent désormais une meilleure visibilité et un meilleur contrôle sur les factures échues en permettant d'afficher et de filtrer les sociétés qui font partie d'une hiérarchie organisationnelle de paiements centralisés.</td>
</tr>
<tr class="odd">
<td>Utilisez l'espace de travail <strong>Gestion des banques</strong>.</td>
<td>Un nouvel espace de travail <strong>Gestion des banques</strong> permet d'effectuer le suivi des comptes et des soldes bancaires pour vos entités juridiques. Les soldes actuels et en attente sont directement disponibles pour tous les comptes, et vous pouvez explorer les soldes dans les documents détaillés de transaction. Vous pouvez également afficher les données historiques du solde de chaque compte bancaire, ou une synthèse de tous les comptes bancaires de la société, dans les vues à court terme et à long terme. Vous pouvez obtenir une meilleure analyse du rapprochement de compte bancaire, car la date du dernier rapprochement est déclarée pour chaque compte bancaire, et il existe également un indicateur des rapprochements en cours.</td>
</tr>
<tr class="even">
<td>Importez des relevés bancaires électroniques pour toutes les entités juridiques en une seule étape.</td>
<td>Vous pouvez désormais importer des relevés bancaires électroniques pour toutes les entités juridiques en une seule étape. Les fichiers de relevé bancaire peuvent contenir des relevés de nombreux comptes bancaires et entités juridiques, et les fichiers compressés reste peuvent contenir plusieurs fichiers de relevés bancaires. L'utilisation d'un processus d'importation unique vous permet de commencer le rapprochement pour tous les comptes bancaires déclarés dans toutes les entités juridiques. Cette fonction vous permet de gagner du temps, car vous n'avez pas à passer des sociétés aux nombreuses importations de relevés. Vous pouvez également exécuter automatiquement les règles de mise en correspondance pour tous les relevés importés dans chaque société.</td>
</tr>
<tr class="odd">
<td>Suivi d'évaluation</td>
<td>Une immobilisation unique peut avoir plusieurs évaluations pour différentes normes comptables et peut éventuellement valider les transactions associées dans la comptabilité. Auparavant, ces évaluations étaient suivies à l'aide des modèles de valeur ou des registres des amortissements. Vous pouvez désormais effectuer le suivi de ces évaluations, qui sont maintenant désigné comme registres, à l'aide d'un ensemble commun de journaux, recherches, et états. L'expérience unifiée simplifie l'implémentation et réduit le nombre d'interfaces que les processus périodiques nécessitent.</td>
</tr>
<tr class="even">
<td>Utilisez les améliorations apportées aux exécutions d'amortissement entre sociétés.</td>
<td>Vous pouvez à présent démarrer l'exécution d'un amortissement entre toutes les entités juridiques sur une seule page. Vous pouvez également valider automatiquement les journaux après leur création. Vous pouvez envoyer la création et la validation des journaux au traitement par lots, afin que l'amortissement s'exécute en arrière-plan. Ces améliorations réduisent les inefficacités, car vous ne devez pas démarrer plusieurs exécutions d'amortissements séparément pour chaque société. Cette amélioration permet également de gérer de manière centralisée vos immobilisations.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Gestion du capital humain
| Ce que vous pouvez faire                                                                                | Pourquoi c'est important                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Créez un journal des performances.                                                                  | Avant de terminer votre révision, vous recueillez souvent des informations sur les activités ou les événements qui ont contribué à votre réussite en tant qu'employé au cours de la période de révision. Vous pouvez ajouter une entrée à votre journal des performances pour documenter les activités et événements. Vous pouvez également associer ces activités et événements à un objectif ou à une évaluation des performances pour fournir plus d'informations à l'évaluateur.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Créez des objectifs plus détaillés.                                                                    | Vous avez plus de contrôle sur le contenu des objectifs que vous avez définis. Vous pouvez créer des mesures pour les objectifs, lier des entrées du journal des performances aux mesures, et joindre et afficher des documents. Vous pouvez enregistrer des objectifs comme modèles et les réutiliser pour un paramétrage rapide.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Créez des évaluations des performances plus détaillées.                                                      | Les évaluations des performances, qui sont étaient appelées des discussions, sont désormais assez flexibles pour prendre en charge la rétroaction continue et des évaluations plus formelles. Vous pouvez récupérer des objectifs actifs et publier des commentaires sur ceux-ci, et ajouter des sections pour une évaluation de vos compétences. Des sections supplémentaires sont fournies, dans lesquelles vous pouvez ajouter ou afficher des mesures, des entrées de journal des performances, des pièces jointes, et des validations associées à l'évaluation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Associez des hiérarchies des postes supplémentaires à des workflows.                                      | Vous pouvez associer un workflow à une hiérarchie des postes. Vous pouvez également modifier les étapes du workflow pour optimiser le processus d'approbation afin qu'il soit conforme aux besoins de l'entreprise. Par conséquent, vous pouvez définir une structure d'approbation efficace qui s'adapte aux différentes relations hiérarchiques utilisées par votre organisation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Prise en charge de workflow pour entrer des numéros d'identification personnels (codes PIN) dans le Libre-service employé. | La capacité de workflow des Ressources humaines (RH) a été développé et comprend désormais la prise en charge des codes PIN. Les employés peuvent ajouter et modifier leur code PIN pour améliorer l'efficacité. Toutefois, les collaborateurs des RH peuvent analyser ces informations à des fins de précision et d'exhaustivité avant de les ajouter au dossier de l'employé.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Créez des modèles d'objectifs, et utilisez-les pour ajouter de nouveaux objectifs.                                          | Vous pouvez créer des modèles d'objectifs pour les objectifs qui sont partagés par plusieurs employés de la société. Les employés peuvent ajouter leurs propres objectifs à partir d'un modèle, les responsables peuvent ajouter des objectifs pour leur équipe à partir d'un modèle, et les membres de l'équipe des RH peuvent ajouter des objectifs pour les employés de toute la société.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Créez des groupes d'objectifs, et utilisez-les pour ajouter de nouveaux objectifs.                                             | Vous pouvez ajouter des modèles d'objectifs à un groupe, puis utilisez le groupe pour créer un ou plusieurs objectifs pour un employé, une équipe, un poste, un service, ou de la société.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Gagnez un meilleur contrôle sur le processus d'évaluation.                                                     | Vous pouvez utiliser un workflow pour contrôler le processus d'évaluation. Vous pouvez créer des modèles d'évaluation et les utiliser pour créer des évaluations. Vous pouvez également ajouter des notes à l'évaluation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Utilisez les périodes d'évaluation pour définir la période de l'évaluation.                                    | Vous pouvez définir une période pour une évaluation des performances et les dates de début et de fin de l'évaluation sont entrés automatiquement. Toutefois, vous pouvez modifier ces dates par défaut si nécessaire.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Accès à cinq nouveaux packs de contenu Power BI pour les Ressources humaines                                     | Les nouveaux packs de contenu permettent aux organisations et aux responsables des ressources humaines d'analyser les éléments suivants : Mesures de la main-d'œuvre • Répartitions démographiques par âge, sexe et situation de famille• Comparaison interannuelle des taux d'attrition et liste des raisons invoquées par les employés pour leur départ de l'organisation • Affichage d'une liste de postes ouverts, et comparaison des rémunérations et avantages des postes ouverts et fermés • Comparaisons des employés à tarif horaire et salariés • Affichage des employés inscrits aux avantages disponibles • Affichage des employés par type d'emploi Recrutement • Analyse des candidats en fonction du nombre de candidats, de leur origine et des postes pour lesquels ils se présentent Formation dans l'organisation • Inscription aux cours par emplacement • Présence aux cours par statut • Liste des employés inscrits aux cours Compétences et développement des employés • Liste des compétences des employés • Répartition des types de compétences par membres d'équipe |

## <a name="localizations"></a>Localisations
<table>




<thead>
<tr class="header">
<th>Ce que vous pouvez faire</th>
<th>Pourquoi c'est important</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Des localisations sont disponibles pour 18 pays supplémentaires :
<ul>
<li>Autriche</li>
<li>Belgique</li>
<li>Brésil</li>
<li>Chine</li>
<li>République tchèque</li>
<li>Estonie</li>
<li>Finlande</li>
<li>Hongrie</li>
<li>Italie</li>
<li>Lettonie</li>
<li>Lituanie</li>
<li>Norvège</li>
<li>Pologne</li>
<li>Arabie saoudite</li>
<li>Espagne</li>
<li>Suède</li>
<li>Suisse</li>
<li>Thaïlande</li>
</ul>
Les pays suivants nécessitent également la localisation de Retail. La localisation de Retail pour ces pays n'a pas été terminée et est prévue uniquement pour H1 CY2017 :
<ul>
<li>Brésil</li>
<li>République tchèque</li>
<li>Estonie</li>
<li>Hongrie</li>
<li>Lettonie</li>
<li>Lituanie</li>
<li>Malaisie</li>
<li>Pologne</li>
<li>Suède</li>
</ul></td>
<td>Dynamics 365 for Operations est disponible dans 18 pays supplémentaires. Dans le cadre de notre effort pour rendre la localisation plus facile et plus configurable, les fonctions de génération d'états électroniques réglementaires ont été converties en configurations d'états électroniques et certains états Microsoft SQL Server Reporting Services (SSRS) ont été convertis en configurations d'états électroniques qui utilisent des modèles Excel. Ces fonctions converties sont mentionnées spécifiquement ultérieurement dans cette table.</td>
</tr>
<tr class="even">
<td>Japon – Regroupez les immobilisations lorsque vous imprimez l'écran 26 et ses tableaux ajoutés.</td>
<td>L'écran 26 doit être envoyé à chaque ville dans laquelle la société opère. Pour vous éviter l'effort lorsque vous imprimez l'écran 26, les immobilisations peuvent être automatiquement regroupées et triées par emplacement.</td>
</tr>
<tr class="odd">
<td>Japon – Affichez les montants de l'amortissement accéléré et supplémentaire sur le profil.</td>
<td>Le profil peut fournir une estimation précise des montants pour l'amortissement accéléré et supplémentaire.</td>
</tr>
<tr class="even">
<td>Japon – Calculez progressivement la retenue à la source.</td>
<td>Le gouvernement japonais requiert que vous calculiez la retenue à la source progressivement, selon le montant du paiement.</td>
</tr>
<tr class="odd">
<td>Japon – Importez le fichier de codes postaux pour les grands bâtiments d'entreprise spécifiques.</td>
<td>Le fichier de codes postaux que l'autorité fournit pour des grands bâtiments d'entreprise spécifiques peut être importé dans le système. L'adresse peut ensuite être dérivée des codes postaux.</td>
</tr>
<tr class="even">
<td>Japon – Configurez une période d'inactivité pour les immobilisations.</td>
<td>Les périodes d'inactivité permettent à l'utilisateur de suspendre l'amortissement d'immobilisations au cours d'une période spécifiée. Cette fonctionnalité est requise par la réglementation.</td>
</tr>
<tr class="odd">
<td>Europe – Configurez un numéro d'enregistrement de taxe sur la valeur ajoutée (TVA) pour l'adresse d'un tiers à l'aide de la structure d'ID d'enregistrement.</td>
<td>Vous pouvez configurer un numéro d'enregistrement de TVA pour l'adresse d'un tiers à l'aide de la structure d'ID d'enregistrement et une nouvelle catégorie d'enregistrement d'<strong>ID de TVA</strong>.</td>
</tr>
<tr class="even">
<td>Finlande – Configurez un numéro de client des services douaniers pour l'adresse d'un tiers à l'aide de la structure d'ID d'enregistrement.</td>
<td>Vous pouvez configurer un numéro de client des services douaniers pour l'adresse d'un tiers à l'aide de la structure d'ID d'enregistrement et une nouvelle catégorie d'enregistrement d'<strong>ID de client des services douaniers</strong>.</td>
</tr>
<tr class="odd">
<td>France – Imprimez les factures client dans une mise en page spécifique à la France.</td>
<td>L'impression des factures client est adaptée pour satisfaire aux exigences spécifiques à la France.</td>
</tr>
<tr class="even">
<td>France – Appliquez la numérotation chronologique des documents par période fiscale.</td>
<td>Pour répondre aux exigences spécifiques à la France pour la numérotation des factures client, vous pouvez paramétrer des souches de numéros pour les factures client par période fiscale.</td>
</tr>
<tr class="odd">
<td>Localisation autrichienne - Configurations d'états électroniques</td>
<td><ul>
<li>Format XML de la liste des ventes intracommunautaires pour l'Autriche</li>
<li>Format de déclaration d'échanges de biens pour l’Autriche</li>
<li>Format de virement bancaire ISO20022 pour l'Autriche</li>
<li>Format de paiement de débit direct ISO20022 pour l'Autriche</li>
<li>Format EDIFACT-PAYMUL pour l'Autriche</li>
<li>Déclaration de TVA pour l'Autriche</li>
</ul></td>
</tr>
<tr class="even">
<td>Localisation belge - Configurations d'états électroniques</td>
<td><ul>
<li>Format BLWI pour la Belgique</li>
<li>Format XML de la liste des ventes intracommunautaires pour la Belgique</li>
<li>État des immobilisations pour la Belgique</li>
<li>Format de déclaration de taxe INTERVAT pour la Belgique</li>
<li>Format de déclaration d'échanges de biens pour la Belgique</li>
<li>État du chiffre d'affaires des factures pour la Belgique</li>
<li>Format d'exportation d'écriture comptable pour la Belgique</li>
<li>Format de paiement fournisseur SWIFT pour la Belgique</li>
<li>Formats d'importation des relevés bancaires CODA pour la Belgique</li>
<li>Format de virement bancaire ISO20022 pour la Belgique</li>
<li>Format de paiement de débit direct ISO20022 pour la Belgique</li>
</ul></td>
</tr>
<tr class="odd">
<td>Localisation brésilienne - Configurations d'états électroniques</td>
<td><ul>
<li>GIA SP pour le Brésil</li>
<li>GIA-ST pour le Brésil</li>
</ul></td>
</tr>
<tr class="even">
<td>Localisation pour la République tchèque – Configurations d'états électroniques</td>
<td><ul>
<li>Format XML de la liste des ventes intracommunautaires pour la République tchèque</li>
<li>Format de déclaration d'échanges de biens pour la République tchèque</li>
<li>Déclaration de TVA pour la République tchèque</li>
</ul></td>
</tr>
<tr class="odd">
<td>Localisation chinoise - Configurations d'états électroniques</td>
<td><ul>
<li>Format de balance âgée des clients pour la Chine</li>
<li>Format de l'état d'analyse des montants dus par les clients pour la Chine</li>
<li>Format de balance âgée des fournisseurs pour la Chine</li>
<li>Format de l'état d'analyse des montants dus par les fournisseurs pour la Chine</li>
<li>Format de l'analyse âgée des paiement des ventes pour la Chine</li>
<li>Format de l'état du solde client pour la Chine</li>
<li>Format de l'état du solde du compte général pour la Chine</li>
<li>Format du solde fournisseur pour la Chine</li>
<li>Fichier GBT pour la Chine</li>
<li>Format du fichier d'exportation GTS</li>
<li>Format de l'état d'écart sur la consommation de la production pour la Chine</li>
</ul></td>
</tr>
<tr class="even">
<td>Localisation estonienne - Configurations d'états électroniques</td>
<td><ul>
<li>Format XML de la liste des ventes intracommunautaires pour l'Estonie</li>
<li>Format de déclaration d'échanges de biens pour l’Estonie</li>
<li>Déclaration de reclassification de stock pour l'Estonie</li>
<li>Format de virement bancaire ISO20022 pour l'Estonie</li>
<li>État des avis de solde fournisseur du client pour l'Estonie</li>
<li>Déclaration de TVA pour l'Estonie</li>
</ul></td>
</tr>
<tr class="odd">
<td>Localisation finlandaise - Configurations d'états électroniques</td>
<td><ul>
<li>Format TXT de liste des ventes intracommunautaires pour la Finlande</li>
<li>Format de déclaration d'échanges de biens pour la Finlande</li>
<li>Format de virement bancaire ISO20022 pour la Finlande</li>
</ul></td>
</tr>
<tr class="even">
<td>Localisation hongroise - Configurations d'états électroniques</td>
<td><ul>
<li>Format XML de la liste des ventes intracommunautaires pour la Hongrie</li>
<li>Format de déclaration d'échanges de biens pour la Hongrie</li>
<li>Format simplifié par déclaration d'échanges de biens pour la Hongrie</li>
<li>Format d'exportation de la liste de factures pour la Hongrie</li>
<li>Déclaration de TVA pour la Hongrie</li>
<li>Déclaration de TVA ventilée pour la Hongrie</li>
<li>Relevé de stock pour la Hongrie</li>
<li>Format de paiement MultiCash pour la Hongrie</li>
</ul></td>
</tr>
<tr class="odd">
<td>Localisation italienne - Configurations d'états électroniques</td>
<td><ul>
<li>Format de déclaration d'échanges de biens pour l'Italie</li>
<li>Format de facture de projet pour l'Italie</li>
<li>Format de facture client pour l'Italie</li>
<li>Format de virement bancaire ISO20022 pour l'Italie</li>
<li>Format de paiement de débit direct ISO20022 pour l'Italie</li>
<li>Format de remise de collection RIBA pour l'Italie</li>
<li>Générer un état des transactions de taxe domestique pour l'Italie</li>
<li>État de la liste rouge pour l'Italie</li>
<li>État Modello770 pour l'Italie</li>
<li>État de communication annuelle de la taxe pour l'Italie</li>
</ul></td>
</tr>
<tr class="even">
<td>Localisation lettonne - Configurations d'états électroniques</td>
<td><ul>
<li>Générer un état d'utilisation des rentrées de fonds (Lettonie)</li>
<li>Format XML de liste des ventes intracommunautaires pour la Lettonie</li>
<li>Format XML des corrections de liste des ventes intracommunautaires pour la Lettonie</li>
<li>Format de déclaration d'échanges de biens (A) pour la Lettonie</li>
<li>Format de déclaration d'échanges de biens (B) pour la Lettonie</li>
<li>Liste de comptage de stock pour la Lettonie</li>
<li>Déclaration de comptage de stock pour la Lettonie</li>
<li>Mouvement de stock pour la Lettonie</li>
<li>Note de livraison de transfert interne pour la Lettonie</li>
<li>Document de reclassification de stock pour la Lettonie</li>
<li>Format de virement bancaire ISO20022 pour la Lettonie</li>
<li>Déclaration de TVA pour la Lettonie</li>
</ul></td>
</tr>
<tr class="odd">
<td>Localisation lituanienne - Configurations d'états électroniques</td>
<td><ul>
<li>Format XML de la liste des ventes intracommunautaires pour la Lituanie</li>
<li>Format de déclaration d'échanges de biens pour la Lituanie</li>
<li>Relevé de stock pour la Lituanie</li>
<li>Format de virement bancaire ISO20022 pour la Lituanie</li>
<li>État d'inter-rapprochement fournisseur client pour la Lituanie</li>
<li>Déclaration de TVA pour la Lituanie</li>
</ul></td>
</tr>
<tr class="even">
<td>Localisation norvégienne - Configurations d'états électroniques</td>
<td><ul>
<li>Format de lettre de relance pour la Norvège</li>
<li>Format de paiement AutoGiro pour la Norvège</li>
<li>Format de paiement client AvtaleGiro pour la Norvège</li>
<li>Format de paiement client eFaktura pour la Norvège</li>
<li>Format de virement bancaire ISO20022 pour la Norvège</li>
<li>Format de paiement NETS pour la Norvège</li>
</ul></td>
</tr>
<tr class="odd">
<td>Localisation polonaise - Configurations d'états électroniques</td>
<td><ul>
<li>Format de déclaration d'échanges de biens pour la Pologne</li>
<li>Documents d'entrepôt pour la Pologne</li>
<li>Document de reclassification de stock pour la Pologne</li>
<li>Format de paiement MultiCash pour la Pologne</li>
<li>Format de paiement étranger MultiCash pour la Pologne</li>
<li>État des confirmations de solde fournisseur du client pour la Pologne</li>
</ul></td>
</tr>
<tr class="even">
<td>Localisation Arabie saoudite- Configurations d'états électroniques</td>
<td>Format de répartition des frais divers de lettre de crédit bancaire pour l'Arabie saoudite</td>
</tr>
<tr class="odd">
<td>Localisation espagnole - Configurations d'états électroniques</td>
<td><ul>
<li>Format TXT de liste des ventes intracommunautaires pour l'Espagne</li>
<li>Format de déclaration d'échanges de biens pour l'Espagne</li>
<li>Format de facture de projet pour l'Espagne</li>
<li>Format de facture client pour l'Espagne</li>
<li>Format de virement bancaire ISO20022 pour l'Espagne</li>
<li>Format de paiement de débit direct ISO20022 pour l'Espagne</li>
<li>Format du registre de la TVA espagnol</li>
<li>Format de la synthèse du registre de la TVA espagnol</li>
<li>Exportation de la déclaration 347 vers un fichier ASCII pour l'Espagne</li>
<li>État de la déclaration 347 pour l'Espagne</li>
</ul></td>
</tr>
<tr class="even">
<td>Localisation suédoise - Configurations d'états électroniques</td>
<td><ul>
<li>Format de déclaration d'échanges de biens pour la Suède</li>
<li>Format de paiement client à Bankgirot Autogiro pour la Suède</li>
<li>Format de paiements fournisseur Bankgirot pour la Suède</li>
<li>Format de paiement fournisseur SWIFT pour la Suède</li>
<li>Format d'exportation SIE pour la Suède</li>
<li>Format de virement bancaire ISO20022 pour la Suède</li>
</ul></td>
</tr>
<tr class="odd">
<td>Localisation suisse - Configurations d'états électroniques</td>
<td><ul>
<li>Format de paiement DebitDirect pour la Suisse</li>
<li>Format de paiement DebitDirect LSV pour la Suisse</li>
<li>Format de virement bancaire ISO20022 pour la Suisse</li>
<li>Format de paiement DebitDirect ISO20022 pour la Suisse</li>
<li>Formats d'importation des relevés bancaires ESR pour la Suisse</li>
</ul></td>
</tr>
<tr class="even">
<td>Allemagne – Paiements fournisseur d'exportation dans le format DTAZV</td>
<td>L'Allemagne nécessite DTAZV pour spécifier le format étranger, soit un message de transfert de crédit (paiement fournisseur) selon la spécification pour les paiements transfrontaliers d'Allemagne vers un compte bancaire étranger ou vers une banque locale dans une devise étrangère. 
</td>
</tr>
</tbody>
</table>

### <a name="electronic-reporting"></a>Gestion des états électroniques

| Ce que vous pouvez faire                                                                                                                                                                                                                                                                                     | Pourquoi c'est important                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuration des états d'ER pour insérer des données, dans plusieurs formats, entre le stockage de gestion des documents et les messages électroniques générés.                                                                                                                                                              | Les états ER permettent d'insérer des données dans les messages électroniques générés dans le stockage de gestion des documents. Par conséquent, les pièces jointes d'un document commercial peuvent être ajoutées aux messages électroniques générés pour ce document, selon les obligations légales. Actuellement, ces pièces jointes peuvent être ajoutées au format MIME à un message XML généré. Sinon, les pièces jointes peuvent être ajoutées au format Base64 à un message binaire qui est généré.                                                                      |
| Configurez les états ER pour générer les documents électroniques au format Excel, Microsoft Word ou PDF.                                                                                                                                                                                                      | Une configuration permet aux états ER de générer des documents électroniques dans trois formats différents : feuille de calcul OpenXML (Excel), Word et format de données d'écrans XML (XFDF) (PDF). Les utilisateurs peuvent sélectionner un format en ajoutant un modèle de format à un état ER en tant que document Excel, Word, ou PDF.                                                                                                                                                                                                                                                                       |
| Configurez des états ER pour insérer des données dans les en-têtes et les pieds de page des documents électroniques générés dans le format de feuille de calcul OpenXML, et pour contrôler les sauts de page.                                                                                                                               | Les états ER peuvent entrer des données commerciales dans les en-têtes et les pieds de page, et contrôler également à quel moment les sauts de page se produisent. Par conséquent, les états peuvent prendre en charge les sections supérieures et inférieures statiques des pages des documents électroniques générés. Ils peuvent également prendre en charge la pagination spécifique de ces documents, afin qu'ils soient conformes aux obligations légales.                                                                                                                                                                                                             |
| Configurez la destination des états ER afin que le résultat soit envoyé comme e-mail, et que les données commerciales et la logique ER (expressions) puissent être utilisées pour spécifier, au moment de l'exécution, l'adresse e-mail à utiliser.                                                                                                    | Auparavant, lorsque vous configuriez une destination ER, l'adresse e-mail du destinataire du résultat pouvait être défini au moment de la conception. Vous pouvez désormais configurer une expression au format ER. Cette expression peut être sélectionnée dans une destination comme source de l'adresse e-mail de chaque configuration de format et de chaque composant de résultat (dossier ou fichier) séparément. Ainsi, lorsqu'un état ER s'exécute, chaque fichier généré peut être envoyé par e-mail à un destinataire différent, et l'adresse e-mail peut être définie selon logique ER et les données commerciales. |
| Configurez la destination des états ER afin que le résultat soit envoyé au dossier Microsoft SharePoint comme un fichier portant un nouveau nom ou une nouvelle version du fichier existant, et que les données commerciales puissent être utilisées dans la structure Microsoft Power BI comme un ensemble de données ou un état.                 | Lorsque vous configurez des états ER, vous pouvez désormais facilement (sans codage) préparer les données commerciales demandées afin qu'elles puissent être utilisées par la structure Power BI. Lorsque vous exécutez ces états ER, vous pouvez fournir à la structure Power BI les données commerciales et/ou les états Excel appropriés qui sont déjà disponibles. Si vous planifiez l'état pour qu'il s'exécute en mode récurrent, vous pouvez l'envoi planifié de données commerciales de Dynamics 365 for Operations vers Power BI pour prendre en charge le programme de mise à jour des états basés sur Power BI.                             |
| Configurez des états ER pour utiliser la partie du document électronique qui a déjà été générée comme source de données pour générer le reste de ce document.                                                                                                                                             | Vous pouvez configurer les états ER qui créent le résultat au format texte pour effectuer le comptage de lignes du document. Ces informations peuvent ensuite être utilisées dans d'autres parties du document pour créer des lignes qui incluent des détails de synthèse. Les informations de synthèse (totaux et numéros) peuvent être calculées et imprimées dans les documents électroniques générés, sans nécessiter de transformations supplémentaires des données. Par conséquent, cette fonction améliore les performances de l'exécution de l'état et facilite la future maintenance du format d'ER configuré.    |
| Configurez les états ER pour spécifier l'extension du nom de fichier pour les documents électroniques générés au format texte.                                                                                                                                                                                 | Vous pouvez configurer des états ER pour créer la sortie au format texte, de manière à pouvoir être enregistrée comme fichier contenant une extension spécifique. Outre l'extension par défaut .txt, vous pouvez configurer des extensions comme .csv et .prn, conformément à la spécification de format.                                                                                                                                                                                                                                                                             |
| Créez de nouveaux états ER basés sur une version spécifique d'un modèle ER.                                                                                                                                                                                                                          | Auparavant, lors de la création d'un nouveau format ER, seule la version la plus récente du modèle ER sélectionné pouvait être utilisée comme emplacement de la source des données du format. Vous pouvez désormais sélectionner n'importe quelle version disponible du modèle ER sélectionné. Cette fonction permet de tenir à jour des états ER pour l'année en cours et de créer une nouvelle version du modèle ER de l'année suivante en parallèle.                                                                                                                                                                                          |
| Recherchez les sources de données et les formats/modèles en fonction du texte ou d'un artefact sélectionné en un clic. Résolvez de manière proactive les conflits redéfinis, et résolvez les conflits entre les configurations. Configurez les états ER pour créer plusieurs messages de validation des erreurs qui sont détectées jusqu'à ce que l'exécution de l'état soit bloquée. | Plusieurs améliorations d'expérience utilisateur (UX) dans la structure d'ER permettent aux utilisateurs d'utiliser les ER plus efficacement et plus facilement.                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Affichez l'espace de travail **ER** dans les états Power BI.                                                                                                                                                                                                                                                      | Les utilisateurs peuvent configurer la page **Espace de travail ER** pour qu'elle inclue de nouveaux éléments de menu et des vignettes actives qui exécutent les états Power BI.                                                                                                                                                                                                                                                                                                                                                                                                                       |

## <a name="payroll"></a>Paie
<table>




<thead>
<tr class="header">
<th>Ce que vous pouvez faire</th>
<th>Pourquoi c'est important</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configurez des enregistrements de paie et traitez les paies à l'aide de la fonctionnalité qui est équivalente à la fonctionnalité du module <strong>Paie</strong> de Microsoft Dynamics AX 2012 R3.</td>
<td>Vous pouvez désormais configurer et traiter la Paie États-Unis à l'aide d'une fonctionnalité définie qui est équivalente à la fonctionnalité définie dans AX 2012 R3.
<ul>
<li>Vous pouvez configurer les cycles de paie et les périodes de rémunération, les cycles de travail et les périodes de travail, les codes de rémunération et les groupes de codes de rémunération, les programmes, les types de congés, et les plans de régularisation des avantages.</li>
<li>Vous pouvez également paramétrer des déductions obligatoires pour les avantages et les taxes, et enregistrer les informations sur les salaires pour les postes et les collaborateurs à des fins de génération d'états et d'analyse.</li>
<li>Vous pouvez également paramétrer et gérer des déductions pour des saisies-arrêts et des prélèvements de taxe, et pour tous les frais administratifs associés.</li>
</ul></td>
</tr>
<tr class="even">
<td>Surveillez et traitez votre processus de période de rémunération à l'aide du nouvel espace de travail <strong>Gestion de la paie</strong>.</td>
<td>Vous pouvez surveiller désormais aisément votre traitement des salaires. D'un coup d'œil, les administrateurs des salaires peuvent afficher les rémunérations et les bordereaux de paie qui nécessitent leur attention, de sorte que le cycle de paie soit exhaustif et précis. L'espace de travail <strong>Gestion de la paie </strong>permet aux utilisateurs de surveiller et d'exécuter des processus de bout en bout depuis un espace de travail unique.</td>
</tr>
<tr class="odd">
<td>Générez des fichiers de paiement positifs pour les vérifications des salaires.</td>
<td>Il existe une nouvelle extension à la fonctionnalité de paiement positif de la Gestion de la trésorerie et de la banque pour les paiements des salaires. Des éléments de menu distincts ont été ajoutés tout au long du processus de base pour activer la configuration isolée spécifique aux salaires. Cette fonctionnalité est identique à la fonction de paiement positif de base lancée dans la version 7.0.1 (mai 2016) de l'application Microsoft Dynamics AX. En raison de cette extension, les données de paie sont isolées entièrement du reste de vos transactions de paiement positif. Cet isolement permet de garantir que seuls les utilisateurs des salaires peuvent accéder aux données associées à la paie et les afficher.</td>
</tr>
<tr class="even">
<td>Importez les lignes de relevé des rémunérations d'une source externe à l'aide de la nouvelle entité Ligne de relevé des rémunérations.</td>
<td>Une nouvelle entité de données importante permet l'intégration à des systèmes externes de calcul de temps et de rémunération. L'entité de données importe des lignes de relevé des rémunérations et effectue la même logique par défaut que l'utilisateur a entrée directement sur le relevé des rémunérations. Après l'importation, les lignes sont automatiquement associées au document de relevé des rémunérations correspondant. S'il n'existe pas de document de relevé des rémunérations correspondant, un document est créé automatiquement.</td>
</tr>
</tbody>
</table>

## <a name="planning-and-scheduling"></a>Planification et programmation
| Ce que vous pouvez faire                                                                                                                                                                                                      | Pourquoi c'est important                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Définissez les paramètres de commande par défaut pour les ventes et achats, selon la dimension de produit active sur le produit générique. Par conséquent, vous pouvez définir les paramètres de commande par défaut pour l'unité de gestion de stock (SKU) ou un SKU partiel. | Vous pouvez spécifier les paramètres de commande par défaut qui s'appliquent à une dimension de produit ou à une combinaison de dimensions de produit. **Exemple** Vous vendez un produit appelé T-shirt de polo. Ce produit est disponible dans deux couleurs : vert et bleu. Il est également disponible dans deux tailles : S et M. La couleur ou la taille sont des dimensions de produit actives pour le T-shirt de polo. Vous pouvez bloquer les achats de tous les T-shirts de polo verts, indépendamment de leur taille. |

## <a name="product-master-data"></a>Données de produit générique
<table>




<thead>
<tr class="header">
<th>Ce que vous pouvez faire</th>
<th>Pourquoi c'est important</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Paramétrez tous les paramètres de commande par défaut et tous les paramètres de commande spécifiques au site en même temps, sur une seule page.</td>
<td>Cette fonctionnalité permet d'avoir une meilleure vue d'ensemble des paramètres article.</td>
</tr>
<tr class="even">
<td>Créez une nomenclature pour les numéros de variantes de produits.</td>
<td>Vous pouvez inclure des éléments tels que les dimensions de produit, les attributs, et les caractères dans vos numéros de variantes de produits. Lorsque vous créez une commande client ou fournisseur, vous pouvez rapidement rechercher la variante de produit spécifique.</td>
</tr>
<tr class="odd">
<td>Recherchez des produits et des variantes de produits dans les scénarios de ventes et d'achat.</td>
<td>Lorsque vous créez une ligne de vente ou une ligne d'achat, vous pouvez rechercher des produits à l'aide de dimensions de produit et de tous les numéros de produit à l'exception des numéro d'identification de commerce mondial (GTIN) et des codes-barres. Cette recherche est une recherche de texte intégral qui remplace la recherche « commence par » existante utilisée dans la liste de recherche des ventes et des achats. Cette fonctionnalité permet de rechercher des groupes de produits ayant des propriétés similaires ou un produit unique ayant des caractéristiques uniques. Pour activer cette fonctionnalité, sélectionnez le paramètre <strong>Activer la recherche pour la recherche de produit</strong> sur la page <strong>Paramètres de recherche</strong>.</td>
</tr>
<tr class="even">
<td>Spécifiez la variante de produit directement lorsque vous créez des transaction de vente ou d'achat. Sinon, vous pouvez choisir parmi une liste de combinaisons de dimensions valides.</td>
<td>Cette fonctionnalité apporte une amélioration de la productivité. <strong>Exemple</strong> Vous vendez un produit appelé T-shirt de polo. Ce produit est disponible dans deux couleurs : vert et bleu. Il est également disponible dans deux tailles : S et M. La couleur ou la taille sont des dimensions de produit actives pour le T-shirt de polo. Lorsque vous entrez une ligne de vente pour le T-shirt de polo de couleur verte et de taille S, vous ne devez pas entrer des données dans les champs <strong>Numéro d'article</strong>, <strong>Couleur</strong> et <strong>Taille</strong>. Vous pouvez créer la ligne en suivant la procédure suivante :
<ul>
<li>Dans le champ <strong>Numéro d'article</strong>, entrez le nombre de variante de produit, la valeur d'une couleur, ou la taille. Dans la recherche, recherchez la variante spécifique que vous souhaitez vendre, puis créez la ligne de vente.</li>
<li>Dans le champ <strong>Numéro d'article</strong>, entrez le numéro d'article. Accédez à n'importe quel champ de dimension de produit. Dans la recherche <strong>Dimension de produit</strong>, vous verrez toutes les combinaisons de dimensions lancées qui s'appliquent au T-shirt de polo. En une étape, vous pouvez sélectionner la variante de produit que vous souhaitez vendre.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Spécifiez si les numéros de produit s'affichent sur les pages transactionnelles.</td>
<td>Les pages transactionnelles, telles que les commandes client et fournisseur, affichent uniquement les champs <strong>Numéro d'article</strong> et <strong>Nom du produit</strong>. Pour afficher le champ <strong>Numéro de produit</strong>, sélectionnez le paramètre <strong>Afficher les numéros de produit sur les écrans</strong> sous <strong>Paramètres de gestion des informations sur les produits</strong>.</td>
</tr>
</tbody>
</table>

## <a name="project-management-and-accounting"></a>Gestion et comptabilité des projets
| Ce que vous pouvez faire                                                                                                           | Pourquoi c'est important                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Utilisez la sélection ultérieure lorsque vous validez des propositions de facture dans un lot.                                                            | Les comptables de projet peuvent paramétrer un traitement par lots pour prélever automatiquement des propositions de facture pour la validation, si ces propositions répondent aux critères spécifiés sur le traitement par lots. Cette fonctionnalité améliore l'automatisation de la validation de factures, car le traitement par lots peut fonctionner en continu et prélever automatiquement des propositions pour la validation. |
| Créez des analyses dans Power BI Desktop.                                                                                     | Le contenu Business Intelligence (BI) pour les données associées au projet et aux ressources peut être facilement créé dans Power BI Desktop.                                                                                                                                                                                                       |
| Utilisez les acomptes de commande fournisseur, et incluez-les correctement au processus d'estimation du projet.                               | Pour les commandes fournisseur de projet, les acomptes doivent être traités avant que des paiements puissent être transmis aux fournisseurs. Ces factures d'acompte s'affichent désormais dans le processus d'estimation/constatation de projet pour des projets de types à **Prix fixe**.                                                                                           |
| Accédez aux estimations de coût et de produit et gérez-les, ainsi que les demandes d'articles, directement depuis une tâche de structure de répartition du travail (WBS). | Vous pouvez gérer les estimations de coût, les estimations de produit, et les demandes d'articles pour une tâche WBS spécifique dans la boîte de dialogue de détails de cette tâche dans la vue de planification WBS.                                                                                                                                                                 |
| Choisissez une source de financement dans les journaux de frais.                                                                                    | Si le contrat d'un projet contient plusieurs sources de financement, vous pouvez sélectionner une source de financement spécifique lorsque des frais sont validés. Si ne sélectionnez pas de source de financement spécifique, les règles de financement spécifiées sur le contrat sont utilisées pour affecter les frais.                                                                   |
| Ouvrez les relevés de projet dans Excel.                                                                                         | Les nouvelles entités de données des mises à jour comptables et des mises à jour budgétaires vous permettent d'ouvrir des données de relevé de projet dans Excel et de créer des analyses à l'aide des fonctionnalités d'Excel.                                                                                                                                                                           |
| Il vous suffit d'utiliser une clé de configuration pour activer la fonctionnalité Gestion et comptabilité des projets (PMA).                       | Les clés de configuration associées aux projets ont été remplacées par une clé de configuration de projet qui active la fonctionnalité PMA.                                                                                                                                                                                                       |

## <a name="retail-and-commerce"></a>Commerce et vente au détail
### <a name="advanced-warehouse-management-in-a-retail-store"></a>Gestion avancée des entrepôts dans un magasin de vente au détail

Les détaillants peuvent utiliser la solution de gestion avancée des entrepôts (WHS) dans leurs magasins et effectuer les mises à jour nécessaires dans les fonctionnalités du point de vente actuel (PDV) pour la prendre en charge. Les processus de la solution portable doivent être exécutés dans un magasin comme dans tout autre entrepôt. Tous les processus actuels de Retail Stocks magasin, et tous les processus de PDV qui créent ou mettent à jour les mouvements de stock, sont mis à jour de sorte qu'ils utilisent les besoins spécifiques des entrepôts activés par WHS.

| Ce que vous pouvez faire                                                                       | Pourquoi c'est important                                                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Utilisez le PDV pour rechercher le stock disponible dans les magasins activés par WHS.                     | Lorsque vous recherchez un stock, le processus doit fonctionner comme avant. La recherche doit afficher les quantités disponibles au niveau de l'entrepôt, et ne doit pas tenir compte des dimensions d'emplacement, de statut du stock, ou de numéro de contenant. |
| Utilisez le PDV pour traiter un accusé de réception de marchandises pour un ordre de transfert dans un magasin activé par WHS. | Vous pouvez recevoir des ordres de transfert dans le PDV pour un magasin et des articlés activés par WHS. L'utilisateur doit pouvoir sélectionner les emplacements dans lesquels effectuer les réceptions, et doit pouvoir entrer des ID de numéro de contenant pour remplir automatiquement les lignes de réception.    |
| Utilisez le PDV pour traiter un accusé de réception de marchandises pour une commande fournisseur dans un magasin activé par WHS. | Vous pouvez recevoir des commande fournisseur dans le PDV pour un magasin et des articlés activés par WHS. L'utilisateur doit pouvoir sélectionner les emplacements dans lesquels effectuer les réceptions, et doit pouvoir entrer des ID de numéro de contenant pour remplir automatiquement les lignes de réception.    |
| Utilisez le PDV pour traiter une expédition des produits depuis un magasin activé par WHS.               | Vous pouvez enregistrer des transferts depuis le PDV pour un magasin et des articlés activés par WHS. L'utilisateur doit pouvoir sélectionner les emplacements vers lesquels effectuer les expéditions, le statut du stock doit être généré automatiquement, et les contenants doivent être ignorés.         |

### <a name="enable-seamless-omni-channel-commerce"></a>Activez le commerce de canal Omni transparent

Le commerce de canal Omni transparent fait référence à la gestion et au traitement des commandes dans les magasins physiques, les vitrines en ligne, les centres d'appels, et les expériences de commerce mobile. Pour cette version, les investissements suivants ont été effectués dans ce domaine :

-   Améliorations pour publier des vitrines de commerce électronique
-   Une application mobile face au client qui active la détection de produit, la gestion de compte, et les achats en ligne

| Ce que vous pouvez faire                                                                                                                                                                                                                                                                   | Pourquoi c'est important                                                                                                                                                            |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Consommateur : Le lancement actuel de l'application face au client active les fonctionnalités suivantes : recherche de produit, parcours de catégories, ajout au chariot et validation des achats. Les détaillants peuvent également appliquer la stratégie de marque de leur société à l'application, puis l'empaqueter pour les boutiques d'applications Android et iOS. | Les détaillants peuvent facilement créer une application face au client qui permet à leurs clients de parcourir, de rechercher des produits et d'expédier des produits en tant qu'invité sur leurs appareils mobiles.                      |
| Listes de souhaits client pour les vitrines en ligne de commerce électronique                                                                                                                                                                                                                             | Les éditeurs de logiciels indépendants (ISV) peuvent utiliser le contrôle de liste de souhaits pour permettre aux utilisateurs de créer et de gérer plusieurs listes dans leur vitrine en ligne, et afficher/utiliser ces listes dans le PDV. |
| Création de client asynchrone via les vitrines en ligne de commerce électronique                                                                                                                                                                                                                  | Les ISV peuvent désormais créer des comptes client, même si Commerce Data Exchange: Real-time Service n'est pas disponible.                                                                        |
| Publiez des produits du canal depuis le serveur de vente au détail à des vitrines tierces.                                                                                                                                                                                                           | Le serveur de vente au détail prend désormais en charge une authentification de service à service. Les ISV peuvent bénéficier de la publication de produit de canal sur le serveur de vente au détail sur des vitrines tierces.               |

### <a name="extensibility"></a>Extensibilité

-   Les projets de runtime de commerce sont désormais fermés au Kit de développement logiciel (SDK) Retail.
-   Déploiement et entretien plus simples à l'aide des packages de composants Microsoft ventilés et les packages ISV du PDV, le serveur de vente au détail, les bases de données, le paiement et les stations matérielles.

| Ce que vous pouvez faire                                                                                                                 | Pourquoi c'est important                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Serveur de vente au détail et CRT : les détaillants ou les ISV peuvent étendre le CRT via les crochets d'extension. Les modifications de code intégré ne sont plus prises en charge. | Pour activer l'intégration et le déploiement continus, les modifications du code intégré doivent être totalement évitées. De plus, pour prendre en charge l'utilisation simple du correctif sans fusion de code et déploiement des composants CRT. |

### <a name="personalized-product-recommendations"></a>Recommandations de produit personnalisées

| Ce que vous pouvez faire                                                                                                                                                                                                                                                                        | Pourquoi c'est important                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Affichez les recommandations de produit personnalisées en plusieurs points de contact des points de vente (PDV) pour déterminer ce qui pourrait intéresser un client en fonction de son historique d'achats, des articles de sa liste de souhaits et des articles que d'autres clients ont acheté en ligne et dans les magasins physiques. | Pour les détaillants ayant des catalogues, les recommandations personnalisées aident le client à découvrir des produits offrent aux employés des magasins une facilité de gestion intelligente de la clientèle. En mettant en avant des produits ciblés selon les intérêts et les habitudes d'achat des clients, les recommandations de produit peuvent aider les détaillants à réaliser des ventes incitatives et à accroître la conservation des clients. Dans Microsoft Dynamics 365 for Retail, les recommandations de produit sont fondées sur le Machine learning et les Cognitive Services de Microsoft Azure. |

### <a name="pos-task-recorder"></a>Enregistreur de tâches du PDV

| Ce que vous pouvez faire                                                                                                                                                                                                  | Pourquoi c'est important                                                                                                                                                                                    |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Les détaillants peuvent utiliser l'enregistreur de tâches du PDV afin de produire des supports de formation, des diagrammes de Concepteur de processus d'entreprise (BPM), et générer du contenu d'aide pour améliorer la productivité et la conception des applications. | Pour activer l'intégration et le déploiement continus, les modifications du code intégré doivent être totalement évitées. De plus, pour prendre en charge l'utilisation simple du correctif sans fusion de code et déploiement des composants CRT. |
| Aide en temps réel dans le PDV.                                                                                                                                                                                           | Le caissier/responsable peut obtenir de l'aide en temps réel du PDV dans le processus entreprise sans changer de contexte.                                                                                                           |

### <a name="store-system-providing-a-seamless-on-premises-store-experience"></a>Système de magasin : fournir une expérience de magasin local transparente

Le système de magasin est un choix de déploiement pour les détaillants qui permet de mener un ensemble d'opérations de magasin, que ce soit dans un magasin local, un cloud public Microsoft, ou un cloud privé propre au client. Pour cette version, la portée est uniquement pour le magasin. Pour améliorer la prise en charge des environnements avec une connectivité réseau lente et peu fiable, nous devons fournir une option pour autoriser les détaillants à déployer la base de données des canaux et le serveur de vente au détail dans le magasin. Ils peuvent ensuite continuer à exécuter leurs scénarios d'entreprise de base, même s'il n'existe aucune connectivité avec les sièges sociaux. Selon les différents points de données, qui incluaient les discussions de l'équipe d'ingénierie, les résultats d'enquête client, et l'analyse de la concurrence, nous avons identifié la portée de solution suivant comme idéale pour nos clients cibles :

-   Un package en libre service est disponible pour le système de magasin.
-   L'installation par défaut est un déploiement one-box, mais le déploiement personnalisé est autorisé.
-   Activez le déploiement/libre service facile.
-   Le serveur de vente au détail et la base de données du magasin sont dans le magasin, avec le service Client Async.
-   Le serveur de vente au détail du magasin communique directement avec le serveur d'objets d'application (AOS) au siège social pour le système de magasin.
-   Prenez en charge les scénarios entre les terminaux où il n'existe aucune connectivité avec le siège social.
-   Retail Modern POS et PDV Cloud communiquent toujours avec le serveur de vente au détail du magasin.
-   Prenez en charge Retail Modern POS et PDV cloud lorsqu'il n'y a aucune connectivité avec le siège social.
-   Prenez en charge une base de données hors connexion spécifique à Retail Modern POS (isolée de chaque instance de Retail Modern POS) lorsqu'il n'y a aucune connectivité avec le siège social.
-   L'authentification est basée sur le service à service uniquement pour le système de magasin.
-   Les appels de service en temps réel ne sont pas pris en charge s'il n'existe aucune connectivité Internet.
-   La connectivité directe de la base de données de Retail Modern POS à la base de données des canaux n'est pas prise en charge.
-   Activez la télémétrie/le contrôle.

| Ce que vous pouvez faire                                                                                                                                       | Pourquoi c'est important                                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Un détaillant télécharge le programme d'installation du libre service du système de magasin sur la page de la base de données des canaux dans Dynamics AX HQ et télécharge le fichier de configuration.   | Le détaillant peut télécharger de façon transparente le package de libre service.                                          |
| Un détaillant installe le système de magasin à l'aide du programme d'installation en libre service.                                                                                 | Le détaillant peut installer le système de magasin à l'aide du package en libre service.                                |
| Le responsable informatique configure le système de magasin dans Dynamics 365 for Operations (base de données des canaux, profil de canal, magasin, et package déployable).             | Le responsable informatique peut configurer le système de magasin facilement et plus efficacement.                                       |
| Un détaillant exécute Retail Modern POS dans le magasin local et peut effectuer des opérations en temps réel, comme émettre des cartes cadeaux, lorsqu'il existe une connectivité. | Le détaillant peut exécuter des actions en temps réel depuis le système de magasin en cas de connectivité.                |
| Un détaillant peut synchroniser les données du système de magasin local avec le siège social dès qu'il existe de connectivité.                                                      | Le détaillant peut synchroniser vers et depuis le système de magasin en cas de connectivité.                              |
| Un détaillant peut disposer d'une communication sécurisée entre le système de magasin local et le siège social.                                                                 | Le détaillant peut communiquer de manière sécurisée de et vers le système de magasin en cas de connectivité.                     |
| Le responsable informatique et Microsoft Operations peuvent surveiller et créer des états sur le système de magasin local (diagnostics et modifications d'état).                   | Le responsable informatique et Microsoft Operations peuvent contrôler le système de magasin en toute sécurité et résoudre les problèmes efficacement. |

### <a name="universal-windows-platform-app-for-retail-modern-pos"></a>Application Universal Windows Platform pour Retail Modern POS

Actuellement, Retail Modern POS est disponible uniquement en tant qu'application Windows 8.1 pour les ordinateurs de bureau et les tablettes, et en tant que PDV Cloud pour les navigateurs d'ordinateur de bureau ou de tablettes. Dans cette version, Retail Moderns POS est converti en application Universal Windows Platform (UWP). Cette modification permettra à Retail Modern POS de s'exécuter sur tous les appareils Windows 10 (ordinateur de bureau, tablette, ou téléphone) et même passer entre les vues pour les appareils sur lesquels Continuum est activé.

| Ce que vous pouvez faire                                                   | Pourquoi c'est important                                                                                     |
|-------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Activez la fonctionnalité de PDV importante pour les petits appareils. | La fonctionnalité Retail POS est disponible pour les téléphones et autres petits appareils qui exécutent Windows 10. |

## <a name="supply-chain-management"></a>Gestion de la chaîne d'approvisionnement.
### <a name="consignment-inventory"></a>Stock de consignation

| Ce que vous pouvez faire                                                                                                                                                                | Pourquoi c'est important                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| En tant que fournisseur, vous pouvez stocker des matières premières à l'entrepôt du client. En tant que client, vous pouvez ajourner l'achat réel jusqu'à ce que les matières premières soient requises pour la production. | La conservation d'un stock de matières premières peut inclure des coûts élevés. Le stock de consignation permet à un fournisseur de stocker des matières premières à l'entrepôt du client. Le client peut ensuite ajourner l'achat réel jusqu'à ce que les matières premières soient requises pour la production. Les matières premières sont commandées et reçues via une commande de réapprovisionnement de consignation. Cette commande de réapprovisionnement enregistre les transactions physiques mais n'affecte pas la comptabilité. Pour distinguer les articles en stock appartenant au client et les articles en stock appartenant au fournisseur, vous pouvez utiliser la dimension de stock du propriétaire. Le changement de propriété du stock est effectué par un processus de journal qui gère le changement de propriété pour les matières premières entre le stock appartenant au fournisseur et le stock appartenant au client. Ce processus déclenche la création d'une commande fournisseur et d'un accusé de réception de marchandises. **Remarque :** cette fonction est limitée à la consignation entrante des matières premières pour la production. Elle n'est pas intégrée à la gestion des entrepôts (WHS) et à la gestion du transport (TMS). |
| En tant que fournisseur, obtenez les informations sur la quantité de stock consigné transférée au client.                                                                      | Pour facturer un client, le fournisseur requiert des informations sur les matières premières achetées dans le stock de consignation et la date de l'achat. Le fournisseur peut également contrôler le stock disponible sur le site du client à l'aide de l'interface de collaboration du fournisseur.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Déplacez le stock appartenant au fournisseur à l'aide d'un journal de transfert.                                                                                                                       | Pour effectuer le suivi de l'emplacement physique du stock appartenant au fournisseur, vous devez pouvoir enregistrer l'emplacement dans le système. Grâce à l'utilisation d'un journal de transfert, vous pouvez enregistrer les mouvements physiques du stock, tels que le mouvement d'un emplacement dans un entrepôt à un autre emplacement dans cet entrepôt.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Ajustez le stock appartenant au fournisseur à l'aide d'un journal d'inventaire.                                                                                                                     | Il est important que vous conserviez le stock disponible dans le système synchronisé sur le stock physique réel. Le stock appartenant au fournisseur peut être ajusté en entrée et en sortie à l'aide des processus d'inventaire, tels que les processus d'ajustement de quantité et de journal d'inventaire.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| En savoir plus sur la prise en charge de la consignation dans Dynamics 365 for Operations                                                                                                         | Pour plus d'informations sur la prise en charge des processus de consignation, consultez [Consignation](/dynamics365/unified-operations/supply-chain/inventory/consignment), [Paramétrage de la consignation](/dynamics365/unified-operations/supply-chain/inventory/set-up-consignment), [Créer une commande de réapprovisionnement de consignation (guide de tâche)](/dynamics365/unified-operations/supply-chain/inventory/tasks/create-consignment-replenishment-order), et [Modifier la propriété du stock de consignation en fonction de la demande de production (guide de tâche)](/dynamics365/unified-operations/supply-chain/inventory/tasks/change-ownership-consignment).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

### <a name="vendor-collaboration-previously-known-as-the-vendor-portal"></a>Collaboration du fournisseur (précédemment appelé le portail fournisseur)

| Ce que vous pouvez faire                                                                      | Pourquoi c'est important                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Autorisez les fournisseurs à répondre à chaque ligne de commande fournisseur et à suggérer des modifications.           | Dans certains cas, les fournisseurs souhaitent accepter certaines lignes de commande fournisseur mais en refuser d'autres. Les fournisseurs peuvent désormais gérer individuellement les lignes de commande fournisseur. Chaque ligne peut être refusée, acceptée, ou acceptée avec des modifications. Par exemple, les fournisseurs peuvent modifier la date de livraison, fractionner la livraison et la quantité, ou suggérer un article de remplacement.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Permettez aux fournisseurs de gérer les informations de contact.                                 | Les fournisseurs peuvent tenir à jour des informations de contact de leur société. Ces informations incluent les noms, les adresses e-mail, et les numéros de téléphone. L'accès à cette fonctionnalité est accordé via un rôle de sécurité dédié.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Partagez des documents associés aux commandes fournisseur avec des fournisseurs.                    | Si vous devez en partager un document avec un fournisseur, tel qu'un document sur les besoins, il est utile de lier le document à la commande fournisseur concernée. Le fournisseur peut ensuite partager des notes et des pièces jointes avec le client en liant le document à sa réponse à la commande fournisseur. La gestion des documents est la structure de prise en charge sous-jacente, et seules des notes et des documents joints classifiés comme « externes » peut être partagés avec des fournisseurs.                                                                                                                                                                                                                                                                                                                              |
| Mettez en service de nouveaux utilisateurs fournisseur.                                                          | Si vos fournisseurs utilisent l'interface de collaboration fournisseur, ils disposent d'une façon transparente de demander de nouveaux comptes utilisateur lorsque de nouveaux contacts nécessitent l'accès à la collaboration fournisseur. Les professionnels de l'approvisionnement peuvent soumettre une demande de compte d'utilisateur pour un contact dans l'organisation du fournisseur. Un contact fournisseur qui est déjà un utilisateur de collaboration fournisseur peut également envoyer ce type de demande. Cette demande crée un utilisateur dans Dynamics 365 for Operations ayant des rôles de sécurité spécifiques au fournisseur. Elle permet également de faire une demande au portail Microsoft Azure B2B pour mettre l'utilisateur en service avec un nouveau compte d'utilisateur Azure Active Directory (Azure AD). Les fournisseurs peuvent également demander que des comptes d'utilisateur fournisseur spécifiques soient désactivés, ou que des rôles de sécurité soient modifiés. |
| En savoir plus sur la prise en charge de la collaboration fournisseur dans Dynamics 365 for Operations. | Pour plus d'informations sur la collaboration fournisseur, consultez [Collaboration fournisseur avec des fournisseurs externes](/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors), [Collaboration fournisseur avec des clients](/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations), [Gestion des utilisateurs de la collaboration fournisseur](/dynamics365/unified-operations/supply-chain/procurement/manage-vendor-collaboration-users), [Paramétrage et mise à jour de la collaboration fournisseur](/dynamics365/unified-operations/supply-chain/procurement/set-up-maintain-vendor-collaboration), et [Espace de travail de facturation de collaboration fournisseur](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace).                                                         |

### <a name="intercompany-order-processing"></a>Traitement des commandes intersociétés

<table>




<thead>
<tr class="header">
<th>Ce que vous pouvez faire</th>
<th>Pourquoi c'est important</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Définissez, directement sur les lignes de commande client, d'où la demande doit provenir, et comment elle doit être approvisionnée. <strong>Exemple</strong> Créez une ligne de commande client, puis spécifiez la livraison directe comme type de livraison. Le fournisseur principal est ajouté à la ligne de commande client en tant que point d'approvisionnement.</td>
<td>Le flux pour prise de commande a été amélioré de manière considérable. Vous pouvez désormais définir, directement sur les lignes de commande client, d'où la demande doit provenir, et comment elle doit être approvisionnée. Vous n'avez plus besoin d'attendre que toutes les lignes aient été ajoutées à la commande client. Les nouvelles options de lignes de commande client vous permettent de spécifier le type de livraison lorsque vous spécifiez un fournisseur. Lorsque vous associez un fournisseur à des lignes de commande client, des chaînes de commande sont créées pour la livraison du fournisseur.
<ul>
<li>Le fournisseur peut être un fournisseur intersociétés qui utilise une commande fournisseur et une commande client internes, où il peut être un fournisseur externe qui utilise une commande fournisseur externe.</li>
<li>Le type de livraison peut être <strong>Livraison directe</strong> ou <strong>Stock</strong>. Le type de livraison <strong>Stock</strong> indique que le fournisseur doit fournir au stock local avant d'effectuer l'expédition au client.</li>
</ul></td>
</tr>
<tr class="even">
<td>Créez une promesse de commande directement dans les lignes de commande client. <strong>Exemple</strong> Créez une ligne de commande client qui provient d'un fournisseur intersociétés. Quittez la ligne. Les dates de livraison sont calculées en fonction de la disponibilité de la société d'approvisionnement.</td>
<td>Lorsque vous créez des lignes de commande client qui utilisent les nouvelles informations d'approvisionnement, les dates de livraison sont calculées selon le contrôle <strong>Date de livraison</strong>. Par exemple, si un fournisseur intersociétés est sélectionné, la disponibilité dans la société d'approvisionnement est calculée. Ainsi, les chaînes de commande sont créées automatiquement avec les lignes de commande client. Cette fonctionnalité permet de garantir que les dates de livraison deviennent visibles dans la société d'approvisionnement, de sorte que les profils disponibles à la vente puissent gérer les demandes anticipées directement à mesure que des commandes client sont créées.</td>
</tr>
<tr class="odd">
<td>Vérifiez la disponibilité du produit à tous les emplacements d'approvisionnement, puis sélectionnez la meilleure option d'approvisionnement.</td>
<td>La page <strong>Autres modes de livraison</strong> a été remodelée, et fournit à présent des informations précieuses sur tous les fournisseurs internes et externes approuvés. Ces informations incluent les options d'approvisionnement pour l'approvisionnement du fournisseur. Lorsque vous sélectionnez un mode de livraison, le système calcule les dates de livraison faisables. Vous pouvez de façon transparente sélectionner la meilleure option pour le client et appliquer cette option à chaque ligne de commande client.</td>
</tr>
</tbody>
</table>

### <a name="warehouse-enhancements-for-high-volume-distribution-centers"></a>Optimisations de l'entrepôt pour les centres de distribution à fort débit

| Ce que vous pouvez faire                                                              | Pourquoi c'est important                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Créez un travail après que les marchandises ont été conditionnées à une station de conditionnement.               | Cette fonction est utile lorsqu'il existe des processus supplémentaires après le travail de conditionnement manuel (comme la palettisation, le contrôle de la qualité, la consolidation des expéditions, ou les modifications apportées aux embarcadères). Le nouveau type de travail **Prélèvement du conteneur compressé** vous permet de modéliser ces tâches à l'aide de lignes de travail distinctes. Vous pouvez désormais modéliser les stations de conditionnement pour générer le travail après le conditionnement. Ce travail peut permettre de planifier le mouvement de stock conditionné.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Regroupez les conteneurs à la station de conditionnement.                                     | Cette fonctionnalité permet à plusieurs colis d'être regroupés en un conteneur ou contenant à la station de conditionnement. Par exemple, un opérateur de commerce électronique/gros peut regrouper 100 colis conditionnés individuellement en un seul conteneur (tel qu'une palette ou une cage). Ce conteneur peut être ensuite déplacé, présenté, ou puis chargé via une seule instruction de travail qu'un collaborateur génère en analysant un seul code-barres (contenant) pour le conteneur groupé. Cette fonction permet de réduire les transactions de travail pour déplacer de nombreux conteneurs emballés plus petits. Pour plus d'informations, voir [Créer une option de menu d'appareil mobile pour la consolidation de contenants (guide de tâche)](/dynamics365/unified-operations/supply-chain/warehousing/tasks/create-mobile-device-license-plate-consolidation).                                                                                                                                                                                                                                                                                                                                                                                            |
| Créez une stratégie de lancement pour les conteneurs emballés.                               | Le travail déclenché par le lancement de conteneur peut être créé automatiquement ou manuellement. Lorsqu'il est automatique, le travail est généré à la fermeture du conteneur à l'aide de l'instruction d'emplacement et du cadre de modèle de travail. Lorsque le lancement est manuel, l'emballeur peut décider si le travail doit être généré pour un seul conteneur ou pour un groupe de conteneurs. Cette fonction permet de réduire le risque que des conteneurs clôturés soient prélevés et déplacés avant qu'ils soient prêts à être déplacés de la station de conditionnement. Elle permet également le lancement groupé piloté par le système.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Réaffectation pour les prélèvements partiels                                                   | Du support a été ajouté aux processus de prélèvements partiels, pour aider un associé ne pouvant pas prélever les marchandises et souhaitant honorer la commande lorsque l'article requis sera disponible à un autre emplacement. Vous pouvez utiliser un processus de réaffectation automatique, qui utilise les mêmes instructions d'emplacement pour récupérer les marchandises si elles sont disponibles dans un autre emplacement. Sinon, lorsque la réaffectation manuelle est utilisée, l'appareil mobile affiche une liste des emplacements avec la quantité disponible. Le collaborateur de l'entrepôt peut ensuite sélectionner l'emplacement duquel utiliser le stock. Ces deux méthodes peuvent être définies individuellement ou combinées en une commande unique dans le menu de collaborateur d'entrepôt. Lorsque la réaffectation manuelle est utilisée, le collaborateur de l'entrepôt peut prélever la quantité d'article faisant l'objet d'un prélèvement partiel à plusieurs emplacements. Pour plus d'informations, voir [Paramétrer la réaffectation des articles pour les prélèvements partiels (guide de tâche)](/dynamics365/unified-operations/supply-chain/warehousing/tasks/set-up-short-picking-item-reallocation).                                                                                                                                                                                          |
| Déplacez du stock auquel du travail est associé.                             | Vous pouvez déplacer du stock auquel du travail est associé. Cette fonction peut être utile si, par exemple, un collaborateur souhaite désactiver de l'espace de quai d'embarquement et déplacer des palettes enregistrées en attente d'être rangées à un autre emplacement entrant. Le quai d'embarquement est dégagé et peut recevoir une charge supplémentaire de marchandises, et le stock déplacé est mis à jour avec les nouvelles informations de rangement. Cette fonction permet également de libérer de l'espace aux emplacements de prélèvement en déplaçant du stock auquel du travail est associé et en créant de l'espace pour le réapprovisionnement. Vous pouvez également l'utiliser pour déplacer des charges d'un emplacement intermédiaire à un autre sans perdre le travail de chargement qui a été généré. De cette manière, la fonction peut aider à optimiser le temps nécessaire pour charger les camions lorsqu'ils arrivent. Vous pouvez déplacer le stock qui a été réservé pour les commandes client, les sorties ordre de transfert, les réceptions d'ordre de transfert, et les commandes fournisseur. Le déplacement est impossible s'il doit entraîner le fractionnement des lignes. Par exemple, si vous avez une ligne de travail pour 100 articles, vous ne pouvez pas déplacer que 30 articles vers un autre emplacement. |
| Fusionnez les contenants auxquels du travail est associé.                    | Vous pouvez fusionner les contenants auxquels du travail sortant est associé. Par exemple, lorsqu'un prélèvement a été fractionné en plusieurs segments de travail, il peut être utile d'autoriser le fusionnement des contenants après leur livraison à l'emplacement intermédiaire. Les contenants peuvent être regroupés uniquement si ils sont au même emplacement, font partie de la même charge, et ont les mêmes informations d'expédition.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Libérez le travail de prélèvement associé au réapprovisionnement au niveau de la ligne. | Vous pouvez désormais libérer le travail au niveau de la ligne plutôt qu'au niveau de l'en-tête, de sorte que les collaborateurs puissent remplir les lignes de prélèvement qui ne sont pas libérées par le réapprovisionnement de la demande. Par conséquent, un grossiste qui a des commandes client importantes, ou un détaillant ayant des commandes client ou ordres de transfert de réapprovisionnement importants, peut autoriser que le travail de prélèvement commence sur toutes les lignes qui ne sont pas soumises au travail de réapprovisionnement. Le travail de prélèvement et de réapprovisionnement peut ensuite être terminé en parallèle. Cette fonction peut être configurée de manière à ce que vous puissiez choisir de libérer au niveau de l'en-tête ou au niveau de la ligne. Vous pouvez également utiliser les deux méthodes et créer un modèle de travail pour chaque méthode. La configuration de l'en-tête ou de la ligne est définie sur les modèles de travail, mais vous pouvez la modifier directement sur le travail généré.                                                                                                                                                                                                                                                                                                                                                                      |
| Annulez le travail à l'aide d'un appareil mobile.                                      | Vous pouvez désormais annuler le travail à l'aide d'un appareil mobile, avec ou sans le réapprovisionnement de demande. Précédemment, vous deviez utiliser le Rich Client. Pour activer cette fonctionnalité, créez une option du menu d'appareil mobile dont le mode est défini sur **Indirect** et le code d'activité défini sur **Annuler le travail**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="warehouse-operation-enhancements"></a>Améliorations des opérations d'entrepôt

| Ce que vous pouvez faire                    | Pourquoi c'est important                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modélisez différents types de conteneurs.   | Vous pouvez utiliser différents types de conteneurs dans l'entrepôt pour optimiser le stockage et pour d'autres motifs. La nouvelle entité de type de conteneur a les caractéristiques physiques des types de conteneurs. Vous pouvez désormais associer les contenants avec un type de conteneur spécifique et utiliser les limites de stockage de l'emplacement. Par exemple, vous pouvez utiliser cette fonction pour contrôler le nombre de palettes (ou d'autres types de conteneurs) que vous autorisez à un emplacement spécifique. Les types de conteneurs ont également été ajoutés aux groupes de séquences d'unités pour ajouter les types de conteneur par défaut pour le processus de réception. Les types de conteneurs peuvent être utilisés avec les instructions d'emplacement entrant et sortant. Ils peuvent également être utilisés dans la vue de stock disponible pour vous aider à déterminer le nombre de types de conteneurs actuellement stockés disponibles. Pour plus d'informations, voir la publication de blog [Utilisation de plaques d'immatriculation associées à un type de conteneur pour piloter les processus de gestion en entrepôt](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/20/use-of-license-plates-associated-with-a-container-type-to-drive-warehouse-management-processes/). Bien que ce cette publication de blog décrive une mise à jour vers Microsoft Dynamics AX 2012, la même prise en charge est désormais ajoutée à Dynamics 365 for Operations.                                                                                                                                                                                                                                                                                                                         |
| Contrepassez des expéditions.                 | Dans un entrepôt, vous devez pouvoir gérer les modifications de dernière minute. Par exemple, certaines marchandises peuvent être endommagées, de sorte que vous ne puissiez pas les expédier. Sinon, un client peut faire une demande tardive pour annuler ou modifier une commande. Dynamics 365 for Operations vous permet désormais de contrepasser une expédition. Par conséquent, vous pouvez annuler un bon de livraison afin de le mettre à jour avec les quantités correctes ultérieurement. De même, dans le flux entrant, vous pouvez annuler des accusés de réception de marchandises afin qu'une version mise à jour puisse être créée.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Utilisez les palettes comportant différents types d'articles. | Vous pouvez désormais recevoir et enregistrer une palette « mixte ». Une palette mixte consiste en différents articles qui sont rassemblées sur une palette pour une ou plusieurs commandes ou lignes fournisseur. Tous les enregistrements peuvent être résumés en un contenant cible. Ce processus est activé par l'appareil mobile de l'entrepôt. Par exemple, lorsque la palette d'articles de différents types arrive à l'entrepôt, le commis de réception identifie les articles et les quantités sur la palette avant que la palette soit déplacée à des emplacements de rangement dédiés. Les emplacements de rangement sont identifiés par les modèles de travail et les instructions d'emplacement. Si les emplacements de rangement sont répartis sur plusieurs articles ayant des emplacements fixes, cette fonction crée autant de lignes de travail qu'il existe d'articles distincts figurant sur la palette mixte. Cette fonction rend l'enregistrement et le rangement des palettes mixtes reçues d'articles plus rapides et plus flexibles. Pour plus d'informations, voir la publication de blog [Recevoir et enregistrer une palette avec les lignes du document source mixte à l’aide d'un contenant](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/13/receive-and-register-a-pallet-with-mixed-source-document-lines-using-1-license-plate-purchase-order-matching/) et les informations sur la prise en charge de palette mixte dans l'[annonce de notre mise à jour cumulative récente](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/30/whats-new-in-cu11-for-wms-and-tms/). Bien que ce cette publication de blog décrive une mise à jour vers AX 2012, la même prise en charge est désormais ajoutée à Dynamics 365 for Operations. |

### <a name="minor-feature-enhancements-in-supply-chain-management"></a>Améliorations mineures de fonction dans la gestion de la chaîne d'approvisionnement

<table>




<thead>
<tr class="header">
<th>Ce que vous pouvez faire</th>
<th>Pourquoi c'est important</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utilisez les nouvelles entités de données pour importer et exporter des données.</td>
<td>Vous pouvez importer et exporter des données à l'aide de ces entités de données :
<ul>
<li>Facture de transport</li>
<li>Agréger disponible par entrepôt et par statut de stock</li>
<li>Frais de stock</li>
<li>Devis</li>
</ul></td>
</tr>
<tr class="even">
<td>Utilisez le contrôle de Gantt amélioré pour développer des scénarios de planification interactifs.</td>
<td>Le contrôle de Gantt amélioré vous permet de développer de nouveaux scénarios de planification interactifs et de fournir des API améliorées permettant de personnaliser l'apparence des activités. Voici certaines des nouvelles API :
<ul>
<li>Glisser-déplacer vertical des activités</li>
<li>Ajout/suppression d'activités</li>
<li>Aperçu des périodes réservées dans la barre récapitulative</li>
<li>Modification de la couleur et du style des bordures d'activité</li>
<li>Modification de la couleur, du style et de l'arrière-plan du texte dans une grille</li>
</ul></td>
</tr>
<tr class="odd">
<td>Mieux gérer la planification du matériel et des ressources.</td>
<td>Certains améliorations ont été effectuées à la planification du matériel et des ressources :
<ul>
<li>La marge de sortie est maintenant gérée lorsqu'un article est disponible.</li>
<li>Remplacez la date de livraison lorsque vous disposez d'ordres prévisionnels confirmés.</li>
<li>Priorisez la réalisation des commandes sur le stock de sécurité.</li>
<li>Empêchez la planification d'ordres prévisionnels par le passé.</li>
</ul></td>
</tr>
<tr class="even">
<td>Déclarez la consommation réelle de la production, et affichez le statut du stock.</td>
<td>Vous pouvez afficher la consommation réelle de la production. En outre, une nouvelle case à cocher <strong>Afficher le statut du stock</strong> qui a été ajoutée au <strong>Mouvement</strong> sur l'option de menu <strong>Création de travail</strong> vous permet d'afficher le statut du stock.</td>
</tr>
<tr class="odd">
<td>Calculez le poids volumétrique, si les taux de votre transporteur sont basés sur le poids volumétrique.</td>
<td>Un nouveau moteur de taux de TMS basé sur le poids volumétrique a été ajouté, vous permettant de calculer le poids volumétrique.</td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Voir également :
--------

[Nouveautés ou changements](whats-new-changed.md)




