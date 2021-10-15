---
title: Modèles de chargement
description: Cette rubrique décrit comment paramétrer des modèles de charge et comment associer un modèle de charge à une nouvelle charge.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 694860d1ade74f9fd51a8ac579aa69fe7fb673a8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569911"
---
# <a name="load-templates"></a>Modèles de chargement

[!include [banner](../../includes/banner.md)]

Lorsque vous créez une charge, vous pouvez attribuer un modèle de charge. Le modèle de chargement contient des informations sur l’équipement et sur des mesures telles que la hauteur, la largeur, la profondeur et le volume de la charge.

Cette rubrique décrit comment paramétrer des modèles de charge et comment associer un modèle de charge à une nouvelle charge.

## <a name="set-up-a-load-template"></a>Définir un modèle de chargement

1. Aller à **Gestion des transports \> Configurer \> Création de charge \> Modèle de charge**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un nouveau modèle, ou sélectionnez **Modifier** pour modifier un modèle existant.
1. Dans la ligne du modèle nouveau ou existant, définissez les champs suivants :

    - **ID de modèle de chargement** – Entrez un identificateur (ID) unique pour la charge.
    - **Équipement** – Sélectionnez l’équipement à utiliser pour expédier le chargement.
    - **Hauteur de chargement**, **Largeur de chargement**, et **Profondeur de chargement** – Entrez les dimensions de la charge.
    - **Volume de chargement autorisé max.** et **Poids de charge autorisé max.** – Entrez le volume et le poids maximum autorisés de la charge.
    - **Poids brut autorisé maximum** – Entrez le poids brut autorisé maximum de la charge. Un poids brut de la charge comprend le poids de la tare et le poids de la charge.
    - **Nombre maximum de pièces de fret autorisé** – Entrez le nombre maximum de pièces de fret que le chargement peut contenir.
    - **Empiler la charge au sol**–- Cochez cette case pour utiliser le chargement au sol. Dans un scénario de chargement au sol, les boîtes sont empilées du sol au plafond et d’un mur à l’autre dans le conteneur afin de maximiser la capacité.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="associate-a-load-template-with-a-new-load"></a>Associer un modèle de charge à une nouvelle charge

1. Accédez à **Gestion du transport \> Planning \> Console de planification des charges**.
1. Dans la partie supérieure de la page, sélectionnez l’un des onglets suivants, en fonction du type de document source pour lequel vous créez une charge : **Expéditions**, **Lignes de vente**, **Lignes de transfert**, ou **Lignes de commande d’achat**. 
1. Sélectionnez le document spécifique pour lequel planifier le chargement.
1. Dans le volet Actions, sous l’onglet **Approvisionnement et demande**, dans le groupe **Ajouter**, sélectionnez **Dans un nouveau chargement**.
1. Dans la boîte de dialogue **Modèle de chargement**, dans le champ **ID modèle de chargement**, sélectionnez le modèle à appliquer.
1. Sélectionnez **OK** pour appliquer le modèle.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]