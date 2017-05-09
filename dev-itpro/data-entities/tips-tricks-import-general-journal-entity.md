---
title: "Bonnes pratiques pour l’importation de numéros document à l’aide de l’entité du journal des opérations diverses"
description: "Cette rubrique fournit des conseils pour l’importation de données dans le Journal des opérations diverses à l’aide de l&quot;entité de Journal des opérations diverses."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 81a52acd1d9baa12fcfe9d848441901894fa5682
ms.lasthandoff: 03/31/2017


---

# <a name="best-practices-for-importing-vouchers-using-the-general-journal-entity"></a>Bonnes pratiques pour l’importation de numéros document à l’aide de l’entité du journal des opérations diverses

[!include[banner](../includes/banner.md)]


Cette rubrique fournit des conseils pour l’importation de données dans le Journal des opérations diverses à l’aide de l'entité de Journal des opérations diverses.  

Vous pouvez utiliser l’entité du journal des opérations diverses pour importer uniquement les N° document ayant pour type de compte de contrepartie **Comptabilité, Client, Fournisseur ou Banque**. Le document peut être entré comme une ligne, à l'aide à la fois des champs **Compte** et **Compte de contrepartie**, ou comme un N° de document multiligne, où seul le champ **Compte** est utilisé (et le champ **Compte de contrepartie** est laissé vierge sur chaque ligne). L'entité de journal des opérations diverses ne prend pas en charge tous les types de compte. Au lieu de cela, les autres entités existent pour les scénarios où les différentes combinaisons de types de comptes sont requises. Par exemple, pour importer une transaction de projet, utilisez l'entité de journal Dépenses de projet. Chaque entité est conçue pour prendre en charge des scénarios spécifiques, ce qui implique que des champs supplémentaires peuvent être disponibles dans les entités pour ces scénarios mais pas pour d'autres scénarios.

## <a name="setup"></a>Configuration
Avant d’importer à l’aide de l’entité de journal des opérations diverses, validez le paramétrage suivant :

-   **Paramètres des séquences de numéros pour le numéro de lot du journal** : par défaut, lorsque vous importez à l’aide de l'entité du journal des opérations diverses, le numéro de lot du journal utilise la souche de numéros qui est définie dans les paramètres de comptabilité générale. Si vous définissez la souche de numéros pour le numéro de lot de journal sur **manuel**, aucun numéro par défaut n’est appliqué. Ce paramétrage n’est pas pris en charge.
-   **Configuration de la dimension financière** : chaque entreprise doit définir l’ordre des dimensions financières lorsque les entités sont utilisées pour importer des transactions. L’ordre n’est défini pour le format **Intégration des dimensions comptables**, dans **Comptabilité** &gt; **Plan de comptes** &gt; **Dimensions** &gt; **Configuration de dimension financière pour les applications d'intégration** &gt; **Sélectionner les entités de données**. Les segments du compte général qui est importé doivent avoir le même ordre. Dans le cas contraire, une erreur se produit lors de l’importation.

## <a name="general-journal-entity-setup"></a>Paramétrage de l'entité du journal des opérations diverses
Deux paramètres de la gestion des données affectent la façon dont le numéro de lot par défaut ou le numéro de document du journal s'appliquent :

