---
title: "EHostBindingPolicyModifyFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EHostBindingPolicyModifyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EHostBindingPolicyModifyFlags
helpviewer_keywords: EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ff7ec7487be649e353b48e537cf1d8d45f6962
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="b192c-102">EHostBindingPolicyModifyFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="b192c-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="b192c-103">允许宿主指定在将从源程序集对目标程序集的策略修改应用时，应执行公共语言运行时 (CLR) 的重定向的类型。</span><span class="sxs-lookup"><span data-stu-id="b192c-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b192c-104">语法</span><span class="sxs-lookup"><span data-stu-id="b192c-104">Syntax</span></span>  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b192c-105">成员</span><span class="sxs-lookup"><span data-stu-id="b192c-105">Members</span></span>  
  
|<span data-ttu-id="b192c-106">成员</span><span class="sxs-lookup"><span data-stu-id="b192c-106">Member</span></span>|<span data-ttu-id="b192c-107">描述</span><span class="sxs-lookup"><span data-stu-id="b192c-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="b192c-108">指定 CLR 将链接到的目标程序集的源程序集的策略值。</span><span class="sxs-lookup"><span data-stu-id="b192c-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="b192c-109">指定 CLR 将执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="b192c-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="b192c-110">指定 CLR 将设置为最大值的目标程序集的策略值。</span><span class="sxs-lookup"><span data-stu-id="b192c-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="b192c-111">指定，CLR 将值替换为策略的目标程序集的源程序集。</span><span class="sxs-lookup"><span data-stu-id="b192c-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b192c-112">备注</span><span class="sxs-lookup"><span data-stu-id="b192c-112">Remarks</span></span>  
 <span data-ttu-id="b192c-113">[Iclrhostbindingpolicymanager:: Modifyapplicationpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)方法采用一个参数类型`EHostBindingPolicyModifyFlags`。</span><span class="sxs-lookup"><span data-stu-id="b192c-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b192c-114">要求</span><span class="sxs-lookup"><span data-stu-id="b192c-114">Requirements</span></span>  
 <span data-ttu-id="b192c-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b192c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b192c-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b192c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b192c-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b192c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b192c-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b192c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b192c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b192c-119">See Also</span></span>  
 [<span data-ttu-id="b192c-120">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="b192c-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="b192c-121">承载枚举</span><span class="sxs-lookup"><span data-stu-id="b192c-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)