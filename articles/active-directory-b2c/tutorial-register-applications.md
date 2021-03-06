---
title: 'Tutorial: Registro de una aplicación en Azure Active Directory B2C | Microsoft Docs'
description: Aprenda a registrar una aplicación web en Azure Active Directory B2C con Azure Portal.
services: active-directory-b2c
author: davidmu1
manager: daveba
ms.service: active-directory-b2c
ms.workload: identity
ms.topic: article
ms.date: 02/05/2019
ms.author: davidmu
ms.openlocfilehash: 1f9a4f2f0ac44c8815e33957b49b4215c998eae3
ms.sourcegitcommit: 039263ff6271f318b471c4bf3dbc4b72659658ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "55754173"
---
# <a name="tutorial-register-an-application-in-azure-active-directory-b2c"></a>Tutorial: Registro de una aplicación en Azure Active Directory B2C

Para que sus [aplicaciones](active-directory-b2c-apps.md) puedan interactuar con Azure Active Directory (Azure AD) B2C, deben estar registradas en un inquilino que administre. En este tutorial se muestra cómo registrar una aplicación web mediante Azure Portal.

En este artículo, aprenderá a:

> [!div class="checklist"]
> * Registro de una aplicación web
> * Creación de un secreto de cliente

Si no tiene una suscripción a Azure, cree una [cuenta gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) antes de empezar.

## <a name="prerequisites"></a>Requisitos previos

Si aún no ha creado su propio [inquilino de Azure AD B2C](tutorial-create-tenant.md), cree una ahora. Puede usar un inquilino de Azure AD B2C existente.

## <a name="register-a-web-application"></a>Registro de una aplicación web

1. Asegúrese de que usa el directorio que contiene el inquilino de Azure AD B2C. Para ello, haga clic en el **filtro de directorio y suscripción** en el menú superior y elija el directorio que contiene el inquilino.
2. Elija **Todos los servicios** en la esquina superior izquierda de Azure Portal, y busque y seleccione **Azure AD B2C**.
3. Seleccione **Aplicaciones** y **Agregar**.
4. Escriba un nombre para la aplicación. Por ejemplo, *webapp1*.
5. En **Incluir aplicación web o API web** y **Permitir flujo implícito**, seleccione **Sí**.
6. En **Dirección URL de respuesta**, escriba un punto de conexión donde Azure AD B2C devolverá los tokens que solicite la aplicación. Por ejemplo, puede establecerlo para que escuche localmente en `https://localhost:44316` Si aún no conoce el número de puerto, puede especificar un valor de marcador de posición y cambiarlo más adelante. Con fines de prueba podría establecerlo en `https://jwt.ms`, que muestra el contenido de un token para su inspección. Para este tutorial, lo estableceremos en `https://jwt.ms`. 

    La dirección URL de respuesta debe comenzar por el esquema `https`, y todos los valores de dicha dirección deben compartir un único dominio DNS. Por ejemplo, si la aplicación tiene una dirección URL de respuesta de `https://login.contoso.com`, puede agregar a ella como esta dirección URL `https://login.contoso.com/new`. O bien, puede hacer referencia a un subdominio DNS de `login.contoso.com`, tal como `https://new.login.contoso.com`. Si quiere una aplicación con `login-east.contoso.com` y `login-west.contoso.com` como URL de respuesta, debe agregar las URL de respuesta en este orden: `https://contoso.com`, `https://login-east.contoso.com`, `https://login-west.contoso.com`. Puede agregar las dos últimas porque son subdominios de la primera URL de respuesta, `contoso.com`.

7. Haga clic en **Create**(Crear).

## <a name="create-a-client-secret"></a>Creación de un secreto de cliente

Si la aplicación intercambia un código para un token, deberá crear un secreto de aplicación.

1. Seleccione **Claves** y, luego, haga clic en **Generar clave**.
2. Seleccione **Guardar** para ver la clave. Anote el valor de la **Clave de la aplicación**. Use el valor como secreto de aplicación en el código de la aplicación.

## <a name="next-steps"></a>Pasos siguientes

En este artículo, ha aprendido cómo:

> [!div class="checklist"]
> * Registro de una aplicación web
> * Creación de un secreto de cliente

> [!div class="nextstepaction"]
> [Creación de flujos de usuario en Azure Active Directory B2C](tutorial-create-user-flows.md)