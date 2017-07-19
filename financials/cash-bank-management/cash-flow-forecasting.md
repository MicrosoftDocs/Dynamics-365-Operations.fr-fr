---
title: "Prévision des flux de trésorerie"
description: "Cette rubrique fournit une vue d'ensemble du processus de prévisions des flux de trésorerie. Elle décrit également comment les prévisions des flux de trésorerie sont intégrées avec d'autres modules dans le système."
author: saraschi
manager: AnnBe
ms.date: 05/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: sarasch
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 3abf4b151b177095b71d44e9a6c9fd8541eaa64e
ms.openlocfilehash: a8ccd99431178c3cb4e73e7cd199de8e0845d716
ms.contentlocale: fr-fr
ms.lasthandoff: 06/14/2017

---

# <a name="cash-flow-forecasting"></a>Prévision des flux de trésorerie

[!include[banner](../includes/banner.md)]

Vous pouvez utiliser les outils de prévisions des flux de trésorerie pour analyser les besoins à venir en devises et vous permettre d'estimer les futurs besoins en disponibilités de votre société. Pour obtenir une prévision des flux de trésorerie, vous devez effectuer les tâches suivantes :

- Identifiez et répertoriez tous les comptes de liquidités. Il s'agit des comptes de disponibilités de la société.
- Configurer le comportement des prévisions des transactions qui affectent les comptes de liquidités de la société.

Une fois ces tâches effectuées, vous pouvez calculer et analyser les prévisions des flux de trésorerie et les futurs besoins de devise.

## <a name="cash-flow-forecasting-integration"></a>Intégration de la prévision de flux de trésorerie

La prévision des flux de trésorerie peut être intégrée avec les modules Comptabilité, Comptabilité fournisseur, Comptabilité client, Budget et Gestion des stocks. Le processus de prévisions utilise les informations de transactions entrées dans le système, et le processus de calcul prévoit l'impact de trésorerie prévu de chaque transaction. Les types de transactions sont considérées lorsque le flux de trésorerie est calculé :

