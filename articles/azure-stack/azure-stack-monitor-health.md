---
title: Supervisar el estado y las alertas en Azure Stack | Microsoft Docs
description: Aprenda cómo supervisar el estado y las alertas en Azure Stack.
services: azure-stack
documentationcenter: ''
author: mattbriggs
manager: femila
editor: ''
ms.service: azure-stack
ms.workload: na
pms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 01/18/2019
ms.author: mabrigg
ms.lastreviewed: 01/18/2019
ms.openlocfilehash: 3e37b8f45d7068586d20b9c4b3ccdabb017d0416
ms.sourcegitcommit: 898b2936e3d6d3a8366cfcccc0fccfdb0fc781b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55242865"
---
# <a name="monitor-health-and-alerts-in-azure-stack"></a>Supervisar el estado y las alertas en Azure Stack

*Se aplica a: Sistemas integrados de Azure Stack y Kit de desarrollo de Azure Stack*

Azure Stack incluye funciones de supervisión de infraestructura que le ayudan a ver el estado y las alertas de una región de Azure Stack. El icono **Region management** (Administración de regiones), anclado en el portal de administración de manera predeterminada para la suscripción de proveedor predeterminada, enumera todas las regiones implementadas de Azure Stack. El icono muestra el número de alertas activas críticas y de advertencia para cada región. El icono es el punto de entrada a la funcionalidad de estado y alerta de Azure Stack.

![Icono Region Management (Administración de regiones)](media/azure-stack-monitor-health/image1.png)

## <a name="understand-health-in-azure-stack"></a>Comprender el estado en Azure Stack

El proveedor de recursos de estado administra el estado y las alertas. Los componentes de infraestructura de Azure Stack se registran en el proveedor de recursos de estado durante la implementación y configuración de Azure Stack. Este registro permite mostrar el estado y las alertas para cada componente. El estado en Azure Stack es un concepto simple. Si existen alertas para una instancia registrada de un componente, el estado de mantenimiento de dicho componente refleja la gravedad de la peor alerta activa: advertencia o crítica.

## <a name="alert-severity-definition"></a>Definición de la gravedad de las alertas

En Azure Stack se generan alertas con solo dos grados de gravedad: **advertencia** y **críticos**.

- **Warning (ADVERTENCIA)**  
  Un operador puede abordar la alerta de advertencia de manera programada. Esta alerta generalmente no afecta a las cargas de trabajo del usuario.

- **Critical)** (Crítico)  
  Un operador debe abordar la alerta crítica con urgencia. Estos son problemas que actualmente afectan o que pronto afectarán a los usuarios de Azure Stack.


## <a name="view-and-manage-component-health-state"></a>Ver y administrar el estado de mantenimiento de un componente

Puede ver el estado de mantenimiento de los componentes en el portal de administración y con la API REST y PowerShell.

Para ver el estado de mantenimiento en el portal, haga clic en la región que quiera ver en la ventana **Region management** (Administración de regiones). Puede ver el estado de mantenimiento de los roles de infraestructura y de los proveedores de recursos.

![Lista de roles de infraestructura](media/azure-stack-monitor-health/image2.png)

Puede hacer clic en un proveedor de recursos o rol de infraestructura para ver información más detallada.

> [!WARNING]  
> Si hace clic en un rol de infraestructura y, luego, hace clic en la instancia de rol, hay opciones para **Iniciar**, **Reiniciar** o **Apagar**. No use estas acciones al aplicar actualizaciones a un sistema integrado. **No** use tampoco estas opciones en un entorno del Kit de desarrollo de Azure Stack. Estas opciones están diseñadas únicamente para un entorno de sistemas integrados, donde hay más de una instancia de rol por rol de infraestructura. Reiniciar una instancia de rol (especialmente AzS-Xrp01) en el kit de desarrollo provoca inestabilidad del sistema. Para obtener asistencia para solucionar problemas, publique su problema en el [foro de Azure Stack](https://aka.ms/azurestackforum).
>

## <a name="view-alerts"></a>Visualización de alertas

La lista de alertas activas para cada región de Azure Stack está disponible directamente desde la hoja **Region management** (Administración de regiones). El primer icono en la configuración predeterminada es **Alertas**, que muestra un resumen de las alertas críticas y de advertencia para la región. Puede anclar la ventana de alertas, al igual que cualquier otra ventana en esta hoja, al panel para un acceso rápido.

![Ventana Alerts que muestra una advertencia](media/azure-stack-monitor-health/image3.png)

Al seleccionar la parte superior del icono **Alertas**, irá a la lista de todas las alertas activas de la región. Si selecciona un elemento de línea **Crítica** o **Advertencia** en la ventana, navega a una lista filtrada de alertas (Crítica o Advertencia). 

La hoja **Alertas** admite la capacidad de filtrar tanto por estado (Activa o Cerrada) como por gravedad (Crítica o Advertencia). La vista predeterminada muestra todas las alertas activas. Todas las alertas cerradas se quitan del sistema después de siete días.

![Panel Filtro para filtrar por estado crítico o de advertencia](media/azure-stack-monitor-health/alert-view.png)

En la acción **View API** (Ver API) se muestra la API de REST que se usó para generar la vista de lista. Esta acción proporciona una forma rápida de familiarizarse con la sintaxis de la API de REST que puede usar para consultar las alertas. Puede utilizar esta API para automatización o para integración con las soluciones existentes de supervisión, informe y vales del centro de datos.

Puede hacer clic en una alerta específica para ver los detalles de la alerta. En los detalles de alerta se muestran todos los campos que están asociados a la alerta y se permite la navegación rápida al componente afectado y al origen de la alerta. Por ejemplo, la alerta siguiente se produce si una de las instancias de rol de infraestructura se queda sin conexión o no está accesible.  

![Hoja Detalles de alerta](media/azure-stack-monitor-health/alert-detail.png)

## <a name="repair-alerts"></a>Reparación de las alertas

Puede seleccionar **Reparar** en algunas alertas.

Cuando se selecciona, la acción **Reparar** realiza pasos específicos para la alerta a fin de intentar resolver el problema. Una vez seleccionada, el estado de la acción **Reparar** está disponible como una notificación del portal.

![Reparación en curso](media/azure-stack-monitor-health/repair-in-progress.png)

La acción **Reparar** notificará la finalización correcta o el error al completar la acción en la misma hoja de notificación del portal.  Si se produce un error en una acción de reparación de una alerta, puede volver a ejecutar la acción **Reparar** a partir de los detalles de alerta. Si la acción de **reparación** se completa correctamente, **no** vuelva a ejecutarla.

![La reparación se completa correctamente](media/azure-stack-monitor-health/repair-completed.png)

Después de que la instancia de rol de la infraestructura vuelve a estar en línea, esta alerta se cierra automáticamente. Muchas alertas se cierran automáticamente cuando se resuelve el problema subyacente. Las alertas que proporcionan un botón de acción Reparar se cerrarán de forma automática si Azure Stack resuelve el problema.  Para todas las demás alertas, le recomendamos que seleccione **Cerrar alerta** cuando haya seguido los pasos de corrección. Si el problema persiste, Azure Stack genera una alerta nueva. Si se resuelve, la alerta permanecerá cerrada y no se tendrán que seguir más pasos.

## <a name="next-steps"></a>Pasos siguientes

[Administrar las actualizaciones en Azure Stack](azure-stack-updates.md)

[Administración de regiones en Azure Stack](azure-stack-region-management.md)
