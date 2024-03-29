---
title: Vue d’ensemble du module de gestion des remises
description: Cet article fournit une vue d’ensemble du module de gestion des remises pour Microsoft Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: cfba391536559ed3a967d0aafe2e352486777dda
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873635"
---
# <a name="rebate-management-module-overview"></a>Vue d’ensemble du module de gestion des remises

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser le module **Gestion des remises** pour créer des contrats, des offres ou des accords entre votre entreprise et ses clients ou fournisseurs et pouvoir en conséquence calculer les remises, les déductions et les redevances. La gestion des remises suit et gère les opérations de remise et de déduction dans un emplacement central où les utilisateurs peuvent les créer, les examiner et les traiter efficacement.

La gestion des remises prend en charge la création, la maintenance et le traitement des *remises*. Une remise est le remboursement d’une partie du prix d’achat par un vendeur ou un acheteur. Les remises sont généralement basées sur l’achat d’une quantité ou d’une valeur spécifique de marchandises au cours d’une période donnée. Contrairement aux réductions, les remises sont effectuées une fois le montant de l’achat entièrement facturé.

La gestion des remises prend également en charge les *déductions*. Une déduction est une compensation, une contrepartie ou une redevance payée soit pour une licence, soit pour le privilège d’utiliser une propriété intellectuelle telle qu’une marque, un droit d’auteur ou un brevet, ou pour le privilège d’utiliser une ressource naturelle à des fins telles que la pêche, la chasse ou l’exploitation minière. Les déductions sont généralement calculées en pourcentage des revenus ou des bénéfices tirés de l’utilisation réalisée. Plus la propriété intellectuelle ou la ressource naturelle est utilisée, plus la déduction réalisée est importante.

De plus, la gestion des remises prend en charge les *redevances* client. Les redevances sont des paiements qu’une partie effectue au titulaire de la licence ou au franchisé pour le droit d’utiliser un actif.

La gestion des remises vous permet de définir des profils de validation pour les provisions, les remises et les annulations. En outre, les validations peuvent être définies pour un client ou un fournisseur spécifique. De cette manière, les accords qui ne s’appliquent pas à tous les scénarios client ou fournisseur peuvent être suivis via des validations.

Les transactions de remise sont automatiquement générées, en fonction de la méthode de calcul sélectionnée et planifiée dans les traitements par lots. De plus, vous pouvez configurer des workflows pour gérer, réviser et approuver les contrats.

## <a name="basis-calculation"></a>Calcul de la base

Les remises client, les redevances client et les remises fournisseur peuvent toutes utiliser une base différente, en fonction des besoins de votre entreprise :

- Les remises client peuvent être basées sur des commandes client, des notes de livraison ou des factures.
- Les redevances client peuvent être basées sur des commandes client, des notes de livraison ou des factures payées.
- Les remises fournisseur peuvent être basées sur des commandes fournisseur ou des commandes client. Elles peuvent être calculées en fonction des produits achetés auprès du fournisseur et vendus aux clients via des factures de vente.

## <a name="flexible-calculations"></a>Calculs flexibles

Les périodes de calcul des remises sont disponibles pour les accords client et les accords fournisseur. Une période de calcul définit la durée de l’accord, la fréquence de calcul et la période de calcul. Les remises peuvent être cumulées en fonction des quantités des commandes client ou des montants des produits éligibles au cours de la période de remise.

Pour chaque calcul du contrat, l’une des périodes suivantes peut être définie :

- Facture
- Jour
- Semaine
- Mois
- Trimestre
- Année
- Période personnalisée
- Tout multiple de l’une des périodes répertoriées précédemment

Le calcul peut être appliqué à des clients et produits individuels, à des groupes de clients et de produits, ou à tous les clients et produits. Les remises qui ont plusieurs lignes de détail peuvent avoir différentes plages de dates éligibles. Les délais de provision et de revendication peuvent différer. Par exemple, les provisions peuvent être traitées tous les jours, tandis que les revendications sont traitées une fois par mois.

Les remises peuvent être configurées en fonction de nombreux paramètres différents. Par exemple, elles peuvent être configurées sous forme de pourcentage, de taux ou de montant fixe. Il existe quatre méthodes de calcul principales :

- Par paliers
- Cumulé
- Roulant
- Valeur totale

Les résultats du calcul de la remise peuvent également être réduits par d’autres remises, selon que la remise est configurée pour être calculée en fonction du montant net.

Du côté du fournisseur, les remises basées sur les commandes client peuvent calculer le prix en fonction d’une règle Premier entré, premier sorti (FIFO), du dernier prix d’achat, du prix d’achat moyen ou du prix de vente.

## <a name="rebate-target-transactions"></a>Transactions cible de remise

Les résultats générés par l’accord de remise ou le contrat peuvent être des éléments financiers ou des articles.

Les résultats financiers sont déterminés par le type de règlement affecté au contrat à partir du profil de validation. Ces résultats peuvent inclure des journaux de déduction client, des factures financières et des factures fournisseur. À des fins de vérification, les transactions cibles des remises financières incluent une référence au contrat de remise d’origine.

Les sorties d’article créent une commande client d’article gratuit pour les remises client et une commande fournisseur pour les remises fournisseur. Les transactions cibles de remise d’article contiennent des options permettant de déterminer quelle référence de remise doit être saisie sur la commande client ou la commande fournisseur d’articles gratuits.

## <a name="accurate-rebate-calculations"></a>Calculs précis des remises

La combinaison des accords associés, la fréquence des calculs, la base de calcul et la méthode de calcul sélectionnée déterminent l’exactitude et la précision des calculs de remise. Les provisions de remise peuvent être utilisées pour régulariser les valeurs validées et revendiquées.

Les provisions peuvent être gérées quotidiennement, hebdomadairement, mensuellement ou selon une période personnalisée. Cependant, la fonctionnalité peut répartir ou payer la remise, ou en recevoir le paiement, à n’importe quelle fréquence définie qui est de la même longueur ou plus longue que la périodicité de la provision. Les annulations utilisent la même fréquence que la remise. Les utilisateurs peuvent facilement ajuster un plan ou des montants de paiement à tout moment pendant le paiement.

Les utilisateurs n’ont plus à gérer les accords ou les provisions en deux étapes. Les provisions et annulations sont validées directement dans la comptabilité. De plus, les avoirs peuvent être créés automatiquement. Par conséquent, il y a une intégration complète avec la comptabilité fournisseur et la comptabilité client. Lors du traitement, les calculs peuvent prendre en compte les remises de règlement, les factures payées, les remises commerciales et les avoirs existants pour garantir que les montants et les valeurs sont calculés avec précision.

Lorsque les remises sont calculées, le processus crée des transactions qui peuvent être examinées avant la validation. Un processus distinct valide les transactions de gestion des remises. Il est alors possible de créer un journal, un avoir ou une transaction de débit lors de la validation des transactions proposées. Il est possible d’obtenir des relevés de déclaration et des listes de transactions aux fins de conformité, d’efficacité et de transparence.

## <a name="guaranteed-royalty-payments"></a>Paiement des redevances garanties

Dans la gestion des remises, la génération automatique de paiements permet de gérer les redevances rapidement et facilement, même lorsque des minimums garantis s’appliquent.

## <a name="maximizing-spend-versus-rebates"></a>Maximiser les dépenses par rapport aux remises

Les vendeurs et les produits peuvent être regroupés par secteur de vente, et différents accords peuvent être proposés, selon le pays ou la région de la transaction. Lorsque les utilisateurs sélectionnent des produits, ils peuvent définir les articles inclus et le nombre d’articles qui seront utilisés dans le règlement de la remise.