- **Commandes client** – Commandes client qui ne sont pas encore facturées et qui aboutissent à des ventes physiques ou financières.
- **Commandes fournisseur** – Commandes fournisseur qui ne sont pas encore facturées et qui aboutissent à des achats physiques ou financiers.
- **Comptabilité client** – Transactions client en cours (factures qui n'ont pas encore été payées).
- **Comptabilité fournisseur** – Transactions fournisseur en cours (factures qui n'ont pas encore été payées).
- **Écritures comptables** – Transactions où il est spécifié qu'une prochaine validation aura lieu.
- **Écritures de registre budgétaires** – Écritures de registre budgétaires qui sont sélectionnées pour les prévisions des flux de trésorerie.
- **Prévisions de la demande** – Lignes de modèle de prévisions de stock sélectionnées pour les prévisions des flux de trésorerie.
- **Prévisions d'approvisionnement** – Lignes de modèle de prévisions de stock sélectionnées pour les prévisions des flux de trésorerie.

Bien qu'il n'y a pas d'intégration directe avec le module Gestion de projets et Comptabilité, il existe plusieurs façons d'inclure les transactions de projet dans les prévisions des flux de trésorerie. Les factures de projet validées sont incluses dans la prévision dans le cadre des transactions client en cours. Les commandes client et fournisseur créées pour un projet sont incluses dans la prévision comme les commandes en cours après leur saisie dans le système. Vous pouvez également transférer des prévisions de projet vers un modèle de budget comptable. Ce modèle de budget comptable est ensuite inclus dans les prévisions des flux de trésorerie dans les écritures de registre budgétaires.

## <a name="configuration"></a>Configuration

Pour configurer le processus de prévisions des flux de trésorerie, utilisez la page **Configuration des prévisions de flux de trésorerie**. Dans cette page, vous spécifiez les comptes de liquidités pour effectuer le suivi, ainsi que les comportements des prévisions par défaut pour chaque région.

### <a name="general-ledger"></a>Comptabilité

Vous devez tout d'abord définir les comptes de liquidités que vous souhaitez suivre via les prévisions des flux de trésorerie. Généralement, ces comptes de liquidités sont des comptes principaux associés aux comptes bancaires qui vont recevoir et décaisser les liquidités. Dans la page **Configuration des prévisions de flux de trésorerie**, sous l'onglet **Comptabilité**, sélectionnez les comptes principaux pour inclure des prévisions. Si un compte bancaire a été associé au compte principal sur la page **Compte bancaire**, il s'affiche dans le champ **Compte bancaire**.

Vous pouvez paramétrer une prévision de flux de trésorerie dépendante pour un compte principal contenant des transactions directement liées à des transactions dans un autre compte principal. Chaque ligne ajoutée dans la section **Dans les comptes des personnes à charge** crée un montant de prévision du flux de trésorerie dans un compte principal dépendant. Ce montant est un pourcentage des montants de flux de trésorerie du compte principal sélectionné.

Premièrement, définissez le champ **Compte principal** pour le compte principal dans lequel il est prévu que des transactions se produisent initialement. Définissez le champ **Compte principal dépendant** pour le compte qui sera affecté par la transaction initiale par rapport au compte principal primaire. Définissez les valeurs appropriées pour les autres champs de la ligne. Vous pouvez modifier la valeur affichée dans le champ **Pourcentage** pour voir l'effet du compte principal primaire sur le compte principal dépendant. Pour une prévision de vente ou d'achat, sélectionnez une valeur **Conditions de paiement** habituelle pour la plupart des clients ou des fournisseurs. Définissez le champ **Type de validation** pour le type de validation attendu associé aux prévisions des flux de trésorerie.

### <a name="accounts-payable"></a>Module Comptabilité fournisseur

Vous pouvez calculer les prévisions pour les achats à l'aide des options de paramétrage sous l'onglet **Comptabilité fournisseur** de la page **Configuration des prévisions de flux de trésorerie**. Avant de pouvoir configurer les prévisions des flux de trésorerie du module Comptabilité fournisseur, vous devez configurer les conditions de paiement, les groupes de fournisseurs et les profils de validation fournisseur.

Dans la section **Valeurs par défaut de prévision d'achat**, vous pouvez sélectionner les comportements d'achat par défaut pour les prévisions des flux de trésorerie. Trois champs déterminent la période de l'impact de trésorerie : **Intervalle entre la date de livraison et la date de facture**, **Conditions de paiement** et **Intervalle entre la date d'échéance de la facture et le paiement**. La prévision utilise le paramètre par défaut pour le champ **Conditions de paiement** uniquement si une valeur n'est pas spécifiée lors de la transaction. Utilisez une condition de paiement pour décrire le nombre de jours le plus courant pour chaque étape du processus.

Le champ **Compte de liquidités pour les paiements** spécifie le compte de liquidités qui est le plus souvent utilisé pour les paiements. Utilisez le champ **Pourcentage du montant à répartir dans les prévisions de flux de trésorerie** pour indiquer si un pourcentage des montants doit être utilisé lors des prévisions. Laissez ce champ vide si les montants de transaction détaillés sont utilisés lors des prévisions.

Vous pouvez remplacer le paramètre par défaut pour le champ **Intervalle entre la date d'échéance de la facture et le paiement** pour des groupes de fournisseurs spécifiques. La prévision utilise la valeur par défaut de la section **Valeurs par défaut de prévision d'achat** à moins qu'une valeur différente ne soit spécifiée pour le groupe de fournisseurs qui est lié au fournisseur lors de la transaction. Pour remplacer la valeur par défaut, sélectionnez un groupe de fournisseurs, puis définissez la nouvelle valeur pour le champ **Délai d'achat**.

Vous pouvez remplacer le paramètre par défaut du champ **Compte de liquidités** pour des profils de validation fournisseur spécifiques. La prévision utilise la valeur par défaut de la section **Valeurs par défaut de prévision d'achat** à moins qu'un autre compte de liquidités ne soit spécifié pour le profil de validation qui est lié au fournisseur lors de la transaction. Pour remplacer la valeur par défaut, sélectionnez un profil de validation, puis spécifiez le compte de liquidités devant être affecté.

### <a name="accounts-receivable"></a>Module Comptabilité client

Vous pouvez calculer les prévisions pour les ventes à l'aide des options de paramétrage sous l'onglet **Comptabilité client** de la page **Configuration des prévisions de flux de trésorerie**. Avant de pouvoir configurer les prévisions des flux de trésorerie du module Comptabilité client, vous devez configurer les conditions de paiement, les groupes de clients et les profils de validation client.

Dans la section **Valeurs par défaut des prévisions de ventes**, vous pouvez sélectionner les comportements de vente par défaut pour les prévisions des flux de trésorerie. Trois champs déterminent la période de l'impact de trésorerie : **Intervalle entre la date d'expédition et la date de facture**, **Conditions de paiement** et **Intervalle entre la date d'échéance de la facture et le paiement**. La prévision utilise le paramètre par défaut pour le champ **Conditions de paiement** uniquement si une valeur n'est pas spécifiée lors de la transaction. Utilisez une condition de paiement pour décrire le nombre de jours le plus courant pour chaque étape du processus. 

Le champ **Compte de liquidités pour les paiements** spécifie le compte de liquidités qui est le plus souvent utilisé pour les paiements. Utilisez le champ **Pourcentage du montant à répartir dans les prévisions de flux de trésorerie** pour indiquer si un pourcentage des montants doit être utilisé lors des prévisions. Laissez ce champ vide si les montants de transaction détaillés sont utilisés lors des prévisions.

Vous pouvez remplacer le paramètre par défaut pour le champ **Intervalle entre la date d'échéance de la facture et le paiement** pour des groupes de clients spécifiques. La prévision utilise la valeur par défaut de la section **Valeurs par défaut des prévisions de ventes** à moins qu'une valeur différente ne soit spécifiée pour le groupe de clients qui est lié au client lors de la transaction. Pour remplacer la valeur par défaut, sélectionnez un groupe de clients, puis définissez la nouvelle valeur pour le champ **Délai de vente**.

Vous pouvez remplacer le paramètre par défaut du champ **Compte de liquidités** pour des profils de validation client spécifiques. La prévision utilise la valeur par défaut de la section **Valeurs par défaut des prévisions de ventes** à moins qu'un autre compte de liquidités ne soit spécifié pour le profil de validation qui est lié au client lors de la transaction. Pour remplacer la valeur par défaut, sélectionnez un profil de validation, puis définissez le compte de liquidités devant être affecté.

### <a name="budgeting"></a>Budget

Les budgets créés à partir des modèles de budget peuvent être inclus dans les prévisions des flux de trésorerie. Dans l'onglet **Budgétisation** de la page **Configuration des prévisions de flux de trésorerie**, sélectionnez les modèles de budget à inclure dans la prévision. Par défaut, de nouvelles écritures de registre budgétaires sont incluses dans les prévisions après l'activation du modèle de budget pour les prévisions des flux de trésorerie. L'inclusion dans les prévisions des flux de trésorerie peut être remplacée sur des écritures de registre budgétaires.

### <a name="inventory-management"></a>Gestion des stocks

Les approvisionnements et les prévisions de la demande de stock peuvent être inclus dans les prévisions des flux de trésorerie. Dans l'onglet **Gestion des stocks** de la page **Configuration des prévisions de flux de trésorerie**, sélectionnez le modèle de budget à inclure dans la prévision de flux de trésorerie. L'inclusion dans les prévisions des flux de trésorerie peut être remplacée sur chaque ligne d'approvisionnement et de prévision de la demande.

### <a name="calculation"></a>Calcul

Avant de pouvoir afficher les analyses de prévisions des flux de trésorerie, vous devez exécuter le processus de calcul du flux de trésorerie. Le processus de calcul projettera les effets de trésorerie futurs des transactions qui ont été saisies.

Calculez les prévisions des flux de trésorerie à l'aide de la page **Calculer les prévisions de flux de trésorerie**. Vous pouvez calculer les prévisions des flux de trésorerie complètes ou les prévisions des flux de trésorerie incrémentielles. 

- Pour effacer toutes les transactions de prévisions des flux de trésorerie et recalculer, définissez le champ **Méthode de calcul des prévisions de flux de trésorerie** sur **Total**. Il est recommandé d'utiliser cette méthode si vous n'avez pas actualisé les prévisions des flux de trésorerie depuis un certain temps. 
- Pour mettre à jour les informations de flux de trésorerie existantes pour les nouvelles transactions uniquement, définissez le champ **Méthode de calcul des prévisions de flux de trésorerie** sur **Nouveau**. La page affiche la date à laquelle vous avez calculé le flux de trésorerie pour la dernière fois.

Vous pouvez également utiliser des traitements par lots pour les prévisions des flux de trésorerie. Pour avoir l'assurance que les analyses de prévision sont régulièrement mises à jour, paramétrez un processus de traitement par lots récurrent pour le calcul des prévisions des flux de trésorerie.

### <a name="reporting"></a>Génération d'états

Une fois les prévisions des flux de trésorerie calculées, vous devez actualiser les informations d'entité associées pour la génération d'états analytiques. Dans la page **Magasin des entités**, sélectionnez la mesure **LedgerCovLiquidityMeasurement aggregate**, puis cliquez sur **Actualiser**.

Il existe deux espaces de travail contenant des données de prévision de flux de trésorerie. L'un des espaces de travail contient des données concernant toutes les sociétés, et l'autre espace de travail contient les données de la société actuelle.

L'accès à l'espace de travail pour toutes les sociétés est contrôlé par le droit **Afficher l'espace de travail de toutes les sociétés du flux de trésorerie**. Par défaut, l'espace de travail **Aperçu de la trésorerie - toutes les sociétés** est disponible pour les rôles suivants :

- Président directeur général
- Directeur financier
- Contrôleur financier

L'accès à l'espace de travail pour la société actuelle est contrôlé par le droit **Afficher l'espace de travail de la société actuelle du flux de trésorerie**. Par défaut, l'espace de travail **Aperçu de la trésorerie - société actuelle** est disponible pour les rôles suivants :

- Comptable
- Responsable comptabilité
- Chef comptable
- Responsable Comptabilité fournisseur
- Responsable Comptabilité client

L'espace de travail **Aperçu de la trésorerie - toutes les sociétés** affiche les analyses de prévisions de flux de trésorerie dans la devise du système. La devise système et le type de taux de change du système utilisés pour les analyses sont définis dans la page **Paramètres système**. Cet espace de travail affiche une vue d'ensemble des prévisions des flux de trésorerie et les soldes du compte bancaire pour toutes les sociétés. Un graphique des encaissements et décaissements fournit une vue d'ensemble des futurs mouvements et soldes de disponibilités dans la devise du système, ainsi que des informations détaillées sur les transactions de prévision. Vous pouvez également afficher les soldes de devise prévus.

L'espace de travail **Aperçu de la trésorerie - société actuelle** affiche les analyses de prévisions des flux de trésorerie dans la devise comptable définie pour la société. La devise comptable utilisée pour les analyses est définie sur la page **Comptabilité**. Cet espace de travail affiche une vue d'ensemble des prévisions des flux de trésorerie et les soldes du compte bancaire pour la société actuelle. Un graphique des encaissements et décaissements fournit une vue d'ensemble des futurs mouvements et soldes de disponibilités dans la devise comptable, ainsi que des informations détaillées sur les transactions de prévision. Vous pouvez également afficher les soldes de devise prévus.

Pour plus d'informations sur les analyses de prévisions des flux de trésorerie, voir la rubrique de contenu Vue d'ensemble des disponibilités Power BI.

En outre, vous pouvez afficher des données de prévision des flux de trésorerie pour des comptes et des articles spécifiques dans les pages suivantes :

- **Balance comptable** : Sélectionnez **Prévisions de flux de trésorerie** pour afficher les futurs flux de trésorerie pour le compte principal sélectionné.
- **Toutes les commandes client** : Dans l'onglet **Facture**, sélectionnez **Prévisions de flux de trésorerie** pour afficher l'impact de disponibilités prévu de la commande client sélectionnée.
- **Toutes les commandes fournisseur** : Dans l'onglet **Facture**, sélectionnez **Prévisions de flux de trésorerie** pour afficher l'impact de disponibilités prévu de la commande fournisseur sélectionnée.
- **Prévision d'approvisionnement** : Sélectionnez **Prévisions de flux de trésorerie** pour afficher les futurs flux de trésorerie associés à la prévision d'approvisionnement de l'article sélectionné.
- **Prévision de la demande** : Sélectionnez **Prévisions de flux de trésorerie** pour afficher les futurs flux de trésorerie associés à la prévision de demande de l'article sélectionné.