-   **Traitement basé sur les jeux** (sur l'entité de données)
-   **Autogénéré** (dans la mise en correspondance des champs)

Les sections suivantes décrivent l’effet de ces paramètres et expliquent également comment les numéros de lot du journal et les numéros de document sont générés.

### <a name="journal-batch-number"></a>Numéro de traitement par lots de journal

-   Le paramétrage **Traitement basé sur les jeux** sur l’entité du journal des opérations diverses n’affecte pas la manière dont les numéros de lot de journal sont générés.
-   Si le champ **Numéro de lot du journal** est défini sur **Généré automatiquement**, un nouveau numéro de lot de journal est créé pour chaque ligne qui est importée. Ce comportement n’est pas recommandé. Le paramètre **Généré automatiquement** se trouve dans le projet d’importation, sous **Afficher le mappage**, sur l'onglet **Détails de la mise en correspondance**.
-   Si le champ **Numéro de lot du journal** n'est pas défini sur **Généré automatiquement**, le numéro de lot de journal est créé comme suit :
    -   Si le numéro de lot du journal défini dans le fichier importé correspond à un journal quotidien existant non validé dans Microsoft Dynamics 365 for Operations, toutes les lignes ayant un numéro de lot de journal correspondant sont importées dans le journal existant. Les lignes ne sont jamais importées dans un numéro de lot de journal validé. Au lieu de cela, un nouveau numéro est créé.
    -   Si le numéro de lot du journal défini dans le fichier importé ne correspond pas à un journal quotidien existant non validé dans Dynamics 365 for Operations, toutes les lignes ayant le même numéro de lot de journal sont regroupées dans un nouveau journal. Par exemple, toutes les lignes ayant un numéro de lot de journal de 1 sont importées dans un nouveau journal, et toutes les lignes ayant un numéro de lot de journal de 2 sont importés dans un second nouveau journal. Le numéro de lot du journal est créé à l’aide de la souche de numéros qui est définie dans les paramètres de comptabilité.

### <a name="voucher-number"></a>N° document

-   Lorsque vous utilisez le paramètre **Traitement basé sur les jeux** de l’entité de journal des opérations diverses, le numéro de document doit être fourni dans le fichier importé. Un numéro de document est attribué à chaque transaction dans le journal des opérations diverses qui est fourni dans le fichier importé, même si le numéro de document n’est pas équilibré. Si vous souhaitez utiliser le traitement basé sur les jeux, mais que vous souhaitez également utiliser la souche de numéros qui est définie pour les numéros de documents dans Dynamics 365 for Operations, un correctif logiciel a été fourni pour l'édition de février 2016. Le numéro de correctif logiciel est 3170316 et est disponible pour le téléchargement dans Licycle services (LCS). Pour plus d’informations, consultez [Téléchargement de correctifs auprès de Lifecycle Services](..\migration-upgrade\download-hotfix-lcs.md).
    -   Pour activer cette fonctionnalité, sur le nom du journal utilisé pour les importations dans Dynamics 365 for Operations, définissez **Attribution d'un numéro pour la validation** sur **Oui**.
    -   Un numéro de document doit toujours être défini dans le fichier importé. Toutefois, ce numéro est temporaire et est remplacé par le numéro de document de Dynamics 365 for Operations lorsque le journal est validé. Il se peut que vous deviez vous assurer que les lignes du journal sont correctement regroupées par numéro de document temporaire. Par exemple, lors de la validation, trois lignes portant le N° document temporaire 1 sont détectées. Le n° document temporaire des trois lignes est remplacé par le numéro suivant dans la souche de numéros. Si ces trois lignes ne sont pas une entrée équilibrée, le document n’est pas validé. Ensuite, si les lignes sont trouvées avec un numéro de document temporaire de 2, ce numéro est remplacé par le numéro de document suivant dans la souche de numéros et ainsi de suite.

<!-- -->

-   Lorsque vous n'utilisez pas le paramètre **Traitement basé sur les jeux**, vous n'avez pas besoin de fournir un numéro document dans le fichier importé. Les numéros de document sont créés pendant l’importation, en fonction de la configuration du nom du journal (**Un seul N° document**, **En relation avec le solde**, et ainsi de suite). Par exemple, si le nom du journal est défini en tant que **En relation avec le solde**, la première ligne reçoit un nouveau numéro de document par défaut. Le système évalue ensuite la ligne pour déterminer si les débits égalent les crédits. S’il existe un compte de contrepartie sur la ligne, la ligne suivante à être importée reçoit un nouveau numéro de document. Si aucun compte de contrepartie n’existe, le système évalue si les débits égalent les crédits à mesure que chaque nouvelle ligne est importé.
-   Si le champ **N° de document** est défini sur **Généré automatiquement**, l’importation ne réussira pas. Le paramètre **Généré automatiquement** pour le champ **N° de document** n’est pas pris en charge.

Par défaut, l’entité de journal des opérations diverses utilise le traitement basé sur les jeux. Après avoir évalué les besoins commerciaux de votre organisation, vous pouvez modifier le paramètre **Traitement basé sur les jeux** en cliquant sur **Entités de données** dans l'espace de travail **Gestion des données**. Le traitement basé sur les jeux est utilisé pour accélérer le processus d’importation. Si vous n’utilisez pas le traitement basé sur les jeux, l’importation de l'entité de journal des opérations diverses sera plus lente.




