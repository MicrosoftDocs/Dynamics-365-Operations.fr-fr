---
title: Configurer les paramètres pour l’automatisation du processus de recouvrement
description: Cet article décrit les paramètres qui affectent les processus de recouvrement automatisés et fournit des conseils pour les définir afin que le processus automatisé reflète vos intentions et vos attentes.
author: JodiChristiansen
ms.date: 08/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c5d0f801c47ef2d98d8ba410dc593bd7640839c1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900040"
---
# <a name="configure-parameters-for-collection-process-automation"></a>Configurer les paramètres pour l’automatisation du processus de recouvrement

[!include [banner](../includes/banner.md)]

Cet article décrit les paramètres qui affectent les processus de recouvrement automatisés et fournit des conseils pour les définir afin que le processus automatisé reflète vos intentions et vos attentes. Pour plus d’informations sur l’automatisation des processus de recouvrement, voir [Automatisation du processus de recouvrement](collections-process-automate.md).

## <a name="general"></a>Générale
Entrez un numéro dans le **Pourcentage de clients par tâche de traitement par lots** pour déterminer le nombre de tâches de traitement par lots par processus d’automatisation. Définissez **Valider automatiquement les lettres de relance** sur **Oui** de sorte que le type d’action de lettre de relance publiera la lettre lors de l’automatisation. Définissez **Créer des activités pour les automatisations** sur **Oui** pour créer et fermer des activités pour les types d’action sans activité pour afficher toutes les étapes automatisées effectuées sur un compte. Définissez le nombre de jours pendant lesquels l’historique de recouvrement est enregistré dans les **Jours pour conserver l’automatisation des processus de recouvrement**. Lorsqu’une facture atteint la dernière étape du processus de recouvrement, elle ne sera pas utilisée pour créer de futurs types d’action d’automatisation de processus si l’option **Exclure la facture après l’activation de la dernière étape du processus** est définie sur **Oui**. La facture la plus ancienne suivante détermine l’étape d’automatisation du processus suivante pour garantir la poursuite des actions d’automatisation du processus de recouvrement. 

## <a name="payment-predictions"></a>Prédictions de paiement
À partir de la version 10.0.21, les prévisions de paiement client, disponibles dans Finance Insights, prévoient si une facture sera payée à temps, en retard ou très en retard. Vous pouvez configurer chacune de ces catégories dans Finance Insights. S’il est prévu que les factures soient payées en retard, il est important de commencer le processus de recouvrement avant l’échéance de la facture. Ces prédictions peuvent être utilisées pour créer des activités de recouvrement lors de l’exécution des automatisations de processus de recouvrement. Définissez **Activer les prévisions de paiement** sur **Oui** pour utiliser les prévisions de paiement des clients pour créer des activités de recouvrement basées sur la probabilité que la facture soit payée en retard. 

Pour plus d’informations sur les prévisions de paiement client et Finance Insights, voir [Prédictions de paiement des clients](payment-insights-overview.md).

Lorsque le modèle de prédictions de paiement client s’exécute, il attribue un pourcentage à la prédiction de la facture payée à temps, en retard ou très en retard. Vous pouvez utiliser ces informations pour démarrer automatiquement les activités de recouvrement à l’aide de l’automatisation du processus de recouvrement au cas où un retard de paiement est attendu. Vous pouvez consulter ces pourcentages sur les pages **Prédictions de paiement par client** ou **Prédictions de paiement par transaction** sous **Crédit et recouvrement > Recouvrements**. 

Si la prédiction de paiement moyenne pour une facture client est inférieure au pourcentage de référence, aucune activité n’est créée. Si la prédiction de facture est supérieure ou égale au pourcentage de référence, une activité est créée par client. Pour **Prédiction : En retard**, entrez le **Pourcentage de référence** du moment où l’automatisation du processus de recouvrement doit créer des activités de recouvrement. Il s’agit d’une valeur globale à la fois en retard et très en retard. Sélectionnez un **Modèle de document commercial** à utiliser pour l’activité créée ou en créer une nouvelle. Cela identifie le **Type**, le **But** et les **Jours jusqu’à la fermeture de l’activité**. Saisissez n’importe quelle **Remarque** qui sera par défaut la description lors de la création de l’activité. Pour **Prédiction : Très en retard**, entrez le **Pourcentage de référence** du moment où l’automatisation du processus de recouvrement doit créer des activités de recouvrement pour un client qui risque de payer ses factures très en retard. Sélectionnez un **Modèle de document commercial** à utiliser pour l’activité créée. Cela identifie le **Type**, le **But** et les **Jours jusqu’à la fermeture de l’activité**. Saisissez n’importe quelle **Remarque** qui sera par défaut la description lors de la création de l’activité. 

### <a name="example"></a>Exemple
Si le pourcentage de référence en retard est fixé à 60 %. Lorsque le modèle de prédictions de paiement client s’exécute pour chaque facture, le système attribue un pourcentage à la prédiction de la facture payée à temps, en retard ou très en retard. Si la prédiction de paiement selon laquelle la facture sera payée en retard est inférieure ou égale à 59 %, aucune activité de recouvrement ne sera créée pour la facture par le processus de recouvrement automatisé. Si la prédiction de paiement client pour une facture est supérieure ou égale à 60 %, une activité de recouvrement est créée lors de l’automatisation du processus de recouvrement. 

> [!NOTE]
> La prédiction très en retard est évaluée avant la prédiction en retard, car très en retard comprend les factures qui devraient être payées en retard. Le processus de recouvrement ne génère qu’une seule activité si la facture tombe à la fois dans les références en retard et très en retard. Dans ce cas, le système utilise l’activité très en retard et le document commercial, car très en retard est prioritaire. Toutes les autres actions qui ont déjà été générées ne seront pas générées une seconde fois.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
