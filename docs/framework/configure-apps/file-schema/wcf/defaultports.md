---
title: '&lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 7ddfddaa13778ce98bd93b6d8029438377fc7e94
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145180"
---
# <a name="ltdefaultportsgt"></a>&lt;defaultPorts&gt;
一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。  
  
\<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<useRequestHeadersForMetadataAddress >  
\<d d >  
  
## <a name="syntax"></a>语法  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<添加 > 的\<d d >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|客户端应用程序侦听的默认通信终结点。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress >](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|默认端口列表。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
