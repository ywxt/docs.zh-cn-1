---
title: '&lt;BackupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 1a6a7ac42b379dd8fb2ba80cf6a3a38998c26a59
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146545"
---
# <a name="ltbackuplistgt"></a>&lt;BackupList&gt;
表示用于定义枚举一组你想要使用在的情况下无法访问主终结点的路由服务的终结点的备份列表的配置节。 如果列表中的第一个终结点关闭，则路由服务会自动故障转移到列表中的下一个终结点。  这样，可以方便地提高应用程序的可靠性，而不必告诉客户端应用程序应如何处理复杂模式或所有服务的部署位置。  
  
 \<system.serviceModel>  
\<路由 >  
\<backupLists >  
\<backupList >  
  
## <a name="syntax"></a>语法  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|一个字符串，指定用于标识此终结点列表的名称。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<路由 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|备份终结点列表。|  
  
## <a name="remarks"></a>备注  
 此节包含终结点的有序集合，如果在将消息发送到主终结点时发生通信异常，则会将消息传输到此集合。  
  
 如果在中列出的主终结点发送`endpointName`的属性[\<添加 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md)失败通信异常，路由服务会尝试将消息发送到在此第一个终结点配置节。 如果此操作同样发生通信异常而导致发送失败，则路由服务会尝试将消息发送到此节包含的下一消息，直到发送尝试成功、返回除通信异常以外的故障或集合中的所有终结点均返回故障为止。  
  
 在以下示例中，如果名为"Destination"的主终结点发送返回通信异常，则服务会尝试将消息发送到"alternateServiceQueue"。 如果此尝试也返回一个通信异常，则路由服务会尝试将消息发送到集合中的下一个终结点。  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
