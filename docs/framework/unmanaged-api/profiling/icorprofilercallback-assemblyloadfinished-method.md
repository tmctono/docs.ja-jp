---
title: ICorProfilerCallback::AssemblyLoadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e32af790c755f65b5435455c326d011656da19ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597376"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="2cd78-102">ICorProfilerCallback::AssemblyLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="2cd78-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="2cd78-103">アセンブリの読み込みが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2cd78-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cd78-104">構文</span><span class="sxs-lookup"><span data-stu-id="2cd78-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cd78-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cd78-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="2cd78-106">[in]読み込まれたアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="2cd78-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="2cd78-107">[in]アセンブリの読み込みが正常に終了するかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="2cd78-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cd78-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2cd78-108">Remarks</span></span>  
 <span data-ttu-id="2cd78-109">値`assemblyId`まで情報の要求に対して無効です、`AssemblyLoadFinished`メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2cd78-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="2cd78-110">アセンブリの読み込みの一部が後に続ける可能性があります、`AssemblyLoadFinished`コールバック。</span><span class="sxs-lookup"><span data-stu-id="2cd78-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="2cd78-111">エラーの HRESULT で`hrStatus`失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="2cd78-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="2cd78-112">ただし、成功 HRESULT で`hrStatus`のみのアセンブリの読み込みの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="2cd78-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cd78-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="2cd78-113">Requirements</span></span>  
 <span data-ttu-id="2cd78-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cd78-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cd78-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2cd78-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2cd78-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cd78-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cd78-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cd78-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd78-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cd78-118">See also</span></span>

- [<span data-ttu-id="2cd78-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cd78-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
