---
title: Tenir à jour la gamme pour le modèle de configuration de produit
description: L’exécution de cette procédure nécessite qu’il existe un modèle de configuration de produit.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13bbdc706280317c5a1ab7fb21c9585f1c7d48ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247788"
---
# <a name="maintain-route-for-a-product-model"></a>Tenir à jour la gamme pour le modèle de configuration de produit

[!include [banner](../../includes/banner.md)]

L’exécution de cette procédure nécessite qu’il existe un modèle de configuration de produit. Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.


## <a name="add-a-route-operation"></a>Ajouter une opération de gamme
1. Cliquez sur Définition du modèle de variante de produit.
2. Cliquez sur Modèles de configuration de produit.
3. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez le modèle de Haut-parleur haut de gamme pour cet exercice.  
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Développez la section Opérations de gamme.
6. Cliquez sur Ajouter.
7. Tapez une valeur dans le champ Nom.
8. Dans le champ Description, entrez une valeur.
9. Cliquez sur Enregistrer.

## <a name="enter-route-operation-details"></a>Entrer les détails de l’opération de gamme
1. Cliquez sur Détails de l’opération de gamme.
2. Dans le champ Opération, saisissez ou sélectionnez une valeur.
3. Dans le champ N° opér. N° , entrez un numéro.
    * Les numéros d’opération déterminent la position dans la gamme.  
    * Chaque propriété sur une opération de gamme peut obtenir une valeur statique ou être mise en correspondance avec un attribut. La mise en correspondance avec un attribut aura pour résultat que les valeurs seront définies dans le cadre de la configuration.  
4. Dans le champ Groupe de gammes, entrez ou sélectionnez une valeur.
    * Le groupe de gammes détermine le comportement essentiel pour l’évaluation des coûts, la consommation et le paramétrage.  
5. Cliquez sur l’onglet Paramétrage.
6. Cliquer sur l’onglet Temps.
7. Dans le champ Qté à traiter , entrez un numéro.
    * Déterminez le nombre qui sera traité au cours d’une opération.  
8. Dans le champ Heures/temps, entrez un nombre.
    * Entrez le ratio de durée.  
9. Activez la case à cocher Définir.
10. Entrez un nombre dans le champ Temps d’exécution.
    * Déterminez le temps de traitement pour la quantité que vous avez spécifiée.  
11. Cliquez sur l’onglet Demandes de ressources.
12. Cliquez sur Ajouter.
13. Dans la liste, marquez la ligne sélectionnée.
14. Dans le champ Type de demande, sélectionnez une option.
    * Décidez si vous souhaitez spécifier les ressources particulières ou les capacités qu’elles doivent posséder.  
15. Dans le champ Demande, saisissez ou sélectionnez une valeur.
16. Cliquez sur OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]