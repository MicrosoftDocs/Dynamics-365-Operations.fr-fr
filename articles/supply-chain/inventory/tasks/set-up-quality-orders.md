---
title: Paramétrer les ordres de qualité
description: Cette procédure décrit comment activer un processus de gestion de la qualité dans lequel le stock entrant doit être inspecté immédiatement après l'enregistrement des arrivées.
author: perlynne
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, InventTestTable, DefaultDashboard, InventTestVariable, InventTestVariableOutcome, InventItemSampling, InventTestQualityGroup, InventTestItemQualityGroupAdd, SysQueryForm, InventTestItemQualityGroup, InventTestGroup, InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 875d79e33fbd1d3d811d93dea98fa9d490716744
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011470"
---
# <a name="set-up-quality-orders"></a>Paramétrer les ordres de qualité

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment activer un processus de gestion de la qualité dans lequel le stock entrant doit être inspecté immédiatement après l'enregistrement des arrivées. La procédure est généralement effectuée par un responsable de la qualité. Le processus inclut la création d'un groupe de qualité, pour définir les articles qui vont être échantillonnés, et un groupe de test pour regrouper les tests à exécuter sur des articles dans le groupe de qualité. Vous pouvez exécuter ce guide dans les données de démonstration de la société fictive USMF.


## <a name="enable-quality-management"></a>Activer la gestion de la qualité
1. Allez dans **Volet de navigation > Modules > Gestion des stocks > Configuration > Paramètres de gestion des stocks et des entrepôts**.
2. Cliquez sur l'onglet **Gestion de la qualité**.
3. Définissez l'option **Utiliser la gestion de la qualité** sur « Oui ».
4. Cliquez sur **Paramétrage d'état**. Dans USMF, le paramétrage d'état pour la gestion de la qualité est déjà défini. Si ce n'est pas le cas, vous devez ajouter de nouvelles lignes ici pour les différents types d'état, et sélectionner le type de document à utiliser pour chaque état.  
5. Fermez la page.
6. Fermez la page.

## <a name="create-a-test"></a>Créer un test
1. Allez dans **Gestion des stocks > Configuration > Contrôle de la qualité > Tests**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Test**.
4. Tapez une valeur dans le champ **Description**.
5. Sélectionnez « Option » dans le champ **Type**. Dans cet exemple, nous allons sélectionner « Option » afin d'affecter les résultats du test selon les valeurs prédéfinies.  
6. Cliquez sur **Enregistrer**.
7. Fermez la page.

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a>Créer des variables de test pour définir la manière dont les résultats de test sont enregistrés
1. Allez dans **Gestion des stocks > Configuration > Contrôle de la qualité > Variables de test**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Variable**.
4. Tapez une valeur dans le champ **Description**.
5. Cliquez sur **Enregistrer**.
6. Cliquez sur **Résultats**.
7. Cliquez sur **Nouveau**.
8. Tapez une valeur dans le champ **Résultat**.
9. Tapez une valeur dans le champ **Description**.
10. Sélectionnez « Réussite » dans le champ **Statut du résultat**.
11. Cliquez sur **Enregistrer**.
12. Cliquez sur **Nouveau**.
13. Tapez une valeur dans le champ **Résultat**.
14. Tapez une valeur dans le champ **Description**.
15. Cliquez sur **Enregistrer**.
16. Fermez la page.
17. Fermez la page.

## <a name="set-up-item-sampling"></a>Paramétrer l'échantillonnage d'article
1. Allez dans **Gestion des stocks > Configuration > Contrôle de la qualité > Échantillonnage d'article**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Échantillonnage d'article**.
4. Tapez une valeur dans le champ **Description**.
5. Entrez un nombre dans le champ **Valeur**. Cette valeur fait référence à la spécification de quantité sélectionnée dans le champ adjacent.  
6. Développez ou réduisez la section **Processus**.
7. Activez ou désactivez la case à cocher **Blocage total**. Si vous sélectionnez cette option, le lot entier ou la quantité de la ligne de commande est bloqué si un test échoue. Si vous ne la sélectionnez pas, seuls les articles de l'ordre de qualité sont bloqués.  
8. Cliquez sur **Enregistrer**.
9. Fermez la page.

> [!NOTE]
> La fonctionnalité *Gestion de la qualité pour les processus d'entrepôt* fournit des capacités d'échantillonnage d'articles supplémentaires. Elle ajoute un concept de *portée d'échantillonnage de l'article* et la possibilité de définir un contenant complet comme spécification de quantité. Si vous avez activé cette fonctionnalité, consultez [Gestion de la qualité pour les processus d'entrepôt](../quality-management-for-warehouses-processes.md) pour plus de détails.

