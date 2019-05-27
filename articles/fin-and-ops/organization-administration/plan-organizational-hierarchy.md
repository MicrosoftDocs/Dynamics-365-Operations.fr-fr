---
title: Planification de votre hiérarchie d'organisation
description: Avant de paramétrer des organisations et des hiérarchies d'organisation, assurez-vous de bien comprendre comment modéliser votre entreprise.
author: sericks007
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMLegalEntity, OMOperatingUnit
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17404
ms.assetid: babde0c6-bb5d-45ae-95ca-2af75a0ea292
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 633d85333a510cec9cee2721e6e2330a47b6c78c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545784"
---
# <a name="plan-your-organizational-hierarchy"></a>Planification de votre hiérarchie d'organisation

[!include [banner](../includes/banner.md)]

Avant de paramétrer des organisations et des hiérarchies d'organisation dans Microsoft Dynamics 365 for Finance and Operations, veillez à planifier votre modèle d'entreprise. Le modèle d'organisation a un impact considérable sur l'implémentation de Finance and Operations et les processus entreprise.

Les hiérarchies d'organisation représentent les relations entre les organisations qui composent une entreprise. Par conséquent, lorsque vous modélisez des organisations, le plus important est la structure de votre entreprise. Il est recommandé de définir les structures d'organisation en fonction des remarques de la direction et des cadres supérieurs des différentes zones fonctionnelles (finances, comptabilité, ressources humaines, exploitation, achat, ventes et marketing).

Lorsque vous planifiez des hiérarchies, il est également important de prendre en considération la relation entre la hiérarchie d'organisation et les dimensions financières. Vous pouvez paramétrer plusieurs hiérarchies organisationnelles pour représenter des vues de votre entreprise. À l'aide des dimensions financières, vous pouvez créer des états sur ces vues. Collaborez avec votre partenaire Microsoft Dynamics 365 for Finance and Operations pour créer des hiérarchies qui répondent aux besoins de génération d'états d'organisation et statutaires.

> [!NOTE]
> Bien que vous puissiez utiliser les dimensions financières pour représenter les entités juridiques sans créer les entités juridiques dans Finance and Operations, les dimensions financières ne sont pas conçues pour répondre aux besoins opérationnels ou d'entreprise des entités juridiques. La fonctionnalité de comptabilité interunités dans Finance and Operations est conçue pour uniquement pour les écritures comptables créées par chaque transaction.

> [!IMPORTANT]
> Vous ne devez pas définir la modélisation des organisations uniquement en fonction des informations de cet article. Cette documentation est un guide. Vous pouvez demander l'assistance de votre partenaire Finance and Operations. Dans la mesure où votre partenaire Finance and Operations a acquis de l'expérience dans divers secteurs et auprès de la base de clients,

## <a name="decide-whether-to-model-internal-organizations-as-legal-entities-or-operating-units"></a>Décision de la modélisation des organisations internes comme entités juridiques ou unités opérationnelles

Vous devez avoir au moins une entité juridique pour représenter votre entreprise dans Finance and Operations. Une entité juridique peut passer des contrats juridiques et est tenue de préparer des tableaux d'analyse faisant état de ses performances.

Dans Finance and Operations, des entités juridiques peuvent être utilisées pour l'activité transactionnelle ou pour une consolidation. Cela signifie qu'une entité juridique dans Finance and Operations ne représente pas nécessairement une entité réelle de votre entreprise. Par exemple, une société qui participe à des transactions peut posséder des entités juridiques filiales. Dans ce scénario, une entité juridique est requise pour les transactions et une entité juridique virtuelle est requise pour consolider les résultats et les soldes des entités juridiques filiales.

Les organisations internes de votre entreprise, telles que les bureaux régionaux, peuvent être représentées comme entités juridiques supplémentaires ou comme unités opérationnelles de l'entité juridique principale. Une unité opérationnelle n'est pas nécessairement une organisation légalement définie. Les unités opérationnelles permettent de contrôler les ressources économiques et les processus opérationnels de l'entreprise. Par exemple, les départements et les centres de coût sont des unités opérationnelles.

