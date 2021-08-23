---
title: Module Enregistrement pour retrait
description: Cette rubrique décrit le module Enregistrement pour retrait et explique comment le configurer dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f6359f41f3b97325db4fda083dc32d39839811297a96a1f2d99a93990c00afae
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747463"
---
# <a name="check-in-for-pickup-module"></a>Module Enregistrement pour retrait

[!include [banner](includes/banner.md)]

Cette rubrique décrit le module Enregistrement pour retrait et explique comment le configurer dans Microsoft Dynamics 365 Commerce.

Le module d’enregistrement pour retrait fournit une page de confirmation aux client qui utilisent les capacités d’enregistrement de Dynamics 365 Commerce pour informer un magasin de leur arrivée. Le module d’enregistrement pour retrait vous permet également de configurer un formulaire qui recueille des informations supplémentaires auprès des clients pour faciliter la livraison de la commande. Ces informations comprennent le numéro de parking du client, ainsi que la marque et le modèle de son véhicule. 

## <a name="module-properties"></a>Propriétés du module

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Texte de confirmation | Chaîne de texte | Contenu de l’en-tête qui apparaît sur la page de confirmation d’enregistrement. |
| Afficher le code QR | **Vrai** ou **Faux** | Lorsque cette propriété est définie sur **True**, la page de confirmation d’enregistrement affiche un code QR qui représente l’ID de confirmation de commande. |
| Informations supplémentaires (titre) | Chaîne de texte | Contenu de l’en-tête qui apparaît lorsque des champs d’informations supplémentaires ont été configurés. |
| Informations supplémentaires (clés) | Paire ID de la ressource / valeur de ressource | Chaque clé crée un champ de formulaire et une étiquette associée qui sont utilisés pour collecter des informations supplémentaires auprès des clients. |
| Informations supplémentaires (clés) \> ID de la ressource | Chaîne de texte | Chaque clé d’informations crée un champ de formulaire et une étiquette associée qui sont utilisés pour collecter des informations supplémentaires auprès des clients. Cette propriété identifie la clé d’informations supplémentaires. Dans la tâche créée dans le point de vente (POS), la valeur de cette propriété est affichée comme étiquette dans le champ d’instructions. |
| Informations supplémentaires (clés) \> Valeur de ressource | Chaîne de texte | Le libellé du champ de texte dans la tâche dans le PDV. |
| Informations supplémentaires (clés) \> Requis | **Vrai** ou **Faux** | Cette propriété spécifie si les clients doivent remplir le champ du formulaire pour pouvoir continuer. Lorsque cette propriété est définie sur **True**, un astérisque est affiché à côté de l’étiquette du formulaire et la valeur NULL est vérifiée pour empêcher les clients de continuer si aucune valeur n’est entrée. |

## <a name="add-the-check-in-for-pickup-module-to-a-page"></a>Ajouter le module d’enregistrement pour retrait à une page

Le module d’enregistrement pour retrait doit être ajouté à la nouvelle page que vous créez pour la confirmation d’enregistrement. Cette page servira à confirmer l’enregistrement des clients qui sélectionnent le lien ou bouton **Je suis là** dans leur e-mail. 

## <a name="configure-the-additional-information-form"></a>Configurer le formulaire d’informations supplémentaires

Par défaut, si aucune clé d’informations supplémentaires n’est configurée, le module affiche aux clients la page de confirmation d’enregistrement. Lorsque la confirmation d’enregistrement est affichée, une tâche est créée dans le PDV du magasin où la commande est retirée.

Lorsqu’une ou plusieurs clés d’informations supplémentaires sont configurées, les clients sont d’abord invités à saisir des informations. Lorsqu’ils sélectionnent **Soumettre**, ils reçoivent une confirmation d’enregistrement et une tâche est créée dans le PDV. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Activer les notifications d’enregistrement des clients dans le point de vente (PDV)](enable-customer-check-in.md)
