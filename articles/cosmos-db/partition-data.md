---
title: Creación de particiones y escalado horizontal en Azure Cosmos DB
description: Obtenga información sobre cómo funciona la creación de particiones en Azure Cosmos DB, cómo configurar la creación de particiones y las claves de partición y cómo seleccionar la clave de partición correcta para su aplicación.
ms.author: mjbrown
author: markjbrown
ms.service: cosmos-db
ms.topic: conceptual
ms.date: 10/30/2018
ms.openlocfilehash: 55e9ef0f8bd268f36378c7d34cea95384c6f725e
ms.sourcegitcommit: eecd816953c55df1671ffcf716cf975ba1b12e6b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2019
ms.locfileid: "55099352"
---
# <a name="partitioning-and-horizontal-scaling-in-azure-cosmos-db"></a>Creación de particiones y escalado horizontal en Azure Cosmos DB

En este artículo se explican las particiones físicas y lógicas en Azure Cosmos DB y los procedimientos recomendados para el escalado y la creación de particiones. 

## <a name="logical-partitions"></a>Particiones lógicas

Una partición lógica consta de un conjunto de elementos con la misma clave de partición. Por ejemplo, en un contenedor donde todos los elementos contienen una propiedad `City`, puede usar `City` como clave de partición para el contenedor. Los grupos de elementos con valores específicos para la propiedad `City` , como "London", "Paris", "NYC" etc. formarán una partición lógica distinta.

En Azure Cosmos DB, un contenedor es la unidad fundamental de escalabilidad. Se crean automáticamente particiones (horizontales) de los datos agregados al contenedor y el rendimiento que se aprovisiona en el contenedor, a través de un conjunto de particiones lógicas. Las particiones se crean en función de la clave de partición que se especifica en el contenedor de Cosmos. Para obtener más información, vea el artículo sobre [cómo especificar la clave de partición para el contenedor de Cosmos](how-to-create-container.md).

Una partición lógica define el ámbito de las transacciones de base de datos. Puede actualizar los elementos dentro de una partición lógica mediante el uso de una transacción con aislamiento de instantánea. Cuando se agregan nuevos elementos al contenedor, se crean nuevas particiones lógicas de forma transparente por el sistema.

## <a name="physical-partitions"></a>Particiones físicas

Un contenedor de Azure Cosmos se escala mediante la distribución de los datos y el rendimiento entre un gran número de particiones lógicas. Internamente, una o varias particiones lógicas se asignan a una **partición física** que consta de un conjunto de réplicas que se conoce como conjunto de réplicas. Cada conjunto de réplicas hospeda una instancia del motor de base de datos de Azure Cosmos. Un conjunto de réplicas hace que los datos almacenados en la partición física sean duraderos, coherentes y tengan una alta disponibilidad. Una partición física admite una cantidad máxima de almacenamiento y RU. Cada réplica que compone la partición física hereda la cuota de almacenamiento. Y todas las réplicas de una partición física admiten colectivamente el rendimiento asignado a la partición física. La siguiente imagen muestra cómo se asignan particiones lógicas a particiones físicas distribuidas globalmente:

![Creación de particiones en Azure Cosmos DB](./media/partition-data/logical-partitions.png)

El rendimiento aprovisionado para un contenedor se divide uniformemente entre las particiones físicas. Por lo tanto, un diseño de clave de partición que no distribuye uniformemente las solicitudes de rendimiento puede crear particiones "activas". Las particiones activas pueden conllevar un uso ineficaz y que limite la velocidad del rendimiento aprovisionado.

A diferencia de las particiones lógicas, las particiones físicas son una implementación interna del sistema. No puede controlar su tamaño, posición o recuento, ni la asignación entre particiones lógicas y particiones físicas. Sin embargo, puede controlar el número de particiones lógicas, así como la distribución de datos y rendimiento mediante la elección de la clave de partición correcta.

## <a name="next-steps"></a>Pasos siguientes

En este artículo, se ha proporcionado información general sobre la creación de particiones de datos, y los procedimientos recomendados para la creación de particiones y el escalado con Azure Cosmos DB. 

* Información sobre el [procesamiento aprovisionado en Azure Cosmos DB](request-units.md)
* Información sobre la [distribución global en Azure Cosmos DB](distribute-data-globally.md)
* Obtenga información sobre la [elección de una clave de partición](partitioning-overview.md#choose-partitionkey)
* Obtenga información sobre [cómo aprovisionar rendimiento en un contenedor de Cosmos](how-to-provision-container-throughput.md)
* Más información sobre [cómo aprovisionar rendimiento en una base de datos de Cosmos](how-to-provision-database-throughput.md)
