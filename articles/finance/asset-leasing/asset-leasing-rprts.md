---
title: États de location d’actifs
description: Cette rubrique répertorie et décrit brièvement les états disponibles dans la location d’actifs.
author: moaamer
manager: Ann Beebe
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-27
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4bc4bac1a422a7505ef4c66b9c3b79a3d754cc4d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971476"
---
# <a name="asset-leasing-reports"></a>États de location d’actifs

[!include [banner](../includes/banner.md)]

Cette rubrique répertorie et décrit brièvement les états disponibles dans la location d’actifs. La plupart des états s’affichent en exécutant ces étapes ou des étapes très similaires, comme indiqué). 

- Pour afficher la plupart des états de location d’actifs, accédez à **Location d’actifs > Recherches et états > États de bail**, puis sélectionnez un état à afficher. Pour les états qui nécessitent un autre chemin de sélection, les étapes d’ouverture de l’état sont incluses dans la description de cet état. 
- Lorsque vous sélectionnez un état à imprimer, une page de paramètres s’ouvre et vous permet de filtrer les informations incluses dans l’état. Saisissez les critères de filtre, puis sélectionnez **OK** pour générer l’état. L’état généré affiche les informations comprises dans les filtres que vous avez spécifiés.

## <a name="asset-movement"></a>Mouvement d’actif
L’état sur les mouvements d’actifs sert d’état de récupération pour les soldes du droit d’utilisation de l’actif pour chaque bail. Avec cet état, visualisez les transactions d’actifs d’un bail pendant une période spécifiée. L’état couvre les champs suivants. 

|     Champs d’état                  |     Description                                                                |
|------------------------------------|--------------------------------------------------------------------------------|
|     Date d’entrée en vigueur              |     La date de début de la version la plus ancienne du bail.                     |   
|     Durée du bail                     |     La durée du bail de la version la plus ancienne du bail.                            |
|     Bail à court terme               |     Si le bail est classé comme un bail à court terme, **Oui** s’affiche.         |
|     Bail de faible valeur                |     Si le bail est classé comme un bail de faible valeur, **Oui** s’affiche.          |
|     Droit d’utilisation initial de l’actif     |     La valeur d’origine du droit d’utilisation de l’actif depuis l’entrée de journal de comptabilisation initiale.      |
|     Solde d’ouverture              |     La valeur nette du droit d’utilisation de l’actif à compter de la **Date de début**.                         |
|     Dépenses de dépréciation au cours de la période    |     Le montant de la dépense d’amortissement prise dans la plage de dates définie pour l’état.        |
|     Amortissement cumulé       |     Le montant de l’amortissement cumulé à compter de la **Date de début**.                               |
|     Dépréciation                     |     Le montant de l’actif a été déprécié dans la plage de dates définie pour l’état.               |
|     Modifications                  |     Le montant des ajustements du droit d’utilisation de l’actif entre les paramètres de date.                            |
|     Valeur comptable nette                 |     La valeur nette finale du droit d’utilisation de l’actif, qui est la valeur nette des amortissements cumulés à la **Date du jour**.    |

## <a name="differences-report"></a>État Différences
L’état Différences présente les différences entre les informations chargées dans l’infrastructure d’importation du bail et les informations actuellement dans le système. Cela vous permet de comparer ce qui a été ajusté, mis à jour ou ajouté via l’infrastructure d’importation de bail.  

Les valeurs de l’état varient en fonction du bail sélectionné. L’état n’affiche que les champs qui diffèrent de ce qui se trouve actuellement dans le système et de ce qui se trouve dans les tables intermédiaires. L’ancienne valeur correspond à ce qui se trouve actuellement dans le système ou à ce qui était auparavant dans le système, selon que le processus d’importation a été exécuté ou non. La nouvelle valeur affiche la valeur qui se trouve dans la table intermédiaire qui remplace l’ancienne valeur.

