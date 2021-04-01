---
title: Journaux d’opérations diverses
description: Cette rubrique décrit les fonctionnalités de Microsoft Dynamics 365 Finance qui vous permettent d’effectuer le traitement du journal des opérations diverses, ainsi que de garantir que les données correctes sont capturées et que le contrôle interne n’est pas compromis.
author: ShylaThompson
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f9f19f0714fc160792a29261e21fe4ec8d62c4b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249237"
---
# <a name="general-journal-processing"></a>Journaux d’opérations diverses

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui vous permettent d’effectuer le traitement du journal des opérations diverses, ainsi que de garantir que les données correctes sont capturées et que le contrôle interne n’est pas compromis.  

## <a name="journal-names"></a>Noms de journal

Les noms des journaux font partie des zones les plus importantes à paramétrer. Il est judicieux de définir des noms de journaux spécifiques pour chaque objectif (intersociétés, régularisation et correction d’erreurs, par exemple). Vous pouvez modifier chaque nom de journal pour faciliter et sécuriser la saisie de données pour chaque objectif. 

Vous pouvez paramétrer les éléments suivants sur la page **Noms des journaux** :

-   **Approbation du workflow** : Pour augmenter le contrôle interne, définissez les workflows de journal qui établissent des seuils d’importance pour les étapes d’approbation et de révision, selon des critères tels que le montant débiteur total. Vous devez paramétrer les workflows pour les journaux des opérations diverses dans la page **Workflows de comptabilité**.
-   **Valeurs par défaut** : Sélectionnez les valeurs par défaut pour les comptes de contrepartie, la devise et les dimensions financières.
-   **Contrôle des journaux** : Vous pouvez paramétrer des restrictions au niveau de la société et du type de compte, ainsi que les valeurs de segment. 

**Exemples**

Un nom de journal peut être utilisé uniquement pour les ajustements. Dans ce cas, vous pouvez spécifier que seul le type de compte **Comptabilité** est valide dans toutes les sociétés. 

