---
title: Vue d’ensemble de la gestion de la qualité et de la non-conformité
description: Cette rubrique présente les fonctionnalités de gestion de la qualité et des non-conformités dans Microsoft Dynamics 365 Supply Chain Management et explique comment elles peuvent contribuer à améliorer la qualité des produits dans votre chaîne d’approvisionnement.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling, InventNonConformanceHistory, InventNonConformanceTable, InventQualityOrderLineResults, InventQualityOrderTable, InventTestCorrection, InventTestDiagnosticType, InventTestInstrument, InventTestReportSetup, InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "11574"
- intro-internal
ms.assetid: 5ac8a059-5cb4-4cb5-ba14-b944bd08dae9
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bb4bcb7f554c22b4e1ab1b41867bd2d3dcca4d4
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985507"
---
# <a name="quality-and-nonconformance-management-overview"></a>Vue d’ensemble de la gestion de la qualité et de la non-conformité

[!include [banner](../includes/banner.md)]

Cette rubrique présente les fonctionnalités de gestion de la qualité et des non-conformités dans Microsoft Dynamics 365 Supply Chain Management et explique comment elles peuvent contribuer à améliorer la qualité des produits dans votre chaîne d’approvisionnement.

L’assurance qualité implique le test des produits et la gestion des matières non conformes. La gestion de la qualité garantit un haut niveau de qualité des produits dans votre chaîne logistique. Ces processus permettent également d’optimiser les processus de la chaîne logistique et d’améliorer la satisfaction client. La gestion de la qualité peut vous aider à gérer les délais de rotation lors de la survenue de produits non conformes, indépendamment du point d’origine de ces produits. Vous pouvez lier les résultats du diagnostic aux tâches de correction. Le système peut programmer des tâches de corriger les problèmes et donc aider à empêcher la répétition de ces problèmes à l’avenir. La gestion de la qualité permet également de suivre les problèmes (notamment les problèmes internes) par type de problème, et vous permet d’identifier des solutions comme étant à court terme ou à long terme. Les statistiques concernant les indicateurs clés de performance (KPI) donnent des indications sur les problèmes de non-conformité qui sont survenus antérieurement et sur les solutions qui ont été appliquées pour les corriger. Vous pouvez utiliser les données historiques pour examiner l’efficacité des mesures de qualité prises antérieurement et déterminer les mesures appropriées à l’avenir.

La gestion de la qualité peut vous aider à gérer les délais de rotation lorsque vous traitez des produits non conformes, indépendamment de leur point d’origine. Étant donné que les types de diagnostics sont liés à la génération d’états de correction, Supply Chain Management peut programmer des tâches afin de corriger les problèmes et les empêcher de se reproduire.

Outre la fonctionnalité de gestion de la non-conformité, la gestion de la qualité inclut la fonctionnalité de suivi des problèmes par type de problème (même lorsqu’il s’agit de problèmes internes) et d’identification des solutions comme à court terme ou à long terme. Les statistiques concernant les indicateurs clés de performance (KPI) donnent des indications sur l’historique des problèmes de non-conformité antérieurs et sur les solutions qui ont été utilisées pour les corriger. Vous pouvez utiliser les données historiques pour examiner l’efficacité des mesures de qualité antérieures et déterminer les mesures appropriées à utiliser à l’avenir.

Lorsque vous paramétrez une association de qualité, Supply Chain Management peut générer des ordres de qualité pour différents processus d’entreprise, événements et conditions. L’association de qualité peut couvrir un article spécifique, un groupe d’articles spécifique, ou tous les articles.

## <a name="examples-of-the-use-of-quality-management"></a>Exemples de l’utilisation de la gestion de la qualité

La gestion de la qualité est flexible et peut être mise en œuvre de différentes manières afin de répondre aux exigences de niveaux spécifiques des opérations de chaîne d’approvisionnement. Les exemples suivants illustrent les utilisations possibles de ces fonctionnalités :

- Démarrer automatiquement un processus de contrôle qualité, basé sur des critères prédéfinis (par exemple, lors de l’enregistrement en entrepôt d’une commande fournisseur provenant d’un fournisseur spécifique).
- Bloquer le stock au cours de l’inspection pour empêcher l’utilisation d’un stock non-approuvé (blocage complet des quantités des commande fournisseur).
- Utiliser l’échantillonnage d’article dans le cadre d’une association de qualité pour définir la quantité de stock physique actuel qui doit être inspectée. L’échantillonnage peut être basé sur des quantités fixes, un pourcentage ou un contenant complet.
- Créez des ordres de qualité pour les réceptions partielles. Pour créer un ordre de qualité basé sur la quantité qui est reçue physiquement avec une commande, vous devez activer la case à cocher **Par quantité mise à jour** sur la page **Échantillonnage d’article**.
- Créer des types de test qui incluent les valeurs minimales, maximales, ainsi que les valeurs de test cibles, et réaliser des tests quantitatifs/qualitatifs ayant des résultats de contrôle prédéfinis.
- Spécifier un niveau de qualité acceptable pour contrôler les tolérances de la mesure de qualité.
- Spécifier les ressources qu’une opération d’inspection nécessite, telles qu’une zone de test et des instruments de test.

