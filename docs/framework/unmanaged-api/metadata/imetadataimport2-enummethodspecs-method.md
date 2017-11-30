---
title: "IMetaDataImport2::EnumMethodSpecs 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumMethodSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: db1968c73d5a1c6e0687bc86f249c70b6c21712c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="c5d79-102">IMetaDataImport2::EnumMethodSpecs 方法</span><span class="sxs-lookup"><span data-stu-id="c5d79-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="c5d79-103">获取的枚举数数组 MethodSpec 与关联的标记指定的 MethodDef 或 MemberRef 令牌。</span><span class="sxs-lookup"><span data-stu-id="c5d79-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5d79-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5d79-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5d79-105">参数</span><span class="sxs-lookup"><span data-stu-id="c5d79-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c5d79-106">[在中，out]枚举数指向的指针`rMethodSpecs`。</span><span class="sxs-lookup"><span data-stu-id="c5d79-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="c5d79-107">[in]新对象或 MemberRef 令牌表示其 MethodSpec 令牌是要枚举的方法。</span><span class="sxs-lookup"><span data-stu-id="c5d79-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="c5d79-108">如果值`tk`为 0 （零），将枚举的作用域中的所有 MethodSpec 令牌。</span><span class="sxs-lookup"><span data-stu-id="c5d79-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="c5d79-109">[out]要枚举的 MethodSpec 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="c5d79-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c5d79-110">[in]请求的令牌中放置的最大数`rMethodSpecs`。</span><span class="sxs-lookup"><span data-stu-id="c5d79-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="c5d79-111">[out]返回的标记数置于`rMethodSpecs`。</span><span class="sxs-lookup"><span data-stu-id="c5d79-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5d79-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c5d79-112">Return Value</span></span>  
  
|<span data-ttu-id="c5d79-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5d79-113">HRESULT</span></span>|<span data-ttu-id="c5d79-114">描述</span><span class="sxs-lookup"><span data-stu-id="c5d79-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c5d79-115">`EnumMethodSpecs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c5d79-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c5d79-116">`phEnum`不包含任何成员元素。</span><span class="sxs-lookup"><span data-stu-id="c5d79-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="c5d79-117">在这种情况下，`pcMethodSpecs`设置为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="c5d79-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5d79-118">要求</span><span class="sxs-lookup"><span data-stu-id="c5d79-118">Requirements</span></span>  
 <span data-ttu-id="c5d79-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5d79-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5d79-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c5d79-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5d79-121">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c5d79-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5d79-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5d79-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5d79-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5d79-123">See Also</span></span>  
 [<span data-ttu-id="c5d79-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="c5d79-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="c5d79-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="c5d79-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)