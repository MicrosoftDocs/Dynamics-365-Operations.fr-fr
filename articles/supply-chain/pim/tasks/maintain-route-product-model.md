---
title: Tenir à jour la gamme pour le modèle de configuration de produit
description: L’exécution de cette procédure nécessite qu’il existe un modèle de configuration de produit.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88df8b867ac7f354417add0462e7999747333451
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577262"
---
# <a name="maintain-route-for-a-product-model"></a>Tenir à jour la gamme pour le modèle de configuration de produit

[!include [banner](../../includes/banner.md)]

L’exécution de cette procédure nécessite qu’il existe un modèle de configuration de produit. Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.

## <a name="add-a-route-operation"></a>Ajouter une opération de gamme

1. Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez le modèle de Haut-parleur haut de gamme pour cet exercice.  
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Développez la section **Opérations de gamme**.
1. Sélectionnez **Ajouter**.
1. Tapez une valeur dans le champ **Nom**.
1. Tapez une valeur dans le champ **Description**.
1. Sélectionnez **Enregistrer**.

## <a name="enter-route-operation-details"></a>Entrer les détails de l’opération de gamme

1. Cliquez sur **Détails de l'opération de gamme**.
1. Dans le champ **Opération**, saisissez ou sélectionnez une valeur.
1. Dans le champ **Au n° opér.** , entrez un numéro.
    * Les numéros d’opération déterminent la position dans la gamme.  
    * Chaque propriété sur une opération de gamme peut obtenir une valeur statique ou être mise en correspondance avec un attribut. La mise en correspondance avec un attribut aura pour résultat que les valeurs seront définies dans le cadre de la configuration.  
1. Dans le champ **Groupe de gammes**, entrez ou sélectionnez une valeur.
    * Le groupe de gammes détermine le comportement essentiel pour l’évaluation des coûts, la consommation et le paramétrage.  
1. Sélectionnez l’onglet **Paramétrage**.
1. Sélectionnez l’onglet **Heures**.
1. Dans le champ **Qté à traiter**, entrez un numéro.
    * Déterminez le nombre qui sera traité au cours d’une opération.  
1. Dans le champ **Heures/temps**, entrez un nombre.
    * Entrez le ratio de durée.  
1. Activez la case à cocher **Définir**.
1. Entrez un nombre dans le champ **Temps d’exécution**.
    * Déterminez le temps de traitement pour la quantité que vous avez spécifiée.  
1. Sélectionnez l’onglet **Demandes de ressources**.
1. Sélectionnez **Ajouter**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Dans le champ **Type de demande**, sélectionnez une option.
    * Décidez si vous souhaitez spécifier les ressources particulières ou les capacités qu’elles doivent posséder.  
1. Dans le champ **Demande**, saisissez ou sélectionnez une valeur.
1. Cliquez sur **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]