> [!NOTE]
> La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ étend les capacités de la gestion de la qualité. Si vous utilisez cette fonctionnalité, consultez [Gestion de la qualité pour les processus d’entrepôt](quality-management-for-warehouses-processes.md) pour des exemples de fonctionnement de la gestion de la qualité lorsqu’elle est activée.

## <a name="controlling-the-quality-management-process"></a>Contrôle du processus de gestion de la qualité

Voici quelques-unes des manières dont vous pouvez contrôler le processus de gestion de la qualité :

- Créer des ordres de qualité fondés sur des points de déclenchement tels qu’un « accusé de réception de marchandises » pour les opérations entrantes ou un « prélèvement de produit » pour les opérations sortantes.
- Documenter les résultats des tests et déterminer si les résultats répondent aux critères de test établis et aux niveaux de qualité acceptables.
- Utiliser la gestion des documents pour les spécifications détaillées des produits et les notes spécifiques à l’utilisateur dans le cadre de la génération d’états lors du processus d’inspection.
- Tenir à jour les produits non conformes et corréler ces produits avec des informations supplémentaires de non-conformité pour dépister la cause d’origine d’un problème.
- Documenter le coût de gestion d’une non-conformité. Ce coût peut inclure les articles (tels que les pièces de rechange), les frais divers, et les heures de travail nécessaires pour corriger la non-conformité.
- Programmer les processus de correction des erreurs à l’aide de la gestion des corrections qui est liée aux ordres de qualité.

[![Processus de gestion de la qualité.](media/quality-management-process-diagram.png)](media/quality-management-process-diagram.png)

## <a name="product-testing-and-quality-orders"></a>Test des produits et ordres de qualité

Le processus de test des produits est généralement désigné comme contrôle qualité et utilise des ordres de qualité. La fonctionnalité de contrôle qualité permet d’effectuer les opérations suivantes :

- Définir les tests qui doivent être exécutés pour les matières, Ces tests sont notamment les spécifications de la qualité, l’instrument de test applicable, les documents décrivant le test, un programme d’échantillonnage et les niveaux de qualité acceptables.
- Créer un ordre de qualité qui identifie les tests à exécuter pour une commande spécifique (commande client ou fournisseur) ou une quantité de stock spécifique. Créer manuellement un ordre de qualité ou en générer un automatiquement en fonction de directives qualité.
- Définir les directives qualité liées à des commandes fournisseur ou client, des ordres de fabrication ou des ordres de contrôle dans chaque processus métier, de sorte à générer automatiquement un ordre de qualité qui identifie les besoins de test pour les matières entrantes et sortantes.
- Enregistrer les résultats du test d’un ordre de qualité, les valider par rapport au niveau de qualité acceptable et imprimer un certificat d’analyse affichant les résultats du test.

## <a name="nonconformance"></a>Non-conformité

Une non-conformité décrit un article qui a un problème qualitatif. Le processus de non-conformité permet de créer un ordre de non-conformité qui décrit la quantité de matières non conformes en termes de source du problème, de type de problème et de notes explicatives. Vous pouvez définir une classification des types de problèmes afin de faciliter l’analyse des matières non conformes. Vous pouvez également imprimer une balise de non-conformité et un état de non-conformité pour guider la mise au rebut des matières non conformes. Par exemple, la balise et l’état peuvent indiquer un état **Inutilisable** ou **Utilisation limitée**.

Le tableau suivant répertorie les six types de non-conformité par défaut et décrit les informations qui doivent être enregistrées pour chaque type.

| Type de non-conformité | Informations sur la source |
|---|---|
| Client | Le numéro de compte client, le numéro de commande client ou un numéro de lot d’une transaction de commande client. Par exemple, la non-conformité peut être liée à l’expédition d’une commande client spécifique ou aux commentaires d’un client sur la qualité du produit. |
| Demande de service | Le numéro de compte client, le numéro de commande client ou un numéro de lot d’une transaction de commande client. Par exemple, la non-conformité peut être liée à l’expédition d’une commande client spécifique ou à la réclamation d’un client en relation avec la qualité de l’article. |
| Fournisseur | Le numéro de compte fournisseur, le numéro de commande fournisseur ou un numéro de lot d’une transaction de commande fournisseur. Par exemple, la non-conformité peut être liée à la réception d’une commande fournisseur ou aux inquiétudes d’un fournisseur en relation avec une pièce qu’il fournit. |
| Production | Le numéro d’ordre de fabrication ou un numéro de lot d’une transaction d’ordre de fabrication. Par exemple, la non-conformité peut être liée à un lot produit spécifique. |
| Interne | Le numéro de l’ordre de qualité ou un numéro de lot d’une transaction d’ordre de qualité. Par exemple, la non-conformité peut être liée aux tests exécutés dans le cadre d’un ordre de qualité, ou aux inquiétudes d’un employé en relation avec la qualité d’un produit. |
| Production de coproduits | Une non-conformité d’ordre de fabrication de coproduit associée à des ordres de pour production par lots. |

