---
title: "Extensibilité dans Attract"
description: "Cette rubrique décrit comment vous pouvez étendre l'application Microsoft Dynamics 365 for Talent - Attract à l'aide de Microsoft Power Platform."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 0af60a0aea0f7a5de793631445aaebb37dbb0d74
ms.contentlocale: fr-fr
ms.lasthandoff: 10/22/2018

---

# <a name="extensibility-in-attract"></a>Extensibilité dans Attract

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent est généré sur la plateforme Common Data Service (CDS) pour les applications, et peut être étendu de différentes manières à l'aide de Microsoft Power Platform et des capacités que Common Data Service pour les applications offre. Par conséquent, vous pouvez configurer et personnaliser le système à l'aide de Microsoft PowerApps et Microsoft Flow. Vous pouvez également obtenir des analyses supplémentaire sur les personnes à l'aide Microsoft Power BI. En outre, de nouvelles activités personnalisées, telles que les activités PowerApps et de contenu web (iframe), rendent le processus de recrutement plus adaptable que jamais. Avec ces activités, vous pouvez personnaliser dans le processus de recrutement selon les besoins et processus de votre entreprise, et vous assurer que l'équipe de recrutement et les candidats ont une expérience transparente et personnalisée.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Tirer profit de Microsoft Power Platform 

Étant donné que toutes les données Attract résident dans Common Data Service pour les applications, vous pouvez utiliser des outils de Microsoft Power Platform de manière à intégrer vos besoins métier uniques dans Attract.

### <a name="powerapps"></a>PowerApps

Vous pouvez utiliser PowerApps pour générer facilement des applications qui se connectent à vos données Attract, et qui utilisent des expressions comme les expressions de Microsoft Excel pour ajouter une logique. Les applications que vous générez à l'aide de PowerApps peuvent s'exécuter sur le web, et sur des appareils Apple et Google Android.

Par exemple, vous pouvez facilement organiser des salons de l'emploi dans des universités pour les recruteurs en créant une application légère qui leur permet d'analyser les CV et d'acheminer les candidats vers un poste dans Attract. Sinon, vous pouvez générer une application qui vous permet de répondre aux besoins de conformité de votre organisation. Pour plus d'informations sur PowerApps et comment l'utiliser pour générer des applications, voir [Intégration de données dans Common Data Service pour les applications](https://docs.microsoft.com/en-us/powerapps).

### <a name="microsoft-flow"></a>Microsoft Flow 

Vous pouvez utiliser Microsoft Flow pour créer des workflows automatisés s'exécutant avec les données Attract. Vous pouvez facilement vous connecter à des centaines d'applications et services populaires sans devoir écrire du code. Lorsque vous générez des flux qui interagissent avec des entités de mission, de candidat et d'application Attract dans Common Data Service pour les applications, vous pouvez automatiser différentes actions. Par exemple, lorsqu'un candidat accepte une offre, une notification peut être envoyées à une équipe d'accueil, ou les nouvelles peuvent être annoncées sur Twitter. Pour plus d'informations sur les flux, voir [la documentation Microsoft Flow](https://docs.microsoft.com/en-us/flow/).

### <a name="power-bi"></a>Power BI

Power BI vous permet de générer et d'afficher des états et des tableaux de bord personnalisés vous offrant un aperçu approfondi de vos données Attract. Pour plus d'informations sur Power BI et comment générer des états et des tableaux de bord interactifs, voir la [documentation Power BI](https://docs.microsoft.com/en-us/power-bi/).

### <a name="custom-activities"></a>Activités personnalisées 

Vous pouvez ajouter des activités personnalisées, telles que les activités d'applications PowerApps et de contenu web (iframe), au niveau du modèle de processus de mission ou lorsque vous créez une mission. Ces activités vous permettent de personnaliser le processus de recrutement et d'apporter une logique métier propre à votre organisation dans Attract.

#### <a name="powerapps-activity"></a>Activité PowerApps 

L'activité PowerApps permet au créateur d'un modèle de mission ou de processus de mission d'incorporer une application PowerApps au processus de recrutement. Après avoir créé et publié l'application, vous pouvez entrer son ID d'application dans les configurations d'activité. En utilisant une application PowerApps, vous pouvez lire et écrire des données dans Common Data Service pour les applications. Vous pouvez même lier l'application à un flux. Par exemple, vous disposez d'une application que les recruteurs utilisent pour renseigner un écran lorsqu'ils effectuent des entretiens téléphoniques. Dans ce cas, vous pouvez lier l'application à un flux qui évalue si un candidat peut être avancé davantage dans le processus de candidature à un poste. Ce type d'activité peut être affiché uniquement par les membres de l'équipe de recrutement. Pour plus d'informations sur la configuration de l'activité PowerApps, voir [Activités dans Attract](./activities-attract.md).

> [!NOTE]
> L'activité PowerApps n'est disponible qu'avec le Composant additionnel de recrutement complet.

#### <a name="web-content-iframe-activity"></a>Activité de contenu web (iframe)

L'activité de contenu web (iframe) permet d'inclure une solution web personnalisée que vous avez intégrée au processus de recrutement ou au portail du candidat. Vous pouvez lire et d'écrire des données directement dans Common Data Service pour les applications. Vous pouvez également personnaliser la solution afin qu'elle déclenche des flux ou tire profit des fonctions de Microsoft Azure. Pour plus d'informations sur la configuration de l'activité de contenu web, voir [Activités dans Attract](./activities-attract.md).

> [!NOTE]
> L'activité de contenu web n'est disponible qu'avec le Composant additionnel de recrutement complet.

