---
title: Prévision des flux de trésorerie
description: Cette rubrique fournit une vue d’ensemble du processus de prévisions des flux de trésorerie. Elle décrit également comment les prévisions des flux de trésorerie sont intégrées avec d’autres modules dans le système.
author: panolte
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 4979a57c966f25dba62a944a4e44086e5f6aed28
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712535"
---
# <a name="cash-flow-forecasting"></a>Prévision des flux de trésorerie

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Vous pouvez utiliser les outils de prévisions des flux de trésorerie pour analyser les besoins à venir en devises et vous permettre d’estimer les futurs besoins en disponibilités de votre société. Pour obtenir une prévision des flux de trésorerie, vous devez effectuer les tâches suivantes :

- Identifiez et répertoriez tous les comptes de liquidités. Il s’agit des comptes de disponibilités de la société.
- Configurer le comportement des prévisions des transactions qui affectent les comptes de liquidités de la société.

Une fois ces tâches effectuées, vous pouvez calculer et analyser les prévisions des flux de trésorerie et les futurs besoins de devise.

## <a name="cash-flow-forecasting-integration"></a>Intégration de la prévision de flux de trésorerie

La prévision des flux de trésorerie peut être intégrée avec les modules Comptabilité, Comptabilité fournisseur, Comptabilité client, Budget et Gestion des stocks. Le processus de prévisions utilise les informations de transactions entrées dans le système, et le processus de calcul prévoit l’impact de trésorerie prévu de chaque transaction. Les types de transactions sont considérées lorsque le flux de trésorerie est calculé :

- **Commandes client** – Commandes client qui ne sont pas encore facturées et qui aboutissent à des ventes physiques ou financières.
- **Factures financières** – Les Factures financières qui ne sont pas encore validées et qui se traduisent par des ventes financières. 
- **Commandes fournisseur** – Commandes fournisseur qui ne sont pas encore facturées et qui aboutissent à des achats physiques ou financiers.
- **Comptabilité client** – Transactions client en cours (factures qui n’ont pas encore été payées).
- **Comptabilité fournisseur** – Transactions fournisseur en cours (factures qui n’ont pas encore été payées).
- **Écritures comptables** – Transactions où il est spécifié qu’une prochaine validation aura lieu.
- **Écritures de registre budgétaires** – Écritures de registre budgétaires qui sont sélectionnées pour les prévisions des flux de trésorerie.
- **Prévisions de la demande** – Lignes de modèle de prévisions de stock sélectionnées pour les prévisions des flux de trésorerie.
- **Prévisions d’approvisionnement** – Lignes de modèle de prévisions de stock sélectionnées pour les prévisions des flux de trésorerie.
- **Source de données externe** – Données externes saisies ou importées dans les prévisions de trésorerie à l’aide de modèles de feuilles de calcul.
- **Prévisions de projet** – Gestion de projet et prévisions comptables à l’aide d’un modèle de prévision.
- **Paiements à l’administration fiscale des ventes de la trésorerie** – Montants et calendrier de paiement prévus par l’autorité fiscale qui entraînent des paiements financiers. Activez la fonctionnalité Paiements à l’administration fiscale des ventes de trésorerie.

## <a name="configuration"></a>Configuration

Pour configurer le processus de prévisions des flux de trésorerie, utilisez la page **Configuration des prévisions de flux de trésorerie**. Dans cette page, vous spécifiez les comptes de liquidités pour effectuer le suivi, ainsi que les comportements des prévisions par défaut pour chaque région.

### <a name="general-ledger"></a>Comptabilité

Vous devez tout d’abord définir les comptes de liquidités que vous souhaitez suivre via les prévisions des flux de trésorerie. Généralement, ces comptes de liquidités sont des comptes principaux associés aux comptes bancaires qui vont recevoir et décaisser les liquidités. Dans la page **Configuration des prévisions de flux de trésorerie**, sous l’onglet **Comptabilité**, sélectionnez les comptes principaux pour inclure des prévisions. Si un compte bancaire a été associé au compte principal sur la page **Compte bancaire**, il s’affiche dans le champ **Compte bancaire**.

Vous pouvez paramétrer une prévision de flux de trésorerie dépendante pour un compte principal contenant des transactions directement liées à des transactions dans un autre compte principal. Chaque ligne ajoutée dans la section **Dans les comptes des personnes à charge** crée un montant de prévision du flux de trésorerie dans un compte principal dépendant. Ce montant est un pourcentage des montants de flux de trésorerie du compte principal sélectionné.

