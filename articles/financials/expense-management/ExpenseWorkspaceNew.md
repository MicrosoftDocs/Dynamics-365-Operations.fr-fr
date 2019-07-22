---
title: États de dépenses repensés
description: Cette rubrique fournit des informations sur l'expérience remodelée et repensée de saisie de l'état de dépenses dans Microsoft Dynamics 365 for Finance and Operations. La nouvelle expérience simplifie le processus de renseignement des états de dépenses et réduit le temps requis.
author: ryansandness
manager: AnnBe
ms.date: 06/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 9e87a61bd6dd7bc1c7ef569882daf2074c7cade9
ms.sourcegitcommit: 672c94704e9a2b0ec7ee3c111d4ceb1bb8597969
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2019
ms.locfileid: "1631953"
---
# <a name="expense-reports-reimagined"></a>États de dépenses repensés

[!include[banner](../includes/banner.md)]

L'entrée d'état de dépenses a été remodelée pour simplifier le processus de renseignement des états de dépenses et réduire le temps requis. Voici les composants principaux de la nouvelle expérience de dépenses :

- Un nouvel espace de travail de gestion des dépenses qui vous permet d'accéder aux dépenses de votre délégué.
- Une nouvelle expérience de mise en correspondance de la réception pour afficher les réceptions au niveau de l'en-tête et simplifier le processus d'association des réceptions aux lignes de dépenses.
- Une nouvelle grille en lecture seule qui vous permet d'afficher beaucoup plus de lignes de dépenses et de colonnes de données supplémentaires. Vous pouvez à présent voir toutes les lignes détaillées et fractionnées, ainsi que leurs dépenses parentes.
- Un volet simplifié pour modifier des dépenses.
- Des messages d'erreur, d'avertissement et de stratégie remodelés pour garantir que vous avez le contexte correct pour comprendre quel est le problème et comment le résoudre. Microsoft a supprimé de nombreux messages qui apparaissaient avant que les utilisateurs aient présenté une opportunité de remplir leurs tâches et de résoudre les problèmes, comme le message de détail incomplet.
- Une nouvelle page indiquant les champs requis par votre organisation, les champs facultatifs, et les champs qui ne doivent pas être capturés. Cette page permettra de réduire le nombre de champs que les utilisateurs doivent définir.
- Un nouvel aspect pour les états de dépenses, de sorte que les états ne s'affichent plus comme s'ils avaient été conçus pour le personnel comptable.

Pour activer la nouvelle expérience, utilisez l'espace de travail **Gestion de fonctionnalités** pour activer la fonctionnalité **États de dépenses repensés**. Lorsque vous activez cette fonctionnalité, les actions suivantes se produisent :

- L'espace de travail de dépenses existant est remplacé par le nouvel espace de travail.
- Une nouvelle option de menu pour la visibilité du champ de dépenses est ajoutée.
- Aucune option de menu existante pour les états de dépenses (la page existante) ou ni aucun champ de l'état de dépenses n'est supprimé.
- Les workflows et les approbations vous dirigent toujours vers la page d'états de dépenses existante.

## <a name="getting-started-video-for-new-users"></a>Vidéo de démarrage pour les nouveaux utilisateurs

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2Y7gO]

La vidéo [Expérience de dépenses dans Dynamics 365 for Finance and Operations](https://youtu.be/Ocy-MsTvEE0) (présentée ci-dessus) est incluse dans [liste de lecture Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.

## <a name="new-features"></a>Nouvelles fonctionnalités

| Nouvelle fonctionnalité | Description |
|---|----|
| Visibilité du champ des dépenses | Une nouvelle page de paramétrage vous permet de spécifier quels champs doivent être désactivés pour une organisation, quels champs doivent être obligatoires, et quels champs sont recommandés. |
| Champs obligatoires | Une nouvelle configuration simple vous permet de rendre certains champs obligatoires sans devoir utiliser la structure de stratégies. |
| Champs facultatifs | Une seconde page pour les champs facultatifs est ajoutée. Ainsi, les employés ne se sentiront pas comme si elles devaient définir des champs, mais les champs sont toujours facilement accessibles. |
| Ajouter des reçus non joints | La possibilité d'ajouter des reçus non joints à l'état des dépenses est plus visible de l'espace de travail et dans l'état des dépenses. |
| Messages améliorés | Une meilleure visibilité dans les lignes de dépenses présentant des avertissements ou des erreurs. |
| Réduction des messages dans la barre de messages| Le nombre de messages d'informations a été diminué, et un effort a été fait pour empêcher les messages en double de s'afficher dans de nombreux cas. |
| Actions courantes regroupées | L'interface a été nettoyée en ajoutant de nouveaux boutons d'action pour la plupart des actions au niveau de la ligne courante et l'ajout d'un bouton de points de suspension (...) pour l'en-tête et d'autres actions moins fréquentes. |
| Un nouvel espace de travail pour améliorer la visibilité | Un nouvel espace de travail unifie les fonctionnalités et les liens qui permettent aux utilisateurs se déplacer dans différentes zones. |
| Ajouter des dépenses et des reçus existants lors de la création de dépenses | Lorsque vous créez des états de dépenses, vous pouvez ajouter tous ou certains dépenses et reçus sélectionnés. |
| Calculatrice du taux de change | Une calculatrice de taux de change a été ajoutée pour vous permettre de calculer le taux de change pour les transactions multidevises décaissées. |
| Enregistrer et ajouter de nouvelles lignes de dépense | Des boutons **Enregistrer** et **Nouveau** sont disponibles lorsque de nouvelles dépenses sont entrées, pour vous aider à entrer rapidement des lignes de dépenses. |
| Une meilleure visibilité dans le fractionnement et le détail des lignes | Les lignes détaillées et fractionnées sont ajoutées directement à la liste des dépenses, pour augmenter la visibilité et pour vous aider à identifier facilement s'il existe des erreurs de stratégie ou autres. |
| Afficher les reçus dans les détails | Les reçus peuvent être affichés dans les détails. |

Le version d'origine est centrées sur des scénarios de saisie de dépenses. Chaque scénario de révision ou d'approbation d'état de dépenses continuera d'utiliser la page de saisie de dépenses existante.

Les fonctionnalités suivantes sont présentes sur la page existante mais ne sont pas encore présentes sur la nouvelle page. Ces fonctionnalités seront réintroduites dans les prochaines versions :

- Approbations
- Approbations de la Comptabilité fournisseur et possibilité de modifier la comptabilité
- Points d'entrée multiples
- Intégration de demande de déplacement
- Entité de données pour la visibilité du champ de dépenses
- Saisie des dépenses d'indemnité journalière
- Workflow au niveau de la ligne
- Support d'approbateur temporaire
- Énumération avancée