[![Types de comptes du contrôle des journaux](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Un nom de journal peut être uniquement utilisé pour un segment spécifique ou pour une plage pour des comptes principaux. 

[![Segment de contrôle des journaux](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

L’option **Contrepassation automatique** est disponible dans les journaux des opérations diverses. Par exemple, vous avez un ajustement de régularisation dans lequel le document actif n’a pas encore été traité, comme le montre l’illustration suivante.
[![Contrepassation du journal des opérations diverses](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

Le complément Microsoft Excel pour l’entrée de journal fournit un niveau supplémentaire d’automatisation et facilite la saisie des données. L’action **Ouvrir les lignes dans Excel** est disponible dans les pages **Journal des opérations diverses** et **N° document de journal**. 

Dans la page **Journaux périodiques**, vous pouvez paramétrer les journaux récurrents pour automatiser le traitement de journal. 

Vous pouvez utiliser les modèles de justificatif à tout moment. Dans la page **Journaux des opérations diverses**, les actions **Enregistrer** et **Sélectionner le modèle de n° document** se trouvent dans la page **N° document de journal**, sous **Fonctions** pour les lignes de justificatif.

## <a name="related-setup"></a>Paramétrage associé
Le paramétrage suivant n’est pas spécifique aux journaux des opérations diverses, mais il aide à garantir que la saisie de données est correcte et facile.

### <a name="main-account"></a>Compte principal

Le paramétrage de compte principal fournit de nombreuses options pour le traitement du journal des opérations diverses :

-   **Obligation de DB/CR** : Utilisez cette option si un compte principal est limité à des transactions de débit ou de crédit. Le paramétrage est vérifié lors du contrôle ou de la validation du journal.

-   **Compte de contrepartie par défaut**
-   **Suspendu** : Permet d’interrompre un compte principal pour la saisie de données dans toutes les sociétés ou pour une société/entité juridique spécifique.
-   **Ne pas autoriser la saisie manuelle** : Permet d’empêcher les utilisateurs d’entrer manuellement une valeur pour le compte dans les journaux.
-   **Valeur par défaut/Contrôler la devise**
-   **Remplacements des entités juridiques** : Ce paramétrage est spécifique à la société/à l’entité juridique définie :
    -   **Valeur par défaut/Valider une taxe**
    -   **Dimension par défaut** : **Non fixe** ou **Valeur fixe**. **Valeur fixe** : Aide à garantir que toutes les validations pour ce compte principal utilisent toujours une valeur de dimension paramétrée comme **Fixe**.
-   **Contrôle de validation**
    -   **Contrôle utilisateur** : Cette option contrôle les utilisateurs qui sont autorisés à valider dans un compte principal.
    -   **Contrôle des types de validation** : Cette option contrôle les types de validations qui sont autorisés pour un compte principal.

### <a name="accounting-structures-and-advanced-rules-structures"></a>Structures de compte et structures de règles avancées

Les structures de compte et les structures de règles avancées sont extrêmement importantes pour garantir que les données requises pour la génération d’états financiers et le suivi de performance sont capturées lors du traitement du journal des opérations diverses et de toute documentation. Les structures de compte et les structures de règles avancées vous permettent d’adapter l’expérience de saisie de données. Vous pouvez autoriser la saisie de données uniquement pour les dimensions financières pertinentes dans chaque cas, et également veiller à ce que les données requises et correctes soient toujours capturées.

Pour plus d’informations, voir les rubriques suivantes :
- [Plan de comptes](plan-chart-of-accounts.md) 
- [Créer des règles avancées pour les journaux](tasks/create-advanced-rules-journals.md)
- [Créer une entrée de journal à l’aide d’un modèle](tasks/create-journal-entry-template.md)
- [Créer et valider des journaux](tasks/create-validate-journals.md)
- [Valider des journaux périodiques](tasks/post-periodic-journals.md)
- [Traiter le journal de répartition comptable](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a>Simuler la validation
La fonction **Simuler la validation** est disponible dans le menu **Valider** pour la plupart des journaux. Lorsque vous validez un journal à l’aide de la fonction **Valider**, le système teste le journal pour rechercher des conditions d’erreur spécifiques. Si vous utilisez la fonction **Simuler la validation**, le système exécute les mêmes processus que ceux exécutés pendant la validation sans valider réellement le journal. Vous pouvez ensuite consulter les messages de validation affichés, corriger les erreurs trouvées, puis ouvrir le menu **Valider** pour valider le journal. 

La fonction **Simuler la validation** n’est pas disponible pour le traitement par lots. Toutefois, un code est disponible pour simuler la validation par lots et les développeurs peuvent étendre le code pour ajouter cette fonctionnalité.  

## <a name="journal-unlock"></a>Déverrouillage du journal
Un bouton est disponible sur la page du journal pour déverrouiller un journal dont le statut « Verrouillé par le système » est défini sur Oui. Ce déverrouillage peut être effectué par un administrateur système qui a analysé l’exécution des traitements par lots et confirmé que ce journal n’est plus activement traité par un traitement par lots. Ce bouton est activé par la fonction nommée **Bouton Déverrouillage du journal** sur la page **Gestion des fonctions**. 

## <a name="workflow-recall"></a>Rappel du flux de travail 
La capacité de rappeler un journal dans workflow dont le statut « Irrécupérable » est activé à l’aide du bouton **Workflow** dans un journal, puis sur la page **Historique du workflow**. Cela est activé par la fonction nommée **Réinitialiser le statut de workflow pour les journaux** sur la page **Gestion des fonctions**.

## <a name="delete-journal-lines"></a>Supprimer des lignes du journal
La possibilité de supprimer rapidement toutes les lignes du journal est activée dans un journal sous **Fonctions** > **Supprimer des lignes du journal**. Pour activer cette fonction, dans **Gestion des fonctions**, sélectionnez **Supprimer les optimisations des performances du journal**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]