Premièrement, définissez le champ **Compte principal** pour le compte principal dans lequel il est prévu que des transactions se produisent initialement. Définissez le champ **Compte principal dépendant** pour le compte qui sera affecté par la transaction initiale par rapport au compte principal primaire. Définissez les valeurs appropriées pour les autres champs de la ligne. Vous pouvez modifier la valeur affichée dans le champ **Pourcentage** pour voir l’effet du compte principal primaire sur le compte principal dépendant. Pour une prévision de vente ou d’achat, sélectionnez une valeur **Conditions de paiement** habituelle pour la plupart des clients ou des fournisseurs. Définissez le champ **Type de validation** pour le type de validation attendu associé aux prévisions des flux de trésorerie.

### <a name="accounts-payable"></a>Module Comptabilité fournisseur

Vous pouvez calculer les prévisions pour les achats à l’aide des options de paramétrage sous l’onglet **Comptabilité fournisseur** de la page **Configuration des prévisions de flux de trésorerie**. Avant de pouvoir configurer les prévisions des flux de trésorerie du module Comptabilité fournisseur, vous devez configurer les conditions de paiement, les groupes de fournisseurs et les profils de validation fournisseur.

Dans la section **Valeurs par défaut de prévision d’achat**, vous pouvez sélectionner les comportements d’achat par défaut pour les prévisions des flux de trésorerie. Trois champs déterminent la période de l’impact de trésorerie : **Intervalle entre la date de livraison et la date de facture**, **Conditions de paiement** et **Intervalle entre la date d’échéance de la facture et le paiement**. La prévision utilise le paramètre par défaut pour le champ **Conditions de paiement** uniquement si une valeur n’est pas spécifiée lors de la transaction. Utilisez une condition de paiement pour décrire le nombre de jours le plus courant pour chaque étape du processus.

Le champ **Compte de liquidités pour les paiements** spécifie le compte de liquidités qui est le plus souvent utilisé pour les paiements. Utilisez le champ **Pourcentage du montant à répartir dans les prévisions de flux de trésorerie** pour indiquer si un pourcentage des montants doit être utilisé lors des prévisions. Laissez ce champ vide si les montants de transaction détaillés sont utilisés lors des prévisions.

Vous pouvez remplacer le paramètre par défaut pour le champ **Intervalle entre la date d’échéance de la facture et le paiement** pour des groupes de fournisseurs spécifiques. La prévision utilise la valeur par défaut de la section **Valeurs par défaut de prévision d’achat** à moins qu’une valeur différente ne soit spécifiée pour le groupe de fournisseurs qui est lié au fournisseur lors de la transaction. Pour remplacer la valeur par défaut, sélectionnez un groupe de fournisseurs, puis définissez la nouvelle valeur pour le champ **Délai d’achat**.

Vous pouvez remplacer le paramètre par défaut du champ **Compte de liquidités** pour des profils de validation fournisseur spécifiques. La prévision utilise la valeur par défaut de la section **Valeurs par défaut de prévision d’achat** à moins qu’un autre compte de liquidités ne soit spécifié pour le profil de validation qui est lié au fournisseur lors de la transaction. Pour remplacer la valeur par défaut, sélectionnez un profil de validation, puis spécifiez le compte de liquidités devant être affecté.

### <a name="accounts-receivable"></a>Module Comptabilité client

Vous pouvez calculer les prévisions pour les ventes à l’aide des options de paramétrage sous l’onglet **Comptabilité client** de la page **Configuration des prévisions de flux de trésorerie**. Avant de pouvoir configurer les prévisions des flux de trésorerie du module Comptabilité client, vous devez configurer les conditions de paiement, les groupes de clients et les profils de validation client.

Dans la section **Valeurs par défaut des prévisions de ventes**, vous pouvez sélectionner les comportements de vente par défaut pour les prévisions des flux de trésorerie. Trois champs déterminent la période de l’impact de trésorerie : **Intervalle entre la date d’expédition et la date de facture**, **Conditions de paiement** et **Intervalle entre la date d’échéance de la facture et le paiement**. La prévision utilise le paramètre par défaut pour le champ **Conditions de paiement** uniquement si une valeur n’est pas spécifiée lors de la transaction. Utilisez une condition de paiement pour décrire le nombre de jours le plus courant pour chaque étape du processus. 

Le champ **Compte de liquidités pour les paiements** spécifie le compte de liquidités qui est le plus souvent utilisé pour les paiements. Utilisez le champ **Pourcentage du montant à répartir dans les prévisions de flux de trésorerie** pour indiquer si un pourcentage des montants doit être utilisé lors des prévisions. Laissez ce champ vide si les montants de transaction détaillés sont utilisés lors des prévisions.