## <a name="five-years-undiscounted-payment-forecast"></a>Prévision du paiement non remisé sur cinq ans
L’état sur les prévisions de paiement non remisé sur cinq ans indique les paiements de location non remisés prévus à régler au cours des cinq prochaines années à compter de la date spécifiée dans les paramètres de l’état. L’état couvre les champs suivants. 

|     Champs d’état         |     Description                                                                                       |
|-------------------------- |---------------------------------------------------------------------------------------------------    |
|     Description du bail     |     La description du bail depuis l’en-tête du bail.                                                      |
|     ID de bail              |     ID de bail unique.                                                                              |
|     Réserver                  |     Registre de location associé à l’ID de registre.                                                         |
|     Classification        |     Classification du bail.                                                                  |
|     Couche de comptabilisation         |     Couche sur laquelle ce bail est publié.                                                         |
|     Devise              |     Devise du bail.                                                                        |
|     Actuelle               |     Somme de tous les paiements de location à régler dans les 12 prochains mois à compter de la date de génération des états.          |
|     13 à 24 mois          |     Somme de tous les paiements de location à régler entre 13 et 24 mois à compter de la date de génération des états.           |
|     25 à 36 mois          |     Somme de tous les paiements de location à régler entre 25 et 36 mois à compter de la date de génération des états.           |
|     37 à 48 mois          |     Somme de tous les paiements de location à régler entre 37 et 48 mois à compter de la date de génération des états.           |
|     49 à 60 mois          |     Somme de tous les paiements de location à régler entre 49 et 60 mois à compter de la date de génération des états.           |
|     Ensuite            |     Somme de tous les paiements de location à régler le 61ème mois ou après à compter de la date de génération des états.              |

## <a name="gaap-cash-flows-report"></a>État des flux de trésorerie GAAP
L’état des divulgations GAAP satisfait à l’exigence de divulgation US GAAP spécifiée dans 842-20-50-4(g)(1). Pour consulter cet état, accédez à **Location d’actifs > Recherches et états > Divulgations > GAAP - flux de trésorerie**. 

|     Champs d’état                                 |     Description                                                                                                                                               |
|------------------------------------------------   |-----------------------------------------------------------------------------  |
|     Date de début <br> Au                        |     Définit une plage de dates utilisée pour restreindre les informations incluses dans l’état.      |
|     Entité juridique                                  |     Entité juridique liée aux baux.                                      |
|     Type de bail                                    |     Classification du bail comme financier ou opérationnel.           |
|     ID de bail                                      |     ID de bail unique.                                                      |
|     Description du bail                             |     La description du bail depuis l’en-tête du bail.                              |
|     Registre de location                                    |     Registre de location auquel la ligne se réfère.                        |
|     Couche de comptabilisation                                 |     Chaque registre associé à une immobilisation est paramétré pour une couche de validation particulière qui a un objectif d’amortissement global.                          |
|     Groupe de baux                                   |     Groupe auquel le bail est lié.                                     |
|     Devise                                      |     Abréviation de la devise transactionnelle utilisée. Tous les états convertissent la devise transactionnelle en devise de déclaration.                      |
|     Contrats de location-financement : flux de trésorerie d’exploitation         |     Somme du total des paiements variables comptabilisés et du total des paiements d’intérêts comptabilisés à partir du programme d’amortissement entre les paramètres de date.        |
|     Contrats de location-financement : flux de trésorerie de financement           |     Somme du total des paiements principaux depuis le programme d’amortissement entre les paramètres de date.       |
|     Contrats de location simple : flux de trésorerie d’exploitation       |     Somme de tous les paiements de location comptabilisés et des paiements variables comptabilisés entre les paramètres de date.            |

## <a name="lease-balances-forecast"></a>Prévision des soldes de loyer
La prévision des soldes de location répertorie les informations directement à partir du programme d’amortissement du passif et du programme d’amortissement des actifs. L’état présente les montants prévus du passif de location prévu et du droit d’utilisation de l’actif sur une période donnée, y compris toutes les dépenses prévues pour ces baux. L’état couvre les champs suivants.

