---
title: Oferta de imagen de contenedor de Azure | Microsoft Docs
description: Información general del proceso de publicación de una oferta de contenedor en Azure Marketplace.
services: Azure, Marketplace, Cloud Partner Portal,
documentationcenter: ''
author: dan-wesley
manager: Patrick.Butler
editor: ''
ms.assetid: ''
ms.service: marketplace
ms.workload: ''
ms.tgt_pltfrm: ''
ms.devlang: ''
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: pbutlerm
ms.openlocfilehash: e40e83e16ab2bfd43c3bb5fa38e52a778694e90e
ms.sourcegitcommit: 1fc949dab883453ac960e02d882e613806fabe6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980426"
---
# <a name="containers"></a>Contenedores

<table> <tr> <td>En esta sección se explica cómo publicar una imagen de contenedor en <a href="https://azuremarketplace.microsoft.com">Azure Marketplace</a>.  
El tipo de oferta de contenedor admite imágenes de contenedor de Docker aprovisionadas como instancias de <a href="https://docs.microsoft.com/azure/aks/index">Azure Kubernetes Service</a> o <a href="https://docs.microsoft.com/azure/container-instances/container-instances-overview">Azure Container Instances</a> y hospedadas en un repositorio de <a href="https://docs.microsoft.com/azure/container-registry">Azure Container Registry</a>. </td> <td><img src="./media/container-icon.png"  alt="Azure container icon" /></td> </tr> </table>

## <a name="offer-components"></a>Componentes de la oferta

En esta sección se describen los elementos de la publicación de un contenedor, y está pensada como una guía para el publicador en Azure Marketplace. La publicación se divide en las siguientes partes principales:

- [Requisitos previos](./cpp-prerequisites.md): se enumeran los requisitos técnicos y empresariales antes de crear o publicar una oferta de contenedor.
- [Creación de la oferta](./cpp-create-offer.md): se enumeran los pasos necesarios para crear una entrada de oferta de contenedor mediante Cloud Partner Portal.
- [Preparación de los recursos técnicos](./cpp-create-technical-assets.md): este paso se refiere a cómo crear los recursos técnicos para una solución de contenedor como una oferta en Azure Marketplace.
- [Publicación de la oferta](./cpp-publish-offer.md): se refiere a cómo enviar la oferta para publicarla en Azure Marketplace.

## <a name="container-publishing-process"></a>Proceso de publicación del contenedor

En el diagrama siguiente se ilustran los pasos generales de la publicación de una oferta de máquina virtual.
![Pasos para publicar una oferta](./media/containers-offer-process.png)

Los pasos generales para la publicación de una oferta de contenedor son:

1. Crear la oferta: proporcione información detallada sobre la oferta. Esta información incluye: la descripción de la oferta, materiales de marketing, información de soporte técnico y especificaciones de recursos.
2. Crear los recursos empresariales y técnicos: creación de los recursos empresariales (documentos legales y materiales de marketing) y los recursos técnicos de la solución asociada (las imágenes de contenedor hospedadas en Azure Container Registry).
3. Crear las SKU: cree las SKU asociadas a la oferta. Se necesita una SKU única para cada imagen que se vaya a publicar.
4. Certificar y publicar la oferta: después de completar la oferta y los recursos técnicos, puede enviar la oferta. Este envío inicia el proceso de publicación. Durante este proceso, la solución se prueba, se valida, se certifica y luego se publica en Azure Marketplace.

## <a name="next-steps"></a>Pasos siguientes

Antes de considerar estos pasos, debe cumplir los [requisitos técnicos y empresariales](./cpp-prerequisites.md) para publicar un contenedor en Microsoft Azure Marketplace.