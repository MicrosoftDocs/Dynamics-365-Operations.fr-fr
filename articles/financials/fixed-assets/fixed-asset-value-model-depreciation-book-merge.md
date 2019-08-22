---
title: Fusion du modèle de la valeur d'immobilisation et du registre d'amortissement
description: "Dans les versions précédentes, il y avait deux concepts d'évaluation pour les immobilisations : modèles de valeur et registres des amortissements. Dans Microsoft Dynamics 365 for Operations version 1611, la fonctionnalité de modèle de valeur et la fonctionnalité du registre des amortissements ont été fusionnées en un concept unique appelé registre."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3225b214e729ff13d4ffe8ad1d8cf0f2d6baae49
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840359"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Fusion du modèle de la valeur d'immobilisation et du registre d'amortissement

[!include [banner](../includes/banner.md)]

Dans les versions précédentes, il y avait deux concepts d'évaluation pour les immobilisations : modèles de valeur et registres des amortissements. Dans Microsoft Dynamics 365 for Operations version 1611, la fonctionnalité de modèle de valeur et la fonctionnalité du registre des amortissements ont été fusionnées en un concept unique appelé registre.

La nouvelle fonctionnalité de registre est basée sur la fonctionnalité précédente de modèle de valeur mais inclut également toutes les fonctionnalités fournies précédemment uniquement dans les registres des amortissements. [![Registre en tant que fusion de modèle de valeur et fonctionnalité de registre d'amortissements](./media/fixed-assets.png)](./media/fixed-assets.png) En raison de cette fusion, vous pouvez désormais utiliser un ensemble unique de pages, de recherches et d'états pour tous vos processus d'immobilisation. Les tableaux de cette rubrique décrivent la fonctionnalité précédente des registres d'amortissement et des modèles de valeur, avec la nouvelle fonctionnalité pour les registres.

## <a name="setup"></a>Configuration
Par défaut, les registres valident la comptabilité et la comptabilité auxiliaire d'immobilisation. Les registres ont une nouvelle option **Valider dans la comptabilité** qui permet de désactiver la validation dans la Comptabilité et la validation uniquement dans la comptabilité auxiliaire d'immobilisation. Cette fonctionnalité est semblable au comportement de validation précédent pour les registres des amortissements. Le paramétrage des noms de journaux dispose d'une couche de validation qui est nommée Aucune. Cette couche de validation a été ajoutée spécifiquement pour les transactions d'immobilisation. Pour valider des transactions pour les registres qui ne valident pas dans la comptabilité, vous devez utiliser un nom de journal dont la couche de validation est définie sur **Aucune**.

|                                                  |                                 |                                 |                                                         |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
|                                                  | Registre des amortissements               | Modèle de valeur                     | Registre (Nouveau)                                              |
| Valider dans la comptabilité                                   | Jamais                           | Toujours                          | Option pour valider dans la Comptabilité                                |
| Couches de validation                                   | Non applicable                  | 3 : Actuel, opérations et taxes | 11 : Actuel, opérations, taxes, 7 couches personnalisées, et aucune |
| Noms de journal                                    | Noms des journaux du registre des amortissements | Comptabilité - Noms de journaux              | Comptabilité - Noms de journaux                                      |
| Registres dérivés                                    | Non autorisé                     | Autorisé(e)                         | Autorisé(e)                                                 |
| Remplacement du profil d'amortissement au niveau de l'immobilisation | Autorisé(e)                         | Non autorisé                     | Autorisé(e)                                                 |

## <a name="processes"></a>Processus
Les processus utilisent maintenant une page commune. Sont processus sont autorisés uniquement si l'option **Valider dans la comptabilité** est définie sur **Non** dans le paramétrage du registre.

|                                |                           |                     |                                          |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
|                                | Registre des amortissements         | Modèle de valeur         | Registre (Nouveau)                               |
| Entrée de transaction              | Journal du registre des amortissements | Journal des immobilisations | Journal des immobilisations                      |
| amortissement de la prime             | Autorisé(e)                   | Non autorisé         | Autorisé(e)                                  |
| Supprime les transactions historiques | Autorisé(e)                   | Non autorisé         | Autorisé, sauf si vous avez validé dans la comptabilité |
| Mise à jour collective                    | Autorisé(e)                   | Non autorisé         | Autorisé, sauf si vous avez validé dans la comptabilité |

## <a name="inquiries-and-reports"></a>Recherches et états
Les recherches et les états prennent en charge tous les registres. Les états qui ne sont pas inclus dans le tableau suivant des registres des amortissements et des modèles de valeur précédemment pris en charge, continueront de prendre en charge tous les types de registres. Le champ **Couche de validation** a également été ajouté aux états, afin de pouvoir plus facilement identifier les validations de transactions.

|                                       |                                |                          |                          |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
|                                       | Registre des amortissements              | Modèle de valeur              | Registre (Nouveau)               |
| Recherches                             | Transactions du registre des amortissements | Transactions d'immobilisation | Transactions d'immobilisation |
| Relevé d'immobilisations                 | Non autorisé                    | Autorisé(e)                  | Autorisé(e)                  |
| Base des immobilisations                     | Autorisé(e)                        | Non autorisé              | Autorisé(e)                  |
| Conditions d'application à mi-trimestre des immobilisations | Autorisé(e)                        | Non autorisé              | Autorisé(e)                  |

## <a name="upgrade"></a>Mettre à niveau
La procédure de mise à niveau déplacera votre paramétrage actuel et toutes les transactions existantes dans la structure du nouveau registre. Les modèles de valeur restent telles qu'elles sont, comme registre qui valide dans la comptabilité. Toutefois, les registres d'amortissements seront déplacés vers un registre dont l'option **Valider dans la comptabilité** est définie sur **Non**. Les noms des journaux du registre des amortissements seront transférés vers un nom de journal de comptabilité dont la couche de validation est définie sur **Aucune**.