|     Champs d’état                 |     Description                                                                                                                                                                               |
|---------------------------------  |--------------------------------------------------------------------------------------------------------------------   |
|     Solde d’ouverture             |     Le solde de début du programme d’amortissement du bail pour la période contenant la date de début de l’état.            |
|     Reconnaissance initiale           |     Si la date de début du bail se situe dans la plage de dates définie pour l’état, cette colonne affiche la valeur du compte passif de l’entrée de journal de comptabilisation initiale.      |
|     Paiements                      |     Somme des paiements de location qui tombent dans la plage de dates définie pour l’état.                               |
|     Intérêts                      |     Somme des charges d’intérêts de location qui tombent dans la plage de dates définie pour l’état.                    |
|     Solde de fin                |     Le solde du passif du bail **À ce jour**.                                                             |
|     Passif à court terme          |     Le montant du passif à court terme dans le tableau d’amortissement du bail **À ce jour**.                           |
|     Passif à long terme           |     Le montant du passif à long terme dans le tableau d’amortissement du bail **À ce jour**.                            |
|     Valeur nette de début      |     La « valeur nette de début » du programme d’amortissement de l’actif du bail pour la période contenant la date de début de l’état.      |
|     Reconnaissance initiale           |     Si la date de début du bail se situe entre les paramètres de dates définie pour l’état, cette colonne affiche la valeur du compte d’actif de l’entrée de journal de comptabilisation initiale.            |
|     Dépenses d’amortissement          |     Somme des dépenses d’amortissement de location qui tombent dans la plage de dates définie pour l’état.                  |
|     Solde de fin                |     Solde de l’actif à compter du bail **À ce jour**.                                                              |
|     Ajustement des capitaux propres             |     Solde de début moins la valeur nette de départ.                                                             |

## <a name="lease-commencements-report"></a>État d’entrée en vigueur du bail
L’état d’entrée en vigueur du bail présente tous les baux qui ont commencé dans une plage de date spécifique, y compris les soldes de passif initial et de droit d’utilisation de l’actif. L’état couvre les champs suivants. 

|     Champs d’état                 |     Description                                                                                       |
|---------------------------------  |---------------------------------------------------------------------------------------------------    |
|     Date d’entrée en vigueur             |     Date d’entrée de journal de comptabilisation initiale validée pour cette version de bail.         |
|     Montant du passif locatif      |     Montant du passif depuis l’entrée de journal de comptabilisation initiale.                                  |
|     Montant de l’actif initial          |     Montant de l’actif depuis l’entrée de journal de comptabilisation initiale.                                      |

## <a name="lease-modification-report"></a>État de modification du bail
L’état de modification du bail présente tous les baux qui ont été modifiés dans une plage de date spécifiée. L’état montre également l’utilisateur ayant ajusté le bail et le montant total du passif ajusté. L’état couvre les champs suivants. 

|     Champs d’état                 |     Description           |
|---------------------------------  |-------------------------  |
|     Ajusté par                   |     Le nom d’utilisateur de la personne qui a modifié le bail.                                |
|     Destinée de l’ajustement               |     Date à laquelle l’entrée de journal d’ajustement a été validée.                        |
|     Ajustements                   |     Le montant de toute entrée de journal d’ajustement imputée au compte de passif du bail entre les paramètres de date. Les crédits apparaîtront positifs, tandis que les débits seront négatifs.       |
|     Montant de gain (perte)            |     Le montant de toute entrée de journal d’ajustement imputée au compte de gain/perte du bail entre les paramètres de date. Les crédits apparaîtront positifs, tandis que les débits seront négatifs.       |
|     Bénéfices non répartis             |     Le montant de toute entrée de journal d’ajustement imputée au compte de bénéfices non répartis du bail entre les paramètres de date.      |
|     Solde du passif à la fin de la période      |     Le solde du passif à la fin de période en tant que date d’ajustement du bail.           |

