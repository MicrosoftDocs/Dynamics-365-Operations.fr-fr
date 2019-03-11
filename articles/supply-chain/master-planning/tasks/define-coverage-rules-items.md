---
title: Définir des règles de couverture pour les articles
description: Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 02aa3b2b7924cdf6317225bfce23f182aa390b8c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "320625"
---
# <a name="define-coverage-rules-for-items"></a>Définir des règles de couverture pour les articles

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cet procédure indique comment créer des règles de couverture et remplacer des paramètres de couverture pour un article spécifique. Il indique également comment spécifier les paramètres de stock par défaut.


## <a name="create-a-coverage-group"></a>Créer un groupe de couverture
1. Allez dans Groupes de couverture.
2. Cliquez sur Nouveau.
3. Dans le champ Groupe de couverture, tapez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Calendrier, tapez une valeur.
    * Choisissez le calendrier que la planification utilise pour créer des suggestions de réapprovisionnement pour les articles de ce groupe.  
6. Dans le champ Code couverture, sélectionnez une option.
    * Sélectionnez Conditions requises pour cette procédure.  
7. Entrez 90 dans le champ Plage de gestion de la couverture (jours).
    * Pour les articles de ce groupe, la planification crée des suggestions de réapprovisionnement jusqu'à 90 jours dans le futur.  
8. Entrez 1 dans le champ Jours négatifs.
9. Entrez 1 dans le champ Jours positifs.
10. Développez ou réduisez la section Autre.
11. Entrez 1 dans le champ Marge de réception ajoutée à la date de besoin.
    * Par exemple, si la marge de réception est définie sur une journée et si une ligne de commande fournisseur est prévue pour réception le 15 mai, la planification calcule le 16 mai comme date de réception ajustée.  
12. Entrez 1 dans le champ Marge de sortie déduite de la date de besoin.
    * Par exemple, si la marge de sécurité est définie sur une journée et si une ligne de commande client est prévue pour livraison le 15 mai, la planification calcule le 14 mai comme date de livraison ajustée.  
13. Entrez 1 dans le champ Marge de renouvellement ajouté au délai de l'article.
14. Cliquez sur Enregistrer.

## <a name="create-a-new-product"></a>Créer un nouveau produit
1. Allez dans Produits lancés.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro du produit, saisissez une valeur.
4. Dans le champ Nom du produit, saisissez une valeur.
5. Dans le champ groupe de modèles d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ Groupe d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Dans le champ Groupe de dimensions de stockage, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
12. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
14. Dans le champ Groupe de dimensions de suivi, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
15. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
17. Cliquez sur OK.

## <a name="setup-default-order-settings"></a>Configurer les paramètres de commande par défaut
1. Cliquez sur Planifier dans le volet Actions.
2. Cliquez sur Paramètres de commande par défaut.
3. Dans le champ Site d'achat, tapez le site utilisé comme valeur par défaut lorsque des commandes fournisseur sont créées.
4. Dans le champ Site de stock, tapez le site de stockage de l'article.
5. Développez ou réduisez la section Stock.
6. Définissez Multiple sur 10.
7. Définissez Quantité de commande min. sur 10.
8. Définissez Quantité de commande max. sur 100.
9. Définissez Quantité de commande standard sur 10.
10. Entrez un numéro dans le champ Délai d'achat.
11. Activez ou désactivez la case à cocher Jours ouvrables.
12. Cliquez sur Enregistrer.
13. Sélectionnez « Commande fournisseur » dans le champ Type de commande par défaut.
14. Cliquez sur Enregistrer.
15. Fermez la page.
    * Fermez la page Paramètres de commande par défaut.  

## <a name="add-an-item-to-a-coverage-group"></a>Ajouter un article à un groupe de couverture
1. Développez ou réduisez la section Plan.
2. Dans le champ Groupe de couverture, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez le groupe de couverture créé.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="create-item-coverage-rules"></a>Créer des règles de couverture d'article
1. Cliquez sur Planifier dans le volet Actions.
2. Cliquez sur Couverture de l'article.
3. Cliquez sur Nouveau.
4. Cliquez sur l'onglet Général.
5. Activez la case à cocher sous l'en-tête Remplacer les paramètres du groupe de couverture.
6. Entrez 60 dans le champ Plage de gestion de la couverture (jours).
    * Même si des articles du groupe de couverture Besoin sont planifiés à 90 jours dans le futur, cet article sera planifié à 60 jours dans le futur.  
7. Entrez 2 dans le champ Jours négatifs.
8. Entrez 2 dans le champ Jours positifs.
9. Cliquez sur l'onglet Délai.
10. Activez la case à cocher dans l'en-tête Achat.
11. Entrez 5 dans le champ Délai d'achat.
12. Cliquez sur Enregistrer.