Vous pouvez remplacer le paramètre par défaut pour le champ **Intervalle entre la date d’échéance de la facture et le paiement** pour des groupes de clients spécifiques. La prévision utilise la valeur par défaut de la section **Valeurs par défaut des prévisions de ventes** à moins qu’une valeur différente ne soit spécifiée pour le groupe de clients qui est lié au client lors de la transaction. Pour remplacer la valeur par défaut, sélectionnez un groupe de clients, puis définissez la nouvelle valeur pour le champ **Délai de vente**.

Vous pouvez remplacer le paramètre par défaut du champ **Compte de liquidités** pour des profils de validation client spécifiques. La prévision utilise la valeur par défaut de la section **Valeurs par défaut des prévisions de ventes** à moins qu’un autre compte de liquidités ne soit spécifié pour le profil de validation qui est lié au client lors de la transaction. Pour remplacer la valeur par défaut, sélectionnez un profil de validation, puis définissez le compte de liquidités devant être affecté.

### <a name="budgeting"></a>Budget

Les budgets créés à partir des modèles de budget peuvent être inclus dans les prévisions des flux de trésorerie. Sur la page **Configuration des prévisions de flux de trésorerie**, sous l’onglet **Budgétisation**, sélectionnez les modèles de budget à inclure dans la prévision. Par défaut, de nouvelles écritures de registre budgétaires sont incluses dans les prévisions après l’activation du modèle de budget pour les prévisions des flux de trésorerie.

Les écritures du registre budgétaire peuvent être incluses dans les prévisions de trésorerie sur une base individuelle grâce à la personnalisation. Lorsque vous ajoutez la colonne "Inclure dans les prévisions de flux de trésorerie" à la page **Saisie du registre budgétaire**, le système écrasera les paramètres de la page **Paramétrage des prévisions de trésorerie** pour inclure une entrée de registre budgétaire individuelle dans la prévision.


### <a name="inventory-management"></a>Gestion des stocks

Les approvisionnements et les prévisions de la demande de stock peuvent être inclus dans les prévisions des flux de trésorerie. Dans l’onglet **Gestion des stocks** de la page **Configuration des prévisions de flux de trésorerie**, sélectionnez le modèle de budget à inclure dans la prévision de flux de trésorerie. L’inclusion dans les prévisions des flux de trésorerie peut être remplacée sur chaque ligne d’approvisionnement et de prévision de la demande.

### <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>Configuration des dimensions pour la prévision des flux de trésorerie
Un nouvel onglet sur la page  **Configuration des prévisions de flux de trésorerie**  vous permet de contrôler quelles dimensions financières doivent être utilisées pour le filtrage dans l’espace de travail  **Prévision des flux de trésorerie** . Cet onglet apparaîtra uniquement lorsque la fonction de prévision des flux de trésorerie est activée.

Sur l’onglet **Dimensions**, choisissez dans la liste des dimensions à utiliser pour le filtrage et utilisez les touches fléchées pour les déplacer vers la colonne de droite. Seules deux dimensions peuvent être sélectionnées pour filtrer les données de prévision des flux de trésorerie. 

### <a name="setting-up-external-source"></a>Configuration de la source externe
Les données externes peuvent être saisies ou importées dans les prévisions de trésorerie lorsque Finance Insights a été configuré. Avant de saisir ou d’importer des données externes, des sources externes doivent être configurées. Sur l’onglet **Source externe**, configurez les catégories de flux de trésorerie externes. Une catégorie peut être **Sortant** ou **Entrant**. **Liquidité** doit être sélectionné comme type de validation. Dans la grille **Paramètres de l’entité juridique**, sélectionnez les entités juridiques et les comptes principaux correspondants auxquels s’appliquent les catégories de flux de trésorerie externes.

Pour plus d’informations sur la configuration des compteurs, voir [Données externes dans les prévisions de flux de trésorerie](../../finance/finance-insights/external-data-in-cash-flow.md). 

### <a name="project-management-and-accounting"></a>Gestion et comptabilité du projet

Dans la version 10.0.17, une nouvelle fonctionnalité permet l’intégration avec la Gestion et comptabilité des projet et la Prévision des flux de trésorerie. Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Prévision des flux de trésorerie de projet** pour inclure les coûts et recettes prévus dans les prévisions de flux de trésorerie. Sur l’onglet **Gestion et comptabilité des projets** de la page **Configuration des prévisions de flux de trésorerie**, sélectionnez les types de projet et les types de transaction à inclure dans la prévision des flux de trésorerie. Sélectionnez ensuite le modèle de prévision du projet. Un sous-modèle de type réduction est le plus approprié. Les comptes de liquidité saisis dans la configuration de la comptabilité client sont utilisés comme comptes de liquidité par défaut. Par conséquent, vous n’êtes pas obligé de saisir des comptes de liquidité par défaut lorsque vous configurez la prévision des flux de trésorerie. Un modèle de budget peut également être utilisé, mais un seul type peut être sélectionné sur la page **Configuration des prévisions de flux de trésorerie** pour la Gestion et comptabilité des projets. Un modèle de prévision offre la plus grande flexibilité lorsque la Gestion et comptabilité des projets ou Project Operations sont utilisés.