## <a name="create-a-quality-group"></a>Créer un groupe de qualité
1. Allez dans **Gestion des stocks > Configuration > Contrôle de la qualité > Groupes de qualité**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Groupe de qualité**. Utilisez un nom descriptif pour vous aider à identifier les types d'articles contenus dans le groupe (vos critères d'échantillonnage).  
4. Tapez une valeur dans le champ **Description**.
5. Cliquez sur **Enregistrer**.
6. Cliquez sur **Ajouter des articles**.
7. Sélectionnez la ligne **Numéro d'article**. Dans cet exemple le filtrage sera exécuté selon le numéro d'article.  
8. Tapez une valeur dans le champ **Critères**. Par exemple, tapez T* pour filtrer les numéros d'article commençant par un T.  
9. Cliquez sur **OK**.
10. Cliquez sur **OK**.
11. Cliquez sur **Groupes de qualité d'article**.
12. Fermez la page.
13. Fermez la page.

## <a name="create-a-test-group"></a>Création d'un groupe de test
1. Allez dans **Gestion des stocks > Configuration > Contrôle de la qualité > Groupes de test**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Groupe de test**. Donnez au **Groupe de tests** un nom qui vous aidera à vous souvenir des types de tests qui sont exécutés, et à quel groupe de qualité ils doivent être associés. Par exemple, s'il doit être utilisé avec un groupe de qualité qui sélectionne des articles en commençant par « T », vous pourriez l'appeler « Tests article-T ».  
4. Tapez une valeur dans le champ **Description**.
5. Dans le champ **Échantillonnage d'article**, sélectionnez la ligne d'échantillonnage d'article que vous avez créée avant.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Cliquez sur **Ajouter**.
8. Entrez un nombre dans le champ **Numéro de souche**.
9. Dans le champ **Test**, sélectionnez le test créé précédemment.
10. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
11. Cliquez sur l'onglet **Test**.
12. Dans le champ **Variable**, sélectionnez la variable de test créée précédemment.
13. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
14. Dans le champ **Résultat par défaut**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
16. Cliquez sur **Enregistrer**.
17. Fermez la page.

## <a name="define-when-quality-orders-will-be-created"></a>Définir à quel moment les ordres de qualité seront créés
1. Allez dans **Gestion des stocks > Configuration > Contrôle de la qualité > Associations de qualité**.
2. Cliquez sur **Nouveau**.
3. Sélectionnez une option dans le champ **Type de référence**.
4. Sélectionnez « Groupe » dans le champ **Code article**. Dans cet exemple, nous allons sélectionner « Groupe » et utiliser le groupe de qualité déjà créé avant. Vous pouvez également le définir sur « Tableau » pour spécifier les articles manuellement, ou sélectionner « Tous » pour ajouter tous les articles à l'ordre de qualité.  
5. Dans le champ **Article**, sélectionnez le groupe de qualité créé précédemment. Les options disponibles dans le champ Article dépendent de ce qui vous définissez dans le champ Article - valide pour.  
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Développez ou réduisez la section Processus.
8. Sélectionnez une option dans le champ **Type d'événement**. Il s'agit de l'événement qui déclenche le test. Les options disponibles ici dépendent du processus que vous avez sélectionné dans le champ Type de référence.  
9. Sélectionnez une option dans le champ **Exécution**.
10. Développez ou réduisez la section **Processus d'ordre de qualité**.
11. Dans le champ **Blocage d'événement**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. Ce champ affiche la liste des processus qu'il est possible de bloquer si l'ordre de qualité est toujours en cours. Les options dépendent de ce que vous avez sélectionné dans le champ Type d'événement.  
12. Dans la liste, cliquer sur le lien dans la ligne sélectionnée. Tout dépend des valeurs sélectionnées précédemment. Sélectionnez cette option si les processus suivants doivent être bloqués tandis que des ordres de qualité en cours sont liés à une ligne de document source.  
13. Développez ou réduisez la section **Spécifications**.
14. Dans le champ **Groupe de test**, sélectionnez le groupe de test créé précédemment.
15. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
16. Cliquez sur **Enregistrer**.
17. Fermez la page.

> [!NOTE]
> La fonctionnalité *Gestion de la qualité pour les processus d'entrepôt* fournit des options supplémentaires pour paramétrer les associations de qualité. Elle ajoute une nouvelle condition (**Type d'entrepôt applicable**) et un nouveau paramètre (**Stratégie de traitement de la qualité**). Si vous avez activé cette fonctionnalité, consultez [Gestion de la qualité pour les processus d'entrepôt](../quality-management-for-warehouses-processes.md) pour plus de détails.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]