---
title: Configurer les taux
description: Les taux dans Microsoft Dynamics 365 Human Resources définissent combien les employeurs et les employés cotisent pour un avantage.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2deb20646a532509c9e3a3e7a39f646bced2a3fb
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693113"
---
# <a name="configure-rates"></a>Configurer les taux


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Les taux définissent combien les employeurs et les employés cotisent pour un avantage. La valeur peut être un montant ou un nombre de crédits flexibles, selon votre configuration.

Utilisez les taux pour déterminer combien les employés et les employeurs paient pour chaque avantage, en fonction de plusieurs facteurs. Les taux de couverture sont effectifs à une certaine date, vous pouvez donc conserver un historique des taux. 

## <a name="set-up-rates"></a>Configuration des taux

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Taux**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Taux** | Nom unique qui identifie le taux d’avantage. |
   | **Description** | Description du taux d’avantage. |
   | **Date d’effet** | Date à laquelle ce taux devient effectif. La valeur par défaut est la date système actuelle. Cette date doit coïncider ou être antérieure à votre période d’avantage. Une bonne pratique consiste à fixer cette date à la date du régime d’avantages. |
   | **Expiration** | Date de fin du taux. 31/12/2154 (qui représente jamais) est la valeur par défaut. |
   | **Utiliser les niveaux** |  Utilisez ce champ si vous avez une logique qui doit être utilisée pour déterminer un taux. Par exemple, si un taux doit augmenter en fonction de l’âge, sélectionnez une valeur ici. Sélectionnez **Niveau unique** pour un taux d’avantage à un niveau ou **Deux niveaux** pour un taux d’avantage à deux niveaux. Un exemple de double niveau est un niveau basé sur le sexe et l’âge. Après avoir sélectionné une valeur, sélectionnez **Actions**, puis sélectionnez **Taux de niveau**. Si vous avez un taux forfaitaire qui ne change pas, laissez ce champ vide. |
   | **Fréquence de paiement** | Précisez la fréquence à laquelle le taux de prime des prestations doit être payé au prestataire. Les tarifs que vous saisissez sur la page, décrits plus loin dans cette rubrique, seront basés sur la fréquence de paiement que vous spécifiez ici. Par exemple, si vous saisissez **Mensuel** dans ce champ, et que vous saisissez un taux d’employé de **100 EUR**, cela suppose que l’avantage coûtera à l’employé 100 EUR par mois. Cependant, un employé peut être payé deux fois par mois, en fonction de la fréquence de paiement des avantages définie dans son enregistrement. Dans ce cas, lorsque l’employé se connecte au **Libre service des employés**, le montant qu’il paiera sera de 50 EUR, car le taux affiché par le **Libre service des employés** est basé sur la fréquence de paiement de l’employé. |
   | **Arrondi du taux de la fréquence de rémunération** | Les méthodes pour arrondir le taux sont : Standard, Tronqué, Normal, Inférieur et Arrondi vers le haut. </br></br><ul><li>**Standard** : Toujours arrondir vers le haut. Par exemple, 10,611 sera arrondi à 10,62. -10,231 sera arrondi à -10,23. </li><li>**Tronqué** : Toujours arrondir vers le bas. Par exemple, 10,619 sera arrondi à 10,61. -10,231 sera arrondi à -10,24. </li><li>**Normal** : les valeurs décimales se terminant par 5 ou un chiffre supérieur seront arrondies en s’éloignant de zéro. Les valeurs décimales se terminant par 4 ou un chiffre inférieur seront arrondies vers zéro. Par exemple, 10,615 sera arrondi à 10,62. -10,235 sera arrondi à -10,24. 10,614 sera arrondi à 10,61. -10,234 sera arrondi à -10,23. </li><li>**Vers le bas** : Arrondir vers zéro. Par exemple, 10,619 sera arrondi à 10,61. -10,231 sera arrondi à -10,23. </li><li>**Arrondir vers le haut** : Arrondir en s’éloignant de zéro. Par exemple, 10,619 sera arrondi à 10,62. -10,231 sera arrondi à -10,24. |
   | **Montant de l’employé non fumeur** | Le montant que le fournisseur d’avantages facture pour un employé non-fumeur. Il s’agit du montant que l’employeur verse au fournisseur d’avantage et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Montant de l’employeur non fumeur** | Le montant que le fournisseur d’avantages facture pour un employé non-fumeur. Il s’agit du montant que l’employeur verse au prestataire de l’avantage et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Montant de l’employé fumeur** | Le montant que le fournisseur d’avantages facture pour un employé fumeur. Il s’agit du montant que l’employeur verse au fournisseur d’avantage et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Montant de l’employeur fumeur** | Le montant que le fournisseur d’avantages facture pour un employé fumeur. Il s’agit du montant que l’employeur verse au fournisseur d’avantage et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Montant administratif** | Montant administratif facturé par un administrateur tiers. Il s’agit du montant que l’employeur verse à l’administrateur tiers et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Taux de crédit flexible** | Nombre de crédits flexibles que l’avantage coûte. Cela s’applique uniquement aux taux des plans d’avantage qui sont associés aux programmes de crédits flexibles. Si vous utilisez des taux échelonnés, le taux de crédit flexible est défini dans Actions > Taux échelonnés. |
   | **Modifier la date d’effet** | Date à laquelle le taux de l’avantage prend effet. Le système modifiera automatiquement le taux de l’avantage et mettra à jour tous les plans d’avantage associés à ce taux, à condition que vous exécutiez le traitement de mise à jour du changement de taux. Vous ne devez pas définir cette date, sauf si vous souhaitez que le système mette automatiquement à jour les plans d’avantages des employés en fonction de ce taux. Ceci est normalement réservé au traitement automatique des changements de taux futurs. La **Date d’entrée en vigueur du changement** doit être comprise dans les dates d’entrée en vigueur et d’expiration du taux d’avantage. |
   | **Modification du taux effectuée** | La case à cocher **Modification du taux effectuée** sera automatiquement cochée une fois que les modifications du taux d’avantage auront été effectuées par le traitement de mise à jour de la modification du taux. |

