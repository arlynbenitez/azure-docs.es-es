---
title: 'Creación de una aplicación web ASP.NET Framework de C#: Azure App Service | Microsoft Docs'
description: Aprenda a ejecutar aplicaciones web en Azure App Service mediante la implementación de la aplicación web ASP.NET de C# predeterminada.
services: app-service\web
documentationcenter: ''
author: cephalin
manager: cfowler
editor: ''
ms.assetid: 04a1becf-7756-4d4e-92d8-d9471c263d23
ms.service: app-service-web
ms.workload: web
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: quickstart
ms.date: 09/05/2018
ms.author: cephalin
ms.custom: seodec18
ms.openlocfilehash: 8dc062a1c9490a03aa5369dc103db750d7531140
ms.sourcegitcommit: c94cf3840db42f099b4dc858cd0c77c4e3e4c436
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53635279"
---
# <a name="create-an-aspnet-framework-web-app-in-azure"></a>Creación de una aplicación web de ASP.NET Framework en Azure

[Azure App Service](overview.md) proporciona un servicio de hospedaje web muy escalable y con aplicación de revisiones de un modo automático.  En este inicio rápido se muestra cómo implementar su primera aplicación web ASP.NET en Azure App Service. Cuando haya terminado, tendrá un grupo de recursos que consta de un plan de App Service y una aplicación de App Service con una aplicación web implementada.

![](./media/app-service-web-get-started-dotnet-framework/published-azure-web-app.png)

[!INCLUDE [quickstarts-free-trial-note](../../includes/quickstarts-free-trial-note.md)]

## <a name="prerequisites"></a>Requisitos previos

Para completar este tutorial, instale <a href="https://www.visualstudio.com/downloads/" target="_blank">Visual Studio 2017</a> con la carga de trabajo de **ASP.NET y desarrollo web**.

Si ya ha instalado Visual Studio 2017:

- Para instalar las actualizaciones más recientes de Visual Studio, haga clic en **Ayuda** > **Buscar actualizaciones**.
- Para agregar la carga de trabajo, haga clic en **Herramientas** > **Obtener herramientas y características**.

## <a name="create-an-aspnet-web-app"></a>Creación de una aplicación web de ASP.NET

Cree un proyecto nuevo en Visual Studio seleccionando **Archivo > Nuevo > Proyecto**. 

En el cuadro de diálogo **Nuevo proyecto**, seleccione **Visual C# > Web > Aplicación web ASP.NET (.NET Framework)**.

Asigne a la aplicación el nombre _myFirstAzureWebApp_ y seleccione **Aceptar**.
   
![Cuadro de diálogo Nuevo proyecto](./media/app-service-web-get-started-dotnet-framework/new-project.png)

Puede implementar cualquier tipo de aplicación web de ASP.NET en Azure. Para esta guía de inicio rápido, seleccione la plantilla **MVC** y asegúrese de que la autenticación se establezca en **Sin autenticación**.
      
Seleccione **Aceptar**.

![Cuadro de diálogo Nuevo proyecto de ASP.NET](./media/app-service-web-get-started-dotnet-framework/select-mvc-template.png)

En el menú, seleccione **Depurar > Iniciar sin depurar** para ejecutar la aplicación web localmente.

![Ejecución de la aplicación de forma local](./media/app-service-web-get-started-dotnet-framework/local-web-app.png)

## <a name="launch-the-publish-wizard"></a>Inicio del Asistente para publicación

En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **myFirstAzureWebApp** y seleccione **Publicar**.

![Publicar desde el Explorador de soluciones](./media/app-service-web-get-started-dotnet-framework/solution-explorer-publish.png)

El Asistente para publicación se inicia automáticamente. Seleccione **App Service** > **Publicar** para abrir el cuadro de diálogo **Crear servicio de aplicaciones**.

![Publicar desde la página de información general del proyecto](./media/app-service-web-get-started-dotnet-framework/publish-to-app-service.png)

## <a name="sign-in-to-azure"></a>Inicio de sesión en Azure

En el cuadro de diálogo **Crear App Service**, haga clic en **Agregar una cuenta** e inicie sesión en su suscripción de Azure. Si ya ha iniciado sesión, seleccione la cuenta que contiene la suscripción deseada en la lista desplegable.

> [!NOTE]
> Si ya ha iniciado sesión, no seleccione **Crear** todavía.
>
>
   
![Inicio de sesión en Azure](./media/app-service-web-get-started-dotnet-framework/sign-in-azure.png)

## <a name="create-a-resource-group"></a>Crear un grupo de recursos

[!INCLUDE [resource group intro text](../../includes/resource-group.md)]

Junto a **Grupo de recursos**, seleccione **Nuevo**.