Les non-conformités sont associées à un type de problème. Les types de problèmes sont définis dans la page **Types de problèmes**, où vous spécifiez les types de problèmes qui peuvent être associé à chaque type de non-conformité. Par exemple, les types de problèmes pour les non-conformités du type **Demande de service** peuvent refléter une classification des réclamations client, alors que les types de problèmes liés à une non-conformité du type **Interne** peuvent représenter une classification des codes défaut.

Quand vous créer une non-conformité, vous sélectionnez le type de non-conformité et le type du problème. Le statut d’approbation initial est **Nouveau**, ce qui représente une demande d’action. L’étape suivante consiste à modifier le statut d’approbation sur **Approuvé** ou **Refusé**, pour indiquer si vous allez agir ou non sur la non-conformité. Vous pouvez également fermer une non-conformité (en sélectionnant une case à cocher distincte) pour indiquer que les actions associées sont terminées, ou l’ouvrir à nouveau pour indiquer que des actions supplémentaires sont requises.

Vous pouvez entrer des commentaires pour une non-conformité en associant un document. Il est judicieux de définir un type de document unique pour les non-conformités à l’aide de la page **Type de document**. Vous pouvez ensuite utiliser la page **Paramétrage d’état** pour définir si les commentaires pour ce type de document doivent être imprimés dans l’état de non-conformité et la balise de non-conformité. Vous pouvez utiliser une balise et un état imprimé de non-conformité pour aider à la gestion des matières. Vous pouvez de manière sélective générer des états et des balises, selon des critères de sélection associés à une non-conformité. Ces critères incluent le numéro de non-conformité, l’article, le client, le fournisseur et le statut.

L’état de non-conformité affiche le numéro de non-conformité, l’article et le type de problème. Selon votre stratégie de paramétrage de l’état, l’état peut également afficher les notes associées sur la non-conformité. La balise de non-conformité affiche des informations similaires et affiche également la zone de quarantaines et le type (**Utilisation limitée** ou **Inutilisable**) affectés à la non-conformité pour guider la gestion des matières défectueuses.

## <a name="approved-nonconformance"></a>Non-conformité approuvée

Vous pouvez définir une ou plusieurs opérations associées pour une non-conformité approuvée. Une opération associée décrit le travail qui doit être effectué, et contient une liste des opérations de qualité définies et un texte descriptif du motif du travail. Après avoir défini une opération, vous pouvez définir les frais divers, les articles et les heures de travail nécessaires à l’exécution de l’opération. Les coûts calculés sont indiqués pour l’opération associée et le total des coûts calculés est indiqué pour la non-conformité. Les coûts calculés et les détails sous-jacents (relatifs aux articles, heures travaillées et frais divers) constituent des informations de référence, qui ne sont utilisées que dans le cadre de la fonctionnalité de gestion de la qualité.

Vous pouvez également créer un ordre de qualité à partir d’une non-conformité en effectuant en premier lieu une recherche d’ordres de qualité, puis en créant l’ordre de qualité. Par exemple, un ordre de qualité peut identifier la nécessité de tester (ou de tester à nouveau) les matières défectueuses. Le nouvel ordre de qualité affiche le lien vers la non-conformité d’origine.

Vous pouvez lier une non-conformité à une autre ou en créer une à partir d’une conformité existante. Par exemple, le lien peut refléter l’interconnexion entre les problèmes de qualité.

## <a name="correction-handling"></a>Gestion des corrections

La page **Corrections** permet de créer une liste de non-conformités qui doivent être corrigées. Chaque article de correction est associé au type de diagnostic qui a permis de découvrir le problème. La page **Corrections** contient également des informations sur qui doit effectuer une action corrective, et quand. Vous pouvez décrire les détails du problème et de l’action corrective requise en associant un document à la correction. Une fois la non-conformité prise en compte ou corrigée, vous « fermez » l’article de correction en sélectionnant l’option **Terminé**. Vous pouvez également indiquer que la solution est une solution à court terme.

Il est judicieux de définir un type de document unique pour les corrections à l’aide de la page **Type de document**. Vous pouvez ensuite utiliser la page **Paramétrage d’état** pour définir si les commentaires pour ce type de document doivent être imprimés dans l’état de correction. Un état des corrections imprimé affiche les informations sur la non-conformité et les notes de non-conformité associées. L’état inclut également des informations de correction, telles que le type de diagnostic, et les notes de correction associées.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Activer la gestion de la qualité et de la non-conformité](enable-quality-management.md)
- [Blocage du stock](inventory-blocking.md)
- [Ordres de contrôle](quarantine-orders.md)
- [Inspecter la qualité des marchandises](tasks/inspect-quality-goods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
