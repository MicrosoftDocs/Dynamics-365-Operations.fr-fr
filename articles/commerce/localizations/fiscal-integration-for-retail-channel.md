---
title: Vue d’ensemble de l’intégration fiscale pour les canaux Commerce
description: Cet article fournit une vue d’ensemble des capacités d’intégration fiscale disponibles dans Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: ea1de0791a0eaffa2a8b1ac57143bdfd753f855b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884842"
---
# <a name="fiscal-integration-overview-for-commerce-channels"></a>Vue d’ensemble de l’intégration fiscale pour les canaux Commerce

[!include [banner](../includes/banner.md)]

Cet article présente une vue d’ensemble des capacités d’intégration fiscale disponibles dans Dynamics 365 Commerce. 

L’intégration fiscale comprend l’intégration à différents périphériques et services fiscaux qui permettent l’enregistrement fiscal des ventes selon les lois fiscales locales dans le but de lutter contre la fraude fiscale dans le secteur de la vente au détail. Voici quelques scénarios traditionnels pouvant être couverts à l’aide de l’intégration fiscale :

- Enregistrez une vente sur un périphérique fiscal connecté à un point de vente (PDV), comme une imprimante fiscale et imprimez un reçu fiscal pour le client.
- Envoyez en toute sécurité des informations concernant les ventes et les retours exécutés dans Retail POS vers un service Web externe géré par l’administration fiscale.
- Assurez l’inaltérabilité des données de transaction commerciale via les signatures numériques.