Certaines fonctionnalités dans Finance and Operations fonctionnent différemment selon que l'organisation est une entité juridique ou une unité opérationnelle. Tenez bien compte de la fonctionnalité décrite ci-dessous dans votre prise de décision.

### <a name="master-data"></a>Données principales

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Certaines données principales, telles que les clients, les conditions de paiement, l'administration fiscale et la commande de stock spécifiques au site, doivent être paramétrées pour chaque entité juridique. Certaines données principales, telles que les utilisateurs, les produits et la plupart des données de ressources humaines, sont partagées par toutes les entités juridiques.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Les données principales sont partagées par les unités opérationnelles.

### <a name="module-parameters"></a>Paramètres du module

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Les paramètres des modules, tels que les paramètres Comptabilité client, les paramètres Comptabilité fournisseur et les paramètres Gestion des fonds et des banques, doivent être définis par entité juridique. Étant donné que le paramétrage du module des entités juridiques est distincte, chaque filiales peut se conformer aux demandes légales et aux procédures de gestion locales. Par exemple, une entité juridique de services professionnels et une entité juridique de fabrication peuvent avoir différents paramètres de module, même si elles fournissent les états à la même société mère.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Les paramètres de module sont partagés par les unités opérationnelles.

### <a name="data-security"></a>Sécurité des données

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

La plupart des données sont automatiquement sécurisées par ID société. Un ID société est un identificateur unique des données associées à une entité juridique. Une société ne peut être associée qu'à une seule entité juridique, et inversement. Les utilisateurs peuvent accéder aux données uniquement pour les sociétés auxquelles ils ont accès. Vous n'avez pas besoin de personnaliser Finance and Operations pour sécuriser les données par ID société.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Les données peuvent être sécurisées par unité opérationnelle en créant des stratégies de sécurité des données personnalisées. Les stratégies de sécurité des données permettent de limiter l'accès aux données. Par exemple, un utilisateur peut créer des commandes fournisseur uniquement dans une section spécifique. Des stratégies de sécurité des données peuvent être créées pour empêcher l'accès aux données de la commande fournisseur à partir d'une autre unité opérationnelle. Le volume les transactions et le nombre de stratégies de sécurité peuvent affecter les performances. Lorsque vous créez des stratégies de sécurité, songez aux performances.

### <a name="ledgers"></a>Comptabilités

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Chaque entité juridique a besoin d'une comptabilité qui fournit un plan de comptes, la devise comptable, la devise de déclaration et le calendrier fiscal. Un bilan peut être créée uniquement pour une entité juridique. Les comptes principaux, les dimensions, les structures de compte, les plans de compte et les règles de compte peuvent être utilisés par plusieurs entités juridiques.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Une unité opérationnelle ne peut pas avoir ses propres informations comptables. Si vos organisations internes n'ont pas besoin de comptabilités uniques, vous pouvez les modéliser comme unités opérationnelles. Les informations comptables sont paramétrés pour l'entité juridique parent dans la hiérarchie. Les relevés de revenus peuvent être créés pour les unités opérationnelles d'une entité juridique ou pour l'entité juridique parent.

### <a name="fiscal-calendars"></a>Calendriers fiscaux

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Chaque entité juridique possède son propre calendrier fiscal. Si vos organisations internes utilisent différents exercices et calendriers fiscaux, vous devez modéliser les organisations comme entités juridiques.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Les unités opérationnelles doivent partager un calendrier fiscal. Si vos organisations internes peuvent utiliser les mêmes exercices et calendriers fiscaux, vous pouvez modéliser les organisations comme unités opérationnelles.

