---
title: 'Tutorial: Integración de Azure Active Directory con Tango Analytics | Microsoft Docs'
description: Aprenda a configurar el inicio de sesión único entre Azure Active Directory y Tango Analytics.
services: active-directory
documentationCenter: na
author: jeevansd
manager: daveba
ms.assetid: 2f7555d3-e9ba-40b2-9b3a-2f0ab38a4c08
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 06/22/2017
ms.author: jeedes
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4aee9031d05bf4d515c24c62a7ef73c68e875268
ms.sourcegitcommit: 301128ea7d883d432720c64238b0d28ebe9aed59
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56166664"
---
# <a name="tutorial-azure-active-directory-integration-with-tango-analytics"></a>Tutorial: Integración de Azure Active Directory con Tango Analytics

En este tutorial, obtendrá información sobre cómo integrar Tango Analytics con Azure Active Directory (Azure AD).

La integración de Tango Analytics con Azure AD proporciona las siguientes ventajas:

- Puede controlar en Azure AD quién tiene acceso a Tango Analytics.
- Puede permitir que los usuarios inicien sesión automáticamente en Tango Analytics (inicio de sesión único) con sus cuentas de Azure AD.
- Puede administrar sus cuentas en una ubicación central: el nuevo Azure Portal.

Si desea saber más sobre la integración de aplicaciones SaaS con Azure AD, consulte [¿Qué es el acceso a aplicaciones y el inicio de sesión único con Azure Active Directory?](../manage-apps/what-is-single-sign-on.md).

## <a name="prerequisites"></a>Requisitos previos

Para configurar la integración de Azure AD con Tango Analytics, necesita los siguientes elementos:

- Una suscripción de Azure AD
- Una suscripción habilitada para el inicio de sesión único en Tango Analytics

> [!NOTE]
> Para probar los pasos de este tutorial, no se recomienda el uso de un entorno de producción.

Para probar los pasos de este tutorial, debe seguir estas recomendaciones:

