---
title: 'Inicio rápido: Obtención de conclusiones de imágenes mediante Bing Visual Search API y Node.js'
titleSuffix: Azure Cognitive Services
description: Aprenda a cargar una imagen en Bing Visual Search API y obtener conclusiones sobre ella.
services: cognitive-services
author: swhite-msft
manager: nitinme
ms.service: cognitive-services
ms.subservice: bing-visual-search
ms.topic: quickstart
ms.date: 5/16/2018
ms.author: scottwhi
ms.openlocfilehash: 7a0103e21b4c287526e53b9f886e98027f49c392
ms.sourcegitcommit: 90cec6cccf303ad4767a343ce00befba020a10f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55863999"
---
# <a name="quickstart-get-image-insights-using-the-bing-visual-search-rest-api-and-nodejs"></a>Inicio rápido: Obtención de conclusiones de imágenes mediante Bing Visual Search API y Node.js

Use este inicio rápido para realizar la primera llamada a Bing Visual Search API y ver los resultados de búsqueda. Esta sencilla aplicación de JavaScript carga una imagen en la API y muestra la información que se devuelve sobre ella. Si bien esta aplicación está escrita en JavaScript, la API es un servicio web RESTful compatible con la mayoría de los lenguajes de programación.

Al cargar una imagen local, los datos del formulario deben incluir el encabezado Content-Disposition. Asimismo, el parámetro `name` se debe establecer en "imagen" y el parámetro `filename` se puede establecer en cualquier cadena. El contenido del formulario es el binario de la imagen. Recuerde que el tamaño de imagen máximo que puede cargar es de 1 MB.

```
--boundary_1234-abcd
Content-Disposition: form-data; name="image"; filename="myimagefile.jpg"

ÿØÿà JFIF ÖÆ68g-¤CWŸþ29ÌÄøÖ‘º«™æ±èuZiÀ)"óÓß°Î= ØJ9á+*G¦...

--boundary_1234-abcd--
```

## <a name="prerequisites"></a>Requisitos previos

* [Node.js](https://nodejs.org/en/download/)
* El módulo de solicitud para JavaScript
    * Puede instalar este módulo mediante `npm install request`.
* El módulo de datos de formulario
    * Puede instalar este módulo mediante `npm install form-data`.


[!INCLUDE [cognitive-services-bing-visual-search-signup-requirements](../../../../includes/cognitive-services-bing-image-search-signup-requirements.md)]


## <a name="initialize-the-application"></a>Inicialización de la aplicación

1. Cree un archivo JavaScript en el editor o el IDE que prefiera y establezca los siguientes requisitos:

    ```javascript
    var request = require('request');
    var FormData = require('form-data');
    var fs = require('fs');
    ```

2. Cree variables para el punto de conexión de API, la clave de suscripción y la ruta de acceso a la imagen.

    ```javascript
    var baseUri = 'https://api.cognitive.microsoft.com/bing/v7.0/images/visualsearch';
    var subscriptionKey = 'your-api-key';
    var imagePath = "path-to-your-image";
    ```

3. Cree una función denominada `requestCallback()` para imprimir la respuesta de la API.

    ```javascript
    function requestCallback(err, res, body) {
        console.log(JSON.stringify(JSON.parse(body), null, '  '))
    }
    ```

## <a name="construct-and-send-the-search-request"></a>Construcción y envío de la solicitud de búsqueda

1. Cree un formulario de datos mediante `FormData()` y anexe a él la ruta de acceso a la imagen, con `fs.createReadStream()`.
    
    ```javascript
    var form = new FormData();
    form.append("image", fs.createReadStream(imagePath));
    ```

2. Use la biblioteca de solicitudes para cargar la imagen, y llame a `requestCallback()` para imprimir la respuesta. No olvide agregar la clave de suscripción al encabezado de solicitud. 

    ```javascript
    form.getLength(function(err, length){
      if (err) {
        return requestCallback(err);
      }
      var r = request.post(baseUri, requestCallback);
      r._form = form; 
      r.setHeader('Ocp-Apim-Subscription-Key', subscriptionKey);
    });
    ```

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Creación de una página web de Custom Search](../tutorial-bing-visual-search-single-page-app.md)
