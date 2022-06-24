---
title: Format d’importation pour la consolidation
description: Cet article fournit des informations détaillées sur le format d’importation utilisé lorsque vous consolidez les données financières de plusieurs entités juridiques.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 0aee830f8fbfa384c86dc16465b202be36f07b73
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871302"
---
# <a name="import-format-for-consolidation"></a>Format d’importation pour la consolidation

[!include [banner](../includes/banner.md)]

Cet article fournit des informations détaillées sur le format d’importation utilisé lorsque vous consolidez les données financières de plusieurs entités juridiques. Le format d’importation doit être enregistré sous forme de fichier texte (.txt).

## <a name="import-format"></a>Format d’importation

Le tableau suivant répertorie le format d’importation à utiliser lorsque vous effectuez une consolidation lors d’une importation.

| Tableau d’enregistrement | Format | Notes |
|--------------|---------|-------|
| 1            | 170150, Goodwill, 4 | <ul><li>Le tableau d’enregistrement</li><li>L’ID du compte principal source</li><li>La ligne du compte principal</li><li>Le type de compte principal</li></ul> |
| 2            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>L’ID de compte principal</li><li>La date de la transaction</li><li>Le type de période fiscale (**0** = Ouverture, **1** = Fonctionnement, et **2** = Fermeture)</li><li>La devise de la transaction</li><li>Débit ou crédit (**0** = Débit et **1** = Crédit)</li><li>La couche de validation</li><li>Montants de la transaction</li><li>Quantité</li><li>Le RecID local (valeur int64 ambiguë et unique pour la transaction)</li></ul> |
| 3            | USMF0000009, 2017/01/01, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>Le numéro de l’écriture (numéro de transaction de l’en-tête du budget)</li><li>La date par défaut de l’en-tête du budget</li><li>L’ID du modèle de budget</li><li>Type de budget (**1** - Budget initial, **2** - Transfert, **3** - Révision, **4** - Engagement, **5** - Pré-engagement, **6** - Report de budget, **7** - Projet, **8** - Immobilisations, **9** - Prévision de la demande, **10** - Prévision d’approvisionnement, **11** - Répartitions, **12** - Budget préliminaire.)</li><li>La date de la ligne</li><li>L’ID de compte principal de la ligne</li><li>Le code devise de la ligne</li><li>Le montant de la ligne, exprimé dans la devise de transaction</li><li>La valeur entière d’énumération pour le type de budget de la ligne (dépense ou produit)</li></ul> |
| 4            | DEMF | RecordCompany est l’entité juridique source. |
| 5            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>ID compte principal</li><li>Date de la transaction</li><li>Le type de période fiscale (0 Ouverture, 1 En fonctionnement, 2 Fermeture)</li><li>Devise de la transaction</li><li>Débit ou crédit (0 pour débit, 1 pour crédit)</li><li>Couche de validation</li><li>Montant de la transaction</li><li>Quantité</li><li>Le recid local (valeur int64 ambiguë et unique pour la transaction)</li></ul>  |
| 6            | BusinessUnit, 1 Département, 2 | Les attributs de dimension financière définis dans l’ordre des segments.<p>Vous pouvez utiliser la page **Exportation** pour vérifier comment les attributs sont définis.</p> |
| 7            | 002,1,658 | <ul><li>La valeur de dimension financière</li><li>La dimension financière, comme l’indice fourni dans RecordDimensions</li><li>Un ID d’enregistrement ambigu et unique associé à l’ID d’enregistrement unique de RecordTrans ou RecordTrans2</li></ul> |
| 8            | 002,1,1 | <ul><li>Valeurs de dimension associées à la transaction depuis RecordBudget</li><li>La dimension financière, comme l’indice fourni dans RecordDimensions</li><li>Un ID d’enregistrement de ligne ambigu qui est aligné sur l’ordre des lignes de transaction dans le fichier</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
