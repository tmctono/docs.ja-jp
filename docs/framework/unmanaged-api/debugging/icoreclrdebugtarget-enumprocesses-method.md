---
title: ICoreClrDebugTarget::EnumProcesses メソッド
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 301e6cc153f905bc5c15e1b526e6fb1a492a76d6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774445"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="70b78-102">ICoreClrDebugTarget::EnumProcesses メソッド</span><span class="sxs-lookup"><span data-stu-id="70b78-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="70b78-103">リモート コンピューターで実行されているプロセスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="70b78-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70b78-104">構文</span><span class="sxs-lookup"><span data-stu-id="70b78-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70b78-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70b78-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="70b78-106">[out] `ppProcs` に返されるプロセス数。</span><span class="sxs-lookup"><span data-stu-id="70b78-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="70b78-107">この値は 0 (ゼロ) になる可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="70b78-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="70b78-108">[out]配列の[CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)リモート コンピューターで実行中のプロセスを表す構造体。</span><span class="sxs-lookup"><span data-stu-id="70b78-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70b78-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="70b78-109">Return Value</span></span>  
 <span data-ttu-id="70b78-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="70b78-110">S_OK</span></span>  
 <span data-ttu-id="70b78-111">成功。</span><span class="sxs-lookup"><span data-stu-id="70b78-111">Success.</span></span>  
  
 <span data-ttu-id="70b78-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="70b78-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="70b78-113">`ppProcs`  用に十分なメモリを割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="70b78-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="70b78-114">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="70b78-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="70b78-115">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="70b78-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70b78-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="70b78-116">Remarks</span></span>  
 <span data-ttu-id="70b78-117">このメソッドによって割り当てられたメモリを解放する呼び出し、 [icoreclrdebugtarget::freememory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="70b78-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70b78-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="70b78-118">Requirements</span></span>  
 <span data-ttu-id="70b78-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70b78-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70b78-120">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="70b78-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="70b78-121">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="70b78-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="70b78-122">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="70b78-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b78-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="70b78-123">See also</span></span>

- [<span data-ttu-id="70b78-124">ICoreClrDebugTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70b78-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
