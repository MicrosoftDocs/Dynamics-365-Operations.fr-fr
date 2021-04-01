---
title: Spécification de la procédure de cession des articles retournés
description: Spécification de la procédure de cession des articles retournés.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 61bff50d55ed4c251918a327f2a033369e731bf0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5242371"
---
# <a name="specify-how-to-dispose-of-returned-items"></a>Spécification de la procédure de cession des articles retournés 

[!include [banner](../includes/banner.md)]


Lorsque vous traitez un ordre de retour, vous devez spécifier un code motif de retour pour identifier la raison pour laquelle le produit est retourné. Vous devez également spécifier un code disposition et une action de disposition pour déterminer les tâches à effectuer avec le produit retourné.

Vous pouvez appliquer un code disposition lorsque vous créez un ordre de retour, enregistrez l’arrivée des articles, mettez à jour le bon de livraison d’une arrivée d’articles ou terminez un ordre de contrôle.

Vous pouvez définir tout code disposition nécessaire à la prise en charge des processus entreprise. Le tableau suivant présente un ensemble de codes généralement utilisés pour affecter une disposition à l’article retourné.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type de disposition</p></th>
<th><p>Code courant</p></th>
<th><p>description ;</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cession</p></td>
<td><p>SC</p></td>
<td><p>Mise au rebut/destruction</p></td>
</tr>
<tr class="even">
<td><p>Cession</p></td>
<td><p>DC</p></td>
<td><p>Don aux œuvres caritatives</p></td>
</tr>
<tr class="odd">
<td><p>Cession</p></td>
<td><p>TD</p></td>
<td><p>Cession à un tiers</p></td>
</tr>
<tr class="even">
<td><p>Cession</p></td>
<td><p>SL</p></td>
<td><p>Valeur résiduelle</p></td>
</tr>
<tr class="odd">
<td><p>Cession</p></td>
<td><p>TS</p></td>
<td><p>Vente à des tiers (marchés secondaires)</p></td>
</tr>
<tr class="even">
<td><p>Réparation/modification</p></td>
<td><p>RW</p></td>
<td><p>Remise en fabrication</p></td>
</tr>
<tr class="odd">
<td><p>Réparation/modification</p></td>
<td><p>RF</p></td>
<td><p>Réusinage/rénovation</p></td>
</tr>
<tr class="even">
<td><p>Réparation/modification</p></td>
<td><p>MD</p></td>
<td><p>Modification</p></td>
</tr>
<tr class="odd">
<td><p>Réparation/modification</p></td>
<td><p>RP</p></td>
<td><p>Réparation</p></td>
</tr>
<tr class="even">
<td><p>Réparation/modification</p></td>
<td><p>RV</p></td>
<td><p>Retour au fournisseur</p></td>
</tr>
<tr class="odd">
<td><p>Divers</p></td>
<td><p>AI</p></td>
<td><p>Utilisation par dérogation</p></td>
</tr>
<tr class="even">
<td><p>Divers</p></td>
<td><p>RS</p></td>
<td><p>Revente</p></td>
</tr>
<tr class="odd">
<td><p>Divers</p></td>
<td><p>EX</p></td>
<td><p>Échanger</p></td>
</tr>
<tr class="even">
<td><p>Divers</p></td>
<td><p>MS</p></td>
<td><p>Autre(s)</p></td>
</tr>
</tbody>
</table>


Pour chaque code disposition défini, vous devez sélectionner une action de disposition. L’action de disposition détermine les conséquences physiques et financières des codes disposition. Par exemple, l’action de disposition détermine la gestion physique de l’article retourné, l’impact financier de l’article retourné et si un article de remplacement doit être envoyé au client. Vous pouvez définir un nombre illimité de codes disposition en fonction de vos besoins, mais vous avez le choix uniquement entre six actions de destination prédéfinies. Le tableau suivant décrit les actions de disposition et leurs définitions.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Action de disposition</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Crédit</strong></p></td>
<td><p>Permet de remettre l’article en stock et de créditer le compte client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Créditer uniquement</strong></p></td>
<td><p>Permet de créditer le client sans demander ni attendre que l’article soit retourné.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rebut</strong></p></td>
<td><p>Permet de mettre l’article au rebut et de créditer le client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Remplacer et créditer</strong></p></td>
<td><p>Permet de remettre l’article en stock, de créer un ordre de remplacement et de créditer le client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Remplacer et mettre au rebut</strong></p></td>
<td><p>Permet de mettre l’article au rebut, de créer un ordre de remplacement et de créditer le client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Retourner au client</strong></p></td>
<td><p>Permet de rejeter l’article retourné et de le renvoyer au client.</p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a>Sélection d’un code disposition pour un ordre de contrôle

1.  Cliquez sur **Gestion des stocks** \> **Périodique** \> **Gestion de la qualité** \> **Ordres de contrôle**.

2.  Pour un ordre de contrôle existant, sélectionnez une action dans le champ **Code disposition** de l’onglet **Vue d’ensemble**.



## <a name="see-also"></a>Voir également :

[Ordre de contrôle (écran)](https://technet.microsoft.com/library/aa554073(v=ax.60))

[Codes disposition (écran)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]