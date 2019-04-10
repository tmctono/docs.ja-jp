---
title: ICoreClrDebugTarget::FreeMemory メソッド
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec156ca7590a2ec637cb59e022fc2dd1a71226e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198505"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="c68aa-102">ICoreClrDebugTarget::FreeMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="c68aa-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="c68aa-103">によって割り当てられたメモリの解放、 [icoreclrdebugtarget::enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)と[icoreclrdebugtarget::enumruntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c68aa-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c68aa-104">構文</span><span class="sxs-lookup"><span data-stu-id="c68aa-104">Syntax</span></span>  
  
```  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c68aa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c68aa-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="c68aa-106">[in]いずれかによって返される配列へのポインター、 [icoreclrdebugtarget::enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)または[icoreclrdebugtarget::enumruntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c68aa-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c68aa-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="c68aa-107">Requirements</span></span>  
 <span data-ttu-id="c68aa-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c68aa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c68aa-109">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="c68aa-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c68aa-110">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="c68aa-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c68aa-111">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c68aa-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c68aa-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c68aa-112">See also</span></span>

- [<span data-ttu-id="c68aa-113">ICoreClrDebugTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c68aa-113">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