- No use el entorno de producción, salvo que sea necesario.
- Si no dispone de un entorno de prueba de Azure AD, puede obtener una versión de prueba de un mes [aquí](https://azure.microsoft.com/pricing/free-trial/).

## <a name="scenario-description"></a>Descripción del escenario
En este tutorial, puede probar el inicio de sesión único de Azure AD en un entorno de prueba. El escenario descrito en este tutorial consta de dos bloques de creación principales:

1. Adición de Tango Analytics desde la galería
1. Configuración y comprobación del inicio de sesión único de Azure AD

## <a name="adding-tango-analytics-from-the-gallery"></a>Adición de Tango Analytics desde la galería
Para configurar la integración de Tango Analytics en Azure AD, será preciso que agregue Tango Analytics desde la galería a la lista de aplicaciones SaaS administradas.

**Para agregar Tango Analytics desde la galería, siga estos pasos:**

1. En el panel de navegación izquierdo de **[Azure Portal](https://portal.azure.com)**, haga clic en el icono de **Azure Active Directory**. 

    ![Active Directory][1]

1. Vaya a **Aplicaciones empresariales**. A continuación, vaya a **Todas las aplicaciones**.

    ![APLICACIONES][2]
    
1. Para agregar una nueva aplicación, haga clic en el botón **Nueva aplicación** de la parte superior del cuadro de diálogo.

    ![APLICACIONES][3]

1. En el cuadro de búsqueda, escriba **Tango Analytics**.

    ![Creación de un usuario de prueba de Azure AD](./media/tangoanalytics-tutorial/tutorial_tangoanalytics_search.png)

1. En el panel de resultados, seleccione **Tango Analytics** y luego haga clic en el botón **Agregar** para agregar la aplicación.

    ![Creación de un usuario de prueba de Azure AD](./media/tangoanalytics-tutorial/tutorial_tangoanalytics_addfromgallery.png)

##  <a name="configuring-and-testing-azure-ad-single-sign-on"></a>Configuración y comprobación del inicio de sesión único de Azure AD
En esta sección, configurará y probará el inicio de sesión único de Azure AD con Tango Analytics con un usuario de prueba llamado "Britta Simon".

Para que el inicio de sesión único funcione, Azure AD debe saber cuál es el usuario homólogo de Tango Analytics para un usuario de Azure AD. Es decir, es preciso establecer una relación de vínculo entre un usuario de Azure AD y el usuario relacionado de Tango Analytics.

Para establecer la relación de vínculo, en Tango Analytics, asigne el valor de **nombre de usuario** de Azure AD como valor de **Nombre de usuario**.

Para configurar y probar el inicio de sesión único de Azure AD con Tango Analytics, es preciso completar los siguientes bloques de creación:

1. **[Configuración del inicio de sesión único de Azure AD](#configuring-azure-ad-single-sign-on)** : para permitir a los usuarios usar esta característica.
1. **[Creación de un usuario de prueba de Azure AD](#creating-an-azure-ad-test-user)** : para probar el inicio de sesión único de Azure AD con Britta Simon.
1. **[Creación de un usuario de prueba de Tango Analytics](#creating-a-tango-analytics-test-user)**: para tener un homólogo de Britta Simon en Tango Analytics vinculado a la representación del usuario en Azure AD.
1. **[Asignación del usuario de prueba de Azure AD](#assigning-the-azure-ad-test-user)** : para permitir que Britta Simon use el inicio de sesión único de Azure AD.
1. **[Testing Single Sign-On](#testing-single-sign-on)** : para comprobar si funciona la configuración.

### <a name="configuring-azure-ad-single-sign-on"></a>Configuración del inicio de sesión único de Azure AD

El objetivo de esta sección es habilitar el inicio de sesión único de Azure AD en Azure Portal y configurar el inicio de sesión único en la aplicación Tango Analytics.

**Para configurar el inicio de sesión único de Azure AD con Tango Analytics, necesita los siguientes elementos:**

1. En Azure Portal, en la página de integración de la aplicación **Tango Analytics**, haga clic en **Inicio de sesión único**.

    ![Configurar inicio de sesión único][4]

1. En el cuadro de diálogo **Inicio de sesión único**, en **Modo** seleccione **Inicio de sesión basado en SAML** para habilitar el inicio de sesión único.
 
    ![Configurar inicio de sesión único](./media/tangoanalytics-tutorial/tutorial_tangoanalytics_samlbase.png)

1. En la sección **Dominio y direcciones URL de Tango Analytics**, lleve a cabo los pasos siguientes:

    ![Configurar inicio de sesión único](./media/tangoanalytics-tutorial/tutorial_tangoanalytics_url.png)

     a. En el cuadro de texto **Identificador**, escriba el valor `TACORE_SSO`.

    b. En el cuadro de texto **URL de respuesta**, escriba una dirección URL con el siguiente patrón: `https://mts.tangoanalytics.com/saml2/sp/acs/post`.

    > [!NOTE] 
    > El valor de dirección URL de respuesta no es real. Actualícelo con la dirección URL de respuesta real. Póngase en contacto con el [equipo de soporte técnico de Tango Analytics](mailto:support@tangoanalytics.com) para obtener este valor.

1. En la sección **Certificado de firma de SAML**, haga clic en **XML de metadatos** y luego guarde el archivo de metadatos en el equipo.

    ![Configurar inicio de sesión único](./media/tangoanalytics-tutorial/tutorial_tangoanalytics_certificate.png) 

1. Haga clic en el botón **Guardar** .

    ![Configurar inicio de sesión único](./media/tangoanalytics-tutorial/tutorial_general_400.png)

1. Para configurar el inicio de sesión único en **Tango Analytics**, es preciso enviar el archivo **XML de metadatos** descargado al [equipo de soporte técnico de Tango Analytics](mailto:support@tangoanalytics.com). Dicho equipo lo configura para establecer la conexión de SSO de SAML correctamente en ambos lados.

> [!TIP]
> Ahora puede leer una versión resumida de estas instrucciones dentro de [Azure Portal](https://portal.azure.com) mientras configura la aplicación.  Después de agregar esta aplicación desde la sección **Active Directory > Aplicaciones empresariales**, simplemente haga clic en la pestaña **Inicio de sesión único** y acceda a la documentación insertada a través de la sección **Configuración** de la parte inferior. Puede leer más aquí sobre la característica de documentación insertada: [Documentación insertada de Azure AD]( https://go.microsoft.com/fwlink/?linkid=845985)
> 

### <a name="creating-an-azure-ad-test-user"></a>Creación de un usuario de prueba de Azure AD
El objetivo de esta sección es crear un usuario de prueba en Azure Portal llamado "Britta Simon".

![Creación de un usuario de Azure AD][100]

**Siga estos pasos para crear un usuario de prueba en Azure AD:**

1. En el panel de navegación izquierdo de **Azure Portal**, haga clic en el icono de **Azure Active Directory**.

    ![Creación de un usuario de prueba de Azure AD](./media/tangoanalytics-tutorial/create_aaduser_01.png) 

1. Para mostrar la lista de usuarios, vaya a **Usuarios y grupos** y haga clic en **Todos los usuarios**.
    
    ![Creación de un usuario de prueba de Azure AD](./media/tangoanalytics-tutorial/create_aaduser_02.png) 

1. Para abrir el cuadro de diálogo **Usuario**, haga clic en **Agregar** en la parte superior del cuadro de diálogo.
 
    ![Creación de un usuario de prueba de Azure AD](./media/tangoanalytics-tutorial/create_aaduser_03.png) 

1. En la página de diálogo **Usuario**, realice los siguientes pasos:
 
    ![Creación de un usuario de prueba de Azure AD](./media/tangoanalytics-tutorial/create_aaduser_04.png) 

     a. En el cuadro de texto **Nombre**, escriba **BrittaSimon**.

    b. En el cuadro de texto **Nombre de usuario**, escriba la **dirección de correo electrónico** de Britta Simon.

    c. Seleccione **Mostrar contraseña** y anote el valor del cuadro **Contraseña**.

    d. Haga clic en **Create**(Crear).
 
### <a name="creating-a-tango-analytics-test-user"></a>Creación de un usuario de prueba de Tango Analytics

En esta sección, creará un usuario llamado Britta Simon en Tango Analytics. Trabaje con el  [equipo de soporte técnico de Tango Analytics](mailto:support@tangoanalytics.com)  para agregar usuarios a la plataforma de Tango Analytics. Los usuarios se tienen que crear y activar antes de usar el inicio de sesión único.

### <a name="assigning-the-azure-ad-test-user"></a>Asignación del usuario de prueba de Azure AD

En esta sección, habilitará a Britta Simon para que use el inicio de sesión único de Azure concediéndole acceso a Tango Analytics.

![Asignar usuario][200] 

**Para asignar Britta Simon a Tango Analytics, siga estos pasos:**

1. En Azure Portal, abra la vista de aplicaciones, navegue a la vista de directorio y vaya a **Aplicaciones empresariales**. Luego haga clic en **Todas las aplicaciones**.

    ![Asignar usuario][201] 

1. En la lista de aplicaciones, seleccione **Tango Analytics**.

    ![Configurar inicio de sesión único](./media/tangoanalytics-tutorial/tutorial_tangoanalytics_app.png) 

1. En el menú de la izquierda, haga clic en **Usuarios y grupos**.

    ![Asignar usuario][202] 

1. Haga clic en el botón **Agregar**. Después, seleccione **Usuarios y grupos** en el cuadro de diálogo **Agregar asignación**.

    ![Asignar usuario][203]

1. En el cuadro de diálogo **Usuarios y grupos**, seleccione **Britta Simon** en la lista de usuarios.

1. Haga clic en el botón **Seleccionar** del cuadro de diálogo **Usuarios y grupos**.

1. Haga clic en el botón **Asignar** del cuadro de diálogo **Agregar asignación**.
    
### <a name="testing-single-sign-on"></a>Prueba del inicio de sesión único 

En esta sección, probará la configuración de inicio de sesión único de Azure AD mediante el Panel de acceso.

Al hacer clic en el icono de Tango Analytics en el panel de acceso, debería iniciar sesión automáticamente en su aplicación Tango Analytics.
Para más información sobre el Panel de acceso, consulte [Introducción al Panel de acceso](../user-help/active-directory-saas-access-panel-introduction.md).

## <a name="additional-resources"></a>Recursos adicionales

* [Lista de tutoriales sobre cómo integrar aplicaciones SaaS con Azure Active Directory](tutorial-list.md)
* [¿Qué es el acceso a aplicaciones y el inicio de sesión único con Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)

<!--Image references-->

[1]: ./media/tangoanalytics-tutorial/tutorial_general_01.png
[2]: ./media/tangoanalytics-tutorial/tutorial_general_02.png
[3]: ./media/tangoanalytics-tutorial/tutorial_general_03.png
[4]: ./media/tangoanalytics-tutorial/tutorial_general_04.png

[100]: ./media/tangoanalytics-tutorial/tutorial_general_100.png

[200]: ./media/tangoanalytics-tutorial/tutorial_general_200.png
[201]: ./media/tangoanalytics-tutorial/tutorial_general_201.png
[202]: ./media/tangoanalytics-tutorial/tutorial_general_202.png
[203]: ./media/tangoanalytics-tutorial/tutorial_general_203.png