## <a name="lease-movement-report"></a>État des mouvements du bail
L’état des mouvements du bail sert d’état de récupération pour les soldes du droit d’utilisation de l’actif pour chaque bail. Cet état permet à l’utilisateur de voir les transactions de passif d’un bail pendant une période spécifiée.

|     Champs d’état             |     Description                                               |
|----------------------------   |-------------------------------------------------------------- |
|     Date d’entrée en vigueur         |     La date de début de la version la plus ancienne du bail.    |
|     Durée du bail                |     La durée du bail de la version la plus ancienne du bail.           |
|     Paiements restants        |     Le nombre de paiements qui n’ont pas encore été comptabilisés pour le bail.                       |
|     Solde d’ouverture         |     La somme de toutes les transactions concernant le passif du bail qui ont eu lieu avant la date de début de l’état.             |
|     Reconnaissance initiale       |     Montant de toute transaction de comptabilisation initiale pour le bail qui a été comptabilisé dans la plage de dates définie pour l’état.     |
|     Paiements                  |     Somme des transactions de paiement du bail comptabilisées dans la plage de dates définie pour l’état. Les valeurs de cette colonne apparaîtront sous forme de montants négatifs, car les paiements diminuent le solde du passif du bail.  |
|     Intérêts                  |     Somme des régularisations d֦’intérêts comptabilisées par rapport au bail dans la plage de dates définie pour l’état.            |
|     Ajustements               |     Somme des transactions d’ajustement comptabilisées du bail qui tombent dans la plage de dates définie pour l’état.                               |
|     Solde de fin            |     Le solde de toutes les transactions de passif du bail qui ont été comptabilisées **À ce jour** dans l’état.                  |

## <a name="lease-transactions-report"></a>État des transactions de location
L’interrogation des transactions de location affiche toutes les entrées de journal qui ont été générées par la location d’actifs. Chaque entrée de journal est liée à l’ID de registre dont elle provenait. Cela vous permet d’associer facilement l’entrée de journal au bail correspondant. L’interrogation des transactions de location fonctionne d’une manière similaire à la page **Pièces comptables** en comptabilité.

## <a name="weighted-average-discount-rate-report"></a>État sur le taux de retour de la moyenne pondérée
L’état sur le taux de retour de la moyenne pondérée répond au besoin de divulgation US GAAP spécifié dans ASC 842-20-50-4(g)(4) pour un taux de retour de la moyenne pondérée. Pour consulter cet état, accédez à **Location d’actifs > Recherches et états > Divulgations > Taux de retour de la moyenne pondérée**. L’état couvre les champs suivants. 

|     Champs d’état                     |     Description                                                           |
|------------------------------------   |------------------------------------------------------------------------   |
|     Date de référence                        |     Cet état comprendra tous les baux qui ont débuté le ou avant le paramètre de date **À partir du**. Cet état doit être exécuté à compter du dernier jour de la période à divulguer.      |
|     Entité juridique                      |     L’entité juridique qui est liée au bail.                           |
|     ID de bail                          |     ID de bail unique.                                                  |
|     Description du bail                 |     La description du bail depuis l’en-tête du bail.                          |
|     Réserver                              |     Le type de livre spécifique du bail affiché.                                                                                                                                            |
|     Couche de validation                     |     Chaque registre associé à une immobilisation est paramétré pour une couche de validation particulière qui a un objectif d’amortissement global.      |
|     Groupe de baux                       |     Groupe auquel le bail appartient.                                 |
|     Taux de remise                     |     Le taux utilisé pour actualiser les paiements de location.                             |
|     Devise                          |     Abréviation de la devise transactionnelle utilisée. Tous les états convertissent la devise transactionnelle en devise de déclaration.  |
|     Paiements de loyer restants          |     Le montant total des paiements de location impayés du calendrier de paiement restant à compter de la date **À partir du**.            |
|     Paiements pondérés restants       |     Reste des paiements de location multipliés par le taux de retour utilisé.   |
