---
title: Valider avec des registres dérivés
description: Cet article décrit l’utilisation des registres déduits.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4704dde64305bd285d9796cc161205709bd6e7ed
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988925"
---
# <a name="post-with-derived-books"></a>Valider avec des registres dérivés

[!include [banner](../includes/banner.md)]

Cet article décrit l’utilisation des registres déduits.

Si vous validez des transactions pour un registre contenant des registres déduits, les transactions de registres déduits sont validées automatiquement dans les journaux, les commandes fournisseur ou les factures financières. Toutefois, si vous préparez les transactions de registre principales dans le journal des immobilisations, vous pouvez afficher et modifier les montants des transactions dérivées avant de les valider.
-   Certains comptes (de taxe, client ou fournisseur) ne sont mis à jour qu’une seule fois par les validations du registre principal. Les transactions du registre déduit sont validées dans les comptes définis pour le registre déduit dans la page Profils de validation d’immobilisation.
-   L’acquisition est souvent utilisée comme type de transaction pour le registre déduit. Utilisez-le lorsque le registre et le registre des déduit doivent être appliqués à l’immobilisation à partir du moment de l’acquisition de l’immobilisation.
-   D’autres valeurs de type de transaction peuvent également s’appliquer. Par exemple, si le registre principal et les registres déduits ont les mêmes intervalles concernant la vente ou la cession, tous les types de transactions d’immobilisation sont disponibles pour le paramétrage d’un registre déduit.

> [!WARNING]
> Un amortissement validé dans le registre déduit sera du même montant que celui validé pour le registre principal. Si les méthodes d’amortissement des registres diffèrent, vous ne devez pas générer de transactions d’amortissement à l’aide du processus déduit. |

## <a name="example"></a>Exemple 
Les informations suivantes décrivent le paramétrage des transactions d’acquisition avec la fonctionnalité de registre déduit.

1.  Créez des registres dans la page Registres.
    -   Registre pour la comptabilité : MV 1, couche de validation actuelle
    -   Registre pour les taxes : MV 2, couche de validation des taxes

2.  Sous MV 1, cliquez sur l’onglet Registres dérivés. Sélectionnez MV 2 dans le champ Registre et Acquisition dans le champ Type de transaction.

Les registres peuvent alors être associés à des immobilisations spécifiques. 

Si une acquisition est validée pour une immobilisation avec le registre MV 1, elle est validée non seulement dans MV 1, mais également dans le registre dérivé MV 2. Le statut des deux registres d’immobilisation est mis à jour sur Ouvert.

> [!NOTE]                                                                                                         
> Si vous n’utilisez pas de registre déduit, vous devez valider l’acquisition de l’immobilisation tant pour le registre MV 1 que pour le registre MV 2.

Pour plus d’informations, voir [Registres dérivés](derived-books.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]