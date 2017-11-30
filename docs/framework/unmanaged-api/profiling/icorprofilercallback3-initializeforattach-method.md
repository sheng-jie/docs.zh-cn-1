---
title: "ICorProfilerCallback3::InitializeForAttach 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.InitializeForAttach Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 323f163774407ff2ddfd261ff6d6584a07ed7d8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="2ccaf-102">ICorProfilerCallback3::InitializeForAttach 方法</span><span class="sxs-lookup"><span data-stu-id="2ccaf-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="2ccaf-103">由公共语言运行时 (CLR) 调用，从而给予分析器一个在附加操作后可将其状态初始化的机会。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ccaf-104">语法</span><span class="sxs-lookup"><span data-stu-id="2ccaf-104">Syntax</span></span>  
  
```  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ccaf-105">参数</span><span class="sxs-lookup"><span data-stu-id="2ccaf-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="2ccaf-106">[in] `ICorProfilerInfo*` 接口的接口指针。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="2ccaf-107">[in]指向的数据传递给[iclrprofiling:: Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)方法在其`pvClientData`参数。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="2ccaf-108">如果此参数为 NULL，则 `cbClientData` 将为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="2ccaf-109">当 CLR 从 `InitializeForAttach` 返回时将释放此内存。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="2ccaf-110">[in] `pvClientData` 指向的数据的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ccaf-111">备注</span><span class="sxs-lookup"><span data-stu-id="2ccaf-111">Remarks</span></span>  
 <span data-ttu-id="2ccaf-112">CLR 调用 `InitializeForAttach` 以便给予分析器请求回调的机会。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ccaf-113">要求</span><span class="sxs-lookup"><span data-stu-id="2ccaf-113">Requirements</span></span>  
 <span data-ttu-id="2ccaf-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ccaf-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2ccaf-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2ccaf-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ccaf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ccaf-117">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ccaf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ccaf-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ccaf-118">See Also</span></span>  
 [<span data-ttu-id="2ccaf-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2ccaf-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="2ccaf-120">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="2ccaf-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="2ccaf-121">分析接口</span><span class="sxs-lookup"><span data-stu-id="2ccaf-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="2ccaf-122">分析</span><span class="sxs-lookup"><span data-stu-id="2ccaf-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)