---
title: Besoins nets et informations sur l’origine des besoins
description: Cet article fournit des informations sur les besoins nets calculés et les informations d’origine des besoins.
author: t-benebo
ms.date: 7/28/2021
ms.topic: article
ms.search.form: ReqTransOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a31ff5490b08d92f0d966388b65de02bca25b050
ms.sourcegitcommit: 613be2f35e600ae1a1fa7ea2ae30e78984ca398a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2022
ms.locfileid: "9748436"
---
# <a name="net-requirements-and-pegging-information"></a>Besoins nets et informations sur l’origine des besoins

[!include [banner](../../includes/banner.md)]

Quand vous exécutez la planification dans la planification intégrée, il est important que vous compreniez sa sortie, comment l’offre existante couvre la demande et pourquoi une offre spécifique a été générée. Vous pouvez utiliser la page **Besoins nets** pour mieux comprendre les besoins calculés générés par la planification générale.

La page **Besoins nets** affiche les besoins nets que la planification générale a calculés pour le produit. Elle affiche également les paramètres de couverture qui ont été appliqués lors de l’exécution de la planification, une ventilation des totaux des besoins par type de transaction et des informations sur l’origine des besoins.

## <a name="open-the-net-requirements-page"></a>Ouvrir la page des besoins nets

Vous pouvez ouvrir la page **Besoins nets** de l’une des manières suivantes :

- Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**. Sélectionnez ou ouvrez un produit. Ensuite, dans le volet Actions, sous l’onglet **Plan**, dans le groupe **Besoin**, sélectionnez **Besoins nets**.
- Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**. Ouvrez une commande client. Puis, sur le raccourci **Lignes de commande client**, dans la barre d’outils, sélectionnez **Produit et approvisionnement \> Besoins nets**.
- Accédez à **Planification \> Planification \> Ordres prévisionnels**. Sélectionnez ou ouvrez un ordre prévisionnel. Ensuite, dans le volet Actions, sous l’onglet **Vue**, dans le groupe **Besoins**, sélectionnez **Profil des besoins**.

## <a name="use-the-net-requirements-page"></a>Utiliser la page des besoins nets

La page **Besoins nets** se compose de sections supérieure et inférieure. Le volet Actions de cette page comprend un bouton **Mettre à jour**. Lorsque ce bouton est sélectionné, un menu de commandes apparaît.

### <a name="select-a-master-plan-to-view"></a>Sélectionnez un plan directeur à afficher

Avant de passer en revue les besoins nets du produit, assurez-vous de sélectionner le plan directeur approprié dans le champ **Plan** en haut de la page.

### <a name="upper-section"></a>Partie supérieure

La partie supérieure de la page contient les onglets suivants :

- **Aperçu** – Voir les besoins de l’article des dimensions du produit.
- **Articles couverts** – Affichez les paramètres de couverture qui ont été utilisés lors du calcul des besoins.
- **Résumé** – Afficher une décomposition des totaux des besoins par type de transaction.
- **Période** – Affichez les réceptions, les sorties et le stock disponible à date pour chaque période définie par le modèle de période. Vous pouvez également obtenir une vue graphique stock disponible à date.

### <a name="lower-section"></a>Partie inférieure

La partie inférieure de la page contient les onglets suivants :

- **Aperçu** – Affichez la liste des besoins en produits qui ont été calculés pendant le cycle de planification générale, ainsi que les transactions de sortie et de réception qui correspondent aux besoins. Par défaut, la liste est triée par date de besoin. Lorsque vous sélectionnez un besoin, le raccourci **origine des besoins** dans la section inférieure affiche soit la source du besoin, soit les transactions qui remplissent l’exigence.
- **Général** – Afficher des informations détaillées sur le besoin sélectionné.
- **action** – Afficher les messages d’action pour les besoins.

### <a name="the-action-pane"></a>Le volet Actions

Les commandes suivantes sont disponibles dans le volet Actions :

- **Mettre à jour \> Plan directeur** – Exécuter la planification directement depuis la page **Besoins nets**.
- **Mettre à jour \> Planification prévisionnelles** – Exécuter la planification prévisionnelle directement depuis la page **Besoins nets**. L’optimisation de la planification ne prend pas en charge cette opération.
- **Mettre à jour \> Planification de la continuité** – Exécutez la planification de la continuité directement à partir de la page **Besoins nets**. L’optimisation de la planification ne prend pas en charge cette opération.

