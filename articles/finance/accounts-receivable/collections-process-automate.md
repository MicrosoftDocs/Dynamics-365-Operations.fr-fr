---
title: Automatisation du processus de recouvrement
description: Cette rubrique décrit le processus de configuration des stratégies de processus de recouvrement qui identifient automatiquement les factures client qui nécessitent un rappel par e-mail, une activité de recouvrement ou une lettre de recouvrement à envoyer au client.
author: panolte
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: a5f5d65f3f757163b22d35c3c99b4d6b7fbdfafb
ms.sourcegitcommit: 3fe4d9a33447aa8a62d704fbbf18aeb9cb667baa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5582749"
---
# <a name="collections-process-automation"></a>Automatisation du processus de recouvrements

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le processus de configuration des stratégies de processus de recouvrement qui identifient automatiquement les factures client qui nécessitent un rappel par e-mail, une activité de recouvrement (comme un appel téléphonique) ou une lettre de recouvrement à envoyer au client. 

Les organisations passent beaucoup de temps à effectuer des recherches dans des états de solde chronologiques, des comptes client et des factures ouvertes pour savoir quels clients doivent être contactés au sujet d’une facture ouverte ou d’un solde de compte. Cette recherche réduit le temps passé par un agent de recouvrement à communiquer avec les clients pour recouvrer les soldes en souffrance ou résoudre les litiges relatifs aux factures. L’automatisation du processus de recouvrement vous permet de définir une approche stratégique de votre processus de recouvrement. Cela vous aide à appliquer les activités de recouvrement de manière cohérente en fournissant des rappels par e-mail personnalisés ou un processus programmé pour l’envoi de lettres de recouvrement. 

## <a name="collections-process-setup"></a>Configuration du processus de recouvrement
Vous pouvez utiliser la page **Configuration du processus de recouvrement** (**Crédits et recouvrements > Configuration > Configuration du processus de recouvrement**) pour créer un processus de recouvrement automatisé qui planifiera des activités, enverra des e-mails et créera et publiera des lettres de recouvrement de clients. Les étapes du processus sont basées sur la facture ouverte principale ou la plus ancienne. Chaque étape utilise cette facture pour déterminer quelle communication ou activité doit avoir lieu avec un client spécifique.  

Les équipes de recouvrement envoient généralement un préavis relatif à chaque facture impayée afin qu’un client soit averti lorsque la facture est sur le point d’être échue. La sélection **Prérelance** peut être définie pour permettre d’appliquer une étape de chaque hiérarchie de processus pour chaque facture lorsque l’échéance des factures atteint cette étape.

### <a name="process-hierarchy"></a>Hiérarchie des processus
Chaque regroupement de clients ne peut être affecté qu’à une seule hiérarchie de processus. Le rang hiérarchique de cette étape identifie le processus qui aura la priorité si un client est inclus dans plus d’un pool auquel une hiérarchie de processus est attribuée. L’ID de pool détermine quels clients seront affectés au processus. 

Les jours calmes sont utilisés pour s’assurer qu’un client n’est pas contacté trop fréquemment par le processus automatisé.  Par exemple, si les jours calmes sont définis sur deux, un client ne sera pas contacté par le processus automatisé pendant au moins deux jours, même si la facture principale d’origine a été réglée en totalité. 

Pour exclure des clients de l’automatisation du processus si le solde du compte ou le solde de la facture est inférieur à une valeur définie, définissez le champ **Exclure du processus** sur **Oui** et entrez la valeur du montant.

## <a name="process-details"></a>Détails du processus
**Description** est utilisé pour identifier le but ou le nom de l’étape dans la hiérarchie.

**Type d’action** définit si l’étape va créer une activité, envoyer un e-mail ou créer une lettre de recouvrement.

**Document commercial** définit le modèle utilisé pour créer le type d’action.  Cela peut être un modèle d’activité, un modèle d’e-mail ou une lettre de recouvrement par client. 

Les types d’action peuvent être créés avant ou après la date d’échéance de la facture, en fonction du paramètre affiché dans la colonne **Jours par rapport à la date d’échéance de la facture**.

Lorsque vous sélectionnez un type d’action par e-mail, le destinataire sera utilisé pour définir s’il s’agit d’un contact client, groupe de vente ou agent de recouvrement. La valeur dans le champ **Contact à des fins commerciales** détermine alors quel contact du compte de ce client recevra la communication.