### <a name="consolidation"></a>Consolidation

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Vous devez consolider les résultats financiers des bureaux régionaux en une seule société consolidée afin de préparer des tableaux d'analyse.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

La consolidation n'est pas nécessaire, car les données sont déjà partagée entre les unités opérationnelles.

### <a name="centralized-payments"></a>Paiements centralisés

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Les paiements centralisés doivent être paramétrés afin que les factures de toutes les entités juridiques enfant puissent être payées à ou depuis une entité juridique de parent unique.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Les paiements centralisés sont facultatifs, car toutes les factures sont enregistrées dans une entité juridique unique.

### <a name="intercompany-transactions"></a>Transactions intersociétés

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Les commandes client intersociétés, les commandes fournisseur, les paiements ou les réceptions peuvent être appliqués entre eux. Vous n'êtes pas tenus d'utiliser les N° documents de journal. Vous pouvez afficher les transactions intersociétés au niveau de la sous-comptabilité (Ventes, Achats). Les exemples suivants illustrent la gestion des transactions intersociétés.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Exemple 1 : Le siège fournit des services aux bureaux régionaux et doit facturer le coût de ces services aux bureaux régionaux.

Si vous modélisez le bureau régional comme entité juridique, vous pouvez choisir entre les options suivantes :

- Le siège crée une entrée de journal pour débiter la dépense en interne au bureau régional. Les transactions ne peuvent pas être vieillies.
- Le siège envoie une commande fournisseur pour les services au bureau régional. Une commande client est créée automatiquement dans l'entité juridique pour le bureau régional, avec des transactions de sous-comptabilité intersociétés.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Exemple 2 : Le siège procure et paye le service fourni à un bureau régional.

Si vous modélisez le bureau régional comme entité juridique, vous pouvez choisir entre les options suivantes :

- La facture et le paiement suivent les réglementations du siège. Le siège peut créer une entrée de journal pour débiter la dépense en interne au bureau régional. Les transactions ne peuvent pas être vieillies.
- La facture et le paiement suivent les réglementations du siège. Le siège peut créer une transaction de sous-comptabilité intersociétés.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Les transactions intersociétés entre unités opérationnelles sont prises en charge uniquement via les N° documents de journal. Une unité opérationnelle ne peut pas émettre ni recevoir une commande fournisseur, une commande client ou une facture d'une autre unité opérationnelle de la même entité juridique. Vous ne pouvez pas afficher les transactions intersociétés au niveau de la sous-comptabilité (Ventes, Achats). Les exemples suivants illustrent la gestion des transactions intersociétés.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Exemple 1 : Le siège fournit des services aux bureaux régionaux et doit facturer le coût de ces services aux bureaux régionaux.

Si vous modélisez le bureau régional comme unité opérationnelle, le siège entre une transaction de dépense et l'encode pour le bureau régional.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Exemple 2 : Le siège procure et paye le service fourni à un bureau régional.

Si vous modélisez le bureau régional comme une unité opérationnelle, la facture et le paiement suivent les réglementations du siège. La facture peut être encodée pour le bureau régional. Dans le relevé des revenus, utilisez une dimension financière d'équilibrage pour déclarer des coûts pour le bureau régional.

### <a name="local-tax-requirements"></a>Exigences des taxes locales

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Une entité juridique est soumise aux droits fiscaux de l'administration fiscale dans la pays/la région où l'entité juridique est enregistrée. Par exemple, une entité juridique qui est enregistrée au Danemark est soumise aux lois et aux règlementations fiscales danoises. Dans Finance and Operations, une entité juridique peut appartenir à un seul pays/une seule région. Le pays/la région que vous sélectionnez pour l'adresse principale de l'entité juridique contrôle les fonctionnalités géographiques spécifiques disponibles pour cette entité. Par exemple, si l'adresse principale de l'entité juridique est située au Danemark, les fonctions qui relèvent des lois et des règlementations fiscales danoises deviennent disponibles. Par conséquent, si vos organisations sont situés dans différents pays/différentes régions et ont besoin de différentes options d'impôt local, vous devez paramétrer les organisations en tant qu'entités juridiques distinctes.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Les entités juridiques utilisent le contexte de pays de l'entité juridique parent. Les entités juridiques de la même entité juridique ne peuvent pas avoir des exigences d'autres pays/régions. Si vos organisations sont dans le même pays/la même région et utilisent les mêmes options de taxe, vous pouvez les paramétrer comme entités juridiques.

