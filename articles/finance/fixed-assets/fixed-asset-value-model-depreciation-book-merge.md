---
title: Fusion du modèle de la valeur d’immobilisation et du registre d’amortissement
description: 'Dans les versions précédentes, il y avait deux concepts d’évaluation pour les immobilisations : modèles de valeur et registres des amortissements. Dans Microsoft Dynamics 365 for Operations version 1611, la fonctionnalité de modèle de valeur et la fonctionnalité du registre des amortissements ont été fusionnées en un concept unique appelé registre.'
author: moaamer
ms.date: 10/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f4f06b7916fb2eeed802b2dce95edfce448dcd97
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880843"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Fusion du modèle de la valeur d’immobilisation et du registre d’amortissement

[!include [banner](../includes/banner.md)]

Cet article décrit la fonctionnalité de registre actuelle dans Immobilisations. Cette fonctionnalité est basée sur la fonctionnalité de modèle de valeur qui était disponible dans des versions précédentes, mais inclut également toutes les fonctionnalités fournies précédemment uniquement dans les registres des amortissements.

La fonctionnalité de registre vous permet d’utiliser un seul ensemble de pages, de demandes et de rapports pour tous les processus d’immobilisations de votre organisation. Les tableaux de cet article décrivent la fonctionnalité précédente des registres d’amortissement et des modèles de valeur, ainsi que la fonctionnalité actuelle pour les registres.

## <a name="setup"></a>Paramétrage
Par défaut, les registres valident la comptabilité et la comptabilité auxiliaire d’immobilisation. Les registres ont une nouvelle option **Valider dans la comptabilité** qui permet de désactiver la validation dans la Comptabilité et la validation uniquement dans la Comptabilité auxiliaire d’immobilisation. Cette fonctionnalité est semblable au comportement de validation précédent pour les registres des amortissements. Le paramétrage des noms de journaux dispose d’une couche de validation qui est nommée Aucune. Cette couche de validation a été ajoutée spécifiquement pour les transactions d’immobilisation. Pour valider des transactions pour les registres qui ne valident pas dans la Comptabilité, vous devez utiliser un nom de journal dont la couche de validation est définie sur **Aucune**.


| &nbsp;                                           | Registre des amortissements               | Modèle de valeur                     | Registre (Nouveau)                                              |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
| Valider dans la Comptabilité                                   | Jamais                           | Toujours                          | Options pour valider dans la Comptabilité                                |
| Couches de validation                                   | Non applicable                  | 3 : Actuel, opérations et taxes | 11 : Actuel, opérations, taxes, 7 couches personnalisées, et aucune |
| Noms de journal                                    | Noms des journaux du registre des amortissements | Comptabilité – Noms de journal              | Comptabilité – Noms de journal                                      |
| Registres dérivés                                    | Non autorisé                     | Autorisé                         | Autorisé                                                 |
| Remplacement du profil d’amortissement au niveau de l’immobilisation | Autorisé(e)                         | Non autorisé                     | Autorisé(e)                                                 |

## <a name="processes"></a>Processus
Les processus utilisent maintenant une page commune. Sont processus sont autorisés uniquement si l’option **Valider dans la comptabilité** est définie sur **Non** dans le paramétrage du registre.

| &nbsp;                                           | Registre des amortissements               | Modèle de valeur                     | Registre (Nouveau)                                              |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
| Entrée de transaction              | Journal du registre des amortissements | Journal des immobilisations | Journal des immobilisations                      |
| amortissement de la prime             | Autorisé(e)                   | Non autorisé         | Autorisé(e)                                  |
| Supprime les transactions historiques | Autorisé(e)                   | Non autorisé         | Autorisé, sauf si vous avez validé dans la comptabilité |
| Mise à jour collective                    | Autorisé(e)                   | Non autorisé         | Autorisé, sauf si vous avez validé dans la comptabilité |

## <a name="inquiries-and-reports"></a>Recherches et états
Les recherches et les états prennent en charge tous les registres. Les états qui ne sont pas inclus dans le tableau suivant des registres des amortissements et des modèles de valeur précédemment pris en charge, continueront de prendre en charge tous les types de registres. Le champ **Couche de validation** a également été ajouté aux états, afin de pouvoir plus facilement identifier les validations de transactions.

| &nbsp;                                           | Registre des amortissements               | Modèle de valeur                     | Registre (Nouveau)                                              |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
| Recherches                             | Transactions du registre des amortissements | Transactions d’immobilisation | Transactions d’immobilisation |
| Relevé d’immobilisations                 | Non autorisé                    | Autorisé(e)                  | Autorisé(e)                  |
| Base des immobilisations                     | Autorisé(e)                        | Non autorisé              | Autorisé(e)                  |
| Conditions d’application à mi-trimestre des immobilisations | Autorisé(e)                        | Non autorisé              | Autorisé(e)                  |

## <a name="upgrade"></a>Mettre à niveau
La procédure de mise à niveau déplacera votre paramétrage actuel et toutes les transactions existantes dans la structure du nouveau registre. Les modèles de valeur restent tels qu’ils sont, c’est-à-dire des registres qui valident dans la Comptabilité. Toutefois, les registres d’amortissements seront déplacés vers un registre dont l’option **Valider dans la Comptabilité** est définie sur **Non**. Les noms des journaux du registre des amortissements seront transférés vers un nom de journal de comptabilité dont la couche de validation est définie sur **Aucune**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