## <a name="example-scenario"></a>Exemple de scénario

Cet exemple montre comment les informations d’origine des besoins sont présentées sur la page **Besoins nets**.

### <a name="prerequisites"></a>Conditions préalables

Avant de travailler sur le scénario, préparez les conditions préalables suivantes :

1. Vous devez travailler sur un système où les exemples de données standard sont disponibles, et vous devez définir l’entité juridique sur *USMF*.
2. Cet exemple utilise le produit *1000*, qui fait partie des exemples de données USMF. Assurez-vous que ce produit est disponible et qu’il est configuré de la manière suivante :

    - **Type de commande par défaut :** *Commande fournisseur*
    - **Stock disponible :** *10,00*

3. Créez une commande client pour une quantité de *25,00* et un produit *1000*. Utilisez les dimensions de stockage où se trouve le stock disponible.
4. Exécuter une planification pour le plan directeur *DynPlan*.

### <a name="review-the-calculated-requirements"></a>Vérifier les besoins calculés

Ensuite, vous ouvrirez la page **Besoins nets** pour le produit *1000* pour examiner comment les besoins calculés correspondent les unes aux autres.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez le produit qui a une valeur **Numéro d’article** de *1000*.
1. Dans le volet Actions, sous l’onglet **Plan**, dans le groupe **Besoin**, sélectionnez **Besoins nets**.
1. Sur la page **Besoins nets**, définissez le champ **Planifier** à *DynPlan*.
1. Sur l’onglet **Aperçu** dans la partie inférieure de la page, vérifiez que les besoins suivantes sont répertoriées sous forme de lignes dans la grille.

    | Référence | Quantité des besoins | Cumul |
    |---|---|---|
    | Disponible | 10.00 | 10.00 |
    | Commandes fournisseur prévisionnelles | 15.00 | 25.00 |
    | Commande de vente | -25,00 | (Vide) |

    > [!NOTE]
    > Le champ **Quantité besoin** représente la quantité totale que le besoin requiert (si la valeur est négative) ou fournit (si la valeur est positive). Le champ **Accumulé** représente les quantités totales de réception et de sortie qui se sont accumulées tout au long de la période sélectionnée.

1. Sélectionnez la ligne de besoin *En stock*, puis, sur le raccourci **Origine des besoins**, passez en revue les besoins couvertes par cette offre. La ligne suivante devrait y apparaître.

    | Référence | Quantité des besoins | Quantité couverte |
    |---|---|---|
    | Commande de vente | -25,00 | -10,00 |

    Le stock disponible existant couvre partiellement la demande issue de la commande client.

    ![Informations d’origine des besoins pour le stock disponible](media/pegging-on-hand.png "Informations d’origine des besoins pour le stock disponible")

1. Sélectionnez la ligne de besoin *Commandes fournisseur prévisionnelles*, puis, sur le raccourci **Origine des besoins**, passez en revue les besoins couvertes par cette offre. La ligne suivante devrait y apparaître.

    | Référence | Quantité des besoins | Quantité couverte |
    |---|---|---|
    | Commande de vente | -25,00 | -15,00 |

    Étant donné que la commande client a déjà été partiellement couverte, le système crée une commande fournisseur prévisionnelle pour la quantité non couverte restante.

    ![Informations sur l’origine des besoins pour la commande fournisseur prévisionnelle](media/pegging-planned-purchase-order.png "Informations sur l’origine des besoins pour la commande fournisseur prévisionnelle")

1. Sélectionnez la ligne de besoin *Commande client*, puis, sur le raccourci **Origine des besoins**, passez en revue les besoins qui couvrent cette demande. Les lignes suivantes devraient y apparaître.

    | Référence | Quantité des besoins | Quantité couverte |
    |---|---|---|
    | Disponible | 10.00 | 10.00 |
    | Commandes fournisseur prévisionnelles | 15.00 | 15.00 |

    ![Informations sur l’origine des besoins pour la commande client](media/pegging-planned-purchase-order.png "Informations sur l’origine des besoins pour la commande client")

> [!NOTE]
> Le besoin *Stock de Sécurité* n’est pas inclus sur la page **Besoins nets**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