4. Pour effectuer le suivi et conserver les modifications apportées à la configuration du taux des avantages, sélectionnez **Actions**, puis sélectionnez **Tenir les versions à jour**.

5. Sélectionnez **Enregistrer**. 

## <a name="set-up-tier-rates"></a>Configuration des taux échelonnés

Vous pouvez utiliser des taux échelonnés dans votre configuration de taux si le taux varie en fonction de divers facteurs. Par exemple, vous pouvez configurer des taux échelonnés pour dire que si votre âge atteint 34,99 ans, le montant pour non-fumeurs est de 2. Si votre âge atteint 39,99 ans, le montant pour non-fumeurs est de 3.

Vous pouvez également utiliser des niveaux doubles. Si vous sélectionnez **Niveau double** pour la valeur **Utiliser des niveaux** sur le formulaire **Paramétrage des taux**, vous pouvez définir des taux basés sur deux dimensions. Par exemple, vous pouvez configurer un système de taux double pour dire que si vous êtes un homme et que votre âge atteint 34,99 ans, le montant pour non-fumeurs est de 2. Si vous êtes un homme et que votre âge atteint 39,99 ans, le montant pour non-fumeurs est de 3. Si vous êtes une femme et que votre âge atteint 34,99 ans, le montant pour non-fumeurs est de 1.8. Si vous êtes une femme et que votre âge atteint 39,99 ans, le montant pour non-fumeurs est de 2.8.

> [!IMPORTANT]
> Dans l’enregistrement du collaborateur, sous **Informations personnelles** se trouve une option indiquant si l’employé est fumeur. Si l’employé est enregistré comme fumeur, le taux fumeur sera utilisé. (L’indication fumeur n’est jamais affichée à l’employé.)
   
1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Taux**.

2. Sélectionnez un ou plusieurs taux dans la liste, sélectionnez **Actions**, puis sélectionnez **Taux échelonnés**.

3. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- | 
   | **Description** | La valeur du champ **Description** est appliquée à partir de la description dans l’enregistrement de configuration du taux. Cela vous aide à identifier la configuration de taux à laquelle les taux échelonnés sont liés. |
   | **Code de niveau** | Sélectionnez un code de niveau. Les codes de niveau sont définis dans la page **Codes de niveau**. Le système affichera automatiquement la description du code de niveau dans la grille de gauche. |
   | **Type de niveau** | Spécifie quel champ doit être utilisé comme critère de sélection pour le processus de calcul de taux de niveau. Par exemple :</br></br><ul><li>Si **Âge** est utilisé, le système utilisera la date de naissance de l’employé dans le processus de calcul du taux des avantages.</li><li>Si **Salaire** est utilisé, le système utilisera le salaire annuel avec avantages de l’employé dans le processus de calcul du taux des avantages.</li><li>Si **Type d’emploi** est utilisé, le système utilise l’enregistrement de poste actif actuel de l’employé pour déterminer le type d’emploi selon l’enregistrement d’emploi lié au poste.</li></ul></br></br>Les types de niveaux sont **Âge**, **Salaire**, **Physique**, **Sexe**, **Équivalent temps plein**, **Type de poste**, **Région de rémunération** et **Niveau**. | 
   | **Niveau** | Valeur à utiliser avec le type de niveau lors du processus de calcul du taux d’avantage. Par exemple :</br></br><ul><li>Si le type de niveau est **Âge**, ce serait la valeur d’âge.</li><li>Si le type de niveau est **Salaire**, ce serait le montant du salaire.</li><li> Si le type de niveau est **Type de poste**, ce serait le type de poste.</li></ul></br></br>Avec un type de niveau **Âge** ou **Salaire**, la valeur du champ **Niveau** représente la limite supérieure du niveau. Avec un type de niveau **Type de poste**, le système utilise une approche de correspondance exacte lors de la sélection du taux de niveau. |
   | **Type de calcul** | Spécifie comment utiliser le montant dans le champ du montant de calcul et quel calcul mathématique effectuer si nécessaire. Si le type de calcul est un montant forfaitaire, le système utilise les champs de montant tels quels. Si le type de calcul est par montant de salaire ou de couverture en EUR, le système utilise le montant de calcul et la direction de calcul dans son calcul mathématique.</br></br>Si le type de calcul est par montant du salaire en EUR, le système utilise l’équation mathématique suivante :</br></br>Salaire annuel des avantages divisé par le montant de calcul (arrondi vers le haut ou vers le bas) multiplié par les montants pour fumeur ou non-fumeur pour l’employé ou l’employeur.</br></br>Si le type de calcul est par montant de couverture en EUR, le système utilise l’équation mathématique suivante :</br></br>Montant de couverture divisé par le montant de calcul (arrondi vers le haut ou vers le bas) multiplié par les montants pour fumeur ou non-fumeur pour l’employé ou l’employeur.</br></br>Dans les deux calculs, la direction du calcul est utilisée pour déterminer s’il faut arrondir le salaire de l’avantage annuel ou le montant de couverture divisé par le montant du calcul vers le haut ou vers le bas. |
   | **Montant du calcul** | Montant à utiliser pendant le processus de calcul du taux d’avantage. Ce montant sera le diviseur lors du calcul mathématique du taux échelonné. |
   | **Sens du calcul** | Direction selon laquelle le montant du résultat calculé doit être arrondi. Le système prend en charge trois directions de calcul : vide (méthode exacte), **augmentation** et **diminution**.</br></br><ul><li>Pour vide, le système utilisera le calcul exact du montant du salaire/de la couverture divisé par le montant du calcul. Si cette valeur a une fraction, le système l’utilise dans son calcul.</li><li>Pour une **augmentation**, le calcul mathématique augmentera le montant du salaire/de la couverture divisé par le montant du calcul à l’entier suivant, ce qui signifie que 12,25 passerait à 13.</li><li>Pour une **diminution**, le calcul mathématique diminuera le montant du salaire/de la couverture divisé par le montant du calcul à l’entier actuel, ce qui signifie que 12,25 passerait à 12.</li></ul> |
   | **Montant de l’employé non fumeur** | Montant qu’un fournisseur d’avantages facture pour un employé non-fumeur. Il s’agit du montant que l’employeur verse au prestataire de l’avantage et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Montant de l’employeur non fumeur** | Montant qu’un fournisseur d’avantages facture pour un employé non-fumeur. Il s’agit du montant que l’employeur verse au prestataire de l’avantage et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Montant de l’employé fumeur** | Montant qu’un fournisseur d’avantages facture pour un employé non-fumeur. Il s’agit du montant que l’employeur verse au prestataire de l’avantage et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Montant de l’employeur fumeur** | Montant qu’un fournisseur d’avantages facture pour un employé non-fumeur. Il s’agit du montant que l’employeur verse au prestataire de l’avantage et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Montant administratif** | Montant administratif facturé par un administrateur tiers. Il s’agit du montant que l’employeur verse à l’administrateur tiers et il doit être basé sur la fréquence de paiement pour la configuration du taux. |
   | **Taux non fumeur de crédit flexible** | Nombre de crédits flexibles des coûts des avantages, basé sur le calcul défini pour le niveau échelonné pour les non-fumeurs. Par exemple, si le calcul est **Par montant en $ de couverture**, le montant de calcul est 10 000 et le taux non fumeur de crédit flexible est 6, ce qui signifie que si un employé non fumeur choisit 10 000 $ de couverture, cela coûtera 6 crédits flexibles. S’ils choisissent une couverture de 20 000 $, cela coûtera 12 crédits flexibles, etc. |
   | **Taux fumeur de crédit flexible** | Nombre de crédits flexibles des coûts des avantages, basé sur le calcul défini pour le niveau échelonné pour les fumeurs. |

5. Sélectionnez **Enregistrer**. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
