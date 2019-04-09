---
title: ICoreClrDebugTarget インターフェイス
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2972b87b2d0136f182f8e8223988953e1896f2bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183340"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="4cf26-102">ICoreClrDebugTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4cf26-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="4cf26-103">参照カウントを制御し、プロセスを列挙し、リモート Macintosh Silverlight ターゲットにアタッチされたデバッガーに関連付けられているメモリを解放するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="4cf26-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf26-104">構文</span><span class="sxs-lookup"><span data-stu-id="4cf26-104">Syntax</span></span>  
  
```  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4cf26-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4cf26-105">Methods</span></span>  
  
|<span data-ttu-id="4cf26-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="4cf26-106">Method</span></span>|<span data-ttu-id="4cf26-107">説明</span><span class="sxs-lookup"><span data-stu-id="4cf26-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4cf26-108">ICoreClrDebugTarget::EnumProcesses メソッド</span><span class="sxs-lookup"><span data-stu-id="4cf26-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="4cf26-109">リモート コンピューターで実行されているプロセスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="4cf26-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="4cf26-110">ICoreClrDebugTarget::EnumRuntimes メソッド</span><span class="sxs-lookup"><span data-stu-id="4cf26-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="4cf26-111">リモート コンピューター上の指定されたプロセスでは、共通言語ランタイム (Clr) を列挙します。</span><span class="sxs-lookup"><span data-stu-id="4cf26-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="4cf26-112">ICoreClrDebugTarget::FreeMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="4cf26-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="4cf26-113">このクラスの列挙メソッドによって割り当てられたメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="4cf26-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cf26-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="4cf26-114">Remarks</span></span>  
 <span data-ttu-id="4cf26-115">現時点では、Macintosh コンピューターをリモートで実行されている Silverlight ベースのアプリケーションのターゲットのデバッグにのみ、この機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4cf26-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cf26-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="4cf26-116">Requirements</span></span>  
 <span data-ttu-id="4cf26-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cf26-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cf26-118">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="4cf26-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="4cf26-119">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="4cf26-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="4cf26-120">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="4cf26-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf26-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cf26-121">See also</span></span>

- [<span data-ttu-id="4cf26-122">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4cf26-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="4cf26-123">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4cf26-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="4cf26-124">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4cf26-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