Asigne el nombre **myResourceGroup** al grupo de recursos y seleccione **Aceptar**.

## <a name="create-an-app-service-plan"></a>Creación de un plan de App Service

[!INCLUDE [app-service-plan](../../includes/app-service-plan.md)]

Junto a **Plan de hospedaje**, seleccione **Nuevo**. 

En el cuadro de diálogo **Configurar un plan de hospedaje**, use la configuración de la tabla que sigue a la captura de pantalla.

![Creación de un plan de App Service](./media/app-service-web-get-started-dotnet-framework/configure-app-service-plan.png)

| Configuración | Valor sugerido | DESCRIPCIÓN |
|-|-|-|
|Plan de App Service| myAppServicePlan | Nombre del plan de App Service. |
| Ubicación | Europa occidental | El centro de datos donde se hospeda la aplicación web. |
| Tamaño | Gratuito | [Plan de tarifa](https://azure.microsoft.com/pricing/details/app-service/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=docs&utm_campaign=visualstudio) determina las características de hospedaje. |

Seleccione **Aceptar**.

## <a name="create-and-publish-the-web-app"></a>Creación y publicación de la aplicación web

En **Nombre de la aplicación**, escriba un nombre único de aplicación (los caracteres válidos son `a-z`, `0-9` y `-`) o acepte el nombre único generado automáticamente. La dirección URL de la aplicación web es `http://<app_name>.azurewebsites.net`, donde `<app_name>` es el nombre de la aplicación.

Seleccione **Crear** para comenzar a crear los recursos de Azure.

![Configuración del nombre de la aplicación](./media/app-service-web-get-started-dotnet-framework/web-app-name.png)

Una vez completado el asistente, publica la aplicación web ASP.NET en Azure y, a continuación, inicia la aplicación en el explorador predeterminado.

![Aplicación web de ASP.NET publicada en Azure](./media/app-service-web-get-started-dotnet-framework/published-azure-web-app.png)

El nombre de aplicación especificado en el [paso de creación y publicación](#create-and-publish-the-web-app) se usa como el prefijo de dirección URL en el formato `http://<app_name>.azurewebsites.net`.

Su aplicación web ASP.NET se está ejecutando en vivo en Azure App Service.

## <a name="update-the-app-and-redeploy"></a>Actualización de la aplicación y nueva implementación

Desde el **Explorador de soluciones**, abra _Views\Home\Index.cshtml_.

Busque la etiqueta HTML `<div class="jumbotron">` en la parte superior y reemplace el elemento entero por el código siguiente:

```HTML
<div class="jumbotron">
    <h1>ASP.NET in Azure!</h1>
    <p class="lead">This is a simple app that we’ve built that demonstrates how to deploy a .NET app to Azure App Service.</p>
</div>
```

Para volver a implementar en Azure, haga clic con el botón derecho en el proyecto **myFirstAzureWebApp**, en el **Explorador de soluciones** y seleccione **Publicar**.

En la página de publicación, seleccione **Publicar**.
![Página de resumen de publicación de Visual Studio](./media/app-service-web-get-started-dotnet-framework/publish-summary-page.png)

Cuando se completa la publicación, Visual Studio inicia un explorador en la dirección URL de la aplicación web.

![Aplicación web actualizada de ASP.NET en Azure](./media/app-service-web-get-started-dotnet-framework/updated-azure-web-app.png)

## <a name="manage-the-azure-app"></a>Administración de la aplicación de Azure

Vaya a <a href="https://portal.azure.com" target="_blank">Azure Portal</a> para administrar la aplicación web.

En el menú izquierdo, seleccione **App Services** y, después, el nombre de la aplicación de Azure.

![Navegación en el portal a la aplicación de Azure](./media/app-service-web-get-started-dotnet-framework/access-portal.png)

Podrá ver la página de información general de la aplicación web. En este caso, puede realizar tareas de administración básicas como examinar, detener, iniciar, reiniciar y eliminar. 

![Hoja de App Service en Azure Portal](./media/app-service-web-get-started-dotnet-framework/web-app-blade.png)

El menú izquierdo proporciona distintas páginas para configurar la aplicación. 

## <a name="video"></a>Vídeo

Vea el vídeo para ver este inicio rápido en acción y, a continuación, siga los pasos para publicar su primera aplicación de .NET en Azure.

> [!VIDEO https://channel9.msdn.com/Shows/Azure-for-NET-Developers/Create-a-NET-app-in-Azure-Quickstart/player]

[!INCLUDE [Clean-up section](../../includes/clean-up-section-portal.md)]

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [ASP.NET con SQL Database](app-service-web-tutorial-dotnet-sqldatabase.md)