### <a name="statutory-reporting-for-a-countryregion"></a>Génération d'états statutaires pour un pays/une région

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Pour les pays/régions pris en charge par Finance and Operations, la plupart des états statutaires peuvent être créés. Pour plus d'informations sur les états disponibles pour chaque pays/région, voir le [Portail de localisation Microsoft Dynamics](https://mbs.microsoft.com/customersource/global/ax/support/support-news/GFMLocalizationPortalMC) pour Finance and Operations. (Un identifiant de connexion CustomerSource est requis.)

> [!NOTE]
> Dans Finance and Operations, une couche de validation dans la comptabilité vous permet d'effectuer des entrées d'ajustement pour une société mère qui utilise un standard de comptabilité différent de celui de la société enfant. Par exemple, pour une société qui utilise la pratique comptable actuelle du Royaume-Uni (GAAP BRITANNIQUE), vous pouvez effectuer les entrées d'ajustement dans la couche de validation. Ces entrées peuvent être consolidées dans une société mère qui utilise les principes comptables généraux des États-Unis (GAAP). Les entrées d'ajustement n'affectent pas la génération d'états GAAP BRITANNIQUE.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Les états statutaires doivent être créés à l'aide d'une autre application. Vous devez vérifier que les données sont capturées dans Finance and Operations pour prendre en charge les exigences de chaque unité opérationnelle, lorsqu'elles diffèrent des besoins du siège.

### <a name="currency"></a>Devise

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Si vos organisations doivent utiliser des devises fonctionnelles différentes, vous devez modéliser les organisations comme entités juridiques. Les devises fonctionnelles sont paramétrés par entité juridique. Toutefois, vous pouvez entrer des transactions dans plusieurs devises.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Si vos organisations peuvent utiliser une devise fonctionnelle unique, vous pouvez modéliser les organisations comme unités opérationnelles. Les unités opérationnelles doivent partager une devise fonctionnelle. Toutefois, vous pouvez entrer des transactions et créer des états dans plusieurs devises.

### <a name="year-end-closing"></a>Clôture de fin d'exercice

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Si les lois et la pratique comptable diffèrent entre les pays/régions où vos organisations sont localisées, vous pouvez avoir besoin de procédures de fin d'exercice différentes par organisation. Cela signifie que vous devez modéliser les organisations comme entités juridiques. Chaque entité juridique a ses propres procédures de fin d'exercice.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Si les lois et la pratique comptable sont identiques entre les pays/régions où vos organisations sont localisées, vous pouvez utiliser un seul ensemble de procédures de fin d'exercice. Cela signifie que vous pouvez modéliser les organisations comme unités opérationnelles. Toutes les unités opérationnelles doivent utiliser la même procédure de clôture de fin d'exercice.

### <a name="number-sequences"></a>Souches de numéros

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Les souches de numéros pour certains références peuvent être paramétrées par entité juridique. Certaines souches de numéros peuvent être partagées.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Les souches de numéros pour certains références peuvent être paramétrées par unité opérationnelle. Certaines souches de numéros peuvent être partagées.

### <a name="products"></a>Produits

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Les définitions de produits sont partagées et doivent être accessibles par chaque entité juridique avant d'être incluses dans des transactions. Chaque entité juridique possède son propre ensemble de produits pouvant être inclus dans les documents de transaction. Si vos organisations internes doivent utiliser des ensembles de produits différents, vous devez modéliser les organisations comme entités juridiques.