## <a name="business-document-details"></a>Détails des documents commerciaux
Les détails du document commercial varient en fonction du type d’action sélectionné dans les détails du processus.  Lorsque le type d’action est une activité, les détails du modèle d’activité seront affichés.  Ces détails incluent le nom du modèle d’activité, le type d’activité qui sera créé, le but de l’activité, le nombre de jours prévus pour terminer l’activité et les détails de l’activité.  Cette activité sera ensuite liée à la facture principale qui informe le destinataire de l’action nécessaire pour terminer l’activité.

Si le type d’action est un e-mail dans les détails du processus, cette section contiendra deux raccourcis.  Le premier est utilisé pour définir l’ID du modèle, la description de l’e-mail, la langue par défaut, le nom d’utilisateur qui sera affecté aux e-mails envoyés automatiquement et l’adresse e-mail de l’expéditeur associée. Le second permettra de créer le corps de l’e-mail après les valeurs des champs **Langue** et **Objet** enregistrées en sélectionnant **Modifier**.  Cela ouvrira une fenêtre permettant de charger du contenu HTML. Vous pouvez également saisir le message créé manuellement dans la zone inférieure gauche de la fenêtre.  

> [!Note]
> Un e-mail Outlook peut être enregistré avec le corps souhaité de la communication au format HTML. Cela peut ensuite être chargé pour implémenter le modèle. <br> <br> Si le type d’action de lettre de collecte est sélectionné, il n’y aura pas de section de détail de document commercial sur le formulaire de configuration.


## <a name="fasttab-reference"></a>Référence du raccourci
Les tableaux suivants répertorient les pages et les champs à partir desquels les raccourcis spécifiés sont accessibles, ainsi qu’une description des informations de cet onglet. 

### <a name="process-hierarchy"></a>Hiérarchie des processus

|     Page                                                  |     Champ                         |     Description                           |
| --------------------------------------------------------  |-------------------------------    |---------------------------------------    |
|     Configuration du processus de recouvrement <br> Automatisation des processus       |                                   |     Créez et gérez des processus de recouvrement en fonction des affectations de pool de clients.                                                                                                                             |
|     Configuration du processus de recouvrement <br> Automatisation des processus       |     Hiérarchie                     |     Définit la priorité de l’automatisation des processus pour affecter un client s’il appartient à plusieurs pools.                                                                                                   |
|     Configuration du processus de recouvrement <br> Automatisation des processus       |     ID de regroupement                       |     Requêtes qui définissent un groupe d’enregistrements client.                                                                                                                                                        |
|     Configuration du processus de recouvrement <br> Automatisation des processus       |     Jours de déconnexion                    |     Limitez la fréquence à laquelle une étape de processus peut être exécutée. Par exemple, si deux jours calmes sont définis, l’étape suivante du processus ne se produira pas pendant au moins deux jours si la facture principale change.     |
|     Configuration du processus de recouvrement <br> Automatisation des processus       |     Exclure du processus        |     En sélectionnant soit **Solde chronologique client inférieur à**, soit **Montant de la facture inférieur à** cela exclura un client de l’automatisation des processus si les critères de valeur ne sont pas remplis.                                   |

### <a name="process-details"></a>Détails du processus
|     Page                                                  |     Champ                                         |      Description                  |
|--------------------------------------------------------   |-----------------------------------------------    |----------------------------   |
|     Configuration du processus de recouvrement <br> Automatisation des processus       |                                                   |     Définissez les étapes effectuées en fonction de la facture principale.                                                                                                |
|                                                           |     Description                                   |     Champ de texte libre utilisé pour fournir un nom et/ou une description de l’étape.                                                                           |
|                                                           |     Type d’action                                   |     Activité, e-mail ou lettre de recouvrement qui sera créée par l’étape du processus.                                                                     |
|                                                           |     Document commercial                           |     Définit l’activité ou le modèle d’e-mail utilisé lors de l’étape de processus.                                                                        |
|                                                           |     Si                                          |     Définit si l’étape du processus se produira avant ou après la date d’échéance de la facture principale avec le champ **Jours par rapport à la date d’échéance de la facture**.        |
|                                                           |     Jours par rapport à la date d’échéance de la facture        |     Avec le champ **Quand**, il identifie le moment de l’étape du processus.                                                                          |
|                                                           |     Pré-relance                                   |     Cette sélection permet de définir et d’exécuter une étape par hiérarchie de processus sur chaque facture lorsqu’elle atteint les critères d’échéance.                                                |
|                                                           |     Destinataire                                     |     Identifie si un e-mail sera envoyé à un contact Client, groupe de vente ou agent de recouvrement.                                                   |
|                                                           |     Contact à des fins commerciales                    |     Détermine l’adresse e-mail du destinataire utilisée dans les communications par e-mail.                                                                                 |

