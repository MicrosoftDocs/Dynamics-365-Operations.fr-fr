---
title: Définir des règles de couverture pour les articles
description: Cet procédure indique comment créer des règles de couverture et remplacer des paramètres de couverture pour un article spécifique. Il indique également comment spécifier les paramètres de stock par défaut.
author: ChristianRytt
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3947c8a51facfb02012cc8e9a3ffd5887073bd9
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860611"
---
# <a name="define-coverage-rules-for-items"></a>Définir des règles de couverture pour les articles

[!include [banner](../../includes/banner.md)]

Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cet procédure indique comment créer des règles de couverture et remplacer des paramètres de couverture pour un article spécifique. Il indique également comment spécifier les paramètres de stock par défaut.

## <a name="create-a-coverage-group"></a>Créer un groupe de couverture

Créez un groupe de couverture en procédant comme suit :

1. Accédez au **Volet de navigation> Modules > Planification > Paramétrage > Groupes de couverture**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Groupe de couverture**, tapez une valeur.
1. Tapez une valeur dans le champ **Nom**.
1. Dans le champ **Calendrier**, tapez une valeur. Choisissez le calendrier que la planification utilise pour créer des suggestions de réapprovisionnement pour les articles de ce groupe.  
1. Dans le champ **Code couverture**, sélectionnez une option. Sélectionnez « Conditions requises » pour cette procédure.  
1. Entrez « 90 » dans le champ **Plage de gestion de la couverture (jours)**. Pour les articles de ce groupe, la planification crée des suggestions de réapprovisionnement jusqu’à 90 jours dans le futur.  
1. Entrez 1 dans le champ **Jours négatifs**.
1. Entrez 1 dans le champ **Jours positifs**.
1. Développez ou réduisez la section **Autre**.
1. Sous la section **Marges de sécurité en jours**, dans le champ **Marge de réception ajoutée à la date de besoin**, entrez « 1 ». Par exemple, si la marge de réception est définie sur une journée et si une ligne de commande fournisseur est prévue pour réception le 15 mai, la planification calcule le 16 mai comme date de réception ajustée.
1. Entrez « 1 » dans le champ **Marge de sortie déduite de la date de besoin**. Par exemple, si la marge de sécurité est définie sur une journée et si une ligne de commande client est prévue pour livraison le 15 mai, la planification calcule le 14 mai comme date de livraison ajustée.  
1. Entrez « 1 » dans le champ **Marge de renouvellement ajouté au délai de l’article**.
1. Sélectionnez **Enregistrer**.

## <a name="create-a-new-product"></a>Créer un nouveau produit

Créez un nouveau produit en procédant comme suit :

1. Accédez à **Volet de navigation > Modules > Gestion d’informations sur les produits > Produits > Produits lancés**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Numéro du produit**, saisissez une valeur.
1. Dans le champ **Nom du produit**, saisissez une valeur.
1. Dans le champ **Groupe de modèles d’articles**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Dans le champ **Groupe d’articles**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Dans le champ **Groupe de dimensions de stockage**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Dans le champ **Groupe de dimensions de suivi**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Cliquez sur **OK**.

## <a name="set-up-default-order-settings"></a>Configurer les paramètres de commande par défaut

Configurez les paramètres de commande par défaut en procédant comme suit :

1. Dans le **volet Actions**, sélectionnez **Planifier**.
1. Sous **Paramètres de la commande**, sélectionnez **Paramètres de commande par défaut**.
1. Sous **Commande fournisseur**, dans le champ **Site par défaut**, tapez le site utilisé comme valeur par défaut lorsque des commandes fournisseur sont créées.
1. Dans le champ **Entrepôt par défaut**, tapez le site de stockage de l’article.
1. Développez ou réduisez la section **Stock**.
1. Dans le champ **Multiple**, saisissez « 10 ».
1. Dans le champ **Quantité de commande min.**, saisissez « 10 ».
1. Dans le champ **Quantité de commande max.**, saisissez « 100 ».
1. Dans le champ **Quantité de commande standard**, saisissez « 10 ».
1. Entrez un numéro dans le champ **Délai d’achat**.
1. Activez ou désactivez la case à cocher **Jours ouvrables**.
1. Sélectionnez **Enregistrer**.
1. Dans le champ **Type de commande par défaut**, sélectionnez « Commande fournisseur ».
1. Sélectionnez **Enregistrer**.
1. Fermez la page. Fermez la page Paramètres de commande par défaut.  

## <a name="add-an-item-to-a-coverage-group"></a>Ajouter un article à un groupe de couverture

Ajoutez un article à un groupe de couverture en procédant comme suit :

1. Développez ou réduisez la section **Plan**.
1. Dans le champ **Groupe de couverture**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
1. Dans la liste, recherchez le **groupe de couverture** créé.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.

## <a name="create-item-coverage-rules"></a>Créer des règles de couverture d’article

Créez des règles de couverture d'article en procédant comme suit :

1. Dans le **volet Actions**, sélectionnez **Planifier**.
1. Sous **Couverture**, sélectionnez **Couverture de l’article**.
1. Sélectionnez **Nouveau**.
1. Sélectionnez l’onglet **Général**.
1. Activez la case à cocher sous l’en-tête **Remplacer les paramètres du groupe de couverture**.
1. Entrez « 60 » dans le champ **Plage de gestion de la couverture (jours)**. Même si des articles du groupe de couverture Besoin sont planifiés à 90 jours dans le futur, cet article sera planifié à 60 jours dans le futur.  
1. Entrez 2 dans le champ **Jours négatifs**.
1. Entrez 2 dans le champ **Jours positifs**.
1. Sélectionnez l’onglet **Délai**.
1. Activez la case à cocher dans l’en-tête **Achat**.
1. Entrez « 5 » dans le champ **Délai d’achat**.
1. Cliquez sur **Enregistrer**.

> [!NOTE]
> Pour les articles fabriqués, le **délai de production standard** est utilisé en cas d’absence d’itinéraire pour l’article. Si un itinéraire actif a été associé à l’article, la planification générale planifiera la commande et calculera ses dates en fonction des heures d’acheminement et de la capacité des ressources (le cas échéant).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