Une fois la fonctionnalité Prévision des flux de trésorerie de projet activée, la prévision de flux de trésorerie peut être affichée pour chaque projet sur la page **Tous les projets**. Dans le volet Actions, sous l’onglet **Planifier**, dans le groupe **Prévision**, sélectionnez **Prévisions de flux de trésorerie**. Dans les espaces de travail **Vue d’ensemble des disponibilités** (voir la section [Génération d’états](#reporting) plus loin dans cette rubrique), le type de transaction de la Prévision de projet affiche les entrées (recettes de la prévision de projet) et les sorties (coûts de la prévision de projet). Les montants ne peuvent être inclus que si le champ **Stade du projet** dans les espaces de travail **Vue d’ensemble des disponibilités** est défini sur **En cours**.

Les transactions du projet sont toujours incluses dans les prévisions de flux de trésorerie de plusieurs manières, indépendamment du fait que la fonctionnalité **Prévision des flux de trésorerie de projet** est activée. Les factures de projet validées sont incluses dans la prévision dans le cadre des transactions client en cours. Les commandes client et fournisseur créées pour un projet sont incluses dans la prévision comme les commandes en cours après leur saisie dans le système. Vous pouvez également transférer des prévisions de projet vers un modèle de budget comptable. Ce modèle de budget comptable est ensuite inclus dans les prévisions des flux de trésorerie dans les écritures de registre budgétaires. Si vous avez activé la fonctionnalité **Prévision des flux de trésorerie de projet**, ne transférez pas les prévisions de projet vers un modèle de budget comptable, car cette action entraînera le comptage des prévisions de projet deux fois.

### <a name="sales-tax-authority-payments"></a>Paiements à l’administration fiscale 

La fonction Paiements à l’administration fiscale des flux de trésorerie prédit l’impact sur les flux de trésorerie des paiements de la TVA. Il utilise les transactions de taxe de vente impayées, les périodes de règlement des taxes et les conditions de paiement de la période d’imposition pour prédire la date et le montant des paiements de flux de trésorerie. 

### <a name="calculation"></a>Calcul

Avant de pouvoir afficher les analyses de prévisions des flux de trésorerie, vous devez exécuter le processus de calcul du flux de trésorerie. Le processus de calcul projettera les effets de trésorerie futurs des transactions qui ont été saisies.

Calculez les prévisions des flux de trésorerie à l’aide de la page **Calculer les prévisions de flux de trésorerie**. Vous pouvez calculer les prévisions des flux de trésorerie complètes ou les prévisions des flux de trésorerie incrémentielles. 

- Pour effacer toutes les transactions de prévisions des flux de trésorerie et recalculer, définissez le champ **Méthode de calcul des prévisions de flux de trésorerie** sur **Total**. Il est recommandé d’utiliser cette méthode si vous n’avez pas actualisé les prévisions des flux de trésorerie depuis un certain temps. 
- Pour mettre à jour les informations de flux de trésorerie existantes pour les nouvelles transactions uniquement, définissez le champ **Méthode de calcul des prévisions de flux de trésorerie** sur **Nouveau**. La page affiche la date à laquelle vous avez calculé le flux de trésorerie pour la dernière fois.

Vous pouvez également utiliser des traitements par lots pour les prévisions des flux de trésorerie. Pour avoir l’assurance que les analyses de prévision sont régulièrement mises à jour, paramétrez un processus de traitement par lots récurrent pour le calcul des prévisions de flux de trésorerie.

Dans la version 10.0.13, une amélioration du processus de calcul a été publiée pour utiliser le cadre d’automatisation des processus pour planifier la tâche de calcul du flux de trésorerie. Ceci est activé en utilisant la fonctionnalité **Automatisation des prévisions de flux de trésorerie** dans l’espace de travail **Gestion des fonctionnalités**. Une fois activé, sélectionnez le lien **Automatisation des prévisions de flux de trésorerie** pour afficher la nouvelle page d’automatisation où vous pouvez planifier le processus de calcul des flux de trésorerie. Pour créer un programme de prévision de flux de trésorerie, sélectionnez **Créer une automatisation des processus**, puis sélectionnez **Automatisation des prévisions de flux de trésorerie** dans le menu déroulant **Type de programme**. Vous devez définir un programme pour chaque société pour laquelle vous mettez à jour les données de prévision de flux de trésorerie.  Cette page indique également les tâches d’automatisation des prévisions de flux de trésorerie en attente et la date de fin de la dernière tâche.  

> [!NOTE] 
> Si des tâches de traitement par lots existantes sont déjà planifiées pour les prévisions de flux de trésorerie, vous recevrez un message d’erreur et vous ne pourrez pas activer cette fonctionnalité. Les tâches de traitement par lots existantes doivent être supprimées avant de pouvoir activer cette fonctionnalité. 

Pour plus d’informations, voir [Automatisation de processus](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

### <a name="reporting"></a>Génération d’états

Une fois les prévisions des flux de trésorerie calculées, vous devez actualiser les informations d’entité associées pour la génération d’états analytiques. Dans la page **Magasin des entités**, sélectionnez la mesure **LedgerCovLiquidityMeasurement aggregate**, puis cliquez sur **Actualiser**.

Il existe deux espaces de travail contenant des données de prévision de flux de trésorerie. L’un des espaces de travail contient des données concernant toutes les sociétés, et l’autre espace de travail contient les données de la société actuelle.

L’accès à l’espace de travail pour toutes les sociétés est contrôlé par le droit **Afficher l’espace de travail de toutes les sociétés du flux de trésorerie**. Par défaut, l’espace de travail **Aperçu de la trésorerie – toutes les sociétés** est disponible pour les rôles suivants :

- Président directeur général
- Directeur financier
- Contrôleur financier

L’accès à l’espace de travail pour la société actuelle est contrôlé par le droit **Afficher l’espace de travail de la société actuelle du flux de trésorerie**. Par défaut, l’espace de travail **Aperçu de la trésorerie – société actuelle** est disponible pour les rôles suivants :

- Comptable
- Responsable comptabilité
- Chef comptable
- Responsable Comptabilité fournisseur
- Responsable Comptabilité client

L’espace de travail **Aperçu de la trésorerie – toutes les sociétés** affiche les analyses de prévisions de flux de trésorerie dans la devise du système. La devise système et le type de taux de change du système utilisés pour les analyses sont définis dans la page **Paramètres système**. Cet espace de travail affiche une vue d’ensemble des prévisions des flux de trésorerie et les soldes du compte bancaire pour toutes les sociétés. Un graphique des encaissements et décaissements fournit une vue d’ensemble des futurs mouvements et soldes de disponibilités dans la devise du système, ainsi que des informations détaillées sur les transactions de prévision. Vous pouvez également afficher les soldes de devise prévus.

L’espace de travail **Vue d’ensemble des disponibilités – société actuelle** affiche les analyses de prévisions des flux de trésorerie dans la devise comptable définie pour la société. La devise comptable utilisée pour les analyses est définie sur la page **Comptabilité**. Cet espace de travail affiche une vue d’ensemble des prévisions des flux de trésorerie et les soldes du compte bancaire pour la société actuelle. Un graphique des encaissements et décaissements fournit une vue d’ensemble des futurs mouvements et soldes de disponibilités dans la devise comptable, ainsi que des informations détaillées sur les transactions de prévision. Vous pouvez également afficher les soldes de devise prévus.

Pour plus d’informations sur les analyses de prévisions des flux de trésorerie, voir [Contenu Power BI Vue d’ensemble des disponibilités](Cash-Overview-Power-BI-content.md).

En outre, vous pouvez afficher des données de prévision des flux de trésorerie pour des comptes et des articles spécifiques dans les pages suivantes :

- **Balance comptable** : Sélectionnez **Prévisions de flux de trésorerie** pour afficher les futurs flux de trésorerie pour le compte principal sélectionné.
- **Toutes les commandes client** : Dans l’onglet **Facture**, sélectionnez **Prévisions de flux de trésorerie** pour afficher l’impact de disponibilités prévu de la commande client sélectionnée.
- **Toutes les commandes fournisseur** : Dans l’onglet **Facture**, sélectionnez **Prévisions de flux de trésorerie** pour afficher l’impact de disponibilités prévu de la commande fournisseur sélectionnée.
- **Prévision d’approvisionnement** : Sélectionnez **Prévisions de flux de trésorerie** pour afficher les futurs flux de trésorerie associés à la prévision d’approvisionnement de l’article sélectionné.
- **Prévision de la demande** : Sélectionnez **Prévisions de flux de trésorerie** pour afficher les futurs flux de trésorerie associés à la prévision de demande de l’article sélectionné.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
