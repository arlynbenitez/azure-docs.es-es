---
author: dominicbetts
ms.service: iot-hub
ms.topic: include
ms.date: 10/26/2018
ms.author: dobett
ms.openlocfilehash: e6ba2a9c27567ccbd3b744a9bfdc0603758c7068
ms.sourcegitcommit: fec0e51a3af74b428d5cc23b6d0835ed0ac1e4d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "56213200"
---
## <a name="prepare-to-authenticate-azure-resource-manager-requests"></a>Prepararse para autenticar solicitudes de Azure Resource Manager
Debe autenticar todas las operaciones que se realizan en los recursos mediante [Azure Resource Manager][lnk-authenticate-arm] con Azure Active Directory (AD). La manera más sencilla de configurar esto es usar PowerShell o CLI de Azure.

Instale los [cmdlets de Azure PowerShell][lnk-powershell-install] antes de continuar.

En los pasos siguientes se muestra cómo configurar la autenticación de contraseña para una aplicación de AD mediante PowerShell. Puede ejecutar estos comandos en una sesión de PowerShell estándar.

1. Inicie sesión en su suscripción a Azure con el siguiente comando:

    ```powershell
    Connect-AzureRmAccount
    ```

1. Si tiene varias suscripciones de Azure, el inicio de sesión en Azure le concede acceso a todas las suscripciones de Azure asociadas a sus credenciales. Use el siguiente comando para mostrar las suscripciones de Azure que están disponibles para su uso:

    ```powershell
    Get-AzureRMSubscription
    ```

    Use el siguiente comando para seleccionar la suscripción que desea usar para ejecutar los comandos para administrar su centro de IoT. Puede usar el nombre de la suscripción o el identificador de la salida del comando anterior:

    ```powershell
    Select-AzureRMSubscription `
        -SubscriptionName "{your subscription name}"
    ```

2. Anote los valores de **TenantId** y **SubscriptionId**. Los necesitará más adelante.
3. Cree una nueva aplicación de Azure Active Directory con el siguiente comando, reemplazando los marcadores de posición:
   
   * **{Nombre para mostrar}**: nombre para mostrar de la aplicación, por ejemplo, **MySampleApp**.
   * **{Home page URL}:** URL de la página principal de la aplicación, como **http://mysampleapp/home**. Esta dirección URL no tiene que señalar a una aplicación real.
   * **{Application identifier}:** un identificador único como **http://mysampleapp**. Esta dirección URL no tiene que señalar a una aplicación real.
   * **{Password}:** una contraseña que se usa para autenticarse en la aplicación.
     
     ```powershell
     $SecurePassword=ConvertTo-SecureString {password} –asplaintext –force
     New-AzureRmADApplication -DisplayName {Display name} -HomePage {Home page URL} -IdentifierUris {Application identifier} -Password $SecurePassword
     ```
4. Anote el **ApplicationId** de la aplicación que ha creado. Lo necesitará más adelante.
5. Cree una nueva entidad de servicio con el comando siguiente, reemplazando **{MyApplicationId}** por el valor de **ApplicationId** del paso anterior:
   
    ```powershell
    New-AzureRmADServicePrincipal -ApplicationId {MyApplicationId}
    ```
6. Configure una asignación de rol con el comando siguiente, reemplazando **{MyApplicationId}** por su valor de **ApplicationId**.
   
    ```powershell
    New-AzureRmRoleAssignment -RoleDefinitionName Owner -ServicePrincipalName {MyApplicationId}
    ```

Ahora ha terminado de crear la aplicación de Azure AD que le permitirá autenticarse desde su aplicación de C# personalizada. En este tutorial necesitará más adelante los siguientes valores:

* TenantId
* SubscriptionId
* ApplicationId
* Contraseña

[lnk-authenticate-arm]: https://msdn.microsoft.com/library/azure/dn790557.aspx
[lnk-powershell-install]: https://docs.microsoft.com/powershell/azure/azurerm/install-azurerm-ps