> [!NOTE]
> Même si les définitions de produits sont partagées, dans chaque entité juridique dans laquelle un produit a été lancé, vous pouvez spécifier différents paramètres de vente, d'achat et de stockage pour l'article sur chaque site de stock.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Toutes les unités opérationnelles partagent le même ensemble de produits. Si vos organisations internes peuvent partager le même ensemble de produits, vous pouvez modéliser les organisations comme unités opérationnelles.

### <a name="inquiry-and-reporting"></a>Recherche et génération d'états

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si l'organisation est modélisée comme entité juridique

Vous devez modifier manuellement des sociétés pour entrer des transactions et effectuer des recherches dans plusieurs entités juridiques. En raison des limites de sécurité des données, la recherche et la génération d'états consolidées peuvent être gourmandes en ressources et chronophages.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si l'organisation est modélisée comme unité opérationnelle

Vous n'avez pas besoin de modifier les sociétés pour accéder aux données de plusieurs unités opérationnelles. La recherche et la génération d'états consolidées et la recherche régionale individuelle sont plus simples et plus rapides.

## <a name="best-practices-for-modeling-organizations-and-hierarchies"></a>Pratiques recommandées en matière de modélisation des organisations et des hiérarchies

Les pratiques suivantes sont recommandées lorsque vous implémentez une hiérarchie d'organisation :

- Créez un département pour modéliser l'intersection entre une entité juridique et une unité commerciale. Vous pouvez ensuite repositionner les données d'un département dans une entité juridique à des fins de génération d'états statutaires, ou dans une unité commerciale à des fins de génération d'états interne. Les départements peuvent faire office de centres de bénéfice. Si vous utilisez des départements, il n'est pas nécessaire d'utiliser des entités juridiques et des unités commerciales en tant que dimensions dans la structure de compte. Vous pouvez vous contenter d'utiliser des départements en tant que dimensions. Toutefois, vous devez utiliser les centres de coût et les départements en tant que dimensions dans une structure de compte si les centres de coût ne sont utilisés qu'en tant que cumulateurs de coûts et que les départements sont utilisés à des fins de constatation du produit.
- Modélisez plusieurs hiérarchies pour les sections en cas de besoins complexes en matière de génération d'états sur les comptes de résultat.
- Dans une entité juridique unique, ne modélisez pas plusieurs hiérarchies pour le même objet de hiérarchie.
- Ne créez pas une hiérarchie pour chaque objet. Vous utilisez généralement une seule hiérarchie pour plusieurs objets. Par exemple, une hiérarchie de sections peut être affectée à tous les objets associés à une stratégie.
- Créez des hiérarchies équilibrées. Dans une hiérarchie, tous les nœuds situés au même niveau par rapport au nœud racine sont définis en tant que niveau. Dans une hiérarchie équilibrée, un seul type de section peut avoir lieu à chaque niveau et la distance entre le nœud racine et chaque niveau est cohérent. S'il existe des niveaux intermédiaires entre un département et une entité juridique ou une unité commerciale, il se peut que des organisations fictives soient requises pour créer une hiérarchie équilibrée.
- Ne modélisez pas une hiérarchie distincte de sections si la structure des entités juridiques correspond également à votre structure opérationnelle. Une hiérarchie mélangée d'entités juridiques et de sections peut servir les deux objets.
- Avant de modéliser des scénarios de restructuration majeurs, utilisez les dates d'effet de la hiérarchie pour réaliser une analyse des impacts et un test de contrôle.
- Utilisez le mode brouillon pour modifier une hiérarchie avant de publier une nouvelle version dans un environnement de production.
- Limitez le nombre d'utilisateurs disposant d'autorisations pour ajouter ou supprimer des organisations d'une hiérarchie dans un environnement de production. Ce nombre réduit permet d'éviter les erreurs coûteuses et la nécessité d'effectuer des corrections.