### <a name="business-process-activity-template-details"></a>Détails du modèle d’activité du processus d’entreprise 
|     Page                                                  |     Champ                     |      Description                  |
|--------------------------------------------------------   |----------------------------   |-------------------------  |
|     Configuration du processus de recouvrement <br> Automatisation des processus       |                               |     Section du processus de configuration qui identifie les détails du modèle d’activité.                                                                      |
|     Configuration du processus de recouvrement <br> Automatisation des processus       |     Modèle d’activité       |     Identifie le type, l’objectif, le nombre de jours à effectuer et fournit des détails sur l’activité qui sera créée au cours d’une étape du processus d’activité.       |

### <a name="business-document-email-template-details"></a>Détails du modèle d’e-mail du document commercial 
|     Page                                                  |     Champ     |      Description                  |
|--------------------------------------------------------   |-------------- |-----------------------------  |
|     Configuration du processus de recouvrement <br> Automatisation des processus       |               |     Identifie la description de l’e-mail, la langue par défaut, le nom de l’expéditeur et l’adresse e-mail qui seront créés lors d’une étape du processus d’e-mail.        |


### <a name="collections-history"></a>Historique des recouvrements 
|     Page                              |     Champ     |      Description                                                          |
|------------------------------------   |-------------- |---------------------------------------------------------------------  |
|     Configuration du processus de recouvrement       |               |     Affichez l’historique récent de la hiérarchie de processus sélectionnée.       |

### <a name="collection-process-assignment"></a>Affectation du processus de recouvrement
|     Page                              |     Champ     |      Description                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|     Configuration du processus de recouvrement       |               |     Affichez les clients affectés à un processus de recouvrement.  
|     Affectation manuelle               |               |     Affichez les clients qui ont été affectés manuellement à un processus ou sélectionnez les clients à affecter à un processus. |
|     Afficher un aperçu de l’affectation de processus      |               |     Prévisualisez les clients qui seront affectés à une stratégie lors de son exécution.   |
|     Afficher un aperçu de l’affectation de client     |               |     Affichez la stratégie attribuée à un client spécifique.    |
 
 ### <a name="process-simulation"></a>Traiter la simulation
|     Page                              |     Champ     |      Description                                                   |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|    Traiter la simulation                 |               |     Prévisualisez les actions qui seront créées si l’automatisation de processus sélectionnée est exécutée à ce moment. |

### <a name="parameters"></a>Paramètres
|     Page                                                                  |     Champ                                             |      Description                               |
|-------------------------------------------------------------------------- |------------------------------------------------------ |-------------------------------------  |
|     Paramètres Comptabilité client > Automatisation du processus de recouvrement     |     Pourcentage de clients par tâche de traitement par lots          |     Paramètre pour déterminer le nombre de tâches de traitement par lots par processus d’automatisation.                                          |
|     Paramètres Comptabilité client > Automatisation du processus de recouvrement     |     Valider automatiquement les lettres de relance           |     Les types d’action de lettre de relance publieront la lettre pendant l’automatisation.                                      |
|     Paramètres Comptabilité client > Automatisation du processus de recouvrement     |     Créer des activités d’automatisation                |     Créez et fermez des activités pour les types d’action non liés à une activité pour afficher toutes les étapes automatisées effectuées sur un compte.        |
|     Paramètres Comptabilité client > Automatisation du processus de recouvrement     |     Jours pour conserver l’automatisation des processus de recouvrement     |     Définit le nombre de jours pendant lesquels l’historique des recouvrements est stocké.                                                       |
|     Paramètres Comptabilité client > Automatisation du processus de recouvrement     |     Exclure la facture après l’activation de la dernière étape du processus    |     Une facture qui atteint la dernière étape du processus de recouvrement ne sera pas utilisée pour créer de futurs types d’action d’automatisation de processus. La facture la plus ancienne suivante déterminera l’étape d’automatisation du processus suivante pour garantir la poursuite des actions d’automatisation du processus de collecte.                                                        |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
