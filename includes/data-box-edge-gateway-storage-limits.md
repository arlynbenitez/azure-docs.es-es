---
author: alkohli
ms.service: databox
ms.topic: include
ms.date: 01/30/2019
ms.author: alkohli
ms.openlocfilehash: 94fe099984fae77c65658d7085a8540ff4f2448b
ms.sourcegitcommit: d1c5b4d9a5ccfa2c9a9f4ae5f078ef8c1c04a3b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55966984"
---
En esta sección se describen los límites del servicio de Azure Storage y las convenciones de nomenclatura necesarias para Azure Files, blobs en bloques de Azure y blobs en páginas de Azure, según corresponda para el servicio Data Box Gateway o Data Box Edge. Revise cuidadosamente los límites de almacenamiento y siga todas las recomendaciones.

Para conocer la información más reciente sobre los límites del servicio de almacenamiento de Azure y los procedimientos recomendados para asignar nombres a recursos compartidos, contenedores y archivos, vaya a:

- [Nomenclatura y referencia de contenedores](https://docs.microsoft.com/rest/api/storageservices/naming-and-referencing-containers--blobs--and-metadata)
- [Nomenclatura y referencia de recursos compartidos](https://docs.microsoft.com/rest/api/storageservices/naming-and-referencing-shares--directories--files--and-metadata)
- [Convenciones de blobs en bloques y blobs en páginas](https://docs.microsoft.com/rest/api/storageservices/understanding-block-blobs--append-blobs--and-page-blobs)

> [!IMPORTANT]
> Si hay archivos o directorios que superen los límites del servicio Azure Storage, o no cumplen las convenciones de nomenclatura de archivos y blobs de Azure, estos archivos o directorios no se ingieren en Azure Storage mediante el servicio Data Box Gateway o Data Box Edge.