---
title: "IMetaDataConverter::GetTypeLibFromMetaData 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter.GetTypeLibFromMetaData
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b2b12c5f3ecb0d30fad3bfb5c96e0e66fd9ee7bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="f2f83-102">IMetaDataConverter::GetTypeLibFromMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="f2f83-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="f2f83-103">获取一个指向`ITypeLib`表示具有指定的库和模块名称的类型库的实例。</span><span class="sxs-lookup"><span data-stu-id="f2f83-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f83-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2f83-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2f83-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2f83-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="f2f83-106">[in]类型库的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="f2f83-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="f2f83-107">[in]类型库的名称。</span><span class="sxs-lookup"><span data-stu-id="f2f83-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="f2f83-108">[out]指向接收的地址的位置的指针`ITypeLib`表示的类型库的实例。</span><span class="sxs-lookup"><span data-stu-id="f2f83-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2f83-109">要求</span><span class="sxs-lookup"><span data-stu-id="f2f83-109">Requirements</span></span>  
 <span data-ttu-id="f2f83-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2f83-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2f83-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2f83-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2f83-112">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f2f83-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2f83-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2f83-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f83-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2f83-114">See Also</span></span>  
 [<span data-ttu-id="f2f83-115">IMetaDataConverter 接口</span><span class="sxs-lookup"><span data-stu-id="f2f83-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)