La fonctionnalité d’intégration fiscale offre un cadre proposant une solution courante pour un développement poussé et une personnalisation de l’intégration entre Retail POS et les périphériques et services fiscaux. La fonctionnalité comprend également des exemples d’intégration fiscale compatibles avec des scénarios de base pour des pays ou régions spécifiques, et qui fonctionnent avec des périphériques ou services fiscaux spécifiques. Un exemple d’intégration fiscale est composé de plusieurs extensions de composants Commerce et est inclus dans le kit de développement logiciel (SDK). Pour plus d’informations sur les exemples d’intégration fiscale, voir [Exemples d’intégration fiscale dans le kit de développement logiciel Commerce](#fiscal-integration-samples-in-the-commerce-sdk). Pour en savoir plus sur la manière d’installer et d’utiliser le SDK Commerce, voir [Architecture du kit de développement logiciel de Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Pour prendre en charge d’autres scénarios non compatibles avec un exemple d’intégration fiscale, pour intégrer Retail POS à d’autres périphériques ou services fiscaux, ou pour répondre aux exigences d’autres pays ou régions, vous devez développer un exemple d’intégration fiscale existant ou créer un exemple à l’aide d’un exemple existant.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services"></a>Processus d’enregistrement fiscal et exemples d’intégration fiscale pour les périphériques et services fiscaux

Un processus d’enregistrement fiscal dans Retail POS peut contenir une ou plusieurs étapes. Chaque étape implique l’enregistrement fiscal des transactions de vente spécifiques ou d’événements dans un périphérique ou service fiscal. Les composants de solution suivants participent à l’enregistrement fiscal dans un périphérique ou service fiscal :

- **Fournisseur de document fiscal** : ce composant sérialise les données de l’événement/transaction de vente au format également utilisé pour interagir avec le périphérique ou service fiscal, analyse les réponses depuis le périphérique ou service fiscal et stocke les réponses dans la base de données du canal. L’extension définit également les transactions et les événements spécifiques qui doivent être enregistrés.
- **Connecteur fiscal** : ce composant lance la communication avec le périphérique ou service fiscal, envoie des demandes et des commandes directes au périphérique fiscal selon les données de transaction/événement de vente extraites du document fiscal, et reçoit les réponses depuis le périphérique ou service fiscal.

Un exemple d’intégration fiscale pourrait contenir les extensions Commerce Runtime (CRT), de station matérielle et PDV pour un fournisseur de documents fiscaux et un connecteur fiscal. Il contient également les configurations de composant suivantes :

- **Configuration de fournisseur de documents fiscaux** – Cette configuration définit un mode de sortie et un format pour les documents fiscaux. Elle contient également une mise en correspondance des données pour les taxes et les modes de paiement, pour effectuer des paiements depuis Retail POS compatibles avec les valeurs prédéfinies dans le microgiciel du périphérique ou service fiscal.
- **Configuration de connecteur fiscal** – Cette configuration définit la communication physique avec le périphérique ou service fiscal spécifique.

Un processus d’enregistrement fiscal pour un registre de PDV spécifique est défini par un paramètre correspondant dans le profil de fonctionnalité de PDV. Pour en savoir plus sur la manière de configurer un processus d’enregistrement fiscal, téléchargez le fournisseur de documents fiscaux et les configurations de connecteur fiscal, et modifiez leurs paramètres de configuration, voir [Configurer un processus d’enregistrement fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

> [!NOTE]
> Si vous avez besoin d’appareils pour des opérations non fiscales, telles que la recherche de catalogue de produits, la recherche de clients ou la création de brouillon de transaction, vous pouvez les sélectionner en tant que registres avec des restrictions de processus fiscaux. Pour plus d’informations, voir [Configurer des registres avec des restrictions d’enregistrement fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-registers-with-fiscal-registration-restrictions).

Le flux d’enregistrement fiscal typique suivant commence par un événement dans le PDV (par exemple, la finalisation d’une transaction de vente) et implémente une séquence prédéfinie d’étapes qui implique d’autres composants Commerce (tels que CRT et la station matérielle).

1. Le PDV demande un document fiscal au cadre d’intégration fiscale (FIF).
1. Le FIF détermine si l’événement actuel exige un enregistrement fiscal.
1. Selon les paramètres de processus d’enregistrement fiscal, FIF identifie un connecteur fiscal et un fournisseur de documents fiscaux correspondant à utiliser pour l’enregistrement fiscal.
1. FIF exécute le fournisseur de documents fiscaux qui génère un document fiscal (par exemple, un document XML) qui représente la transaction ou l’événement de vente au détail.
1. FIF renvoie le document fiscal généré au PDV.
1. Le PDV demande au FIF de soumettre le document fiscal au périphérique ou service fiscal.
1. FIF exécute le connecteur fiscal qui traite le document fiscal et l’envoie au périphérique ou au service fiscal.
1. FIF renvoie la réponse fiscale (c’est-à-dire la réponse du périphérique ou service fiscal) au PDV.
1. Le PDV analyse la réponse pour déterminer si l’enregistrement fiscal a réussi. Au besoin, le PDV demande que le FIF traite toutes les erreurs qui se sont produites. 
1. Le POS demande au FIF de traiter et d’enregistrer la réponse fiscale.
1. Le fournisseur de documents fiscaux traite la réponse fiscale. Dans le cadre de ce traitement, le fournisseur de documents fiscaux analyse la réponse et en extrait des données étendues.
1. FIF enregistre la réponse et les données étendues dans la base de données du canal.
1. Au besoin, le PDV imprime un reçu via une imprimante de reçus ordinaire connectée à la station matérielle. Le reçu peut contenir les données requises de la réponse fiscale.
 
Les exemples suivants affichent des flux d’exécution d’enregistrement fiscal traditionnels pour les périphériques ou services fiscaux types.
 
### <a name="fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station"></a>L’enregistrement fiscal se fait via un appareil connecté à la station matérielle

Cette configuration est utilisée lorsqu’un périphérique fiscal physique, tel qu’une imprimante fiscale, est connecté à la station matérielle. Cela s’applique également lorsque la communication avec un périphérique ou un service fiscal se fait via un logiciel installé sur la station matérielle. Dans ce cas, le fournisseur de documents fiscaux est situé sur CRT, et le connecteur fiscal est situé sur la station matérielle.

![L’enregistrement fiscal se fait via un appareil connecté à la station matérielle.](media/FIF-CRT-HWS.png)

### <a name="fiscal-registration-is-done-via-an-external-service"></a>L’immatriculation fiscale se fait via un service externe

Cette configuration est utilisée lorsque l’enregistrement fiscal est effectué via un service externe, tel qu’un service Web géré par l’administration fiscale. Dans ce cas, le fournisseur de documents fiscaux et le connecteur fiscal sont situés sur CRT.

![L’immatriculation fiscale se fait via un service externe.](media/FIF-CRT-CRT.png)
 
### <a name="fiscal-registration-is-done-internally-in-the-crt"></a>L’enregistrement fiscal se fait en interne dans CRT

Cette configuration est utilisée lorsqu’aucun dispositif ou service fiscal externe n’est requis pour l’enregistrement fiscal. Par exemple, il est utilisé lorsque l’enregistrement fiscal est effectué via la signature numérique des transactions de vente. Dans ce cas, le fournisseur de documents fiscaux et le connecteur fiscal sont situés sur CRT.

![L’enregistrement fiscal se fait en interne dans CRT.](media/FIF-CRT-CRT-SGN.png)

### <a name="fiscal-registration-is-done-via-a-device-or-service-in-the-local-network"></a>L’enregistrement fiscal se fait via un périphérique ou un service dans le réseau local

Cette configuration est utilisée lorsqu’un périphérique fiscal physique ou un service fiscal est présent dans le réseau local du magasin et fournit une interface de programmation d’application (API) HTTPS. Dans ce cas, le fournisseur de documents fiscaux est situé sur CRT, et le connecteur fiscal est situé sur le PDV.

![L’enregistrement fiscal se fait via un périphérique ou un service dans le réseau local.](media/FIF-CRT-POS.png)

## <a name="error-handling"></a>Gestion des erreurs

La structure d’intégration fiscale offre les options suivantes pour traiter les échecs lors d’un enregistrement fiscal :

- **Réessayer** – Les opérateurs peuvent utiliser cette option si l’échec peut être rapidement résolu et si l’enregistrement fiscal peut être à nouveau exécuté. Par exemple, cette option peut être utilisée lorsque le périphérique fiscal n’est pas connecté, lorsque l’imprimante fiscale est à court de papier ou présente un bourrage papier.
- **Annuler** – Cette option permet aux opérateurs de remettre à plus tard l’enregistrement fiscal de la transaction ou de l’événement actuel en cas d’échec éventuel. Une fois l’enregistrement remis à plus tard, l’opérateur peut continuer à travailler sur le PDV et terminer une opération pour laquelle l’enregistrement fiscal n’est pas requis. Lorsqu’un événement qui exige un enregistrement fiscal survient dans le PDV (par exemple, une nouvelle transaction est ouverte), la boîte de dialogue de traitement des erreurs s’ouvre automatiquement pour prévenir l’opérateur que la transaction précédente n’a pas été bien enregistrée et pour fournir les options de gestion des erreurs.
- **Ignorer** – Les opérateurs peuvent utiliser cette option si l’enregistrement fiscal peut être ignoré dans le cadre de conditions spécifiques et si les opérations habituelles peuvent se poursuivre dans le PDV. Par exemple, cette option peut être utilisée lorsqu’une transaction commerciale pour laquelle l’enregistrement fiscal a échoué peut être enregistrée dans un journal papier spécial.
- **Marquer comme enregistrée** : les opérateurs peuvent utiliser cette option lorsque la transaction a été enregistrée réellement dans le périphérique fiscal (par exemple, un reçu fiscal a été imprimé), mais qu’un échec s’est produit lorsque la réponse fiscale a été enregistrée vers la base de données du canal.
- **Reporter** : les opérateurs peuvent utiliser cette option lorsque la transaction n’a pas été enregistrée, car le service d’enregistrement n’était pas disponible. 

> [!NOTE]
> Les options **Ignorer**, **Marquer comme enregistrée** et **Reporter** doivent être activées dans le processus d’enregistrement fiscal pour être utilisées. En outre, les autorisations correspondantes doivent être accordées aux opérateurs.

Les options **Ignorer**, **Marquer comme enregistrée** et **Reporter** permettent aux codes info de saisir certaines informations spécifiques concernant l’échec, comme la raison de l’échec ou la justification de l’omission de l’enregistrement fiscal ou du marquage de la transaction comme enregistrée. Pour en savoir plus sur la manière de configurer les paramètres de traitement des erreurs, voir [Définir les paramètres de traitement des erreurs](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Enregistrement fiscal facultatif

L’enregistrement fiscal peut être obligatoire pour certaines opérations mais facultatif pour d’autres. Par exemple, l’enregistrement fiscal des ventes et retours ordinaires peut être obligatoire, mais l’enregistrement fiscal des opérations associées à des dépôts client peut être facultatif. Dans ce cas, le manquement à réaliser l’enregistrement fiscal d’une vente bloquerait les ventes suivantes, mais le manquement à réaliser l’enregistrement fiscal d’un dépôt client ne bloquerait pas les ventes suivantes. Pour distinguer les opérations obligatoires et facultatives, nous vous recommandons de les gérer via différents fournisseurs de document, et de configurer des étapes distinctes dans le processus d’enregistrement fiscal pour ces fournisseurs. Le paramètre **Continuer lors d’erreurs** doit être activé pour chaque étape liée à l’enregistrement fiscal facultatif. Pour en savoir plus sur la manière de configurer les paramètres de traitement des erreurs, voir [Définir les paramètres de traitement des erreurs](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-rerun-fiscal-registration"></a>Réexécuter manuellement l’enregistrement fiscal

Si l’enregistrement fiscal d’une transaction ou d’un événement a été reporté après un échec (par exemple, si l’opérateur a sélectionné **Annuler** dans la boîte de dialogue de gestion des erreurs), vous pouvez relancer manuellement l’enregistrement fiscal en appelant une opération correspondante. Pour plus de détails, voir [Activer l’exécution manuelle d’un enregistrement fiscal reporté](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

### <a name="postpone-option"></a>Option de report

L’option **Reporter** vous permet de poursuivre le processus d’enregistrement fiscal si l’étape en cours échoue. Elle peut être utilisée lorsqu’il existe une option de sauvegarde de l’enregistrement fiscal.

### <a name="fiscal-registration-health-check"></a>Contrôle d’intégrité d’enregistrement fiscal

La procédure de contrôle d’intégrité des enregistrements fiscaux vérifie la disponibilité du dispositif ou du service fiscal lorsque des événements spécifiques ont lieu. Si l’enregistrement fiscal ne peut actuellement pas être réalisé, l’opérateur en est averti par avance.

L’appareil de PDV exécute le contrôle d’intégrité lorsque les événements suivants se produisent :

- Une nouvelle transaction est ouverte.
- Une transaction en suspens est rappelée.
- Une transaction de vente ou de retour est finalisée.

Si le contrôle d’intégrité échoue, l’appareil de PDV affiche la boîte de dialogue de contrôle d’intégrité. Cette boîte de dialogue contient les boutons suivants :

- **OK** : ce bouton permet à l’opérateur d’ignorer une erreur de contrôle d’intégrité et de continuer à traiter l’opération. L’opérateur ne peut sélectionner ce bouton que si l’autorisation **Autoriser d’ignorer l’erreur du contrôle d’intégrité** est activée pour lui.
- **Annuler** : si l’opérateur sélectionne ce bouton, l’appareil de PDV annule la dernière action (par exemple, un article n’est pas ajouté à une nouvelle transaction).

> [!NOTE]
> Le contrôle d’intégrité n’est effectué que si l’opération actuelle nécessite un enregistrement fiscal, et si le paramètre **Continuer lors d’erreurs** est désactivé pour l’étape actuelle du processus d’enregistrement fiscal. Pour plus de détails, voir [Définir les paramètres de traitement des erreurs](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

## <a name="storing-fiscal-response-in-fiscal-transaction"></a>Enregistrer la réponse fiscale dans la transaction fiscale

Si l’enregistrement fiscal d’une transaction ou d’un événement est une réussite, une transaction fiscale est créée dans la base de données du canal et associée à la transaction ou à l’événement d’origine. De même, si l’option **Ignorer** ou **Marquer comme enregistrée** est activée pour un enregistrement fiscal ayant connu un échec, ces informations sont enregistrées dans une transaction fiscale. Une transaction fiscale détient la réponse fiscale du périphérique ou du service fiscal. Si le processus d’enregistrement fiscal est constitué de plusieurs étapes, une transaction fiscale est créée pour chaque étape du processus ayant résulté en un échec ou une réussite de l’enregistrement.

Les transactions fiscales sont transférées vers Headquarters par la *Tâche-P*, de même que les transactions de vente au détail. Dans le raccourci **Transactions fiscales** de la page **Transactions de magasin**, vous pouvez afficher les transactions fiscales liées aux transactions de vente.

Une transaction fiscale stocke les informations suivantes :

- Les détails du processus d’enregistrement fiscal (processus, groupe de connecteurs, connecteur, etc.). Elle stocke également le numéro de série du périphérique fiscal dans le champ **Numéro de registre**, si ces informations sont incluses dans la réponse fiscale.
- Le statut de l’enregistrement fiscal : **Terminé** pour un enregistrement réussi, **Ignoré** si l’opérateur a sélectionné l’option **Ignorer** pour un enregistrement échoué, ou **Marquée comme enregistrée** si l’opérateur a sélectionné l’option **Marquer comme enregistrée** ou **Reportée** si l’opérateur a sélectionné l’option **Reporter**.
- Les transactions de code d’informations associées à une transaction fiscale sélectionnée. Pour afficher les transactions de code d’informations, dans le raccourci **Transactions fiscales**, sélectionnez une transaction fiscale dont le statut est défini sur **Ignoré** ou **Marquée comme enregistrée** ou **Reportée**, puis sélectionnez **Transactions de code info**.

En sélectionnant **Données étendues**, vous pouvez également afficher certaines propriétés de la transaction fiscale. La liste des propriétés pouvant être affichées est spécifique à la fonctionnalité d’enregistrement fiscal qui a généré la transaction fiscale. Par exemple, vous pouvez afficher la signature numérique, le numéro séquentiel, l’empreinte numérique du certificat, l’identification de l’algorithme de hachage et d’autres propriétés de transaction fiscale pour la fonctionnalité de signature numérique pour la France.

## <a name="fiscal-texts-for-discounts"></a>Textes fiscaux pour les remises

Certains pays ou certaines régions ont des besoins spéciaux concernant des textes supplémentaires à imprimer sur des reçus fiscaux lorsque différents types de remises sont appliqués. La fonctionnalité d’intégration fiscale vous permet de paramétrer un texte spécial pour une remise imprimée après une ligne de remise sur un reçu fiscal. Pour les remises manuelles, vous pouvez configurer un texte fiscal pour le code info spécifié comme code info **Remise de produit** dans le profil de fonctionnalité du PDV. Pour plus de détails sur le paramétrage des textes fiscaux pour les remises, voir [Configurer les textes fiscaux pour les remises](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Impression des états fiscaux X/Z

La fonctionnalité d’intégration fiscale prend en charge la génération des relevés de clôture de caisse qui sont spécifiques au périphérique ou au service fiscal intégré :

- De nouveaux boutons qui exécutent des opérations correspondantes doivent être ajoutés à la mise en page de l’écran du PDV. Pour en savoir plus, voir [Configurer les états fiscaux X/Z depuis le PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- Dans l’exemple d’intégration fiscale, ces opérations doivent être associées aux opérations correspondantes du périphérique fiscal.

## <a name="fiscal-integration-samples-in-the-commerce-sdk"></a>Exemples d’intégration fiscale dans le SDK Commerce

Des exemples d’intégration fiscale sont actuellement disponibles dans le SDK Commerce :

- [Exemple d’intégration de l’imprimante fiscale pour l’Italie](./emea-ita-fpi-sample.md)
- [Exemple d’intégration de l’imprimante fiscale pour la Pologne](./emea-pol-fpi-sample.md)
- [Exemple d’intégration du service d’enregistrement fiscal pour l’Australie](./emea-aut-fi-sample.md)
- [Exemple d’intégration du service d’enregistrement fiscal pour la République tchèque](./emea-cze-fi-sample.md)
- [Exemple d’intégration de l’unité de contrôle pour la Suède](./emea-swe-fi-sample.md)
- [Exemple d’intégration du service d’enregistrement fiscal pour l’Allemagne](./emea-deu-fi-sample.md)
- [Exemple d’intégration de l’imprimante fiscale pour la Russie](./rus-fpi-sample.md)

La fonctionnalité d’intégration fiscale suivante est également implémentée à l’aide du cadre d’intégration fiscale, mais elle est prête à l’emploi et n’est pas incluse dans le SDK Commerce :

- [Enregistrement fiscal pour le Brésil](./latam-bra-commerce-localization.md#fiscal-registration-for-brazil)
- [Signature numérique pour la France](./emea-fra-cash-registers.md)

La fonctionnalité d’intégration fiscale suivante est également disponible dans le SDK Commerce, mais ne bénéficie pas actuellement du cadre de l’intégration fiscale. La migration de cette fonctionnalité vers le cadre de l’intégration fiscale est prévue pour des mises à jour ultérieures.

- [Signature numérique pour la Norvège](./emea-nor-cash-registers.md)

La fonctionnalité d’intégration fiscale héritée suivante, disponible dans le Kit de développement logiciel (SDK) Commerce, n’utilise pas l’infrastructure d’intégration fiscale et sera rendue obsolète dans les mises à jour ultérieures :

- [Exemple d’intégration de l’unité de contrôle pour la Suède (hérité)](./retail-sdk-control-unit-sample.md)
- [Signature numérique pour la France (héritée)](./emea-fra-deployment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
