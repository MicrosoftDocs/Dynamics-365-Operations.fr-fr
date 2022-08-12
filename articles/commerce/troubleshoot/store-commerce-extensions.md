---
title: Résoudre les problèmes liés à l'extension Store Commerce
description: Cet article explique comment résoudre les problèmes d'extension dans l'application Microsoft Dynamics 365 Commerce Store Commerce.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: b440183e255e05c4f93a4f11106be2967163ff74
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/16/2022
ms.locfileid: "9169015"
---
# <a name="troubleshoot-store-commerce-extension-issues"></a>Résoudre les problèmes liés à l'extension Store Commerce

[!include [banner](../includes/banner.md)]

Cet article explique comment résoudre les problèmes d'extension dans l'application Microsoft Dynamics 365 Commerce Store Commerce.

## <a name="extensions-packages-arent-loaded"></a>Les packages d'extensions ne sont pas chargés

### <a name="extensions-packages-dont-appear-on-the-pos--settings-page"></a>Les packages d'extensions n'apparaissent pas sur la page PDV \> Paramètres

Les déclencheurs Commerce Runtime (CRT) n'ont peut-être pas été mis à jour pour inclure le package d'extension, ou ils ne sont pas déployés. Pour plus d'informations, voir [Extensibilité et déclencheurs Commerce Runtime (CRT)](../dev-itpro/commerce-runtime-extensibility-trigger.md).

### <a name="extensions-packages-appear-on-the-pos--settings-page-but-the-manifest-isnt-loaded"></a>Les packages d'extensions apparaissent sur la page PDV \> Paramètres, mais le manifeste n'est pas chargé

Vérifiez que les packages d'extensions existent dans le dossier **C:\\Program Files\\Microsoft Dynamics 365\\10.0\\Store Commerce\\Extensions**. Si les packages existent, il devrait y avoir un dossier **PDV** qui contient le manifeste.

S'il n'y a pas de dossier **POS**, vérifiez que le projet Store Commerce référence correctement le projet d'extension de point de vente (PDV). Validez le chemin de référence du projet et assurez-vous qu'il existe. 

Dans l'exemple d'illustration suivant, le projet d'installation rencontre des problèmes avec le projet d'extension référencé.

![La référence du projet d'installation de Store Commerce n'est pas valide.](media/ReferenceNotValid.png)

Si la référence du projet d'extension est correctement ajoutée, il n'y aura pas d'avertissement ou de problème de dépendance dans le projet d'installation, comme illustré dans l'exemple suivant.

![La référence du projet d'installation de Store Commerce est valide.](media/ReferenceValid.png)
